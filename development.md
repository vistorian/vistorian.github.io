# Developing for the Vistorian

The Vistorian has a set of repositories and has undergone different versions. This document will help you getting to grips with how you can start helping with the development of the Vistorian. 

## Highlevel structure

The Vistorian is modular, in that is has
* `networkcube.js`: which contains core functionality on loading and querying dynamic networks. This is managed by it's own repository: [Vistorian-core](https://github.com/networkcube/vistorian-core).
* A set of visualizations, which query network data from `networkcube.js` and visualize them. Each visualization is its own project and independent from any other visualization. 
* A web-application, _Vistorian_ that manages uploading data and creates a website with differnt visualizations.

## Repositoriss

The Vistorian is an open-source project hosted at GitHub with several repositories involved. Please get in touch with us if you are planning to help with the development (vistorian@inria.fr).

All repositories are hosted here [https://github.com/networkcube](https://github.com/networkcube). Ignore any of the repositories not mentioned below.

The following repositories are involved in the vistorian.

* [Vistorian-core](https://github.com/networkcube/vistorian-core): core functionalities for all the underlying functions, except he individual visualizations. This includes  
  * dynamic network data structure
  * network measures
  * util packages (colors, motifs, search)
  * inter-view messages.
*[Vistorian-nodelink](https://github.com/networkcube/vistorian-nodelink): the nodelink visualization 
*[Vistorian-matrix](https://github.com/networkcube/vistorian-matrix): the matrix visualization 
Vistorian-bookmarkbrowser](https://github.com/networkcube/vistorian-browser): the sidebar containing 
  * search box
  * legends for node and link colors (and shapes)
*[Vistorian-map](https://github.com/networkcube/vistorian-map): the network map visualiztion
*[Vistorian-dynamicego](https://github.com/networkcube/vistorian-dynamicego): the timeline visualization with functionality to show the dynamic network.
*[Vistorian-web](https://github.com/networkcube/vistorian-web): web-application including 
  * landing page (e.g., http://vistorian.net)
  * data view for uploading and mapping data
  * individual websites for each view (nodelink, matrix, combined view, etc..)
  * functionality for obtaining geo coordinates


## Local development
  
To setup the code locally, read the instructions in the README in the [vistorian-web](https://github.com/networkcube/vistorian-web) repository.

