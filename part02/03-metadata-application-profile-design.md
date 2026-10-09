---
title: Designing and Drafting a Metadata Application Profile
---

This section provides information about
how to design your metadata application profile (MAP),
which is the task of [](/labs/project-02-map.md). Although it is not the first step in the [ETL process](TODO), the design of the metadata transformation is one of the most important parts of the process. Since it is a design step, rather than an implementation process, it is a good place to start.

Keep in mind that this kind of work to transform or restructure the metadata
is a basic step that you might encounter in different forms in many workflows
that involve moving resources from one place to another. This step may often be
called by other names, including data transformation, data wrangling, data cleaning,
data normalization, data modeling, or even something else. Whatever you call it, this is a fundamental
process in many digital curation activities. One of the "value adds" that you
can bring as a digital curator (whatever your title) is in providing guidance,
expertise, and structure for planning and documenting data transformations.

:::{important} Learning Objectives

After completing this section and the associated assignment, you should:

- Be able to explain the concept of metadata extraction and transformation.
- Design and plan a structure for documenting metadata practices in a collection or repository, also known as a Metadata Application Profile (MAP).
- Understand the role of the MAP in planning and creating ingest-ready (loadable) collection metadata that conforms to Dublin Core and other digital collection metadata standards, which can be used to load content into a collection platform.
:::

## Designing a MAP

The larger transformation step has many substeps, including: working with and testing your process with a small sample, developing a conceptual model for your transformation (ultimately expressed in a Metadata Application Profile and a crosswalk), testing the implementation with a larger sample, designing an implementation process, then running your transformation on the entire set.

This section focuses on the conceptual model and design step. While the end goals of the design process are a MAP document and implementable metadata crosswalk, it's best to start with an exploratory activity. This allows you to take some time examining the structure and description of one or two sample resources. In the project, the target goal is to transform the existing metadata into consistent and regular Dublin Core and MODS terms. So start by examining your small collection (gathered in [](/labs/lab-04-artisanal-metadata.md)), and identify the attributes that you will need in your new collection platform. The goal is to identify the information that you want to display there, as well as information that you may need to track or manage collection resources.
(In the exercise, you are planning to publish these in CollectionBuilder and Omeka S.)
Beginning with the most complete metadata that you can find (you will likely be working with XML or JSON),
the basic task is to document what fields exist, what they represent, and what their destinations will be in the new collection.
At this point, the work is largely conceptual and does not require any programming or implementation tools.
Even so, the design work is critical as a plan for the overall transformation process.

### Draft and Design a metadata crosswalk

The following does not outline a complete design, but it should give you an idea
of how to proceed. While many MAPs have more fields, the project asks you to identify 10&ndash;15 fields
that you will transform for your new site.
Most of these will be DublinCore terms, but you must also choose at least one field
from another scheme.
The best candidate for the collections under review in the project are terms from the MODS scheme (if your collection has bibliographic items), potentially VRA (if your collection has visual items), or PBCore (if you have audiovisual items). Any of the specialized schemes offer more granularity than DublinCore, and they can be supported in Omeka S (though not necessarily in CollectionBuilder without significant additional add-ons).

## Identify Fields to Keep or Transform

In the drafting process, you need to look closely at the metadata from which you gathered
[your collection items](/labs/lab-04-artisanal-metadata.md).

:::{hint} Look for Structured Metadata to Examine
Your python skills will be useful to investigate the source metadata.
If you gathered JSON data from the Library of Congress's "Free to Use" collections, you will be able to find a metadata manifest. Other collections may publish collection data in IIIF manifests, or other standard structures.
:::

### Examining the Source Data

In the LOC basic JSON, you will find most of the information you're looking
for in the `item` element of the item JSON files.
After importing JSON, you can examine the data with a process like that illustrated in @ex-python-lc-json-output.

```{code} python
:label: ex-python-lc-json-output
:caption: Using Python's built-in JSON module to read and examine LOC's metadata for a digitized historical photographic print of the Carnegie Library in Cordele, Georgia at <https://www.loc.gov/item/91787443/>
import json
from pathlib import Path

python
# read in a sample file
with open(Path.join('..','collection-site-materials','item-metadata','item_metadata-cph.3b41963.json'), encoding='utf-8') as file:
    metadata = json.load(file)

# check if it's there
print(json.dumps(metadata, indent=2)[:100])
```

% add output

Next, you can look at particular keys and elements of the data. For example, @ex-python-lc-json-item-extract

