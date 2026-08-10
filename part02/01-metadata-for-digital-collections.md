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

## Metadata and Digital Cultural Heritage Management

Just as cataloging provided a basis for collection organization, management, and preservation, metadata work is essential to the management of digital collections. Frequently noted [e.g., @caplan2003; @mayernik2020; @johnston2024] are three general distinctions about the functions of metadata in cultural collections:

Descriptive metadata
: This is information that serves "the purposes of discover (how one finds a resource), identification (how a resource can be distinguished from other, similar resources), and selection (how to determine that a resource fills a particular need)" [@caplan2003, pg. 3]. This maps closely onto the basic objectives of many bibliographic organization systems to find, identify, select, and obtain desired information resources [see @svenonius2000, pg. 15 ff.].

Administrative metadata
: This metadata helps to administer and control content, specifically in relation to rights, licenses, and access restrictions.

Structural metadata
: This information reflects how a resource is laid out and how its parts relate to one another. While this might be as basic as "225 pages, with figures and index" for a printed book, it is often much more critical for digital objects, which often have multiple component files. As @caplan2003 [pg. 5] notes, this kind of data "can be though of as the glue that holds compound digital objects together," like a list of files that represent pages, chapters, images, or fonts.

@mitchell2015 [pg. 105] and others note two additional metadata types include **preservation metadata**, which is particularly salient in tracking the preservation management of digital materials, and **technical metadata**, which is often managed by systems for resource and content management.

:::{warning} TODO: Revise above section & typology
**Revise above** - metadata functions should be focused on digital content. Descrip/admin/struct = METS convention [@gilliland2016]. Preservation and technical essentially tied in digital metadata to PREMIS, bring this to Mitchell's point. Additionally, use @gilliland2016 and @svenonius2000 to note that metadata is critical to allow for greater access, sharing, publication, tracking versions, preserving, validating, searching and locating [@gilliland2016; see also @bacaed2016; @eckard2020].

***Why does this matter?***

Reliable and consistent metadata are even more important in an age of AI and absolutely compounding copies and misinformation, particularly for digital collections.

### A reframe for the "types" and "why metadata" section above

The descrip/admin/struct distinctions remain useful in thinking about metadata in cultural heritage contexts
because we are concerned about meaningful information resources and coherent "items,"[^item-fn] even in the digital realm.
That said, however, technical and preservation information is essential for
managing digital content.
In part, this is because digital "items" have many distinct but inter-related components.
If you ask conservators about caring for a printed book, they would note it is a complex object with various material challenges that can differ because of the individual components and how they interact, ranging from
paper composition, types of ink(s) used, binding materials, printing methods, and other componentsway whatever corresponds to a book
:::

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

### An Example Item: An Image File and Metadata

As an example, let's take a look at the illustration of a wild turkey from
a Audubon's _Birds of America_ series (see [](#turkey-img)). This copy is a scanned image from
the University of Michigan's Special Collections Research Center, which provides a fully-featured and detailed presentation of the image at various resolutions with extensive descriptive and technical metadata, which you can see [here][turkey-permalink].

```{figure} /data/sclaudubon_sclib_B464540_AUDUBON_V1_1_P1_audubon_v1_1_p1_2702x4086.jpg
:label: turkey-img
:alt: Color illustration of a wild turkey by James Audubon, printed in the late 1820s
:align: center
:width: 75%

The wild turkey illustration from Audubon's _Birds of America_ (1827&ndash;1830), captioned "Wild Turkey, Meleagris Gallopavo, Linn." This scanned image comes from the University of Michigan's [Special Collections Research Center](https://lib.umich.edu/locations-and-hours/special-collections-research-center)
```

