---
title: Adding Content to Caves
audience: users
last_updated: 2026-01-09
related: [../../core-concepts/caves-and-connections.md, ../../getting-started/what-is-caves.md, ../../reference/glossary.md]
---

# Adding Content to Caves

**Purpose:** Learn all the ways to add content to caves - text, URLs, images, videos, files, and more.

**Prerequisites:** Basic understanding of caves ([What is Caves?](../../getting-started/what-is-caves.md))

---

## Opening the Content Input

There are three ways to open the input modal:

1. **Keyboard shortcut:** Press **Cmd+J** (Mac) or **Ctrl+J** (Windows)
2. **Bottom bar:** Click the add/plus icon in the bottom navigation
3. **In-cave button:** Click an "Add" button within a cave view

This opens a **sheet modal** (slide-up panel on mobile, side panel on desktop) with a text input field and action header.

---

## Content Input Modes

The input modal has different modes depending on context:

### Normal Mode (Default)
- **Purpose:** Add items to the current cave
- **Action header:** "Add to [cave name]"
- **Behavior:** When you submit, the item is added to the current cave with an implicit Yes vote

### Chat Mode
- **Purpose:** Send real-time messages
- **Action header:** "Chat in [cave name]"
- **Behavior:** Input stays always visible, messages send instantly via PartyKit
- **Access:** Activate by switching to Chat view in the filter bar

### Add to Another Cave
- **Purpose:** Add content to a different cave while viewing the current one
- **Behavior:** Specify the target cave name/path

### Edit Mode
- **Purpose:** Edit existing cave descriptions or items
- **Behavior:** Pre-populated with existing content

---

## Content Types

### 1. Text Content

**Short text** (under ~50 characters):
- Displayed inline without expansion
- Good for: Definitions, keywords, short notes

**Long text** (50+ characters):
- Displayed with "more/less" expansion
- Good for: Explanations, summaries, reflections

**How to add:**
1. Open input (Cmd+J)
2. Type your text directly
3. Press Enter or click send (airplane icon)

**Example uses:**
- `"Neural networks learn through backpropagation"`
- `"TODO: Research this topic more deeply"`
- `"Key insight: Connections emerge through voting, not pre-planning"`

---

### 2. URL/Link Content

**Caves automatically detects URLs and generates previews.**

**Supported URL types:**
- Web articles (generic link preview with title, description, image)
- YouTube videos (embedded player)
- Twitter/X tweets (full tweet display with media)
- TikTok videos (embedded player)
- Spotify tracks/albums/playlists (embedded player)
- Facebook posts (embedded content)
- Pinterest pins (embedded pins)
- IPFS links (`ipfs://` or gateway URLs)

**How to add:**
1. Copy a URL to your clipboard
2. Open input (Cmd+J)
3. Paste the URL (Cmd+V)
4. **Watch the magic:** Caves automatically:
   - Detects the URL type
   - Fetches metadata (title, description, image)
   - Shows a preview BEFORE you submit
   - Embeds it properly after submission
5. Submit with Enter or send button

**URL detection:**
- Happens automatically as you type/paste
- Preview appears within 1-2 seconds

**Example workflow:**
```
1. Find interesting article
2. Copy URL
3. Cmd+J to open input
4. Cmd+V to paste
5. See preview: "Why Neural Networks Work | MIT Research"
6. Submit → Article appears with rich preview in feed
```

---

### 3. Image Content

**Three ways to add images:**

#### A. Image URL
- Paste an image URL (ends with .jpg, .png, .gif, .webp, .heic)
- Caves detects it's an image and displays it directly

#### B. Drag & Drop (Recommended)
1. Open input (Cmd+J)
2. Drag an image file from your desktop
3. Drop it onto the input area
4. Image uploads automatically
5. Submit when ready

#### C. Upload Button
1. Open input (Cmd+J)
2. Click upload/attach button (if visible)
3. Select image file from filesystem
4. Wait for upload
5. Submit

**Supported formats:**
- JPG/JPEG
- PNG
- GIF (static and animated)
- WebP
- HEIC (iOS photos)

---

### 4. Media Content (Videos & Audio)

**Videos:**
- **YouTube:** Paste video URL → Embedded playable player
- **TikTok:** Paste TikTok URL → Embedded player
- **Direct uploads:** Drag-drop video files (support varies)

**Audio:**
- **Spotify:** Paste track/album/playlist URL → Embedded player
- **Direct uploads:** Drag-drop audio files

**Transcription (BERF Feature):**
- Uploaded media can be automatically transcribed
- Transcription appears alongside media
- Makes content searchable
- Useful for accessibility

---

### 5. File Content

**General files:**
1. Drag & drop any file onto the input
2. Caves uploads it and creates a link
3. Other users can download the file

**Special file type - .ic files:**
- Open format for interconnected thoughts
- Import `.ic` files from anywhere on the web into caves
- Human-readable format for knowledge graphs
- Special handling via IC.js library

