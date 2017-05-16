---
layout: page
title: Arbor for developers
permalink: /build/
---

There are lots of ways that you can contribute and participate in Arbor. You can add new functions, datasets, and collections to Arbor, expanding the types of analyses you can do in Arbor. You can also access our source code, using github to report bugs and pull requests to fix things and extend our functionality.

# Add to Arbor

## Add new functions to Arbor

It is straightforward to add new functions (in R or Python) to Arbor. You can also save, download, and share your functions with your friends. For instructions on how to do that, see our [tutorials]({{ site.baseurl}}/tutorials).

## Create and share Arbor workflows

Arbor workflows are visual maps of functions that are connected via inputs and outputs. You can also save, download, and share workflows. For instructions on how to do that, see our [tutorials]({{ site.baseurl}}/tutorials).

## Create or modify Arbor collections

Arbor functions and workflows are organized in collections. If you want to add to or edit our collections, or submit your own collection, see our page on [adding collections]({{site.baseurl}}/build/addCollection.html).

## Add a new R package or python library to Arbor

If you have an R package stored on CRAN or github, you can install it on Arbor and immediately use functions from your package in Arbor. Instructions [here]({{site.baseurl}}/build/addPackage.html)

## Document your Arbor functions and collections

Arbor documentation is maintained on this webpage which is stored [here](https://github.com/arborworkflows/arborworkflows.github.com). More information on [creating documentation.]({{ site.baseurl }}/build/addDocumentation/)

# Create new Arbor apps

You can take a useful Arbor function or workflow and create a dedicated Arbor app, which is a web page that runs your algorithm. This requires just a bit of knowledge of javascript. You can get started [here]({{site.baseurl}}/addApp.html).

# Work with the Arbor source code to fix bugs or extend functionality

Arbor workflows uses an open development paradigm. To get our source code, or to contribute to the project, please visit our github repository at [github.com/arborworkflows](https://github.com/arborworkflows).

In particular, you can access the [Arbor workflow main web application](https://github.com/arborworkflows), the [Arbor collections](https://github.com/arborworkflows/arborCollections), or [all current Arbor apps](https://github.com/arborworkflows/ArborWebApps).

Under the hood, Arbor uses open-source Kitware products: the workflow engine [flow](https://github.com/kitware/flow); the data management platform [girder](https://github.com/kitware/girder); and the web framework [tangelo](https://github.com/kitware/tangelo). We also draw liberally from a large number of R packages, and maintain our own, [aRbor](https://github.com/arborworkflows/aRbor).

For detailed instructions on installing Arbor on your own machine, go to [http://arborworkflows.readthedocs.org/en/latest/installation.html](http://arborworkflows.readthedocs.org/en/latest/installation.html).

For more information about the source code repository, [contact us]({{site.baseurl}}/team).
