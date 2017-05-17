---
layout: page
title: Documenting workflows
permalink: /styleGuide/workflows/
---

# Structure of an Arbor workflow documentation page

Pages should have the following sections.

## yaml header

The beginning of the markdown text file is the yaml header. For all documentation files, the layout should be "documentation."  "arbortype" should be "workflow". If you include an image then a matching file must also be in the "images" folder in the archive - and then that image will be displayed at the top of the page.

````
---
layout: documentation
title: matchTreeAndTraits
author: Arbor core team
categories: collections ancestralStates
arbortype: workflow
arborcollection: ancestralStates
description: "match a tree and tip data"
image: acearbor.png

---
````

## Documentation

### Overview: brief description of workflow

The overview should give a brief (one sentence) overview of what the workflow in the collection does.

### More details

This can give additional details about the workflow, such as which algorithms are included.

### References

Include all references to the functions in the workflow.
