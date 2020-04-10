# Developing for the Vistorian

The Vistorian has a set of repositories and has undergone different versions. This document will help you getting to grips with how you can start helping with the development of the Vistorian. 

## Highlevel structure

The Vistorian is modular, in that is has
* A __libary `networkcube.js`__ which contains core functionality on loading and querying dynamic networks. This is managed by it's own repository: [Vistorian-core](https://github.com/networkcube/vistorian-core).
* A __set of visualizations__, which query network data from `networkcube.js` and visualize them. Each visualization is its own project and independent from any other visualization. 
* A __web-application, _Vistorian_,__ that manages uploading data and creates a website with differnt visualizations.

## Repositoriss

The Vistorian is an open-source project hosted at GitHub with several repositories involved. Please get in touch with us if you are planning to help with the development (vistorian@inria.fr).

All repositories are hosted here [https://github.com/networkcube](https://github.com/networkcube). Ignore any of the repositories not mentioned below.

The following repositories are involved in the vistorian.

* __[Vistorian-core](https://github.com/networkcube/vistorian-core):__ core functionalities for all the underlying functions, except he individual visualizations. This includes  
  * dynamic network data structure
  * network measures
  * util packages (colors, motifs, search)
  * inter-view messages.
* __[Vistorian-nodelink](https://github.com/networkcube/vistorian-nodelink):__ the nodelink visualization 
* __[Vistorian-matrix](https://github.com/networkcube/vistorian-matrix):__ the matrix visualization 
Vistorian-bookmarkbrowser](https://github.com/networkcube/vistorian-browser): the sidebar containing 
  * search box
  * legends for node and link colors (and shapes)
* __[Vistorian-map](https://github.com/networkcube/vistorian-map):__ the network map visualiztion
* __[Vistorian-dynamicego](https://github.com/networkcube/vistorian-dynamicego): the timeline visualization with functionality to show the dynamic network.
* __[Vistorian-web](https://github.com/networkcube/vistorian-web):__ web-application including 
  * landing page (e.g., http://vistorian.net)
  * data view for uploading and mapping data
  * individual websites for each view (nodelink, matrix, combined view, etc..)
  * functionality for obtaining geo coordinates


## Local development
  
To setup the code locally, read the instructions in the README in the [vistorian-web](https://github.com/networkcube/vistorian-web) repository.

