---
title: "Lab 04: Gather Five Collection Items"
---

In this lab, you will create "artisanal metadata" for five collection items.
These items will be reused in your initial CB sites and Omeka sites.

## Process

The basic concept is that you are going to select five (5) digital
resources, which will be the source of an initial sample collection.
This sample collection is one you will use to design a metadata profile,
initiate metadata transformations, and create an ingest process for multiple
collection platforms.
You aren't required to work with these for the final project,
so they don't need to be things you feel deeply attached to or interested in.

### Select Resources

First, you need to identify five items to include in your digital collection.
These items will be samples, and so they should be selected from items that are already in other collections.
Although it is your choice as the creator, I would suggest choosing a subset of an existing collection,
such as five things from the ["Free to Use Libraries" set from the Library of Congress](https://www.loc.gov/free-to-use/libraries/). These items are useful since they are high quality digital objects, they have complete metadata, and they are rights free (meaning that there is no copyright or intellectual property concern to reuse them).
If you'd prefer to use other digital samples, consult the [sample digital collections page](/teaching/digital-collections-of-interest.md); if you'd prefer to use something else, please notify the instructor first.

### Design and Choose an Identifer Scheme

As you choose digital objects, you should also consider an identifier scheme.
You will need a unique identifier that can apply to and differentiate between your logical collection items. That is, there should be an identifiable name for each "thing" in your collection. Your identifier scheme design is up to you,
but make sure it is something that is unique for the items and can also be included in a filename. You may keep the names from the source repository, but if they are generic, like `download.jpg`, then name them with a unique identifier.
For example you might choose `sample_001` for your first resource,
and it might be represented by `sample_001.jpg` in the file, while the metadata
is identifiable in your metadata spreadsheet on the line that begins with `sample_001`.

### Collect Digital Objects

Next, "collect" your digital items.
Create a folder named `lab_04` (or along those lines).
Once you identify an item, save a copy from the source collection in
your SI 676 github repo folder. You should have at least five digital files
that represent your digital object. For the purposes of simplicity,
the demo at this point assumes each resource has one file.

:::{tip} Complex Digital Objects (Objects with Multiple Files)
Keep in mind that many digital objects are comprised of multiple files.
So, you may have more than five individual files.
If you choose a resource that has multiple files,
make sure that you name each with a related identifier.

For example, if you are collecting `sample_001`, and it is a digitized
representation of a three-page flyer, you might name the files `sample_001a.jpg`, `sample_001b.jpg`, and `sample_001c.jpg`. The names thus suggest that they are related by the unique identifier, while the sequence of files is represented by `a`, `b`, and `c`.
:::

### Gather Metadata

Next, you need to gather the metadata for these resources.
Each item should have a complete set of descriptive information,
which for CollectionBuilder will be largely DublinCore fields.
Use the provided metadata template (see below [](#cb-csv-metadata-template)).

For example, imagine you had collected the digitized image of the first page of the
_Votes for Women Broadside_, published March 4, 1911, shown at <https://www.loc.gov/resource/rbcmil.scrp7005601/>.
As you collected the digital object, you gave it the identifier `nc_001` and named the saved file `nc_001.jpg`.
Then, using the Library of Congress's existing metadata, you filled in each of the
suggested DublinCore fields.
Note that CollectionBuilder also requests a few options beyond DublinCore (see [](/part01/static-sites-collection-builder.md#item-metadata)).
For now, the most important one is `object_location` which is required
and must include the correct path to the digital object.
For now, use your repo path, meaning that if my repo was named `SI_676`, my digital object path would be `/SI-676/lab_04/nc_001.jpg`. This path must be exact in the metadata spreadsheet (it won't matter for your gathering activity, but it will matter when you want to publish your CB site).

```{literalinclude} ./data/cb-csv-metadata-template.csv
:label: cb-csv-metadata-template

```

## Lab 4: Deliverables

- A CSV with the metadata for your resources
- Digital objects (files) corresponding to your resources
- Submit all by uploading to your course github repo in a folder titled `lab_04` (or along these lines), provide the URL via the Canvas assignment
