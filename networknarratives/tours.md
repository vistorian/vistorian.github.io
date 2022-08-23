# Tours in Network Narratives

* [Network Overview](#network-overview)
* [Subgraph overview](#subgraph-overview)
* [Community Exploration](#community-exploration)
* [Centrality Exploration](#centrality-exploration)
* [Ego-Network Exploration](#ego-network-exploration)
* [Temporal Network Exploration](#temporal-network-exploration)

Below, are the tours currently implmented. You can select these tours from the side menu in Network Narratives. Some tours require you to select a subgraph or a node. 


## Network Overview 
Network Overview describes an entire network. It starts
with four introductory slides, covering the geographic extent
(skipped for non-geographic networks), the number of nodes
and links, and the density. The second section focuses on links: it
shows the total and average link weight as well as the strongest and
weakest links in the network. A third section provides some details
about node centralities and the overall community structure (number of
clusters).

![Network Overview-Geo](https://user-images.githubusercontent.com/1230497/186126310-5fa8d881-d178-4751-83a0-8d09678525e1.png)

## Subgraph Overview 

Subgraph Overview is similar to Network Overview but fo-
cuses on a specific subgraph. It shows the subgraph’s size and
the percentage of the network’s nodes it comprises, important
nodes, density, and important links to the rest of the network. After
selecting the templates, a user is asked to select a subgraph using a
lasso selection tool.

![Subgraph Overview-Geo](https://user-images.githubusercontent.com/1230497/186126377-c0769492-f27d-4c0a-9cf9-bfd4cdc04d89.png)


## Community Exploration 

This walkthrough explores and compares clusters in
the network. It shows their sizes, connections, and important
nodes. For example, the Most connected cluster displays the cluster
that has the most connections with the others. For community detec-
tion, we use the algorithm by Newman [49]. More advanced multiple
community detection algorithms can easily be included and used for
comparison (e.g., k-means with different values for k) and shown on
different slides (e.g., one slide per value of k).

![Community Exploration-Geo](https://user-images.githubusercontent.com/1230497/186126451-414060a5-885c-4813-99c7-8ae31fec3f40.png)


## Centrality Exploration 

This walkthrough explores nodes based on different
centrality measures (e.g., degree or betweenness). For exam-
ple, we compute the node with the Highest centrality for both
Betweenness centrality and Closeness centrality. Possible extensions
include comparison of several centrality measures.
Subgraph Comparison compares two specified subsets of
nodes and links (e.g., regions, subgraphs). Selecting this
template prompts the user to select two sets of nodes. The
walkthrough first mentions the Number of nodes and the Number of
links for each subgraph, then details important nodes such as the Most
connected node in each, and finally shows links between the two sub-
graphs (e.g., Number of links, their Total link weight, and the Strongest
link among them).

![Centrality Exploration-Geo](https://user-images.githubusercontent.com/1230497/186126400-a51fd748-62fb-4c2b-8ac5-52d0a34e161b.png)


## Ego-Network Exploration

This walkthrough explores the network around a selected node
and its neighbors. The walkthrough starts with the selected
node and its position within the entire network. The template
then explores the node’s direct neighborhood (nodes, links, strong
connections), then their mutual connections, and finally its neighbors’
neighbors.
Possible Paths explores a set of possible paths between two
selected nodes. The walkthrough reports on path length, com-
bined weights along each path, and the minimum link weight
within each path. This walkthrough was motivated by Archaeologist’s
desire to explore historical travel costs between cities.

![Ego-network Analysis-Geo](https://user-images.githubusercontent.com/1230497/186126427-2d914e3c-1c62-445a-82b1-d0789ab531bc.png)


## Temporal Network Exploration

...in progress.