---

### 6. IPFS Content

**InterPlanetary File System** - distributed, permanent storage.

**How to add IPFS content:**
- Paste an IPFS URL:
  - `ipfs://Qm...` (protocol format)
  - `https://ipfs.io/ipfs/Qm...` (gateway format)
- Caves detects IPFS and handles it specially

**IPFS text content:**
- Automatically displayed in **Text View**
- Fetched from IPFS network
- Rendered in readable format
- Can be quite long (full documents)

**Why IPFS?**
- Content is permanent (can't be deleted by any central authority)
- Decentralized (no single point of failure)
- Content-addressed (URL is hash of content)
- Aligns with caves' web3 philosophy

---

## Voting While Adding

**Every time you add content, you're implicitly voting Yes.**

When you add an item to a cave, you're saying:
- "This belongs in this cave"
- "This is relevant to this topic"
- "I endorse this connection"

**Your Yes vote is automatically recorded.**

**Vote counts:**
- The item shows 1+ Yes votes immediately (yours at minimum)
- Others can add their own Yes votes
- Others can vote No if they disagree

**Voting creates connections:**
- Your vote links the item to the cave in the network graph
- These connections are what power the Cave Map
- Vote-based curation emerges naturally

**Fire cost:**
- Adding content with a vote costs 1 fire
- You must have at least 1 fire to add content to a cave
- If you're low on fire, you'll see a warning before submitting
- New users start with 500 fire, topped up to 100 daily if below

**Earning potential:**
- When others agree with your connections, you can earn fire
- The more caves you add an item to, the more earning opportunities
- Earned fire lets you keep voting and adding content

---

## Content Input Tips & Best Practices

### 1. Use Descriptive Text
When adding text, be clear and concise:
- ✅ "Research paper on transformer attention mechanisms"
- ❌ "this is cool"

### 2. Let URLs Do the Work
Don't manually format - just paste the URL:
- ✅ Paste YouTube URL → Auto-embedded player
- ❌ Type "Watch this video: [long URL]" → Just a link

### 3. Drag & Drop is Fastest
For images and files, drag-drop is quicker than clicking upload buttons.

### 4. Preview Before Submitting
Check the automatic preview for URLs - ensure it fetched the right metadata.

### 5. Context Matters
Add items to caves where they make sense. Voting will help surface the best content.

### 6. Use Multiple Perspectives
Add content from different shadows to represent different viewpoints:
- Professional shadow: Industry articles, research papers
- Personal shadow: Blog posts, opinion pieces
- Skeptical shadow: Counterarguments, critiques

---

## Content Actions After Adding

Once content is in a cave:

**Vote on it:**
- Click vote buttons to vote
- Click again to unvote
- Vote counts update immediately

**Expand it:**
- Long text items have "more/less" toggles
- Cave items can expand to show child items

**Share it:**
- Every item has a unique URL
- Share button generates shareable link

**Transcribe it (BERF):**
- Media items can be transcribed
- Access transcription from item menu

---

## Advanced: Adding to Multiple Caves

**Scenario:** You want to add the same item to multiple related caves.

**Workflow:**
1. Add the item to the first cave (Cmd+J, paste, submit)
2. Navigate to the second cave
3. Open input, paste the same URL
4. Submit again

**Result:**
- Same item appears in both caves
- Your Yes votes connect both caves to the item
- Network graph shows the item as a bridge between caves

**Pro tip:** Use this to create meaningful cross-connections in your knowledge graph.

---

## Keyboard Shortcuts

| Action | Mac | Windows |
|--------|-----|---------|
| **Open input** | Cmd+J | Ctrl+J |
| **Submit** | Enter | Enter |
| **Close input** | Escape | Escape |
| **Search caves** | Cmd+K | Ctrl+K |

---

## Common Questions

**Q: Can I edit content after adding it?**
A: Currently, you can unvote (remove your Yes vote), but editing the content itself is limited. Check the item menu for edit options.

**Q: What happens if I add a duplicate?**
A: Caves may detect duplicates and merge them, or show them as separate items with the same URL. Vote counts accumulate.

**Q: Can I add content without opening a cave?**
A: You need to be in a cave context to add content. The input needs to know which cave you're adding to.

**Q: How big can files be?**
A: File size limits depend on your account tier and caves' current settings. Large files (>10MB) may take longer to upload.

**Q: Does adding content cost fire?**
A: Yes - adding content includes an implicit Yes vote, which costs 1 fire. You must have at least 1 fire to add content. New users start with 500 fire and are topped up to 100 daily if below.

---

## See Also

- **[Caves & Connections](../../core-concepts/caves-and-connections.md)** - How content creates network structure
- **[Cave Map](../exploration/cave-map.md)** - Visualize your content connections
- **[Media Support](media-support.md)** - Deep dive into embeds and transcription
- **[Organizing Caves](organizing-caves.md)** - Best practices for structure
