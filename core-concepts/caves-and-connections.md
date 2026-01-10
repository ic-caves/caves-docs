---
title: Caves & Connections
audience: users
last_updated: 2026-01-09
related: [perspectives-shadows.md, ../features/exploration/cave-map.md, ../getting-started/what-is-caves.md]
---

# Caves & Connections

**Purpose:** Understand how caves work, how relationships form through voting, and how collaborative curation builds network structure.

**Prerequisites:** Basic caves knowledge ([What is Caves?](../getting-started/what-is-caves.md))

---

## What is a Cave?

**A cave is a container for related content** - like a topic, concept, project, or area of interest. **Caves are cheap to create:** literally any string of letters instantly becomes a cave. Type a name, and it exists.

Think of it as:
- A **subreddit** for any niche interest
- **Tweets sharing a hashtag** - loose collections around a topic
- A **Yahoo Answers question** - anyone can contribute
- A **folder** without rigid hierarchy
- A **Pinterest board** for collecting ideas

**Key characteristics:**
- **Instant creation:** Any string becomes a cave - no setup needed
- **Named:** Each cave has a unique name/tag (e.g., "machine learning," "climate research")
- **Contains items:** Text, links, images, videos, files
- **Connected:** Linked to other caves through parent-child relationships
- **Collaborative:** Multiple users (perspectives) can contribute
- **Vote-curated:** Quality emerges through voting
- **Visualizable:** Appears as a node in the Cave Map graph

---

## Cave Anatomy

### Cave URL Structure

Every cave has a URL:
```
/c/[cave-name]
/c/machine learning
/c/climate research/renewable energy
```

**Path structure - Multiple Parents (Intersection):**
- Single cave: `/c/topic`
- Two parents: `/c/parent a/parent b` - Shows children that belong to BOTH caves
- Multiple parents: `/c/parent a/parent b/parent c` - Shows children shared by ALL parents

**Example:**
- `/c/climate research/renewable energy` shows items tagged with both "climate research" AND "renewable energy"
- It's not a hierarchy - it's an intersection filter
- Each segment is a parent cave, and you see children they have in common

**Note:** The network structure is defined by votes, not URL paths. URLs just let you filter to items that share multiple parent tags.

### Cave Information

Each cave tracks:
- **Tag name:** The cave's identifier
- **Item count:** Number of items inside (tagCount)
- **Contributor count:** Number of unique perspectives who voted
- **Last updated:** Timestamp of most recent activity
- **Description:** Optional AI-generated or user-written summary
- **Representative image:** Auto-selected from cave contents

### Cave Header

When you're inside a cave, the header shows:
- **Current cave name**
- **Parent caves** (if any) - clickable breadcrumb
- **Actions:** Add parent, edit description, share
- **Statistics:** Item count, contributor count

---

## How Connections Form

**Connections between caves are created through voting, not manual linking.**

### Yes/No Voting System

**Every interaction in caves involves voting:**

**Yes vote (✓):**
- "This item belongs in this cave"
- "These caves are related"
- "I endorse this connection"
- "This is valuable/relevant"

**No vote (✗):**
- "This doesn't belong here"
- "These caves aren't related"
- "I disagree with this connection"
- "This isn't valuable/relevant"

**Vote counts:**
- **yes:** Total Yes votes across all perspectives
- **no:** Total No votes across all perspectives
- **mine:** Your current perspective's vote (-1, 0, or 1)

### Parent-Child Relationships

**The fundamental connection type in caves.**

**How it works:**
- When you add an item to a cave, you create a parent-child link:
  - **Parent:** The cave you're in
  - **Child:** The item you added
- Your vote creates the connection between them

**Example:**
1. You're in the "machine learning" cave
2. You add a YouTube video about neural networks
3. Caves connects them: "machine learning" → "neural networks video"
4. Your Yes vote creates this relationship

---

## Collaborative Curation Through Voting

**This is where caves becomes truly collaborative.**

### Multiple Perspectives, One Cave

**Scenario:** Three users explore the "climate science" cave:
- **User A (Optimistic perspective):** Votes Yes on solutions, No on doomsday articles
- **User B (Skeptical perspective):** Votes No on unverified claims, Yes on peer-reviewed research
- **User C (Neutral perspective):** Votes Yes on raw data, neutral on interpretations

**Result:**
- Each item has aggregate vote counts from all perspectives
- High Yes counts signal broad consensus
- High No counts signal controversy or irrelevance
- Split votes (equal Yes/No) indicate debate

### How Votes Work in Both Views

**One voting system, two purposes:**

**In Feed View:**
- High Yes votes → Content rises to the top (consensus sorting)
- Items are ranked by vote score (Yes minus No)
- Filter by type, perspective, or recency
- Like Reddit: community voting surfaces quality

