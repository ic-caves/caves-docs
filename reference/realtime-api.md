# Caves Realtime API Documentation

## 1. Introduction

The Caves Realtime API provides WebSocket-based live communication for any cave in the Caves platform. This enables real-time features including:

- **Live chat**: Send and receive messages instantly in any cave
- **Suggestions**: Submit ideas and topics for cave exploration
- **Cave activity**: Monitor real-time activity and participation

The API is powered by PartyKit, providing scalable WebSocket connections with persistent message storage and automatic synchronization across all connected clients.

## 2. Authentication

### 2.1 Creating and Managing API Keys

Create and manage your API keys on your Account page at https://itscaves.com. API keys start with the `cav_` prefix and are shown only once during creation, so save them immediately.

**API Key Format:**
```
cav_<64-character-hex-string>
```

**Security Notes:**
- Store API keys securely in environment variables
- Never commit API keys to git or share them publicly
- Delete compromised keys immediately from your account page

### 2.2 Using API Keys for Authentication

Two methods are supported for authentication:

1. **Authorization header**: `Authorization: Bearer cav_<your-api-key>`
2. **API key header**: `X-API-Key: cav_<your-api-key>`

Both methods work identically for WebSocket authentication when passed as the `token` query parameter.

## 3. Connecting to the Realtime API

### 3.1 WebSocket Endpoint

**URL:** `wss://caves-chat.owise1.partykit.dev/parties/main/<room-id>?token=<your-api-key>`

**Components:**
- **Protocol**: `wss://` (secure WebSocket)
- **Host**: `caves-chat.owise1.partykit.dev`
- **Path**: `/parties/main/<room-id>`
- **Query param**: `?token=<your-api-key>`

### 3.2 Room Naming Convention

**Critical:** Room IDs are Base64-encoded cave paths

**Important:** For multi-tag caves, tags must be in alphabetical order by UTF-8 code. For example, use `"a/b/c"` not `"a/c/b"`.

**Format:**
```javascript
// Cave path: "technology/ai/machine-learning"
// Room ID: btoa("technology/ai/machine-learning")
// Result: "dGVjaG5vbG9neS9haS9tYWNoaW5lLWxlYXJuaW5n"
```

**Implementation:**
- **JavaScript**: `window.btoa(cavePath)`
- **Python**: `base64.b64encode(cave_path.encode()).decode()`
- **Node.js**: `Buffer.from(cavePath).toString('base64')`

**Examples:**
- Cave: `"test"` → Room: `dGVzdA==`
- Cave: `"caves/docs"` → Room: `Y2F2ZXMvZG9jcw==`
- Cave: `"ai/machine-learning/technology"` → Room: `YWkvbWFjaGluZS1sZWFybmluZy90ZWNobm9sb2d5` (alphabetically sorted)

## 4. Message Protocol

### 4.1 Client → Server Messages

#### Chat Message

```json
{
  "type": "message",
  "content": "Hello, world!",
  "pId": "your-perspective-id"
}
```

#### Suggestion/Item

```json
{
  "type": "item",
  "content": "Interesting topic to explore"
}
```

#### Batch Messages

```json
[
  {
    "type": "message",
    "content": "First message",
    "pId": "your-perspective-id"
  },
  {
    "type": "message",
    "content": "Second message",
    "pId": "your-perspective-id"
  }
]
```

### 4.2 Server → Client Messages

#### Update Message (initial + broadcasts)

```json
{
  "type": "update",
  "messages": [
    {
      "type": "message",
      "content": "Message content",
      "pId": "sender-perspective-id",
      "timestamp": "2026-01-20T...",
      "avatar": "avatar-url",
      "earnedFire": 100
    }
  ]
}
```

#### Error Message

```json
{
  "type": "error",
  "message": "Invalid authentication token"
}
```

### 4.3 Message Types

- **`message`**: Standard chat message (requires `pId`)
- **`item`**: Suggestion or note (no `pId` required)
- **`update`**: Server broadcast of current messages
- **`error`**: Authentication or validation error

## 5. Perspective IDs (pIds)

### 5.1 What are Perspective IDs?

- Each user can have multiple perspectives (identities)
- Messages are sent from a specific perspective
- Format: Ethereum-style addresses or custom identifiers
- Example: `0xd05D783Ec33a8dF2BC40d3197629406EcF29eFB8`

### 5.2 Getting Your Perspective IDs

**Endpoint:** `GET /user/pIds`

```bash
curl https://its.itscaves.com/user/pIds \
  -H "Authorization: Bearer <your-api-key>"
```

**Response:**
```json
{
  "fire": 1000,
  "pIds": [
    {
      "pId": "0xd05D783Ec33a8dF2BC40d3197629406EcF29eFB8",
      "username": "my-username",
      "description": "My perspective description"
    }
  ]
}
```

### 5.3 Perspective Validation

- Server validates you own the `pId` before accepting messages
- Attempting to use someone else's `pId` results in message rejection
- Warning logged: `"User attempted to use pId they don't own"`

## 6. Rate Limiting

- **Limit:** 100 messages per connection
- **Enforcement:** Soft limit using rate limiter
- **Recommendation:** Throttle message sending to avoid hitting limit

## 7. Troubleshooting

### 7.1 Common Errors

#### "Invalid authentication token"

- Check API key is valid and not expired
- Ensure API key is properly URL-encoded in query parameter
- Verify API key starts with `cav_` prefix

#### "pId does not belong to authenticated user"

- Verify you own the perspective ID
- Check `GET /user/pIds` for your available perspectives
- Ensure `pId` is spelled correctly

#### Connection immediately closes

- Authentication likely failed
- Check browser console / WebSocket logs for error message
- Verify endpoint URL is correct

#### Messages not appearing

- Check room ID is correctly Base64-encoded
- Verify you're connected to the right cave path
- Check message format matches schema

### 7.2 Testing Your Connection

```javascript
// Quick connection test
const testConnection = (cavePath, token) => {
  const roomId = btoa(cavePath);
  const ws = new WebSocket(
    `wss://caves-chat.owise1.partykit.dev/parties/main/${roomId}?token=${token}`
  );

  ws.onopen = () => console.log("✓ Connected successfully");
  ws.onerror = () => console.error("✗ Connection failed");
  ws.onmessage = (e) => console.log("Received:", JSON.parse(e.data));

  setTimeout(() => {
    ws.send(JSON.stringify({
      type: "message",
      content: "Test message",
      pId: "your-perspective-id"
    }));
  }, 1000);

  return ws;
};
```
