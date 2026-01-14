# What is Caves?

## The Problem

Information is everywhere, but it's scattered across bookmarks, notes, screenshots, tweets, articles, and conversations. Traditional tools force you into rigid hierarchies (folders), flat lists (documents), or unwieldy proprietary file formats. Finding connections between ideas is manual work, and collaborating means sharing entire workspaces or nothing at all.

## The Caves Solution

**Caves is a knowledge management platform where you create interconnected "caves" of information and explore them through multiple lenses.**

Think of caves as topics, concepts, or areas of interest - like "machine learning," "climate research," or "recipes I want to try." Instead of organizing content in rigid folders, you create caves and connect them through voting. You can navigate two ways: browse linearly like Reddit (with consensus sorting) or explore visually through network graphs.

**What makes caves different:**
- **Two navigation modes:** Feed view (Reddit-style) AND network view (visual graphs)
- **Multiple perspectives:** Create different "shadows" to maintain separate viewpoints
- **You control the algorithm:** Vote to curate, create perspectives to shape what you see
- **Collaborative:** Real-time chat, see others' contributions, build consensus
- **Open, shareable format:** Built on `.ic` - human-readable, easy to share online, import from anywhere on the web

---

## The Three Pillars

### 1. Content: Everything in One Place

Add any type of content to your caves:
- **Text:** Ideas, notes, definitions
- **Links:** Articles, tweets, TikToks, YouTube videos
- **Images:** Screenshots, photos, diagrams
- **Audio & Video:** Upload or link, then transcribe to make content available to everyone
- **Files:** Documents, data, media
- **IPFS content:** Distributed, permanent storage

**Transcription:** Images, audio, video, and YouTube links can be transcribed automatically. This makes visual and audio content available as text in your knowledge graph and available to all.

### 2. Connections: Vote-Based Curation

**This is where caves shines.** Instead of forcing everything into a hierarchy, you create connections through Yes/No voting:

- **Yes vote:** "This item belongs in this cave" or "These caves are related"
- **No vote:** "This doesn't belong here" or "These aren't related"

These votes serve two critical purposes:

**A. Surface Quality in Feed View** (like Reddit)
- Items with high Yes votes rise to the top (consensus sorting)
- Filter by recent, by content type, by perspective
- Linear reading experience focused on the best content

**B. Build Network Structure for Visual Exploration**
- Votes form a network graph you can explore visually
- Cave Map shows caves as nodes with connections as edges
- Click nodes to jump between caves, discover clusters and bridges

**Two views, one voting system.** Use feed view for focused consumption, network view for discovery.


### 3. Perspectives: Multiple Viewpoints

**Caves' unique feature:** Create multiple "shadows" (perspectives) to maintain different viewpoints on the same information.

Why multiple perspectives?
- **Professional vs Personal:** Keep work and personal interests separate while seeing the overlap
- **Exploration vs Production:** Experiment with new connections without affecting your main graph
- **Different Roles:** Maintain different identities (researcher, teacher, skeptic, enthusiast)

Each perspective has its own vote history, cave contributions, and view of the network. You can filter any cave to see it through a specific perspective, revealing how different people (or different versions of you) see the same information.

**Control your algorithm:** As you create and use perspectives, caves' algorithms adapt to show you relevant content. The activity map, for example, is algorithmically generated based on YOUR perspectives - not hidden corporate interests. You control what the algorithm learns from by controlling which perspectives you create and use.

### 4. Two Navigation Modes

**Caves gives you two equally powerful ways to navigate:**

**Feed View (Default):**
- Linear list of items, like Reddit or a news feed
- **Sort by consensus:** Highest-voted content first
- **Sort by recent:** Newest additions first
- **Filter by type:** Show only images, videos, text, etc.
- **Filter by perspective:** See only specific shadow's contributions
- Best for: Focused reading, catching up on activity, consuming curated content

**Cave Map:**
- Interactive force-directed graph visualization
- Caves as nodes, connections as edges
- Click nodes to jump between caves
- Discover clusters, bridges, hidden relationships
- Best for: Exploration, discovery, understanding structure, finding surprising connections

**Use both.** Feed view for consumption, network view for exploration. Same data, different lenses.

---

## Your Data is Portable

**Unlike most platforms, your caves aren't locked in - and the format is designed for the open web.**

Most platforms let you export data, but give you proprietary formats you can't actually use elsewhere. Caves is different:

- **Human-readable:** `.ic` files are plain text - you can open and read them in any text editor
- **Machine-parseable:** Simple format means any tool can read and write `.ic` data
- **Designed for sharing:** Not just export/backup, but made to be hosted and shared online
- **Import from anywhere:** Find `.ic` files anywhere on the internet (blogs, GitHub, IPFS) and import them directly into caves
- **Truly interoperable:** Other tools can build on the same format

This means if caves disappeared tomorrow, your knowledge isn't trapped in some proprietary format. You have human-readable files that work anywhere.

---

## Core Metaphors to Remember

🏔️ **Cave:** A container for related content (like a topic or concept). Literally just any string of text.

👥 **Shadow/Perspective:** One of your identities with its own viewpoint

🔗 **Connection:** A relationship between caves created by voting

📊 **Cave Map:** Visual graph showing how caves connect

🔥 **Fire:** Scarce currency that makes voting valuable. Every vote costs 1 fire. Earn more through consensus when others agree with your connections. Prevents spam and rewards quality curation.

___

## Technical Deep Dive: The .ic Format

**For those interested in the technical foundation:**

Caves is built on `.ic` - a simple, portable format for interconnected thoughts and perspectives.

**What's an .ic file?**
- Plain text format (like markdown or CSV)
- Contains "thots" (thoughts) - any text, URL, image, or concept
- Perspectives connect thots with `+` (yes/association) or `-` (no/dissociation)

**Example .ic structure:**
```
machine learning
+ neural networks
+ deep learning
- rule based systems
```

**Why it matters:**
- **Portability:** Export/import `.ic` files anywhere
- **Decentralization:** Files can live on IPFS, GitHub, personal servers
- **Interoperability:** Different tools can read/write the format
- **No vendor lock-in:** Your data isn't trapped

**Caves as .ic browser:**
Just like Chrome renders HTML, caves renders `.ic` files as:
- Feed views (Reddit-style browsing)
- Network graphs (visual exploration)
- Chat interfaces (real-time collaboration)

This means caves is part of a larger vision: a decentralized knowledge layer for the internet where meaning emerges from human perspectives, not algorithms.

---

## Fire: Making Votes Valuable

Unlike platforms where voting is infinite and meaningless, caves uses **fire** - a scarce resource that makes every vote count.

**How it works:**
- Every vote costs 1 fire
- Each day you're topped up to 100 fire if you've fallen below
- Earn more when others agree with your connections
- The more interconnected your items, the more earning potential

**Why this matters:**
- **Spam prevention:** Can't spam votes with limited fire
- **Thoughtful curation:** Scarcity encourages quality over quantity
- **Consensus rewards:** Good connections earn you more fire to keep voting
- **Real-world costs:** Transcriptions cost fire because they cost real money

Fire creates a sustainable curation economy where quality emerges naturally.

---

## Next Steps

Dive deeper into caves:

- **[Glossary](../reference/glossary.md)** - Essential terminology and concepts
- **[Caves & Connections](../core-concepts/caves-and-connections.md)** - How relationships work
- **[Perspectives & Shadows](../core-concepts/perspectives-shadows.md)** - Deep dive into the multi-perspective system
- **[Cave Map](../features/exploration/cave-map.md)** - Master visual navigation
- **[Adding Content](../features/content-management/adding-content.md)** - All the ways to add content
