---
title: "Part 2: Working with Metadata"
---

The second part of the book works through
techniques that use programming to design batch operations for working with descriptive metadata from digital collections. The examples use the Python language, but the underlying techniques and planning approaches can be adapted to any language or other computational environments.
The approaches in this section assume that your collection already has some amount of structured data, ideally in a documented and shared metadata standards.
The examples explored here largely use the DublinCore standard [@dcmiterms; @miller2022, pg. 65 ff.; @mitchell2015, pp. 105&ndash;107], since it is not only lightweight but is also an openly documented standard that has been widely used to describe digital cultural heritage content.

% comment out sub-section TOC - only want to appear on online version
%## Parts in this Section
%
%:::{toc}
%:context: children
%:::

***TODO:*** things adding in this section

- metadata: what is it, how is it processed by systems, how is it documented?
  - functions
  - schemes
    - quality and validation
  - serialization
  - transformation
- dublincore - overview with basic example, and qualified dublincore example
- MODS: a library example
- Working with XML, XML as a control structure (and can introduce JSON schemas in "Networks" section)
  - basics, more advanced: namespaces, schemas and validation
- transforming metadata - a process for which you can use Python skillz
  - getting data
  - crosswalking
  - implementing a transformation
  - example: creating basic and qualified dublincore
- Documenting metadata: the MAP as an example: activity, creating a MAP for a digital collection
  - exercise: validate the metadata (are the fields valid, proper data; note this won't address metadata quality or accuracy)