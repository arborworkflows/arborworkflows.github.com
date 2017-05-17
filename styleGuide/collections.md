---
layout: page
title: Documenting collections
permalink: /styleGuide/collections/
---

# Structure of an Arbor collection documentation page

Pages should have the following sections.

## yaml header

The beginning of the markdown text file is the yaml header. For all documentation files, the layout should be "documentation."  "arbortype" should be "collection". If you include an image then a matching file must also be in the "images" folder in the archive - and then that image will be displayed at the top of the page.

````
---
layout: documentation
title: ancestralStates
author: Arbor core team
categories: collections ancestralStates
arbortype: collection
arborcollection: ancestralStates
description: "ancestral state reconstruction for discrete and continuous characters"
image: acearbor.png

---
````

## Documentation

### Overview: brief description of collection

The overview should give a brief (one sentence) overview of what the functions and workflows in the collection do.

### More details

This can give additional details about the collection

### References

Include all references to the collection itself - references for individual functions should go in the documentation for that function.