Basic descriptive metadata is already given above: this is an illustration of a turkey, from James Audubon's _Birds of America_. This offers a basic description or title, a creator, and an original source. The above description hints, though, at the underlying complexity:
this is a digital copy of a file that was _scanned_ from an original book,
there are multiple resolutions of the image, and there is a series.
If you wanted to find this image, the basic descriptive information might be enough.
The significance and utility of the above image would be significantly reduced, however, if its relationship to these other items was lost, which is largely the purpose of the additional metadata
that fills in necessary structural, technical, and preservation information, which allows a system to reconstruct, render, and present in context; and allows the owner and user to preserve or demonstrate the integrity of the image over time.

The online presentation of the turkey plate contains significant and robust
metadata already. To illustrate the above points, let's take a look at some of the basic information included under the heading _Record Details_ (see [](#turkey-basic-metadata)).

:::{table} Selected information from the _Record Details_ section of the wild turkey item page (note that the source page provides much more information).
:label: turkey-basic-metadata

| Attribute | Value |
| --- | ------ |
| Item ID | B464540 |
| Image Title | Wild Turkey, Meleagris Gallopavo, Linn. |
| Work Title | The birds of America; from original drawings by John James Audubon |
| Comments | Engraved title page. Imprint dates: v. 1, 1827-30; v. 2, 1831-34; v. 3, 1834-35; v. 4, 1835-38, June 20. Originally issued in 87 parts. "The plates were published without any text, to avoid the necessity of furnishing copies gratis to the public libraries in England, agreeably to the law of copyright."--Sabin, A dictionary of books relating to America, v. 1, p. 315. |
| Creator | Audubon, John James, 1785-1851, (illustrator, publisher) |
|         | Havell, Robert, 1793-1878, (illustrator, printer of plates.) |
|         | Lizars, W. H. (William Home), 1788-1859, (illustrator.) |
| Date    | 1827-1830 |
| Rights  | The images in this collection are in the public domain and may be used without permission. Kindly provide attribution to the University of Michigan Special Collections Library. |
| Item Dimensions | 100 x 68 cm. |
| Medium | Intaglio printing, hand-colored |
| Subject | Birds |
| Type | Book |

:::

