# Visualizations

* [NodeLink Diagram](#node-link)
* [Time Arcs](#time-arcs)
* [Adjacency Matrix](#adjacency-matrix)
* [Map](#map)

## Node Link

Node-link diagrams show nodes in the network as points (dots) and (multiple) relations between nodes as straight lines. Moving the time slider on the top of the visualization filters links between nodes according to their presence in time.

### Visual Encoding

Layout = Connectivity: The node-link diagram uses the simple default force-directed layout, implemented in D3. Nodes with many common neighbors are drawn closer to each other, while nodes with few connections are drawn at the periphery of the layout.

* Node size = Number of connections: Larger nodes indicate nodes with more connections, smaller nodes have less connections (node degree)
* Multiple lines = multiple relations: Multiple straight lines between two nodes indicate multiple links, e.g. different letters or different types of relationships.
* Line thickness = relation weight: lines of different thickness indicate relations of different strength (or weight).
* Line color = relation type: Different colors mean different types of relation. A color legend is presented in the Browser (see below).

### Interaction
* Zoom: Move mouse wheel (or use the specific zooming gesture on your device)
* Pan: Drag on the empty plane with the mouse
* Show node label by hovering over a node
* Fix or hide the node label by clicking on the node
* Hide/show relation type by clicking onto the colored circle in the legend. The circle is filled if relations of that type are shown in the visualization and empty (white) when the relations of this type are not shown.

## Visual Patterns

Often, we look at visualizations with preconceptions. That means, we're seeing just what we want to see. That also means that we do not see new things. Exploring a network means to see new things. The network below shows letter correspondences between persons. Colors indicate types of letters.

Below, a list of patterns we can find in this network.

* Cluster: Group of densely connected nodes.
* Central nodes, highly connected nodes with many connections.
* Triangle motif with multiple connections.
* Fan: central node connected to many individual nodes.


## Adjacency Matrix
Adjacency matrices (or simply matrices) are table representations of network. Nodes are represented both as rows and columns, connections are shown as marks in the corresponding cells at the intersection of row and column. Contrary to node-link representations, matrices do not suffer from visual clutter if the network is dense (i.e. contains many links). Matrices help you exploring dense networks that would look too cluttered with node-link diagrams.

The above picture shows a cluster of connections of the same type (red). The first row in the matrix, featuring cells of different types (colors), indicates a highly connected node.

Node labels are shown for rows and columns. A small overview on the left shows the entire matrix and the currently visible part when panning and zooming.

### Visual Encodings
* Squared cells = connections: Squared cells indicate connections with a positive weight. If no connection weight is specified in the data, the default weight is set to 1.
* Diamond cells = connections with negative weight: e.g. to show negative correlation between brain regions.
* Split cells = multiple connections between nodes: some squared matrix cells are split into vertical bars. This means that more than one connection exists between the two nodes represented by the row and column.
* Cell color = connection type: Different colors mean different types of relation. A color legend is presented in the Browser (see below).

### Interaction
* Zoom :mouse wheel
* Pan: drag and drop on matrix
* Show connection weight: hover cell

### Parameters
* Label Ordering: Defines the ordering of rows and columns
* Alphanumerical: Order by name
* Reverse Alphanumerical: by name, reversed
* Node degree: according to number of connections, descending
* Similarity: groups nodes with similar connectivity to reveal patterns in the matrix.

### Visual Patterns

Visual patterns inside the matrix are defined by a reordering algorithm, optimizing row and column ordering of the matrix. Vistorian uses one of these algorithms called Leaf-ordering, implemented in reorder.js. Choosing 'Similarity' from the order menu optimizes row and column ordering, based no the currently visible links. I.e., only links present in the current temporal selection will be taken as basis for the reordering. That means that the ordering can be optimized for individual time periods as clusters might be present at specific periods only.

Matrices contain potentially a variety of patterns. The four most important are the following ones:

* Squares along the diagonal of the matrix indicate groups of densely connected nodes in the network; each node indicated in the rows is connected to each node in the column.
* Incomplete squares along the diagonal are almost squares but are missing some cells, i.e. not all nodes in the rows are connected to all nodes in the columns. Such incomplete squares are clusters of densely connected nodes. 
* Complete or incomplete squares off the diagonal indicate bigraphs. In bigraphs nodes from one set are only connected to nodes from the other set. In the figure from the left (almost all) nodes in the rows are connected to (almost all) nodes in the columns.
* The last of the main patterns are dense rows or columns: a row or column with lots of cells indicates a highly connected node. In the figure just above, the node Hubert Antheaume is connected almost all the nodes in the visible columns. The node can be called a hub.

## Time Arcs

Time arcs shows nodes as vertical list (top left) and time along the horizontal axis. Arcs represent links between two nodes at different locations. Clicking a node label on the left side, enters into the ego mode. A ego network shows a node in a network (ego) and its immediate neighbors (alters), as well as connections between the alters. A dynamic ego network shows only these connections over time.  Clicking the ego node a second time, returns to the full view.

### Visual Encoding

* Arc colors: Different colors mean different types of relation. A color legend is presented in the Browser (see below).
* Numbers in brackets at node labels: Node degree (number of connections).

### Interaction
* Set ego node: click node label. Clicking the ego node label twice brings in all previously removed nodes.
* Scroll: rotate mouse wheel

## Map

The map visualization shows a dynamic network with nodes having geographic node positions. This requires that nodes have geographic coordinates associated with them in the data model. Every dot-node on the map represents a position of an actual node in the network. In other words, for every geographical position that one node occupies during its lifetime, there is one node rendered on the map. Hovering a node on the map, shows all the nodes belonging to the same node in the network. For example, if a person in a social network moves between threedifferent positions over time, there will be three nodes rendered on the map and highlighted if one of them is hovered.

All locations that are occupied by some node over time, are rendered as black transparent squares. Hovering, reveals the location's name as well as the names of the present nodes.

Nodes without any geographic position (free nodes) will be placed as close as possible to all their connected neighbors. Free nodes are rendered transparent, which can be adjusted using the corresponding slider on the top of the map visualization.

One common problem with geographic positions is, that multiple nodes are present at the same location. The map visualization allows to specify an offset between these nodes (slider on the top of the visualization) that nodes at the same geographical position slightly apart.

The visual encoding of the network is otherwise the same as for the node link visualization.

### Visual encodings
* Node Transparency: Transparent nodes are free, i.e. they do not have geographic positions associated with them.
* Node Overlap: defines the spatial distance between nodes with the same position. If set to 0, all nodes in the same place will completely overlap. Setting the slider to a higher value will show nodes in the same place in a circle for better readability.


