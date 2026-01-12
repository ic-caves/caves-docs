---
title: Cave Map
audience: users
last_updated: 2026-01-09
related: [../../core-concepts/caves-and-connections.md, ../../core-concepts/perspectives-shadows.md, ../../getting-started/what-is-caves.md]
---

# Cave Map

**Purpose:** Master caves' signature feature - visual network navigation through interactive force-directed graphs.

**Prerequisites:** Understanding of caves and connections ([Caves & Connections](../../core-concepts/caves-and-connections.md))

---

## What is the Cave Map?

**The Cave Map is an interactive graph visualization that shows your caves as nodes and connections as edges.** Instead of navigating through lists or folders, you click through a living map of your knowledge.

**This is caves' most distinctive and powerful feature.**

**Why it matters:**
- **Reveals hidden connections** you didn't know existed
- **Shows relationships visually** that lists hide
- **Enables serendipitous discovery** through graph exploration
- **Makes navigation intuitive** - click nodes to jump between caves
- **Highlights perspective contributions** through avatar stacks

The Cave Map transforms static information into a dynamic, explorable space.

---

## Accessing the Cave Map

**Multiple entry points:**

1. **From any cave:**
   - Look for the graph/network icon in the cave interface
   - Usually in the top-right or near the filter bar
   - Click to open the explorer panel

2. **From the navigation menu:**
   - Click "Explorer" or "Network" in main navigation
   - Opens a full-screen network view

3. **From the CaveExplorer component:**
   - Some caves show an embedded explorer panel
   - Always-visible side panel with the graph

---

## Understanding the Graph

### Nodes (Circles)

**Each node represents one cave.**

**Node characteristics:**
- **Position:** Determined by force-directed algorithm
  - Related caves cluster together
  - Unrelated caves push apart
- **Size:** Indicates importance
  - Larger = more children/items inside
  - Smaller = fewer connections
- **Color/Highlighting:**
  - **Selected node:** Special highlighting (current focus)
  - **Focal node:** The "center" of the current view (your location)
  - **Common connections:** Special color when connecting multiple selected nodes
  - **Perspective-based:** Different colors for yes/no votes or perspective activity
- **Avatar stack:** Small avatars show which perspectives contributed
  - Click avatar stack to see contributor details

**Node states:**
- **Normal:** Default appearance
- **Hovered:** Highlighted when you move your mouse over it
- **Selected:** Clicked or actively focused
- **Focal:** The current cave you're viewing from (center of graph)

### Edges (Lines)

**Each edge represents a connection between caves** (parent-child relationship).

**Edge characteristics:**
- **Direction:** Points from parent to child
  - May be implicit (not always shown with arrows)
- **Thickness:** Can indicate connection strength
  - More votes = thicker line
  - Higher engagement = more prominent
- **Color:**
  - Green/default: Yes connections (positive relationships)
  - Red: No connections (negative relationships)
  - Highlighted: Special color for selected paths or common connections
- **Curvature:** Straight or curved depending on graph density

**Connection types:**
- **Parent-child:** Hierarchical relationships
- **Cross-connections:** Items appearing in multiple caves
- **Perspective-specific:** Visible when filtering by perspective

---

## Interacting with the Graph

### Clicking Nodes

**Primary navigation method.**

**What happens when you click a node:**
1. You **jump to that cave** - the page navigates to `/c/[cave-name]`
2. The graph **re-centers** around the new focal node
3. The **node log** updates (see below)
4. Connected nodes and edges adjust their positions
5. The cave feed/content updates to show the new cave

**Use when:**
- Exploring related topics
- Following connections
- Discovering new caves
- Quick navigation between areas

**Pro tip:** Click nodes rapidly to "surf" through your knowledge graph - much faster than search or manual navigation.

### Hovering Over Nodes

**Reveals details without navigating.**

**What happens on hover:**
- **Node label appears** (cave name)
- **Tooltip may show:**
  - Item count
  - Contributor count
  - Last updated
  - Vote counts
- **Connected edges highlight** (shows direct relationships)
- **Avatar stack becomes visible** (who contributed)

**Use when:**
- Scanning for interesting caves
- Checking cave details before clicking
- Understanding relationships without leaving current cave

### The Node Log

**Breadcrumb trail of your exploration path.**

**What it shows:**
- **Ordered list** of nodes you've clicked
- **Clickable entries** - jump back to previous nodes
- **Visual indicator** of your journey through the graph

