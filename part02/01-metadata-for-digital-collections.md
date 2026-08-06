---
title: Metadata for Digital Collections
---

Metadata in the cultural heritage context refers to "structured information about an information resource of any media type or format" [@caplan2003, pg. 3].
Much has been written about the varieties and uses of
metadata in libraries and archives, as well as in the related activities of digital collecting.
In cultural heritage collections, metadata is linked to cataloging and inventorying activities.
In fact, these links point out that metadata as a reigning terminology amongst the cultural heritage community in the later 1990s with the rise of the World Wide Web and what came to be called Dublin Core metadata [@caplan2003, pg. 2].
It gradually became clear that metadata for information management was closely related to practices of cataloging and description in the realms of library and archival work.

This book continues to use the term metadata as a shorthand for resource description and management, but it is worth remembering this is not an unproblematic term. _Metadata_ is a widely used term that often gets used without particular understandings of its history. Using the frequent shorthand for metadata as "data about data," @caplan2003 [pg. 2] notes that in the early 2002, "librarians were quick to realize that they had been creating data about data, in the form of cataloging, for centuries." Thus, the term naturally mapped onto critical library work and has gradually come to stand in for this work overall. But as @coyle2005 points out, this has also been seen to elevate the work of information organization and description beyond _mere_ cataloging with an observation that "metadata is cataloging done by men." The use of _metadata_, then, not only makes this work sound much more technical and digital, it also points to the ongoing deprecation and sidelining of library and archival work as feminized spaces and activities. 
Tracing the development of the term _metadata_ suggests that calling resource management and organization _metadata work_ carries certain cultural implications and assumptions.

## Cultural Heritage Functions of Metadata

Just as cataloging provided a basis for collection organization, management, and preservation, metadata work is essential to the management of digital collections. Frequently noted [e.g., @caplan2003; @mayernik2020; @johnston2024] are three general distinctions about the functions of metadata in cultural collections:

Descriptive metadata
: This is information that serves "the purposes of discover (how one finds a resource), identification (how a resource can be distinguished from other, similar resources), and selection (how to determine that a resource fills a particular need)" [@caplan2003, pg. 3]. This maps closely onto the basic objectives of many bibliographic organization systems to find, identify, select, and obtain desired information resources [see @svenonius2000, pg. 15 ff.].

Administrative metadata
: This metadata helps to administer and control content, specifically in relation to rights, licenses, and access restrictions.

Structural metadata
: This information reflects how a resource is laid out and how its parts relate to one another. While this might be as basic as "225 pages, with figures and index" for a printed book, it is often much more critical for digital objects, which often have multiple component files. As @caplan2003 [pg. 5] notes, this kind of data "can be though of as the glue that holds compound digital objects together," like a list of files that represent pages, chapters, images, or fonts.

@mitchell2015 [pg. 105] and others note two additional metadata types include **preservation metadata**, which is particularly salient in tracking the preservation management of digital materials, and **technical metadata**, which is often managed by systems for resource and content management.

While the above distinctions are useful in thinking about what the metadata "does" in a given system or use case,
most of the metadata that we will be managing
in the course of this book is of the descriptive variety.
Information that is used to technically manage content, like file names, locations, size, type,
and more are largely managed by the system or by
blocks of python code, in which case it is basically __system metadata__, or just data.

In the case of this book's approach to digital collections and metadata,
the information that functions as _metadata_ fulfills all of the above purposes. Particular elements of metadata often support more than one of these functions at a time.
As you are managing and "wrangling" metadata later on in the book, however, it may be useful to think about these functions as ways to explain the need or justification for any given data and information about a resource. Some may be transitory, variables named and only useful for a short time to accomplish a particular transformation or ingest step, but others may be introduced and become important parts of your collection system.
Whatever the case, it is useful to consider what any given information element is doing and why, and for how long, it may be needed.

## Metadata Schemes: Defining structure and usage

Digital systems represent data in complex ways,which can seem daunting.
This is particularly so in our current age of complexity where data can be found, generated, copied, and recombined in seemingly endless ways.
The many roles and functions of metadata, its unclear distinctions from other kinds of data, and the proliferation of uses, can all be confusing.
At its most basic, however, the functions of metadata in cultural heritage are examples of how we structure and control language in specific ways. As @svenonius2000 [pg. 1] sums it up, "information is organized by describing it using a special-purpose language."
Learning about using, managing, and creating metadata, then, is about learning how to effectively manage this special purpose language.

While metadata definitions are often called _schemas_, in this book I follow Caplan's use of _scheme_ instead. For one thing, this is sensible English usage rather than adopting the redundant Latin and English plural. But also, _schema_ has specific meanings "in relation to computer technology as the formal organization or structure of a database, and another specialized meaning in relation to XML" [@caplan2003, pg. 5].

##TODO Describe schemes: rules for what is valid or invalid. Valid terms, usage, data defintions, etc; good quotes from @mitchell2015 around page 104 or so.

```
possible figure or table
Example: DublinCore element? or EAD tag and DACS description to show complexity
```

This book primarily uses three major metadata schemes: DublinCore metadata, the Metadata for Object Description Schema (MODS) for describing digital library resources, and Encoded Archival Description (EAD) for describing archival collections. Below each of these are introduced and further resources are provided.[^resource-note]

### DublinCore

A lightweight, widely used metadata scheme that developed in the 1990s to be used for digital resources that could be accessed on the web.

:::{seealso}
Dublin Core is highly documented online at <https://www.dublincore.org/specifications/dublin-core/> [@dcmiterms].
:::

## MODS

[^resource-note]: The usage of these schemes for describing and managing digital collections is covered in depth by many different projects and tutorials. This section draws particularly on @miller2022 for discussions of Dublin Core and MODS, all three are discussed to some extent in @mitchell2015, and the author's personal use and experience with archival metadata informs the examples using EAD.
