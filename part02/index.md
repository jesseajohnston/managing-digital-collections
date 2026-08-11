---
title: "Part 2: Working with Metadata"
---

The second part of the book works through
techniques that use programming to design batch operations for working with descriptive metadata from digital collections. The examples use the Python language, but the underlying techniques and planning approaches can be adapted to any language or other computational environments.
The approaches in this section assume that your collection already has some amount of structured data, ideally in a documented and shared metadata standards.
The examples explored here largely use the DublinCore standard [@dcmiterms; @miller2022, pg. 65 ff.; @mitchell2015, pp. 105&ndash;107], since it is not only lightweight but is also an openly documented standard that has been widely used to describe digital cultural heritage content.

Following the discussion of metadata, this part turns to XML as a common, open data encoding structure for metadata.
Interactive examples demonstrate how to use Python to interact with XML, search and query an XML structure, modifying and write XML documents, and how to validate against external standards. This section provides a full toolbox that supports working with, analyzing, and modifying XML.

:::{note} Assumptions and Skills in this Section
This section assumes you:

- Can use python and Jupyter notebooks
- Can import python libraries
- Have a basic understanding of markup language syntax, both HTML and XML
:::

% comment out sub-section TOC - only want to appear on online version
%## Parts in this Section
%
%:::{toc}
%:context: children
%:::

***TODO:*** things adding in this section

- [x] metadata: what is it, how is it processed by systems, how is it documented?
  - functions
  - schemes
    - quality and validation
  - serialization
  - transformation
- [~] Introduce basic flavors we'll use!
  - [~] dublincore - overview with basic example, and qualified dublincore example - in progress
  - [X] MODS: a library example
  - [~] EAD - more details, though currently in progress
- [x] Working with XML, XML as a control structure (and can introduce JSON schemas in "Networks" section)
  - [x] basics with `ElementTree`
  - [ ] more advanced: namespaces, Xpath
  - [ ] maniuplating and writing
  - [ ] advanced (requries lxm`l): validate, shcemas the metadata (are the fields valid, proper data; note this won't address metadata quality or accuracy)
- [ ] Final ACTIVITY transforming metadata - a process for which you can use Python skillz
  - crosswalking
  - implementing a transformation
  - example: creating basic and qualified dublincore
  - Documenting metadata: the MAP as an example: activity, creating a MAP for a digital collection
    - use a basic object to create dublincore (the MAP), then write it to XML (transformation)
    - ASSIGNMENT: identify a digital object (from UM or LOC), extract the metadata (put it in a table, that also labels metadata as different functions descrip/tech/admin); then, map and document to create a transformation (table), and write a clean XML version