**Example path:**
```
machine learning → neural networks → transformers → attention mechanism
```

**Use when:**
- You want to backtrack to a previous cave
- Reviewing your exploration path
- Understanding how you discovered something

**Location:** Usually displayed in a panel near or within the Cave Map

---

## Force-Directed Layout

**The graph uses physics simulation to position nodes.**

**How it works:**
- **Attraction:** Connected nodes pull toward each other
- **Repulsion:** All nodes push away from each other
- **Balance:** Graph settles into an equilibrium
- **Clusters emerge:** Highly connected caves group together
- **Bridges visible:** Nodes connecting clusters become prominent

**Why force-directed?**
- Automatically reveals structure
- No manual layout needed
- Adjusts dynamically as connections change
- Makes relationships intuitive (closer = more related)

**Visual dynamics:**
- Graph "settles" over a few seconds after loading
- Nodes may bounce or oscillate slightly
- Dragging a node (if enabled) disrupts the layout temporarily
- Layout recalculates when focal node changes

---

## Advanced Features

### Avatar Stack

**Shows who has contributed to each cave.**

**What you see:**
- **Small circular avatars** attached to nodes
- **Multiple avatars** if multiple perspectives contributed
- **Your perspective** may be highlighted or shown first

**Interaction:**
- **Click avatar stack** to see contributor details
  - Perspective names
  - Contribution counts
  - Fire earned in this cave
- **Hover** for quick preview

**Use when:**
- Tracking collaboration
- Identifying active contributors
- Understanding perspective diversity in a cave
- Finding caves where specific perspectives are active

### Common Connections Highlighting

**Identifies caves that bridge multiple clusters.**

**What it shows:**
- When you select multiple nodes (or filter by multiple criteria)
- Caves that connect to BOTH nodes are highlighted
- Special color/emphasis distinguishes bridge nodes

**Example:**
- Select "machine learning" and "healthcare"
- "medical ai" lights up as a common connection
- Reveals the bridge concept linking both domains

**Use when:**
- Finding relationships between disparate topics
- Identifying bridge concepts
- Understanding how domains overlap
- Discovering interdisciplinary caves

**Visual indicator:** Usually a distinct color (purple, orange) or pulsing effect

### Perspective Filtering

**View the graph through a specific perspective's lens.**

**How to filter:**
1. Look for perspective/pId selector in explorer UI
2. Select a specific shadow
3. Graph updates to show only that perspective's connections

**What changes:**
- **Nodes:** Only caves the perspective has interacted with
- **Edges:** Only connections the perspective voted on
- **Avatar stacks:** Perspective's avatar is highlighted or isolated
- **Layout:** Graph re-organizes around that perspective's activity

**Use when:**
- Understanding a specific perspective's focus
- Comparing how different shadows organize knowledge
- Tracking individual contributions in collaborative spaces
- Isolating your own work from others'

---

## Exploration Strategies

### 1. Cluster Diving

**Strategy:** Identify tight clusters and explore them thoroughly.

**How:**
1. Zoom out or pan to see the full graph
2. Look for groups of tightly connected nodes (clusters)
3. Click into the center of a cluster
4. Explore outward through connected nodes

**Why it works:**
- Clusters represent coherent knowledge domains
- Dense connections mean high relevance
- Systematic exploration ensures coverage

### 2. Bridge Hunting

**Strategy:** Find bridge nodes connecting clusters and explore them.

**How:**
1. Identify nodes positioned between clusters
2. Click to see what they connect
3. Follow bridges to discover interdisciplinary concepts

**Why it works:**
- Bridges reveal surprising connections
- Cross-domain insights often emerge here
- Less obvious relationships become visible

### 3. Peripheral Exploration

**Strategy:** Explore weakly connected nodes on the graph's edge.

**How:**
1. Look for isolated nodes or small sub-graphs
2. Click to investigate why they're disconnected
3. Consider creating connections if relevant

**Why it works:**
- Reveals forgotten or underdeveloped areas
- Identifies orphaned content that needs integration
- Sparks ideas for new connections

### 4. Perspective Comparison

**Strategy:** Switch between perspectives and observe graph changes.

**How:**
1. View graph with Perspective A
2. Note the structure, clusters, bridges
3. Switch to Perspective B
4. Observe what changed - different focal areas, connections, importance

