---
title: "Project 2: Designing a MAP"
categories: activities assignments metadata map
---

**Assignment Due: October 30**

A **metadata application profile (MAP)** is a technical document that documents and expresses all of the types of items and the descriptive information about them that you plan to collect. It documents where the information comes from (in most cases, these descriptions will be from already extant schemas), how they are used in your local site, what is valid or invalid, whether they are required or not required, and whether they are repeatable.

## Assignment Background and Resources

In this assignment, you will design a MAP for your resource set. Begin planning by using the small set of resources that you chose for your initial site setup in [](/labs/lab-04-artisanal-metadata.md), with the assumption that your larger collection will follow the same models that you are setting now. (Keep in mind that some updating may be required later, as you identify further collection resources.)

The essential requires you to understand and model the metadata you're receiving, then to decide how these fields will be used in your new site. While doing this, you will document the kinds of metadata that already appear in the descriptive metadata, then plan where they should go to display in your digital repository site, preferably within a standard and known metadata scheme (like Dublin Core, MODS, or another). The key is to identify which types of information are used, the granularity and apparent semantics of the metadata, and their relationship to the items. This design must work at the item level, but also apply across the collection. That is, each field documented in your MAP should be documented in a way that is applicable to any resource in the collection. While often described as a Dublin Core application profile (if your site metadata is only Dublin Core), this is a more generic metadata profile that describes all terms in use in your collection. (Additional, but more conceptual, guidelines for designing DublinCore Application Profiles are available from [DublinCore application profile guidelines](https://www.dublincore.org/specifications/dublin-core/profile-guidelines/).)

The MAPs will be similar in form and content, but each person/collection's MAP should be unique, based on the content of the collection. Start by determining the full range of fields associated with your main object types. You can start with one exemplar object, and adapt as further object types are added.

### Source Data

While individual item metadata may vary slightly, your MAP needs to accommodate general patterns across the collection. For example, it's likely that all items will have a title or description field, but only items digitized from films would have information about frame rate or substrate media. Similarly, all digital image files will have a format designation, but only images representing multi-page or complex documents will need page numbers. You're looking for the commonalities, and edge cases can be added later or in an appendix.

For the purposes of beginning the assignment, assume your source data is digitized images, similar to those represented in the "[Free to Use Libraries](https://www.loc.gov/free-to-use/libraries/)" set from the Library of Congress.
See []() for a full discussion of how to pull data from an API (with the loc.gov collections as an example), as well as an overview of what is contained in the JSON response for an item with one corresponding digital image.

% insert full metadata table, e.g., from https://www.loc.gov/resource/rbcmil.scrp7005601/?sp=1&__cf_chl_tk=RPQTylaRowAbxsbf3S1zQ2Od8iITcsWAwgiR5.E8b_Q-1790893816-1.0.1.1-jWI5QfZoSC2ZzWxOtZfnX.HE0bbbLCAsJ_Mq_yp1G_k

Questions will undoubtedly arise as you are working with the data. Feel free to use the shared slack channel to pose questions as you're working.

### Term table template

