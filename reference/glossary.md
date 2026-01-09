---
title: Caves Glossary
audience: users
last_updated: 2026-01-09
related: [../getting-started/what-is-caves.md, ../core-concepts/caves-and-connections.md]
---

# Caves Glossary

**Purpose:** Quick reference for all caves terminology.

---

## Core Concepts

### Cave
A container or topic for related content - literally any string of text instantly becomes a cave. Think of it as a subreddit, a hashtag, or a Yahoo Answers question where anyone can contribute. Caves are cheap to create by design: just type a name and it exists. They can contain text, links, images, videos, and files, and connect to other caves through voting.

**Examples:** "machine learning," "climate research," "recipes to try"

### Shadow / Perspective / pId
One of your multiple identities or viewpoints in caves. Each shadow has its own username, avatar, vote history, and contributions. You can switch between shadows to view caves from different angles or maintain separate professional and personal spaces.

**Free tier:** 3 shadows maximum
**BERF tier:** Unlimited shadows

**Examples:** "Professional," "Personal," "Skeptical," "Learner"

### Connection / Relationship
A link between two caves created through voting. When you vote Yes or No on content, you're creating connections in the network graph. These connections are what make the Network Explorer visualization possible.

**Types:**
- **Parent-child:** Hierarchical relationships
- **Yes vote:** "These are related" or "This belongs here"
- **No vote:** "These aren't related" or "This doesn't belong"

---

## Navigation & Views

**Caves offers two equally important navigation modes:**

### Feed View
Linear, Reddit-style browsing of cave items with sorting, filtering, and voting. The default view for focused reading and catching up on content.

**Access:** Default view when entering any cave

**Key features:**
- **Consensus sorting:** Highest-voted content appears first
- **Recent sorting:** Newest additions first
- **Type filtering:** Show only videos, images, text, links, etc.
- **Perspective filtering:** See contributions from specific shadows
- **Search:** Find items within the cave
- **Voting:** Vote buttons on each item

**Best for:** "What's the best content?" "What's new?" "Catch me up."

### Network Explorer
Interactive force-directed graph visualization showing caves as nodes and connections as edges. Visual navigation for discovery and exploration.

**Access:** Graph icon in cave interface or "Explorer" in navigation

**Key features:** Node clicking, hover details, node log, common connections highlighting, avatar stack

**Best for:** "What's related?" "How does this connect?" "Show me the structure."

### System View
High-level overview of a cave showing tag pills (parent caves), contributor avatars, and cave structure. Use when you want to understand cave organization without diving into all the items.

**Access:** Add `?view=system` to cave URL or use view toggle button

### Text View
Dedicated view for displaying IPFS text content in a readable format. Automatically activates when a cave contains IPFS text items.

**Access:** Automatic when IPFS text is detected

### Chat View
Real-time messaging view within a cave. Switch from feed to chat using the filter bar to collaborate with others through live conversation.

**Access:** Click "Chat" tab in the filter bar

### Node Log
Breadcrumb trail in the Network Explorer showing your exploration path. See where you've been and jump back to previous nodes.

**Location:** Within Network Explorer panel

---

## Actions & Features

### Voting
Curating content and creating connections through Yes/No votes. **One voting system serves two purposes:**

**In Feed View:**
- High Yes votes → Content ranks higher (consensus sorting)
- Surfaces quality through community voting (like Reddit upvotes)

**In Network View:**
- Yes votes create positive connections (green edges in graph)
- No votes create negative connections (red edges in graph)
- Builds the network structure

**Vote types:**
- **Yes vote:** "This item belongs in this cave" or "These caves are related"
- **No vote:** "This doesn't belong" or "These aren't related"
- **Unvote:** Click the same button again to remove your vote

Vote counts are visible on all items. Your personal vote (mine) is tracked separately.

### Fire
In-app currency that makes voting valuable and prevents spam. Fire is scarce by design - you have a limited amount per day and must spend it wisely.

**Fire Costs:**
- **Every vote costs 1 fire** - Makes voting a thoughtful, scarce resource
- Description writing: 30 fire
- Image transcription: 100 fire
- Audio transcription: 200 fire per minute

**How to Earn Fire:**
- **New users:** Start with 500 fire
- **Daily top-up:** Topped up to 100 fire if you've fallen below (lunar cycle based)
- **Through consensus:** When others agree with your connections, you earn fire
  - The more caves you place an item in, the more earning opportunities
  - Fire goes to eligible perspectives who made the connection first
  - You can earn up to the number of times you've tagged that item