```{code} python
:label: ex-python-lc-json-item-extract
:caption: Focusing on the `item` key in the data
# now take a look at the "item" key

for attribute in metadata['item'].items():
    print(attribute[0], ':\t', attribute[1])
```

    call_number :	 SSF - Libraries--Georgia--Cordele <item> [P&P]
    control_number :	 91787443
    created :	 2016-04-21T09:17:00Z
    created_published :	 [ca. 1916]
    created_published_date :	 [ca. 1916]
    date :	 [ca. 1916]
    digital_id :	 ['cph 3b41963 //hdl.loc.gov/loc.pnp/cph.3b41963']
    display_offsite :	 True
    format :	 ['still image']
    formats :	 [{'link': 'https://www.loc.gov/pictures/related/?fi=format&q=Photographic%20prints--1910-1920.&co=cph', 'title': 'Photographic prints--1910-1920.'}]
    genre :	 ['Photographic prints--1910-1920']
    id :	 91787443
    link :	 https://www.loc.gov/pictures/item/91787443/
    location :	 ['Georgia--Cordele']
    marc :	 https://www.loc.gov/pictures/item/91787443/marc/
    medium :	 ['1 photographic print.']
    medium_brief :	 1 photographic print.
    mediums :	 ['1 photographic print.']
    modified :	 2016-04-21T09:17:00Z
    notes :	 ['At bottom right of photo: "Cordele Book Co."', 'Wittemann Collection.']
    number_former_id :	 ['https://www.loc.gov/item/91787443', 'https://www.loc.gov/item/11583075']
    other_control_numbers :	 ['11583075']
    place :	 [{'latitude': '', 'link': 'https://www.loc.gov/pictures/related/?fi=place&q=Georgia--Cordele&co=cph', 'longitude': '', 'title': 'Georgia--Cordele'}]
    reproduction_number :	 LC-USZ62-95830 (b&w film copy neg.)
    resource_links :	 ['//hdl.loc.gov/loc.pnp/cph.3b41963']
    rights_advisory :	 No known restrictions on publication.
    rights_information :	 No known restrictions on publication.
    service_low :	 https://tile.loc.gov/storage-services/service/pnp/cph/3b40000/3b41000/3b41900/3b41963_150px.jpg
    service_medium :	 https://tile.loc.gov/storage-services/service/pnp/cph/3b40000/3b41000/3b41900/3b41963r.jpg
    sort_date :	 1916
    source_created :	 1991-08-22T00:00:00Z
    source_modified :	 2012-06-14T21:04:56Z
    subject_headings :	 ['Libraries--Georgia--Cordele--1910-1920.', 'Georgia--Cordele']
    subjects :	 ['Libraries--Georgia--Cordele--1910-1920']
    summary :	 Photo shows a group of children posed on and in front of steps, roof and dome draped with stars and stripes banners. A Carnegie grant for $10,000 in 1903 funded this building, with an  additional $7,556 in 1916 for remodeling. Still used as a public library.
    thumb_gallery :	 https://tile.loc.gov/storage-services/service/pnp/cph/3b40000/3b41000/3b41900/3b41963_150px.jpg
    title :	 Carnegie Library, Cordele, Georgia



```python
# for reusability, you may want to write this to a file

metadata_fields_file = join('..','collection-site-materials','metadata_fields.txt')

with open(metadata_fields_file, 'w') as f:
    f.write('attribute\tvalue\n')
    for attribute in metadata['item'].items():
        f.write(str(attribute[0]) + '\t' + str(attribute[1]) + '\n')
```

The above will create a tab-delimited file (aka `.tsv`, like a CSV).
You can view it in VSCode as a plain text file, or
you can open it in a spreadsheet application like Excel or Sheets.

Use that export to start your MAP list. Exploring the data a bit will
help you understand the data and develop a transformation plan. For example,
the cells below demonstrate how I looked into the date fields and decided what
information was best to keep and how to map it.
From looking at the previous list exported to the TXT file, I knew that fields with `date` and `created` in their field names were likely to have related information:


```python
for attribute in metadata.keys():
    if 'created' in attribute:
        print(attribute)
```

    created
    created_published
    created_published_date
    source_created



```python
for attribute in metadata.keys():
    if 'date' in attribute:
        print(attribute)
```

    created_published_date
    date
    dates
    sort_date



```python
created = metadata['created']
date = metadata['date']
created_published_date = metadata['created_published_date']
source_created = metadata['source_created']
dates = metadata['dates']

print(created)
print(date)
print(created_published_date)
print(source_created)
print(dates)
```

    2016-04-21T09:17:00Z
    1916-01-01
    [ca. 1916]
    1991-08-22T00:00:00Z
    [{'1916': 'https://www.loc.gov/search/?dates=1916/1916&fo=json'}]


