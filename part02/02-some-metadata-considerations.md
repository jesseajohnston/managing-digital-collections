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

While there are many common properties for describing things, there are frequently semantic nuances
even between things with similar names when they are used in different practices or contexts.
This is also true between metadata schemes. Consider, for example, the concept of _title_. For a published work, a Title is a formal, known name; book publications frequently have a "title page" near the beginning on which the formal title is clearly written out. For an archival collection, which generally brings together a set of records or materials from a common source, or provenance, there is no formal title or title page to be found. In this case, archivists follow the guidelines set forth in a content standard like Describing Archives: A Content Standard (DACS), which stipulates how to create a title for an archival collection. When searching for either type of resource, a publication or an archival fonds, it's often useful to be able to search for things by their title, but the specific meaning and source of information in the metadata is quite different. Namespacing, or developing a process to specifically state what realm of knowledge a term has meaning within, is one technique that metadata design can use to retain distinctions between similar terms.

### Differentiating Namespaces

As noted above, the property of _title_ is common across different types of resources, and although it connotes an overall name for a resource, it can mean different things in different contexts. In XML, this use of a similar name but in a different context is sometimes called a "namespace collision." An XML _namespace_ refers to the definition of terms, definitions, and usage that may be considered appropriate or valid in a given kind of XML.
In order to differentiate between the different usages, XML defines what namespace each tag is derived from using a qualified name, or QName for short.

Consider, for example, three different senses of _title_ in different metadata schemes:

- in Dublin Core, the [`title` property](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#title) is defined as "a name given to the resource."
- in Encoded Archival Description (EAD), the [`<title>` tag](https://www.loc.gov/ead/v4/EAD4-TL-eng.html#elem-title) is defined as "an element for encoding the formal name of a finding aid."
- in the Metadata Object Description Schema (MODS), the [`<title>` tag](https://www.loc.gov/standards/mods/userguide/titleinfo.html#title) is "a word, phrase, character, or group of characters that constitutes the chief title of a resource, i.e., the title normally used when citing the resource."

While similar, there are slight differences. Dublin Core appears to be the most permissive,
suggesting the title could be any name applied to a resource. In EAD, the title is defined technically,
specifying that it is an element (that is, a specific piece of the XML) used to "encode" a "formal name."
As noted above, an archival collection's name is often formulated by an archivist during the description process,
not determined by intrinsic information or defined in the resource itself. Finally, a MODS title
defines both the language structure but also suggests this is "the chief title" for a resource.
Both MODS and EAD _title_ properties have specific information about the formulation and role of a title, while Dublin Core suggests this could be any name. These properties are similar, but they may not be exactly interchangeable.

For the most part, this type of semantic disambiguation is not needed. When moving data from one structure to another, however, it is important to know if the fields are indeed interchangeable even if they have "the same" name. In this case, while both MODS and EAD titles might be converted into Dublin Core titles, additional steps would be required when going the other direction, from DC to MODS or EAD, since the data might go elsewhere. For example, in MODS there is also a `subTitle` field which might require a portion of a DC title.

## Collection Inventory

A collection consists of multiple items. An important issue for digital collections metadata, then,
is to track the contents and relationships between the components of a collection.
While some of this can be handled in the presentation or publication of collections on the web.
Metadata, however, often acts as the primary link or key to tracking, sorting, and organizing collections.
A list of things in a particular collection may have different names in different contexts, like _index_, _shelflist_, _manifest_, or _set_. In some cases this may be a relatively basic, named text string, like a [URL slug](https://developer.mozilla.org/en-US/docs/Glossary/Slug), in others it may be a more complex result of multiple queries and filters, for example all of the image files associated with a particular source

OAI_PMH uses the collection property to track this.
BagIt uses manifests

## Validation

## Quality Control