- **BERF subscribers:** 30,000 fire per full moon

**Why Fire Matters:**
- **Makes voting valuable:** Limited resource means votes are meaningful
- **Prevents spam:** Economically unfeasible to spam with limited fire
- **Rewards quality:** Consensus on your connections earns you more fire
- **Real-world connection:** Costs reflect actual computation (transcriptions)
- **Reputation system:** Earned fire in a cave becomes your ranking
- **Shared among contributors:** Fire earnings distributed among those who contributed

**Where to see fire:**
- Header: Your current balance
- Account page: Breakdown of earned fire by cave and perspective

### Tag / Tagging
The technical term for cave names. When you "tag" something, you're adding it to a cave or creating a cave name.

**Format:** Any text you want - spaces, capitals, anything (e.g., "machine learning")

---

## Collaboration

### PartyKit
Real-time collaboration infrastructure powering caves' chat and live updates. Ensures messages appear instantly and multiple users can collaborate simultaneously.

**User impact:** You don't need to refresh - changes appear in real-time

### Avatar Stack
Visual display showing contributors to a cave or connection. Appears in Network Explorer and system views. Click to see who's been active in specific caves.

### Contributor / pId Filtering
Filter caves to see only contributions from specific perspectives. Useful for understanding individual viewpoints or tracking who added what.

**Access:** Filter options in cave views

### Common Connections / Intersection
Highlighting in Network Explorer showing caves that connect to multiple selected nodes. Helps identify bridge concepts and shared relationships.

**Visual:** Usually highlighted with special colors or emphasis

---

## Content Types

### Item / Cave Item
A single piece of content within a cave. Can be text (short or long), a URL/link, an image, a video embed, or a file.

**Components:**
- Content itself
- Vote buttons
- Vote counts
- Contributor avatar
- Timestamp
- Optional: transcription, preview, IPFS link

### Embed
Automatically rendered content from URLs. Caves detects and embeds:
- YouTube videos (playable inline)
- Twitter/X tweets (full display)
- TikTok videos
- Spotify tracks (playable)
- Facebook posts
- Pinterest pins
- Generic link previews

### IPFS (InterPlanetary File System)
Distributed storage protocol for permanent, decentralized content. Caves supports IPFS links and can display IPFS text content in Text View.

**Format:** URLs like `ipfs://Qm...` or gateways like `https://ipfs.io/ipfs/Qm...`

### Transcription
AI-generated text from images, audio, video, and YouTube links. Makes visual and audio content available to everyone as text. Transcriptions appear alongside the original media and become part of your knowledge graph.

**Access:** Automatic transcription available for uploaded media

---

## Technical & Advanced

### MCP (Model Context Protocol)
Integration protocol allowing AI tools (like Claude) to access your caves data. BERF subscribers can generate API keys and connect caves to Claude Code, Claude.ai, or other MCP-compatible tools.

**Tools available:**
- `caves__my_shadows` - List your perspectives
- `caves__search_caves` - Search all caves
- `caves__connect_caves` - Create connections
- `caves__disconnect_caves` - Remove connections
- `caves__get_subcaves` - Get child caves
- `caves__my_shadow_caves` - Get full graph for a perspective

**Access:** BERF subscribers only, managed in Account page

### API Key
Authentication token for programmatic access to caves data. Generate and manage in Account page (BERF only).

**Uses:**
- Custom integrations
- Automation scripts
- Data export
- Third-party tool connections

### OAuth
Standard authentication protocol for third-party app authorization. Caves supports OAuth for integrations.

**User flow:** App requests permission → You authorize → App gets access token

### BERF
Premium subscription tier unlocking advanced features.

**Price:** $5.28/month

**Benefits:**
- Unlimited perspectives (vs 3 for free)
- API key access
- MCP integration
- 30,000 fire per full moon
- Media transcription
- Priority support

---

## UI Elements

### Bottom Bar
Navigation bar at the bottom of the page with quick actions:
- **Search** (Cmd+K) - Find caves
- **Add Item** (Cmd+J) - Open content input

### Filter Bar
Tabs within a cave view allowing you to filter content:
- **All:** Everything in the cave
- **Parents:** Just parent connections
- **Recent:** Recently added items
- **Chat:** Real-time messaging view