**In Network View:**
- Votes create edges in the graph
- Yes votes = positive connections (green edges)
- No votes = negative connections (red edges)
- Vote strength affects edge thickness
- Network structure emerges from collective voting

**Same votes, different representations.** When you vote Yes, you're both saying "this is valuable" (for feed ranking) AND "this belongs here" (for network structure).

### Quality Emergence

**Vote-based curation surfaces valuable content without centralized authority.**

**High Yes votes signal:**
- Broad relevance across perspectives
- Valuable contribution to the cave
- Strong connection to parent caves
- Will rank higher in feed view

**High No votes signal:**
- Misplaced content (wrong cave)
- Low quality or relevance
- Controversial or disputed

**Balanced votes signal:**
- Legitimate disagreement
- Context-dependent value
- Multiple valid interpretations

### Vote Weighting by Engagement

**All votes count, but context matters:**

- **Contributor count:** Caves with more contributors have more diverse perspectives
- **Fire-weighted voting:** Users with more fire (earned through contribution) may have vote weight (future feature)
- **Perspective filtering:** Filter caves to see vote counts from specific perspectives only

### Fire: The Economics of Voting

**Every vote costs 1 fire.** This scarcity is intentional - it makes voting thoughtful and prevents spam.

**Fire flow:**
1. You vote on a connection → Spend 1 fire
2. Others vote Yes on the same connection → You can earn fire
3. More caves you connect an item to → More earning opportunities
4. Fire is randomly distributed to one eligible contributor per vote

**Why this works:**
- **Prevents spam:** Limited fire (topped up to 100 daily if below) makes mass voting impossible
- **Rewards consensus:** Good connections earn you fire to keep voting
- **Creates ranking:** Earned fire in a cave becomes your reputation
- **Reflects real costs:** Transcriptions cost fire because they cost actual computation

**Check your fire:** Header shows current balance, Account page shows earned fire breakdown.

---

## Cave Types & Content Organization

### Content Type Filtering

Caves contain different types of items:

- **Text:** Notes, definitions, thoughts
- **Links:** Articles, webpages, documentation
- **Images:** Photos, screenshots, diagrams
- **Videos:** YouTube, TikTok, direct uploads
- **Audio:** Spotify, podcasts, sound files
- **Files:** PDFs, datasets, code files
- **pIds:** Other perspectives (for social graphs)

**Filter by type:**
- Use the filter bar to show only specific content types
- See the cave through different lenses (visual, textual, audio)

### Cave Purposes

**Different caves serve different purposes:**

**Topic caves:**
- Broad subjects: "machine learning," "philosophy," "cooking"
- Collections of related concepts

**Project caves:**
- Specific endeavors: "project alpha," "dissertation research"
- Focused, time-bound

**List caves:**
- Collections: "books to read," "tools I use," "favorite articles"
- Curated resources

**Meta caves:**
- About caves itself: "how to use caves," "caves features"
- System-level organization

**Social caves:**
- People/perspectives: Caves about users or perspectives
- Relationship mapping

---

## Network Structure

### How the Graph Forms

**The Cave Map visualizes your cave connections:**

**Nodes (Circles):**
- Each node = one cave
- Node size = number of children/items
- Node color = relationship type (yes/no/selected)

**Edges (Lines):**
- Each edge = a parent-child connection
- Edge thickness = vote strength
- Edge color = yes (green) vs no (red)

**Graph dynamics:**
- Force-directed layout: Related caves cluster together
- Bridge nodes: Caves connecting multiple clusters
- Isolated nodes: Unconnected caves (rare)

### Hierarchies vs. Networks

**Traditional tools:**
- Folders enforce strict parent-child hierarchies
- One item, one location
- Single organization scheme

**Caves:**
- Items can have multiple parents (exist in multiple caves)
- Cycles are allowed (A → B → C → A)
- Network structure, not tree structure
- Organization emerges from voting

**Why this matters:**
- Real knowledge doesn't fit in trees
- Concepts relate in complex, multi-directional ways
- Different perspectives see different structures

---

## Cave Discovery & Navigation

### Two Ways to Navigate

**Caves offers two complementary navigation modes:**

**1. Feed View (Linear Navigation)**
- **Purpose:** Focused reading, catching up, consuming content
- **How it works:**
  - Browse items in order (consensus or recent)
  - Filter by type (videos, images, text)
  - Filter by perspective (see specific shadows)
  - Search within cave
- **Best for:**
  - "What's new in this cave?"
  - "What's the highest-quality content here?"
  - Reading through updates linearly

**2. Network View (Graph Navigation)**
- **Purpose:** Discovery, exploration, understanding structure
- **How it works:**
  - See caves as nodes in force-directed graph
  - Click nodes to jump between caves
  - Follow edges to related topics
  - Discover clusters and bridges
