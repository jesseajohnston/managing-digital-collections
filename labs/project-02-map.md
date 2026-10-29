---
title: "Project 2: Designing a MAP"
categories: activities assignments metadata map
---

**Assignment Due: October 30**

A **metadata application profile (MAP)** is a technical document that documents and expresses all of the types of items and the descriptive information about them that you plan to collect. It documents where the information comes from (in most cases, these descriptions will be from already extant schemas), how they are used in your local site, what is valid or invalid, whether they are required or not required, and whether they are repeatable.

## Assignment Background and Resources

In this assignment, you will design a MAP for your resource set. Begin planning by using the small set of resources that you chose for your initial site setup in [](/labs/lab-04-artisanal-metadata.md), with the assumption that your larger collection will follow the same models that you are setting now. (Keep in mind that some updating may be required later, as you identify further collection resources.)

The essential requires you to understand and model the metadata you're receiving, then to decide how these fields will be used in your new site. While doing this, you will document the kinds of metadata that already appear in the descriptive metadata, then plan where they should go to display in your digital repository site, preferably within a standard and known metadata scheme (like Dublin Core, MODS, or another). The key is to identify which types of information are used, the granularity and apparent semantics of the metadata, and their relationship to the items. This design must work at the item level, but also apply across the collection. That is, each field documented in your MAP should be documented in a way that is applicable to any resource in the collection. While often described as a Dublin Core application profile (if your site metadata is only Dublin Core), this is a more generic metadata profile for any and all schemes in use. (Additional, but more conceptual, guidelines for designing DublinCore Application Profiles are available from [DublinCore application profile guidelines](https://www.dublincore.org/specifications/dublin-core/profile-guidelines/).)

The MAPs will be similar in form and content, but each person/collection's MAP should be unique, based on the content of the collection. Start by determining the full range of fields associated with your main object types. You can start with one exemplar object, and adapt as further object types are added.

% insert full metadata table, e.g., from https://www.loc.gov/resource/rbcmil.scrp7005601/?sp=1&__cf_chl_tk=RPQTylaRowAbxsbf3S1zQ2Od8iITcsWAwgiR5.E8b_Q-1790893816-1.0.1.1-jWI5QfZoSC2ZzWxOtZfnX.HE0bbbLCAsJ_Mq_yp1G_k

Questions will undoubtedly arise as you are working with the data. Feel free to use the shared slack channel to pose questions as you're working.

## Researching metadata schemes

To the extent possible, your destination fields should come from standardized (or at least known) extant metadata schemes. A large majority of these can come from DublinCore, but you will find that DublinCore does not have the granularity to accurately describe all of the terms in the museum data. You should therefore investigate fields from at least one other scheme.

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

1. **Your MAP.** It should have an introductory statement explaining what it is, an alphabetical list of all the terms described (alphabetize by term name), a key (the fields explained for each term), and then each term listed out individually as a table (or row if you are using the TAP variation). Each term table describes the basic rules governing the term's use, equivalence/relationship in Dublin Core (crosswalk), and the name or significance of the term in your goal collection. Begin with the list of terms that you identify from loc.gov, which you want to import to your site, and directions on how to crosswalk them into the scheme that you will use to shape the descriptive metadata that you want to use in your digital collection. Each term table should state what standards the term comes from (DC, MODS, or other). Explain how you are using each term: is it applied at the collection or item level, repeatable, what conventions do you use to transcribe the information, are they human created by hand or created automatically? Etc. Essentially, begin with a table of terms that you extract from the loc.gov collection, direct equivalents in at least two other metadata schemes (suggested are mostly DublinCore but possibly also MODS, and you can consider others if you like), and notes on why you chose the target field, considerations (like information that may be lost), and any conventions on data encoding.
    % For a sample, see the table in the pulling data Jupyter notebook in the course GitHub repo ([link here](https://github.com/morskyjezek/si676-2025-data/blob/main/examples/assignment-transform-1-design-metadata-profile.ipynb)).
    Your MAP should include as many of the data fields as possible from the original data (when you skip items, you should note in the introduction a reason that these were not included, such as that they didn't have useful data, the data was not important for a digital display, or for some other reason). You should have at least 15 fields mapped in your index and corresponding tables for each term in your MAP.  
2. **A short reflection on this process (300-500 words).** How did you find the process of extracting the collection information from loc.gov? What did you learn about crosswalking the information into the fields that you want in your proposed digital collection? Although both the source and your target site should be using standards, did you find the process to be subjective? What sorts of decisions did you make when developing the crosswalk?

### Resources

- [Assignment submission on Canvas](https://umich.instructure.com/courses/858493/assignments/3288741)
- Section TBD
- [Sample MAP Planning (Google Sheet used in class)](https://docs.google.com/spreadsheets/d/1qQvWRJ7Ki_yZx0dLKedljyfyTvp1981VnhxWRW-NrVI/edit?usp=drive_link)
