---
title: Some Metadata Considerations
---

:::{warning}
TODO: title & section? Maybe this should be more like, some special needs, functions, and properties of metadata for collections.

- What is a good title for this? "Metadata Considerations" seems a bit vague . . .

This started as a consideration of XML and properties like namespaces, XSDs, etc.
:::

Recall Svenonius's admonition that information is organized by describing it with a special purpose langauge [@svenonius2000, pg. 1].
Such a language is not possible without specific usage rules, shared definitions, and common practices.
While syntax, usage, and grammar structures are commonly theorized by those who study language's role in human communication,
information organization schemes are generally much more controlled and rule-bound.

## Retaining Semantic Distinctions

While there are many common properties for describing things, there are frequently important semantic
differences even between things with similar names across multiple schemes. In XML, this is called "namespace collisions." Consider, for example, the concept _title_. For a cultural work or collection item, a Title is generally considered a formal, known name. In finding resources, it's often useful to be able to search for things by a known title. Yet while _title_ is a common property, it operates differently in different contexts.

Consider, for example, the Dublin Core `title` [property](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#title), the EAD `<title>` [tag](https://www.loc.gov/ead/v4/EAD4-TL-eng.html#elem-title), and the MODS `<title>` [tag](https://www.loc.gov/standards/mods/userguide/titleinfo.html#title).

## Collection Inventory

A collection consists of multiple items. An important issue for digital collections metadata, then,
is to track the contents and relationships between the components of a collection.
While some of this can be handled in the presentation or publication of collections on the web.
Metadata, however, often acts as the primary link or key to tracking, sorting, and organizing collections.
A list of things in a particular collection may have different names in different contexts, like _index_, _shelflist_, _manifest_, or _set_. In some cases this may be a relatively basic, named text string, like a [URL slug](https://developer.mozilla.org/en-US/docs/Glossary/Slug), in others it may be a more complex result of multiple queries and filters, for example all of the image files associated with a particular source

OAI_PMH uses the collection property to track this.
BagIt uses manifests

