---
layout: page
title: Documenting functions
permalink: /styleGuide/functions/
---

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