As described in the section on [data encodings](/part01/04-open-data-formats.md),
this metadata could easily be understood as a list of _attribute - value_ pairs.
These might be encoded equally well as a CSV, JSON, or XMl file.
Although these would look slightly different, the data is equivalent, as demonstrated in the selected examples of a few data attributes about the wild turkey image. [](#encoding-comparison) below shows how these "same" data would look in different encoding formats.
Note that this example illustrates only five selected fields, `Image Title`,
`Work Title`, `Subject`, `Type`, and `Rights`. Check the number of fields in the source example to get an idea of the full extent of this metadata.

% NOTE: `tab-set` accepts only class/label/enumerated/enumerator options. Do not use :description:/:caption: text. What was formerly there is now incorporated into the main prose body.

::::::{tab-set}
:enumerated: true
:label: encoding-comparison

:::{tab-item} CSV 1: listed pairs
:label: encoding-ex-csv1
```csv
image_title,"Wild Turkey, Meleagris Gallopavo, Linn."
work_title,The birds of America; from original drawings by John James Audubon
subject,birds
type,book
rights,public domain
```
:::

:::{tab-item} CSV 2: rows & records
:label: encoding-ex-csv2
```csv
image_title,work_title,subject,type,rights
"Wild Turkey, Meleagris Gallopavo, Linn.",The birds of America; from original drawings by John James Audubon,birds,book,public domain
```
:::

:::{tab-item} XML
:label: encoding-ex-xml
```xml
<metadata>
    <image_title>Wild Turkey, Meleagris Gallopavo, Linn.</image_title>
    <work_title>The birds of America; from original drawings by John James Audubon</work_title>
    <subject>birds</subject>
    <type>book</type>
    <rights label="Public Domain" type="uri">https://creativecommons.org/publicdomain/mark/1.0/</rights>
</metadata>
```
:::

:::{tab-item} JSON
:label: encoding-ex-json
```json
[{"image_title","Wild Turkey, Meleagris Gallopavo, Linn."},
{"work_title","The birds of America; from original drawings by John James Audubon"},
{"subject": "birds"},
{"type": "book"},
{"rights":"https://creativecommons.org/publicdomain/mark/1.0/"}]
```
:::

::::::

% mystmd's typst renderer does not emit labels for tabSet/tabItem, so cross-references
% to the tabs above break the PDF export. These raw typst anchors supply the missing
% labels; they render nothing in HTML. Remove if mystmd fixes the typst tab renderer.
:::{raw:typst}
#metadata("tab-set") <encoding-comparison>
#metadata("tab-item") <encoding-ex-csv1>
#metadata("tab-item") <encoding-ex-csv2>
#metadata("tab-item") <encoding-ex-xml>
#metadata("tab-item") <encoding-ex-json>
:::

Let's take a quick look at the various encodings. In tab [**CSV 1**](#encoding-ex-csv1)  above, the data is encoded as a single _attribute - value_ pair on each line. This format works for a single record, but it would quickly become unwieldy for multiple records.
Multiple records would be easier to encode in a style like that shown in the [**CSV 2**](#encoding-ex-csv2) tab,
which is styled in a _rows & records_ format. In this example, new records could readily be added by adding a new row in the file, which would have the same attributes as outlined in the first row, also known as the _header row_.
In the [**XML**](#encoding-ex-xml) tab, note how each field is wrapped
by an opening and closing tag in pointy braces (e.g., `<tag>text</tag>`).
In addition, the XML structure enables a deeper structure: note how the
rights tag includes embedded attributes, including the `@label` of `Public Domain` and an indication that the data enclosed in the tag is a URI (`@uri`).
Finally, the [**JSON**](#encoding-ex-json) tab shows how the data might be encoded in this format.
We will be discussing and working with JSON much more later, but it is worth noting
in brief that the entire record here is enclosed in square brackets (`[ ]`),
which hints that Python can work with this data as a list.

We will see below how the metadata examined here can be encoded more effectively
in data structures that are more closely defined through specific metadata schemes.

:::{hint} TODO?: Add a complex/multi-file example?
Example objects that could illustrate metadata examples. Possibly two to illustrate a complex/simple object?

**Possibility:** web archive, such as the Slate example below?
:::

This book primarily uses three major metadata schemes: DublinCore metadata, the Metadata for Object Description Schema (MODS) for describing digital library resources, and Encoded Archival Description (EAD) for describing archival collections. Below each of these are introduced and further resources are provided.[^resource-fn]

### Dublin Core / DCMES

The Dublin Core Metadata Element Set (or DCMES), commonly known as just _Dublin Core_, is a flexible and actively maintained metadata scheme [see @dcmiterms].
The basic uses of Dublin Core developed in the late 1990s, when it was developed to be used for digital resources that could be accessed on the web.
Dublin Core takes its name from Dublin, Ohio, which was the location of a meeting in 1995 at which the intial set of Dublin Core attributes was memorialized.
The meeting included fifty-two participants and focused on the question "Can a simple metadata record be defined that sufficiently describes a wide range of electronic objects?" The question responded to concerns about the difficulty of finding documents on the early Web, and with an assumption that while standard description could help users locate these resources, a simpler (less laborious approach than bibliographic description) way forward would be more widely adopted and beneficial to the web. The meeting aimed to "achieve consensus on a list of metadata elements that would yield simple descriptions of data in a wide range of subject areas, and to lay the groundwork for achieving further progress in the definition of metadata elements that describe electronic information" [@weibel1995].

TODO: add pomerantz?

DCMES thus produced a "simple set of data elements for describing documents and other objects on the Internet" [@coyle2005, pg. 161]. Those elements were refined into a set of fifteen basic attributes, which were codified in 1998 in a standard issued by the Internet Engineering Task Force as [RFC 2413](http://www.ietf.org/rfc/rfc2413.txt) in 1998 [@rfc2413]. As @coyle2005 [pg. 162] points out, the scheme is easy to use, permissive, and "there are no cataloging rules involved." All of this made the scheme easy to use, and while it did not gain the same level of detail and control as did other metadata schemes, it became a widely used _lingua france_ for digital resource description.

- additional elements have been added, and more granularity possible; this is DCMES/DCTERMS, known as RFC 5013 [@rfc5013]; as of August 2026 there are 55 defined terms.
- and more recently, a data model and reference documentation have added classes (types of elements), as well as domains (kinds of data) and ranges (valid type values), so that DCMES now functions as a robust, highly extensible, linked-data-capable metadata scheme;
- because it retains its original terms, the scheme is backwards compatible to the original 15 elements
- DCMES is agnostic as far as data encoding, and valid data can be serialized in CSV, XML, or JSON depending on the publisher's needs and preferences;
- because it remains open, highly documented, and hospitable, the DCMES essentially provides a metadata framework upon which other systems can be built; for example, the [DarwinCore scheme](https://dwc.tdwg.org/) adds standard metadata elements for describing biodiversity data and taxonomies, which are a specialized area beyond DCMES but allows for the use and reuse of the "core" DC terms.

:::{seealso} Learn More about the DCMES
Dublin Core is highly documented online at <https://www.dublincore.org/specifications/dublin-core/> [@dcmiterms].
:::

### MODS

The Metadata Object Description Schema (MODS) was developed by the Library of Congress
in the early 2000s as a standard way to serialize and share descriptive information
about collections on the Web. Because many of these items corresponded to digitized analog sources,
which were typically already described according to cataloging conventions in the MARC (Machine Readable Cataloging) format, many of the elements in the scheme can be directly linked to bibliographic conventions.
MODS is a much simpler scheme with fewer elements and a less fussy structure; as Coyle puts it, MODS is a "kinder, gentler MARC" [@coyle2005, pg. 162; see also @mitchell2015].
The first version of MODS was formally published in 2002, and the current version, as of 2026, is 3.8.

Although the data can be stored or presented in different ways, this schema
was designed with XML in mind [@guentheretal2003], and MODS records are always presented in XML.
A basic MODS record may look something like the example presented in [](#mods-sample).

```{code} xml
:label: mods-sample
:filename: /data/lcwa-mods-5.xml (excerpt)
:linenos:
:emphasize-lines: 5, 7-9, 11, 17-23, 31
:caption: This is an example of a simplified MODS record for the Library of Congress' web archive of _Slate Magazine_. The collection is accessible at <http://www.loc.gov/item/lcwaN0010234>. This example is excerpted from a larger set of records in the associated file.
<?xml version="1.0" encoding="UTF-8"?>
<mods>
    <identifier>lcwaN0010234</identifier>
    <titleInfo>
        <title>Slate Magazine</title>
    </titleInfo>
    <language>
        <languageTerm authority="iso639-2b" type="code">eng</languageTerm>
    </language>
    <typeOfResource>text</typeOfResource>
    <genre authority="marcgt">web site</genre>
    <originInfo>
        <place>
            <placeTerm type="text">United States</placeTerm>
        </place>
    </originInfo>
    <relatedItem displayLabel="URL" type="constituent">
        <identifier displayLabel="Access URL" type="uri">http://www.slate.com/</identifier>
        <identifier type="database id">15046</identifier>
        <location>
            <url displayLabel="thumbnail image">http://cdn.loc.gov/service/webcapture/project_1/thumbnails/lcwaS0015046.jpg</url>
        </location>
    </relatedItem>
    <location>
        <url displayLabel="Archived site">http://www.loc.gov/item/lcwaN0010234</url>
    </location>
    <location>
        <physicalLocation>Library of Congress, Washington, D.C., 20540 USA</physicalLocation>
        <physicalLocation authority="marcorg">dlc</physicalLocation>
    </location>
    <accessCondition type="restrictionOnAccess">None</accessCondition>
    <recordInfo>
        <recordContentSource authority="marcorg">dlc</recordContentSource>
        <recordIdentifier source="dlc">lcwaN0010234</recordIdentifier>
    </recordInfo>
</mods>
```

A full set of information about a specific item, which is linked to the valid MODS values,
is called a _MODS record_. MODS records may be standalone (as illustrated above in [](#mods-sample)),
they may be embedded within a larger metadata entity (for example, some sections of EAD, as discussed later, may contain MODS metadata),
or they may be grouped together. When grouped together, you will see the `modsCollection` element
enclosing a series of MODS records.

The example illustrates a mix of the various functions of metadata mentioned earlier.
**Descriptive** information that may be useful to find or identify the item is indicated
in the `title` tag (line 5). Likewise, the `language` tag indicates the primary language of the described resource (lines 7&ndash;9); in a collection that is largely developed for an English-speaking audience,
this might not be highly useful, but in the case of a research collection that contains items
in many languages, this could be useful, particularly when items are not in English.
**Administrative** information, in this case confirming that there are no restrictions,
is indicated in the `accessCondition` tag (line 31).
Finally, **Structural** information is indicated in the `relatedItem` section (lines 17&ndash;23),
which provides a link to the original web site (line 18) and to a related thumbnail image (line 21)
that displays on the web archive's catalog record.

Like qualified Dublin Core, MODS can also embed information about valid structure and sources of data.
MODS can indicate controlled vocabularies or Vocabulary Encoding Schemes, which it calls _Sources_. This is illustrated at line 11, where the `@authority` attribute on the `genre` tag indicates `marcgt`,
a list of genres and forms that can be described in MARC, which is [defined here](https://www.loc.gov/standards/valuelist/marcgt.html).
MODS can also indicate specific data format patterns or Syntax Encoding Schemes, which it calls _Value lists_. This is illustrated at line 8, where the `@authority` attribute on the `languageTerm` tag is given as the numeric ISO language code `iso639-2b`. These three-digit language codes are defined by the International Standards Organization and listed by Library of Congress at the [ISO 639-2 site](https://www.loc.gov/standards/iso639-2/).  

We will work more later with MODS in the section on XML.
For now, beyond noting that MODS is serialized in XML,
it is additionally useful to note that if you open
an XML file and are looking for MODS content, it can be identified
by the root element `mods` (line 2).
In files that contain more than one MODS record, you may also find the `modsCollection` element.

:::{seealso} Learn more about MODS
MODS is well documented and maintained by the Library of Congress's Network Development and MARC Standards Office at <https://www.loc.gov/standards/mods/>.

An alphabetized list of valid MODS elements, with links to the their usage information, is at <https://www.loc.gov/standards/mods/userguide/userguide-index.html>.
:::

### EAD

The Encoded Archival Description scheme (EAD) was developed to work
with semi-structured text that can describe hierarchically organized collections
most commonly found in archives. Because these collections often contain
large amounts of unpublished materials, including manuscripts and business records among many other kinds of content,
they are only rarely described at the item level.
Instead, they often describe broad categories, or _series_, of material,
which are distinguished by function or material form.

Like MODS, EAD was developed with XML in mind and, while current systems
do not necessarily rely on the XML encoding, this shcme is defined by XML.
The scheme was developed in [TODO: year?]
The ArchivesSpace finding aid management system, for example,
serializes data in a JSON format (more on that later)

Let's talk more about EAD!

:::{seealso} EAD Resources
EAD was developed by the Society of American Archivists and is maintained and published by the Library of Congress. The most current definition of the scheme (EAD 4 as of July 2026) can be found at <https://www.loc.gov/ead/v4/EAD4-TL-eng.html>.[^ead-fn]

A highly useful additional resource is [EADiva](https://eadiva.com/elements/), which provides an accessible and comprehensive overview of the scheme, maintained by Ruth Kitchin Tillman.
:::

## Metadata Encoding

Metadata for digital content is generally stored in a system or database.
It does not matter too much how that data is structured, as long as it is stable, consistent, and understood by the system that uses it.
When information is transferred between systems, for example when it is provided as a response that will be displayed in a browser, the format of the information becomes more important.
This transferable or transmittable state is described as _serialization_.
This book will discuss three main structural standards that may be encountered by users
and collections managers, and are common formats to _serialize_ or transfer data.[^structure-fn]

The data encoding formats XML and JSON are currently among the most common structural formats for metadata serialization. While there are fans of different data
formats, and there are folks out there who have deeply invested in specific data formats as developers or system admins, the material consequences of these formats does not impact the collection manager on a regular basis.
It is useful to be aware of the various ways that data can be encoded, but it is no longer essential to learn only one format in great detail.
It is, instead, a good idea to be comfortable with multiple encoding formats,
and to develop skills with reusable tools that can manage them.

Practices and workflows, particularly from the 1990s and early 2000s, often developed to function in situations that did not fully support programmatic use of data and databases.
Thus, in some cases, catalogers and processors transcribed meticulously coded artisanal metadata. Modern systems should support working with this data programatically, which is less dependent on specific encoding structures and, hopefully, less prone to inconsistencies in the future.
It is therefore no longer so critical to focus on the subtleties of data encoding.
As @eckard2020 [pg. 76] notes, "it is worth noting that focusing _too much_ on the data standard for format/technical interchange&mdash;as might be the case, for example, if an archivist these days opted to hand-encode XML&mdash;can sometimes indicate a misdirected fixation on the way that metadata standards are serialized."
Effort, instead, should be focused on developing tools that support consistent management and creation of metadata for digital collections, as well as learning and conforming to extant metadata standards.

[^item-fn]: The definition and meaning of _item_ can be confusing in collecting contexts, because it depends on an organization's collecting focus and activities. For some collections, if they collect only one kind of thing, say books, this might be a relatively simple concept. But very few organizations collect only books, and even if one does it would quickly become clear that there are meaningful needs for different types of description based on time period, publisher, region, language, etc. Libraries, archives, and museums collect all manner of things from books to journals to ephemera to rare manuscripts to biological specimens, any of which can be digitized in some way. For collections that collect different kinds of things, which encompasses most libraries and archives, then, the _item_ concept is both a useful category and a term of art. This complexity is only amplified when content is digitized, or born digital, since the digital content has management needs and often its associated metadata may have distinct needs or challenges based on the original item type. To get around this, the PREMIS metadata scheme uses the term "intellectual entity," meaning "a distinct intellectual or artistic creation that is considered relevant to a designated community in the context of digital preservation [@premis2015, pg. 8]. An intellectual entity, which may or may not have any canonic instantiation, is realized in a "representation," which is "the set of files, including structural metadata, needed for a complete rendition of an Intellectual Entity" [@premis2015, pg, 8]. My usage of "item," then, is most closely related to the PREMIS sense of representation. It is worth noting, however, that the concept of _item_ here is distinct from another stream of bibliographic description theory that includes the FRBR WEMI model, in which the term is closer to "intellectual entity." But for now, that distinction and debate is beyond the scope of this project.
[^resource-fn]: The usage of these schemes for describing and managing digital collections is covered in depth by many different projects and tutorials. This section draws particularly on @miller2022 for discussions of Dublin Core and MODS, all three are discussed to some extent in @mitchell2015, and the author's personal use and experience with archival metadata informs the examples using EAD.
[^structure-fn]: Note that _data structure_ should not be conflated with _structural metadata_. The terms are unfortunately similar, but they are distinct.
[^ead-fn]: All discussions as of this writing are based on EAD 3. EAD 4 was released while this book was in production, so it is referenced here as the current version, but its freshness means that no examples herein utilize version 4.

[turkey-permalink]: https://quod.lib.umich.edu/s/sclaudubon/x-b464540/audubon_v1_1_p1