You already developed a crosswalking approach while recording the descriptive information (metadata) for your small digital collection (see [](/labs/lab-04-artisanal-metadata.md)).
Now, your task is to document the decisions that you made in that process.
Each resulting field in your target site should be illustrated with a table that includes information about what it is, where it came from, and what it does in the new collection site. See [](#table-map-term-template) for a template. (In the previous lab, you worked with CollectionBuilder, but this should also be possible to adapt to Omeka S, or any other collections platform.)

:::{table} A MAP term table template describing the information that should be included for each term for each element in the collection.
:label: table-map-term-template

| Table Label | Is this value required? | Description of what's in the field |
| ---- | -- | ------ |
| Element Name [in My Collection] | Required | The label that will appear when the information is displayed on the collection site; this should effectively be the "title" of your table as well |
| Source collection element | Optional | The label that was used by the source collection (note: may be the same as or very similar to the element name in your site); this field should include a specific notation of how to find the information in response retrieved from the source collection (likely a JSON object, though may be in other formats) |
| Label [in My New Collection] | Required | How the data will be labelled or described in your new collection |
| Element with Namespace [in My New Collection] | Required | The namespace and term of the element, corresponding to the value in the new collection |
| Description | Required | A plain-language explanation of the what this element describes in your collection site |
| Required? | Required | Explain if the field is required, recommended, or optional |
| Repeatable? | Required | Explain whether this field may occur more than once (Yes), or only once (No), in the description of the item |
| Entry Rules | Optional | Explain if there are any rules that constrain how the data is formatted (such as, it is a string or a number), or if there are any external standards like a controlled vocabulary the field should follow |
| Data Type | Required | The most basic information here is whether this is a literal (a string) or a structured entry (often a URL or other identifier), though you can be more expansive if there is a specific datatype you need |
| Notes | Optional | Any notes about what the field contains, how it is created from the source data, any conventions (e.g., name order), or other information about the field that you consider to be useful |
| Example(s) | Required | Provide an example of what the field might contain |
| Source scheme/mapping | Optional | Most terms that you choose to include should correspond to an existing element in Dublin Core, MODS, or another standard scheme |

:::

### Sample term table

Taking as an example the date fields noted above, a sample MAP entry of the first type might look something like the table below (see [](#table-map-term-example)).

:::{table} Sample MAP table for a metadata field called `date`.
:label: table-map-term-example

| **Element Name** | **Date** |
| --- | ------ |
| Source | Descriptive metadata for item JSON at loc.gov.
| Label in My New Collection | Date of Creation |
| Element Name in My New Collection | dcterms:date |
| Description | This is a date extracted from the LOC's original metadata, which indicates when the original resource was scanned or digitized |
| Required? | No. Optional, but unless no date was provided in original item, this is strongly encouraged |
| Repeatable? | No |
| Entry Rules | Use ISO-8601 Date formatting; format should be `YYYY`, `YYYY-MM`, or `YYYY-MM-DD` |
| Data Type | literal (a plain string value with ISO-8601 formatting) |
| Example Entry | 1916 |
| Source (LOC) Attribute Name | date |
| DC Mapping | dcterms:date |

:::

## Researching metadata schemes

To the extent possible, your destination fields should come from standardized (or at least known) chosen from extant metadata schemes, which you predict will be useful in your new digital collection presentation platform. A large majority of these can come from Dublin Core, but you will find that DublinCore does not have the granularity to accurately describe many of the terms you'll want to use. You should therefore investigate fields from at least one other scheme.

Here are some additional schemes to consider, with links to their description and documentation:

- [DublinCore Terms](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/) ([Wikipedia](wiki:Dublin_Core))
- [MODS](http://www.loc.gov/standards/mods/) ([Metadata Standards Catalog entry](https://rdamsc.bath.ac.uk/msc/m97), [Wikipedia](wiki:Metadata_Object_Description_Schema))
- The *schema.org* ontologies ([download ontology files here](https://schema.org/docs/developers.html), [Wikipedia](wiki:Schema.org))
- [Nomenclature](https://page.nomenclature.info/apropos-about.app?lang=en) for Museum Cataloging (indexed within Omeka S Value Suggest module, [ISKO article](https://www.isko.org/cyclo/nomenclature))
- [LIDO](https://cidoc.mini.icom.museum/working-groups/lido/lido-overview/lido-schema/) (Metadata Standards Catalog, [Wikipedia](wiki:LIDO))
- [CCO (Cataloging Cultural Objects)](https://www.vraweb.org/cco) ([Wikipedia](wiki:Visual_Resources_Association#Cataloguing_Cultural_Objects_(CCO)))

An additional resource that may be of use in researching schemes and other metadata fields
is the [Linked Open Vocabularies (LOV) database](https://lov.linkeddata.es/dataset/lov),
which provides a search interface for metadata schemes,
but also provides the capacity to search across term/field names. This does not include all
schemes, but it does include most that are used in cultural heritage and are also represented
in a formal schema definition or ontology. The term search can be found directly at <https://lov.linkeddata.es/dataset/lov/terms>.

## Metadata crosswalking resources

- Mary S. Woodley, “Metadata Matters: Connecting People and Information,” in _Introduction to Metadata_, ed. and rev. Murtha Baca, 3rd edition (Getty Publications, 2016), available at [https://www.getty.edu/publications/intrometadata/metadata-matters/](https://www.getty.edu/publications/intrometadata/metadata-matters/).  
- Digital Library Federation Metadata Application Profile Clearinghouse, available at [https://dlfmetadataassessment.github.io/MetadataSpecsClearinghouse/](https://dlfmetadataassessment.github.io/MetadataSpecsClearinghouse/)
- Dublin Core Metadata Initiative (DCMI), “DC Tabular Application Profiles,” ed. Karen Coyle, online at [https://www.dublincore.org/groups/application-profiles/dctap-primer/](https://www.dublincore.org/groups/application-profiles/dctap-primer/)

## MAP Examples / Templates

You can find some examples of MAPs at the [DLF's MAP "clearinghouse" project](https://dlfmetadataassessment.github.io/MetadataSpecsClearinghouse/).

- For example, the PA Digital Metadata Guidelines 1.2 is a very clear example: [https://dlfmetadataassessment.github.io/assets/maps/PA\_Digital\_Metadata\_Guidelines-v1.2(August\_2018).pdf](https://dlfmetadataassessment.github.io/assets/maps/PA_Digital_Metadata_Guidelines-v1.2(August_2018).pdf).
- Likewise, the Empire State Digital Network Metadata Guidelines: [https://dlfmetadataassessment.github.io/assets/maps/ESDN\_Metadata\_Best\_Practices\_and\_Guidelines.pdf](https://dlfmetadataassessment.github.io/assets/maps/ESDN_Metadata_Best_Practices_and_Guidelines.pdf).  
- Another variation is the TAP, which is intended to be computer processable, which encodes everything as a CSV table, with appropriate namespace prefixes. This is under development by the DCMI TAP project, which provides a useful primer on how to think about this: [https://github.com/dcmi/dctap/blob/main/TAPprimer.md](https://github.com/dcmi/dctap/blob/main/TAPprimer.md). This resource is particularly useful in demonstrating how this information may be placed into a data table, which will be useful for making an actionable crosswalk (the next assignment).

## What to Submit

1. **Your MAP.** It should have an introductory statement providing context about your collection, an alphabetical list of all the terms described (alphabetize by term name), a key (the fields explained for each term), and then a table for each metadata element (including its corresponding title term, source term, and likely target term). Each term table describes the basic rules governing the term's use, equivalence/relationship in Dublin Core (crosswalk), and the name or significance of the term in your goal collection. Begin with the list of terms that you identify from loc.gov, which you want to import to your site, and directions on how to crosswalk them into the scheme that you will use to shape the descriptive metadata that you want to use in your digital collection. Each term table should state what standards the term comes from (DC, MODS, or other). Explain how you are using each term: is it applied at the collection or item level, repeatable, what conventions do you use to transcribe the information, are they human created by hand or created automatically? Etc.
    % For a sample, see the table in the pulling data Jupyter notebook in the course GitHub repo ([link here](https://github.com/morskyjezek/si676-2025-data/blob/main/examples/assignment-transform-1-design-metadata-profile.ipynb)).
    Your MAP should include as many of the data fields as possible from the original data (when you skip items, you should note in the introduction a reason that these were not included, such as that they didn't have useful data, the data was not important for a digital display, or for some other reason). You should have at least 15 fields mapped in your index and corresponding tables for each term in your MAP.  
2. **A short reflection on this process (300-500 words).** How did you find the process of extracting the collection information from loc.gov? What did you learn about crosswalking the information into the fields that you want in your proposed digital collection? Although both the source and your target site should be using standards, did you find the process to be subjective? What sorts of decisions did you make when developing the crosswalk?

### Resources

- [Assignment submission on Canvas](https://umich.instructure.com/courses/858493/assignments/3288741)
- Section TBD
- [Sample MAP Planning (Google Sheet used in class)](https://docs.google.com/spreadsheets/d/1qQvWRJ7Ki_yZx0dLKedljyfyTvp1981VnhxWRW-NrVI/edit?usp=drive_link)

:::{tip} Basics of MAP design and creation
In brief, how can you start a MAP and what should it contain? Begin with a table of terms that you extract from the source collection (loc.gov or other); map out crosswalks from those terms to standard metadata elements that you will use in your collection, determining equivalents or other relationships (in this case, you will likely use mostly Dublin Core and MODS elements, but you may consider others if you like); finally, document the crosswalk with notes explaining the source and target fields, why the target field is the best choice, any considerations (like information that may be lost), and conventions on data encoding. The latter elements will be most useful when building the transformation script.
:::
