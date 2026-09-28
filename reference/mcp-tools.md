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
get all your perspectives (shadows). this is usually the first tool you'll use in a session to see which perspectives you can work with, since most write actions need a perspective id.

**caves__create_shadow**
create a new perspective with a username. each call creates a new perspective with its own automatically generated id and a random profile picture. use different perspectives to organize knowledge from different viewpoints. if you work across multiple cave systems, you'll state which system the new perspective is born into.

**caves__update_shadow**
update an existing perspective's identity — its username, profile picture, and/or tagline. pass the perspective id plus at least one field to change; anything you leave out stays as it is. the profile picture is set from a reachable image url (this tool doesn't upload image bytes); to use a local image, upload it first with caves__create_upload_token and then pass the resulting url here. you must own the perspective.

**caves__list_cave_systems**
list the cave systems you can work in, with their descriptions. only appears if your account has access to more than the default system — it helps your assistant pick the right system when creating shadows or searching.

### searching and exploring

**caves__search_caves**
search for caves by similarity. finds caves with tags similar to your query. optionally filter by specific perspectives to narrow results (this is more computationally intensive, so use it only when you need it). multi-system accounts can scope the search to a particular cave system.

**caves__search_shadows**
find perspectives (shadows). two modes: (1) free-text — pass a query to find shadows about a topic, searching everyone's shadows or just your own; (2) similar-to — pass a perspective id to find perspectives like it, optionally scoped to specific caves so results are ranked by agreement in voting patterns inside those caves rather than overall similarity. to simply list your own shadows, use caves__my_shadows instead.

**caves__get_subcaves**
get all the subcaves (children) of a specific cave. great for exploring hierarchies and seeing what's connected under a topic. pass a perspective id to view the hierarchy through that perspective's eyes (its own connections layered over anything it inherits from).

**caves__get_shadow_map**
fetch the entire map (all connections) for any perspective. returns the graph for a given perspective id in markdown, json, or ic format. use markdown by default — it's more compressed and easier to work with; use json for in-depth analysis when you need richer data. great for exploring other people's maps or exporting your own.

**caves__recent_connections**
see recent connection activity, newest first — what's been happening lately. system-wide by default; pass a perspective id for a "kindred" view (activity from perspectives similar to or followed by that one). filter by time or by caves, and walk further back in history by passing the returned cursor on your next call.

### creating knowledge

**caves__connect_caves**
create connections between caves. this is the core action for building knowledge graphs, and you can create multiple connections at once. it needs a perspective id, so run caves__my_shadows first. before planning connections, load the shared "caves conventions" shadow with caves__get_shadow_map and follow it for naming, phrasing, and reusing existing structure — once per session is enough. connections cost fire, so use them thoughtfully.

**caves__disconnect_caves**
remove a connection between caves. use this to clean up mistakes or change your mind about a relationship. like connecting, it needs a perspective id.

**caves__upload_text**
upload text content and associate it with your perspective. great for storing transcripts, articles, or any text. small text uploads directly; for large text (100kb or more), use caves__create_upload_token and upload via curl to stay within your assistant's limits. place content under a meaningful `parent` cave, and after uploading, use caves__connect_caves to tag it so you can find it later.

**caves__create_upload_token**
get a short-lived upload token for a perspective. returns a bearer token (valid for up to an hour, ten minutes by default) that you can use with curl to upload large content directly — bypassing the context limits of an mcp conversation. also the way to host a local image before setting it as a profile picture with caves__update_shadow.

### discovery and collaboration

**caves__get_shadows_for_tags**
find all perspectives that have made connections with one or more specified caves. match on all of the tags (intersection) or any of them (union). useful for discovering like-minded people or seeing who's working in a particular area.

**caves__get_shadows_for_connection**
find all perspectives that made a specific connection (e.g. who connected "art" as a child of "ai"). shows who agrees (yes votes) or, if you ask, who disagrees (no votes).

**caves__fetch_content**
fetch content from ipfs, private cave-system files, or urls. for ipfs it checks the content type and returns the image or text; for private `/caves/` files it fetches through an authenticated request; for urls it extracts the text content and metadata. useful for working with content that's already referenced in caves.

### capturing and account

**caves__capture_conversation**
capture the connections you've been discussing and prepare to publish them to your caves map. call this when you want to save, record, or add the current discussion (or your thinking) to caves. it loads a step-by-step guide that the assistant follows using the other tools — nothing is written until you confirm.

**caves__crypto_subscribe**
subscribe to caves with cryptocurrency (ethereum or solana) through a guided, multi-step flow: fetch pricing and benefits, create a payment session, submit your transaction, and check its status.

## common workflows

### building a knowledge graph

1. use **caves__my_shadows** to get your perspective id
2. use **caves__search_caves** to find related caves
3. use **caves__connect_caves** to create relationships between concepts

### setting up a perspective's identity

1. use **caves__create_shadow** to create a perspective (it starts with a random profile picture)
2. use **caves__update_shadow** to set its username, tagline, and profile picture
3. to use a local image as the picture, upload it via **caves__create_upload_token** first, then pass the resulting url to **caves__update_shadow**

### organizing uploaded content

1. use **caves__upload_text** to store content
2. use **caves__connect_caves** to tag it with relevant topics
3. use **caves__get_subcaves** to see everything organized under a topic

### discovering perspectives

1. use **caves__search_caves** to find caves you're interested in
2. use **caves__get_shadows_for_tags** to see who else is working in that area
3. use **caves__search_shadows** to find perspectives similar to one you like
4. use **caves__get_shadow_map** with their perspective id to explore their map (if they've made it public)

### keeping up with activity

1. use **caves__recent_connections** to see what's been connected lately
2. pass a perspective id for a kindred view, or filter by caves you care about
3. page further back by passing the returned cursor on the next call

## tips

- always use lowercase for cave tags (unless it's a perspective id, which keeps its checksummed case)
- use markdown format for caves__get_shadow_map — it's more compact
- batch multiple connections together in caves__connect_caves to save time
- connections cost fire, so think before you connect
- use different perspectives for different contexts (work, personal, experimental)
