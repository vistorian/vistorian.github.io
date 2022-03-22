# Guided Tours with Network Narratives

![](assets/nn.png)

NetworkNarratives is a module to the Vistorian, providing a set of guided tours in the form of annotated slideshows to help you exploring your network. Chosing from  a set of tours, you can click through facts about your network with a simple click. 

![Find an introductory video here]()

You can launch NetworkNarratives direclty from TheVistorian side menu where you launch the individual visualizations. 

<img src="assets/vistorian-nn.png" hight="200px">

# Available Tours

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

## Subgraph Overview 

Subgraph Overview is similar to Network Overview but fo-
cuses on a specific subgraph. It shows the subgraph’s size and
the percentage of the network’s nodes it comprises, important
nodes, density, and important links to the rest of the network. After
selecting the templates, a user is asked to select a subgraph using a
lasso selection tool.

## Community Exploration 

This walkthrough explores and compares clusters in
the network. It shows their sizes, connections, and important
nodes. For example, the Most connected cluster displays the cluster
that has the most connections with the others. For community detec-
tion, we use the algorithm by Newman [49]. More advanced multiple
community detection algorithms can easily be included and used for
comparison (e.g., k-means with different values for k) and shown on
different slides (e.g., one slide per value of k).

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

## Ego-Network explores 

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

## Temporal Network Exploration

...in progress.