- **Best for:**
  - "What's related to this cave?"
  - "How does this fit in my knowledge?"
  - Serendipitous discovery

**Use both.** Feed for consumption, network for exploration.

### Finding Caves

**Search:**
- Press **Cmd+K** to open search
- Type cave name or keyword
- Jump directly to caves

**Trending:**
- Homepage shows "Signs of Life" - popular caves
- High activity = recent votes or contributions
- Discover what others are exploring

**Cave Map:**
- Click nodes to jump between connected caves
- Follow edges to related topics
- Discover caves through relationships

**Parent/Child Lists:**
- Each cave shows parent caves (breadcrumb at top)
- Can expand items to see their children
- Navigate up/down the hierarchy

### Creating New Caves

**Caves are cheap to create - literally any string instantly becomes a cave:**
1. Type any cave name in the input (doesn't need to exist)
2. Add your item
3. Cave is created automatically

**No setup, no approval, no "New Cave" button.** Just type a name and it exists. This is intentional - caves should be as frictionless as creating a hashtag or asking a question.

---

## Cave Statistics & Activity

### Tracking Engagement

**Each cave tracks:**
- **Item count:** How many items inside
- **Contributor count:** How many perspectives have voted
- **Last updated:** Timestamp of most recent activity
- **Vote counts:** Aggregate votes across all perspectives

**View in:**
- Cave header (when inside cave)
- Cave listings (homepage, search results)
- Cave Map (node hover)

### Activity Maps

**Homepage shows activity visualization:**
- Visual representation of recent cave activity
- Hotspots indicate high engagement
- Clickable to jump to active caves

---

## Advanced: Connection Strategies

### Creating Bridge Caves

**Strategy:** Add the same item to multiple caves to create bridge connections.

**Example:**
1. Find an article about "solar panels reducing carbon emissions"
2. Add to "renewable energy" cave → Yes vote
3. Add to "climate solutions" cave → Yes vote
4. Add to "carbon reduction" cave → Yes vote

**Result:**
- Article appears in all three caves
- Network graph shows all three caves connected through this item
- Item becomes a bridge node in the visualization

### Curating with No Votes

**Don't just vote Yes on everything - curate actively.**

**Strategic No votes:**
- Remove off-topic items from caves
- Signal disagreement with connections
- Maintain cave focus

**Example:**
- Someone adds a political opinion piece to "climate science"
- You vote No: "This is opinion, not science"
- No votes help keep caves focused

### Perspective-Specific Organization

**Different shadows can organize the same caves differently:**

**Example: "Machine Learning" cave**
- **Professional shadow:** Votes Yes on academic papers, No on tutorials
- **Learner shadow:** Votes Yes on tutorials, No on advanced papers
- **Project shadow:** Votes Yes on practical tools, No on theory

**Result:**
- Same cave, three different filtered views
- Each perspective sees relevant content
- Collaborative curation without compromise

---

## Cave Best Practices

### 1. Use Descriptive Names
- ✅ "machine learning transformers"
- ✅ "climate policy us"
- ❌ "stuff," "misc," "notes"

### 2. Vote Thoughtfully
- Yes = relevant and valuable
- No = off-topic or low-quality
- Don't vote on everything - vote when you have an opinion

### 3. Create Bridges
- Add important items to multiple related caves
- Build connections across domains

### 4. Use Multiple Perspectives
- Switch shadows to vote differently on the same content
- See caves through different lenses

### 5. Explore the Network
- Use Cave Map regularly
- Discover unexpected connections
- Understand your knowledge structure

---

## Common Questions

**Q: Can I delete a cave?**
A: Caves can't be explicitly deleted, but they disappear if all items are removed or voted out (No votes).

**Q: What happens if more people vote No than Yes on an item?**
A: Items with net negative votes may be hidden or deprioritized in feeds. They still exist in the network.

**Q: Can caves have multiple parents?**
A: Yes! An item can be added to multiple caves, creating multiple parent-child relationships.

**Q: How do I rename a cave?**
A: Cave names are tags - just create a new cave name and migrate content. Old name remains if items still reference it.

**Q: Can I make a cave private?**
A: Currently, caves are shared/public. Privacy features may be added in the future.

**Q: Do I need to vote on everything?**
A: No - vote when you have an opinion. Abstaining (not voting) is valid.

---

## See Also

- **[Perspectives & Shadows](perspectives-shadows.md)** - How multiple perspectives vote differently
- **[Cave Map](../features/exploration/cave-map.md)** - Visualize cave connections
- **[Adding Content](../features/content-management/adding-content.md)** - How to add items and create connections
- **[Voting & Curation](voting-curation.md)** - Deep dive into the voting system
