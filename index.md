<link rel="stylesheet" type="text/css" href="assets/styles/style.css">

# The Vistorian 

[The Vistorian](http://vistorian.net) is an online tool for **interactive exploration** of dynamic, multivariate, and geographic networks. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/lr9Kfo-3y5g" title="The Vistorian" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

_[Marie Boucher Dataset](https://hal.archives-ouvertes.fr/hal-02508730/document) Explored Using The Vistorian, courtesy of Dr. Nicole Dufournaud_

**Interactive exploration means to discover and scrutinize your data through interactive queries and multiple complementary perspectives (visualizations).** The idea of exploratory data analysis (EDA) goes back to the [American statistician John Tukey](https://en.wikipedia.org/wiki/John_Tukey).

The Vistorian is an active research project at the [Vishub at the University of Edinburgh](http://vishub.net) and [Inria, France](http://aviz.fr/). The Vistorian is free to use by everyone. If you're using the Vistorian for work, please cite our [poster](#cite-the-vistorian) and send us feedback and examples of your work of our gallery. This helps us keeping the Vistorian funded. Similarly, if you find bugs, send us screenshots and descriptions, we're happy to help you with your data. The Vistorian is open source.

# [>> Launch the Vistorian](http://vistorian.net)

We are currently working an updated version Vistorian 2.0 (release mid Jan 2022) with:
* an easier data uploading routine, and 
* updated visualization features. 

<br/>
## Why the Vistorian?

The Vistorian provides four [interactive visualizations](visualizations.html) to help explore networks: 

![The four visualizations provided by the Vistorian: a node-link diagram, timeline, adjacency matrix, and map view.](figures/vistorian-visualizations.png)

* [Node-link diagram](visualizations.html#node-link): shows networks in the traditional force-directed layout. This visualization is a great start to gain an overview and see the network changing over time. 
* [Adjacency matrix](visualizations.html#adjacency-matrix): shows your network in a compact table format to help visulize very dense networks. It allows you understand clusters using differnet [matrix serialization methods](https://hal.inria.fr/hal-01326759/document).
* [Timeline](visualizations.html#time-arcs): shows you network over time to track frequency and pace of connectivity in your network.
* [Map](visualizations.html#map): shows your network on an interactive map.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0VE5X2GS3AE" title="The Vistorian" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe><br/>

<br/>
## What kinds of networks does it visualize?
The Vistorian provides visualiztions for the following data in networks:

![Diagram shwoing how multiple links, link types, link weights, geography, and changes over time are represented in the Vistorian.](assets/Images/multiple-links.png)


<br/>
## Upload data in simple CSV

Your data needs to be formatted in tables like shown below. All your data will remain securly on your machine. No data will be send to our server. 
<br/>

![Screenshot showing a table of data, with columns labelled "Index", "Sender", "Location_sender", "Qualification", "Receiver", "Location_receiver" and "Date"](assets/Images/loadData_1.png)

Learn more about [formatting data for The Vistorian](formattingdata).

<br/>
## Learn

We provide [detailed tutorials](gettingstarted.html) as well as a [live workshops](tutorials.html).

## Join 

* Join our mailing list: [vistorian-community](https://groups.google.com/u/1/g/vistorian-community).
<!-- * The Vistorian is open source. Get in touch with us if you are interested in contributing. -->

<br/>
## Cite The Vistorian
`Benjamin Bach, Nathalie Henry Riche, Roland Fernandez, Emmanoulis Giannisakis, Bongshin Lee, Jean-Daniel Fekete. NetworkCube: Bringing Dynamic Network Visualizations to Domain Scientists. Posters of the Conference on Information Visualization (InfoVis), Oct 2015, Chicago, United States. 2015.`

<br/>
## Support

The Vistorian is an ongoing research project. It is open source. If you wish to contribute or find issues, get in contact with us.

* Contact: [vistorian@googlegroups.com](mailto:vistorian@googlegroups.com)
<!-- * sign up for the mailing list: [vistorian-community@googlegroups.com](https://groups.google.com/u/1/g/vistorian-community) -->