Also includes search and type filtering.

### Sheet Modal
Slide-up panel (mobile) or side panel (desktop) for actions like:
- Adding content (CaveInput)
- Viewing perspectives
- Cave explorer panel

### Tag Pills
Visual buttons/chips representing cave names. Click to navigate to that cave. Common in System View and parent listings.

---

## Technical Concepts

### .ic File
Open, human-readable format for interconnected thoughts and perspectives. The underlying data structure for all caves. Contains "thots" (thoughts) connected via `+` (yes/association) or `-` (no/dissociation).

**What makes .ic different:**
- **Human-readable:** Plain text you can open in any text editor
- **Machine-parseable:** Simple format any tool can read and write
- **Designed for sharing:** Made to be hosted and shared online, not just exported
- **Import from anywhere:** Find `.ic` files anywhere on the internet and import them into caves
- **Truly interoperable:** Other tools can build on the same format

No platform lock-in.

**Format example:**
```
machine learning
+ neural networks
- rule based systems
```

### Thot
Technical term for "thought" in the .ic format. Any piece of content - text, URL, image, concept. The atomic unit of caves. Multiple thots connect through perspectives to form knowledge graphs.

---

## Concepts & Philosophy

### Non-hierarchical Organization
Caves don't force rigid folder structures. Everything can connect to everything. You build organization through voting and connections, not predetermined hierarchies.

### Vote-based Curation
Quality emerges through community voting, not centralized authority. Votes surface valuable content and create meaningful connections.

### Perspective-aware
Same data, multiple lenses. Your viewpoint doesn't dictate others'. Filter by perspective to see how different users (or different versions of you) see the same information.

### Visual-first Navigation
Graphs reveal patterns lists hide. The Network Explorer makes relationships visible and navigable.

### Interoperability & Open Format
Unlike proprietary exports, caves uses `.ic` - a human-readable, machine-parseable format designed for sharing online. You can read your data as plain text, host it anywhere on the internet (IPFS, GitHub, personal servers), and import `.ic` files from anywhere on the web. Build knowledge graphs that transcend platform silos.

### Open Format for Knowledge
Caves uses an open, portable format (`.ic`) for storing interconnected thoughts. This means your knowledge graphs can live anywhere on the internet (IPFS, GitHub, personal servers), not just in caves. Other tools can read and write the same format.

### The Human Index & User-Controlled Algorithms
Caves combines human curation with algorithmic personalization - but YOU control the algorithm. Consensus emerges from voting (human curation), while algorithms adapt to YOUR perspectives (user control). The activity map, for example, is algorithmically generated based on your perspectives, not corporate interests. Quality surfaces through collective intelligence + personalized recommendations driven by the perspectives you create.

### Your Data, Truly Portable
Most platforms let you export data in proprietary formats you can't actually use elsewhere. Caves is different: your data is stored in `.ic` - plain text that's human-readable and machine-parseable. You can open it in any text editor, host it anywhere online, and import `.ic` files from across the internet. It's interoperable, not just exportable.

---

## Quick Reference Table

| Term | What It Is | Why It Matters |
|------|-----------|---------------|
| **Cave** | Topic/container for content | Organizing unit |
| **Shadow** | Your perspective/identity | Multiple viewpoints |
| **Feed View** | Reddit-style browsing | Consensus-sorted content |
| **Network Explorer** | Graph visualization | Visual navigation |
| **Voting** | Vote on content | Curates quality + builds graph |
| **Fire** | Reputation/currency | Contribution tracking |
| **Connection** | Vote-based relationship | Network structure |
| **pId** | Perspective ID | Technical identifier |
| **BERF** | Premium tier | Advanced features |
| **MCP** | AI integration protocol | Claude/AI tools access |
| **.ic file** | Portable data format | Export/import anywhere |
| **PartyKit** | Real-time infrastructure | Live collaboration |

---

## See Also

- **[What is Caves?](../getting-started/what-is-caves.md)** - Core concepts explained
- **[Caves & Connections](../core-concepts/caves-and-connections.md)** - Deep dive into relationships
- **[Perspectives & Shadows](../core-concepts/perspectives-shadows.md)** - Multiple viewpoints system
- **[Network Explorer](../features/exploration/network-explorer.md)** - Visual navigation guide
