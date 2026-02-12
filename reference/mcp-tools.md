# mcp tools

the caves mcp server provides a set of tools that let ai assistants interact with your caves account. these tools enable powerful workflows like building knowledge graphs, organizing content, and discovering connections.

## what is mcp?

[model context protocol (mcp)](https://modelcontextprotocol.io/) is a standard way for ai assistants to connect to external systems. our mcp server lets you use claude, cursor, or other mcp-compatible tools to work with caves directly in your workflow.

## getting started

to use the caves mcp server:

1. get the mcp server url from your caves account settings on [itscaves.com](https://itscaves.com)
2. configure your ai assistant (claude desktop, cursor, etc.) to connect to that url
3. authenticate with your caves account via oauth when prompted

once connected, your ai assistant will have access to all the tools below.

## available tools

### working with perspectives

**caves__my_shadows**
get all your perspectives (shadows) and their fire balances. this is usually the first tool you'll use in a session to see which perspectives you can work with.

**caves__createPerspective**
create a new perspective with a username. each perspective gets its own identity with a random profile picture. use different perspectives to organize knowledge from different viewpoints.

### searching and exploring

**caves__search_caves**
search for caves by similarity. finds caves with tags similar to your query. optionally filter by specific perspectives to narrow results.

**caves__get_subcaves**
get all the subcaves (children) of a specific cave. great for exploring hierarchies and seeing what's connected under a topic.

**caves__get_shadow_caves**
fetch the entire knowledge graph for any perspective. returns all connections for a given perspective id in markdown, json, or ic format. use markdown format by default - it's more compressed and easier to work with. great for exploring other people's knowledge graphs or exporting your own.

### creating knowledge

**caves__connect_caves**
create connections between caves. this is the core action for building knowledge graphs. you can create multiple connections at once. requires fire to create connections, so use thoughtfully.

**caves__disconnect_caves**
remove a connection between caves. use this to clean up mistakes or change your mind about relationships.

**caves__upload_text**
upload text content to ipfs and automatically tag it with your perspective. great for storing transcripts, articles, or any text content. after uploading, use caves__connect_caves to add meaningful tags so you can find it later.

### discovery and collaboration

**caves__getPidsForTags**
find all perspectives that have made connections with specific caves. useful for discovering like-minded people or seeing who's working in a particular area.

**caves__getPidsForConnection**
find all perspectives that made a specific connection (e.g., who connected "ai" to "art"). shows both agreements (yes votes) and disagreements (no votes).

**caves__fetch_content**
fetch content from ipfs tags or urls. for ipfs, it checks metadata and returns images or text. for urls, it extracts text content and metadata. useful for working with content that's already in caves.

## common workflows

### building a knowledge graph

1. use **caves__my_shadows** to get your perspective id
2. use **caves__search_caves** to find related caves
3. use **caves__connect_caves** to create relationships between concepts

### organizing uploaded content

1. use **caves__upload_text** to store content on ipfs
2. use **caves__connect_caves** to tag it with relevant topics
3. use **caves__get_subcaves** to see everything organized under a topic

### discovering perspectives

1. use **caves__search_caves** to find caves you're interested in
2. use **caves__getPidsForTags** to see who else is working in that area
3. use **caves__get_shadow_caves** with their perspective id to explore their knowledge graph (if they've made it public)

### exploring hierarchies

1. start with a broad cave (e.g., "technology")
2. use **caves__get_subcaves** to see what's underneath
3. drill down into interesting subcaves
4. use **caves__get_shadow_caves** to see your full hierarchy

## tips

- always use lowercase for cave tags (unless it's a perspective id)
- use markdown format for caves__get_shadow_caves - it's more compact
- batch multiple connections together in caves__connect_caves to save time
- connections cost fire, so think before you connect
- use different perspectives for different contexts (work, personal, experimental)