It's clear that the 1991 and 2006 dates refer to some collection management action.
Look into that another time. The 1916 dates are of most interest.
So in this case, the `created_published_date` is most useful.
It also maps cleanly to DublinCore's [created](http://purl.org/dc/terms/created) term.
It's possible that not all of the items has this field, so I would also focus on the `date` field.

Thus, you can start building up your data structure:


```python
item_data = {
    'date': metadata['date'],
    'created': metadata['created_published_date']
}

print(item_data)
```

    {'date': '1916-01-01', 'created': '[ca. 1916]'}


## Documenting your decisions

For each field that you select to crosswalk into your new collection,
you will need to create a MAP entry for each metadata element you choose. 

For each element, you will make two MAP entries: 

1. List the term in the MAP table (see example below, or look at the samples linked in the assignment).
2. Create a row in the DCTAP profile.

For the most part, these are the same information. The first is intended for human readers,
while the second is intended for "machine" readability.

Taking as an example the date fields noted above, a sample MAP entry of the first type might look something like this:

| Element Name | date |
| --- | ------ |
| Label in My New Collection | Date of Creation |
| Mapping for My New Collection | dcterms:date |
| Description | This is a date extracted from the LOC's original metadata, which indicates when the original resource was scanned or digitized |
| Required? | No. Optional, but unless no date was provided in original item, this is strongly encouraged |
| Repeatable? | No |
| Entry Rules | Use ISO-8601 Date formatting * format should be YYYY, YYYY-MM, or YYYY-MM-DD |
| Data Type | literal (a plain string value with ISO-8601 formatting) |
| Example Entry | 1916 |
| Source (LOC) Attribute Name | date |
| DC Mapping | dcterms:date |


A DCTAP row for this might look as follows:

```csv
shapeID,shapeLabel,propertyID,propertyLabel,mandatory,repeatable,valueNodeType,valueDataType,valueConstraint,valueConstraintType,valueShape,note
       ,          ,dcterms:title,Title,TRUE,FALSE,literal,xsd:string,,,,
       ,           ,dcterms:date,Date,FALSE,FALSE,literal,xsd:date,,,,
```

## Developing your crosswalking implementation script

This is actually in preparation for Assignment 4 (your transformation script),
but in practice and concept these two steps are linked.

Simultaneously, start to make notes about how you will map the original fields
to the destinations for your new collection sites.
A good way to do this is to start a spreadsheet file, which you could base on the previously exported TSV file.
Or, you can [use a template like this one designed in Google Sheets for the course](https://docs.google.com/spreadsheets/d/1m2nq-PInOIN1GTRKRVGtKtc5qI0DTojw6waMe5hVzMc/edit?usp=sharing).

In looking through these files, you will not find the exact matches for each data element in the JSON,
but you should find clear parallels between the source data, DublinCore, and/or MODS.
Your goal should be to crosswalk as much as possible from the items
into your new collection presentation sites.

Here's a draft table to start the process:


| source field name | source field path/dict name | target | target namespace | notes |
| --- | --- | --- | --- | --- |
| title | item['title'] | dc:title | DCTerms | Title provided by the orginal metadata, could also be mapped to MODS:titleInfo:title or other fields in other namespaces | 
| date | item['date'] | dc:date | DCTerms | This is a 4-digit year, corresponds to date of creation in most cases |
| LC control number | item['item']['control_number'] | dc:identifier @type=lccn | DC Element with attribute | Corresponds to the Library of Congress Control Number |
| creator | item['creator'] | dc:creator | DCTerms | Should be a name. May be repeated. If possible, are various roles needed? Such as 'photographer', 'author', etc. |
| description | item['description'] \/ item['summary'] | mods:physicaldescription | MODS | In the source data, this seems most like physical description, although it might correspond to dc:format or dc:type. Content in the record may come from a controlled vocabulary, such as LC Genre & Form Thesaurus. |
| format, physical | item['type'] | mods:physicalDescription:form | MODS | Description of the original physical format of this item \(photograph, book, poster\). _Note:_ this may not be present or in the same place for the different types of objects in the collection |
| format | item['format'] | dc:format | DCTerms | The basic type of the digital surrogate \(e.g., 'image' or 'text'\) |
| notes (may be multiple) | item['notes'] (array) | dcterms:abstract | DC Terms | This appears to be closest to a "summary" or description of the content of the items. |
| subject_heading | | mods:subject | mods | |
| source_collection | | | | |
| rights | | | | |
| place | | | | |
| languages | | | | |
| mime_type | | | DCTerms | |

**Note:** this table does not include information about the digital assets,
it's only about the descriptive metadata.
