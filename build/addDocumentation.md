---
layout: page
title: Add documentation to Arbor
permalink: /build/addDocumentation/
---

Each function and workflow should be paired with a documentation page. This page explains how to add to or modify the documentation in Arbor.

# Format

Documentation in Arbor uses markdown syntax. These are text files which are then converted to html by jekyll and displayed as web pages.

# Adding to or modifying documentation pages

Documentation pages are stored in the arbor web page github collection. They belong in the \_posts/documentation folder.

## Adding a new documentation file

To add a new documentation file, first create a local copy of the [arborworkflows.github.com repository](https://github.com/arborworkflows/arborworkflows.github.com). If you are a member of the arbor core team, you can be a contributor to this repository - in which case you can [clone](https://git-scm.com/docs/git-clone) the repo to your computer and push changes. If not, then you can [fork the repo, clone a copy to your computer, make the changes, and then create a pull request](https://help.github.com/articles/fork-a-repo/).

## Modifying existing documentation

Modifying documentation works in basically the same way, and is again handled through the [arborworkflows.github.com repository](https://github.com/arborworkflows/arborworkflows.github.com). Basically, you can either push a change directly (if you are a contributor) or create a pull request for the change.

# Structure of an Arbor documentation page

These pages should have the following sections. See also the Arbor style guide for more detail.

## yaml header

The beginning of the markdown text file is the yaml header. For documentation files, the layout should be "documentation." Under "arborcollection" you can specify the collection where your function or workflow should appear. "arbortype" can be function, workflow, or dataset. If you include an image then a matching file must also be in the "images" folder in the archive - and then that image will be displayed at the top of the page.

````
---
layout: documentation
title: aceArbor
author: Arbor core team
categories: collections ancestralStates
arbortype: function
arborcollection: ancestralStates
description: "ancestral state reconstruction for discrete and continuous characters"
image: acearbor.png

---
````

## Documentation

### Overview: brief description of function

The overview should give a brief (one sentence) overview of what the function does.

### More details

This can give additional details about the function, especially in terms of assumptions and particular methods applied.

### Inputs and outputs

Define the inputs and outputs both in terms of their types and a brief description of what each one represents.

### References

Include all references to the methods used in this function or workflow.