**Why it works:**
- Reveals how different viewpoints organize the same data
- Identifies consensus (shared structure) vs. divergence
- Highlights unique contributions from each perspective

---

## Cave Map Best Practices

### 1. Use it Regularly

**The Cave Map reveals patterns that emerge over time.**
- Check weekly to see how your graph evolved
- Look for unexpected clusters
- Identify areas needing more connections

### 2. Click, Don't Just Look

**Navigation is learning.**
- Don't just observe - click nodes
- Follow interesting paths
- Get lost and find your way back (use node log)

### 3. Combine with Search

**Use both tools together:**
- Search (Cmd+K) to find a starting node
- Explorer to discover related caves from there

### 4. Pay Attention to Avatar Stacks

**They tell you where collaboration is happening:**
- Many avatars = popular/collaborative cave
- Solo avatar = individual work
- Your avatar = your contributions

### 5. Use Perspective Filtering

**See your graph through different eyes:**
- Switch perspectives weekly
- Notice what each shadow focuses on
- Identify gaps or overlaps

---

## Mobile vs. Desktop

### Desktop Experience

**Full-featured exploration:**
- Larger graph size (600px+ depending on screen)
- Hover interactions work smoothly
- Node labels always visible
- Detailed tooltips on hover
- Side panel or full-screen mode available

### Mobile Experience

**Optimized for touch:**
- Responsive sizing (fits screen width)
- Touch to select nodes (no hover)
- Tap node log to navigate
- Swipeable panels (if in sheet/modal)
- Simplified UI to focus on graph

**Note:** Force-directed graphs are more performant on desktop but work on mobile. Consider using feed view on mobile for primary navigation.

---

## Troubleshooting

### Graph Isn't Loading

**Possible causes:**
- Large dataset taking time to process
- Network issue fetching connections
- Browser performance (too many nodes)

**Try:**
- Refresh the page
- Filter by perspective (fewer nodes)
- Use feed view instead temporarily

### Nodes Are Overlapping

**This is normal in dense clusters.**
- Zoom in if supported
- Click nodes to re-center and separate them
- Hover to see labels despite overlap

### Can't Find a Specific Cave

**Graph doesn't show all caves, only connected ones.**
- Use Search (Cmd+K) to find the cave directly
- Add connections to make it appear in graph
- Check if it's in a different perspective's graph

### Graph Layout Keeps Moving

**Force-directed layouts stabilize over time.**
- Wait 5-10 seconds for physics to settle
- Avoid clicking nodes while it's settling
- Layout is recalculating based on new connections

---

## Common Questions

**Q: Does the Cave Map show ALL my caves?**
A: It shows caves connected to the current focal node, plus nearby connections. Very distant or unconnected caves may not appear.

**Q: Can I manually arrange nodes?**
A: Generally no - the force-directed algorithm handles layout automatically. This ensures consistent, relationship-based positioning.

**Q: Why do some caves have bigger nodes?**
A: Node size typically reflects the number of children/items. More content = bigger node.

**Q: Can I zoom or pan the graph?**
A: Click nodes to re-center the graph around them. The graph automatically adjusts to show relevant connections.

**Q: Do edge colors mean something?**
A: Yes - typically green for Yes connections, red for No connections, and special colors for highlights or selections.

**Q: Can I see the entire knowledge graph at once?**
A: Large graphs may be too complex to display fully. The explorer focuses on local neighborhoods around the focal node.

---

## Why the Cave Map Matters

**Traditional navigation** (folders, lists, search) assumes you know what you're looking for. **The Cave Map enables discovery** - you find things by following relationships, not by searching for keywords.

**Key insights enabled by visual exploration:**

1. **Serendipity:** Stumble upon caves you forgot existed
2. **Pattern recognition:** See clusters and themes emerge
3. **Gap identification:** Notice areas lacking connections
4. **Perspective awareness:** Understand how different shadows organize knowledge
5. **Relationship understanding:** Grasp how concepts relate beyond parent-child

**The network becomes a second brain** - not just storage, but a tool for thinking.

---

## Next Steps

- **[Caves & Connections](../../core-concepts/caves-and-connections.md)** - Understand how graph structure forms
- **[Perspectives & Shadows](../../core-concepts/perspectives-shadows.md)** - See how perspectives affect the graph
- **[System View](system-view.md)** - Alternative high-level cave overview
- **[Use Cases: Knowledge Management](../../use-cases/knowledge-management.md)** - Practical applications of network exploration
