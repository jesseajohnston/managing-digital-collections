---
title:  "Assignment 1a: A CollectionBuilder Site and Unique Collection"
categories: assignments web collectionbuilder jekyll
canvas-link:
---

**Assignment Due: October 16, 2026**

This page describes the activities and tasks to complete for the first course assignment: building a static site with a unique digital collection that you have created.
While it's conceivable that you could do this with extreme customization to your first Jekyll site (see [](/labs/lab-03-static-site-jekyll-setup.md)), there's no need to do that! The existing [CollectionBuilder framework](/part01/static-sites-collection-builder.md) was designed for this purpose. So, in this assignment, you will create a new collection site and add your set of digital objects and metadata that you curated in the lab [](/labs/lab-04-artisanal-metadata.md).

## 1. Create a CollectionBuilder Site

First, create a new repository with a clean CollectionBuilder install. The basic process is described in This assignment builds on the CollectionBuilder template site that you created last week.
You should use the site you created in [last week's lab]({{ site.baseurl }}{% post_url 2025-09-18-lab-4-collectionbuilder %}).

## 2. Gather Your Collection

If you didn't already do this in the lab, you will need to gather your metadata, develop an identifier scheme for your digital objects, and gather the objects. If you previously completed the lab, use the five items and the artisanal metadata you gathered in [](/labs/lab-04-artisanal-metadata.md) for this step.

### 2a. Gather Metadata and Decide on an identifier scheme

CollectionBuilder supports standard DublinCore elements for digital objects.
Consult each of the above resources, and complete the metadata entry for each one.
To do this, you may use the [sample CSV template provided in the course data](/data/cb-csv-metadata-template.csv).

To link together the metadata and files comprising the digital objects,
you will need to create a standard naming scheme.
I suggest some combination of letters and numbers, joined together in a standard pattern.
For example, you could use some abbreviation of your collection, an underscore, and an item number, such as `nc_001` where `nc` is "new collection" with an appended iterated number after the underscore.
Another possibility would be to use the LCCN numbers for each object.

### 2b. Find and organize the digital objects

In some cases, the files may not be immediately downloadable.
In others, they will be easy to find.
In either case, you are looking for a high resolution digital image
in a jpeg or tif format. Once you locate the file, save it and rename it
according to the identifier scheme you created above.
Once the file is downloaded and renamed, move it to your site's `objects` directory.
Make sure the file's name matches the `objectid` column in your metadata spreadsheet.

## 3. Add Content to Your CB Collection Site

Now, work locally to ensure that your site works and everything is structured as you want it.
You will need: digital file(s) for each resource, Dublin Core metadata about each, derived from its source, and individual locator information (as [defined by the CollectionBuilder metadata structure](/part01/static-sites-collection-builder.md)).

Your goal is to restructure all of this into information
that CollectionBuilder can use, then republish it on your site.
Work locally to see if everything works.
Ultimately, each item should publish on its own page and look something like [this sample page](https://morskyjezek.github.io/cb-test-turbo-octo-sniffle/items/nc_047.html).
When things look okay, publish your collection using GH Pages.

## Deliverables

- Link to your updated and working CollectionBuilder site,
  now populated with the four items that you created metadata for
  (all still publishing from your GitHub repo)
- Invite the course instructor to collaborate on the repo
- Submit the link via the Canvas Assignment
