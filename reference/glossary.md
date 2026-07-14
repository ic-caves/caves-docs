---
title: Caves Glossary
audience: users
last_updated: 2026-07-14
related: [../getting-started/what-is-caves.md, ../core-concepts/caves-and-connections.md]
---

# Caves Glossary

**Purpose:** Quick reference for caves terminology.

---

## Core Concepts

### Cave / Tag / Thot
A container or topic for related content - literally any string of text instantly becomes a cave. Think of it as a subreddit, a hashtag, or a Yahoo Answers question where anyone can contribute. Caves are cheap to create by design: just type a name and it exists. They can contain text, links, images, videos, and files, and connect to other caves through voting.

**Examples:** "machine learning," "climate research," "recipes to try"

### Shadow / Perspective / pId
One of your multiple identities or viewpoints in caves. Each shadow has its own username, avatar, vote history, and contributions. You can switch between shadows to view caves from different angles or maintain separate professional and personal spaces.

**Examples:** "Professional," "Personal," "Skeptical," "Learner"

### Connection / Relationship
A link between two caves created through voting. When you vote Yes or No on content, you're creating connections that form the network graph of caves.

**Types:**
- **Parent-child:** Hierarchical relationships
- **Yes vote:** "These are related" or "This belongs here"
- **No vote:** "These aren't related" or "This doesn't belong"

---

## Actions & Features

### Voting
Curating content and creating connections through Yes/No votes. One voting system serves two purposes: it surfaces quality (higher-voted content ranks higher by consensus, like Reddit upvotes) and it builds the network (Yes votes create positive connections, No votes create negative ones).

**Vote types:**
- **Yes vote:** "This item belongs in this cave" or "These caves are related"
- **No vote:** "This doesn't belong" or "These aren't related"
- **Unvote:** Vote again to remove your vote

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

**Why Fire Matters:**
- **Makes voting valuable:** Limited resource means votes are meaningful
- **Prevents spam:** Economically unfeasible to spam with limited fire
- **Rewards quality:** Consensus on your connections earns you more fire
- **Real-world connection:** Costs reflect actual computation (transcriptions)
- **Reputation system:** Earned fire in a cave becomes your ranking
- **Shared among contributors:** Fire earnings distributed among those who contributed

### Tag / Tagging
The technical term for cave names. When you "tag" something, you're adding it to a cave or creating a cave name.

**Format:** Any text you want - spaces, capitals, anything (e.g., "machine learning")

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

### IPFS (InterPlanetary File System)
Distributed storage protocol for permanent, decentralized content. Caves supports IPFS links and can display IPFS text content in a readable format.

**Format:** URLs like `ipfs://Qm...` or gateways like `https://ipfs.io/ipfs/Qm...`

---

## Concepts & Philosophy

### Non-hierarchical Organization
Caves don't force rigid folder structures. Everything can connect to everything. You build organization through voting and connections, not predetermined hierarchies.

### Vote-based Curation
Quality emerges through community voting, not centralized authority. Votes surface valuable content and create meaningful connections.

### Perspective-aware
Same data, multiple lenses. Your viewpoint doesn't dictate others'. Filter by perspective to see how different users (or different versions of you) see the same information.

### Visual-first Navigation
Graphs reveal patterns lists hide. Seeing your caves as a network makes relationships visible and navigable.

### Interoperability & Open Format
Unlike proprietary exports, caves uses `.ic` - a human-readable, machine-parseable format designed for sharing online. You can read your data as plain text, host it anywhere on the internet (IPFS, GitHub, personal servers), and import `.ic` files from anywhere on the web. Build knowledge graphs that transcend platform silos.

### Open Format for Knowledge
Caves uses an open, portable format (`.ic`) for storing interconnected thoughts. This means your knowledge graphs can live anywhere on the internet (IPFS, GitHub, personal servers), not just in caves. Other tools can read and write the same format.

### The Human Index & User-Controlled Algorithms
Caves combines human curation with algorithmic personalization - but YOU control the algorithm. Consensus emerges from voting (human curation), while algorithms adapt to YOUR perspectives (user control). Your personalized view is generated based on your perspectives, not corporate interests. Quality surfaces through collective intelligence + personalized recommendations driven by the perspectives you create.

### Your Data, Truly Portable
Most platforms let you export data in proprietary formats you can't actually use elsewhere. Caves is different: your data is stored in `.ic` - plain text that's human-readable and machine-parseable. You can open it in any text editor, host it anywhere online, and import `.ic` files from across the internet. It's interoperable, not just exportable.
