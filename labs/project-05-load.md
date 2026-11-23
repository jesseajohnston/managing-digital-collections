---
title:  "Project 5: Load Set (Metadata & Content) into Two New Presentation Sites"
categories: activities assignments metadata python csv collection load
canvas-link: https://umich.instructure.com/courses/779862/assignments/2943873
published: true
---

**Assignment Due: December 11**

The final step of the assignment is structured around the load process (aka, *ingest*),
which completes the ETL workflow. The goal of the assignment is to create as a collection that is as complete as possible given the resources that you identified in your source collection.
The resources should be presented in both Omeka S and CollectionBuilder.

There will be a few distinct steps, including:

- preparing resource metadata for load,
- preparing the digital content (gathering and ingesting images), and
- quality control.

### Resource Metadata (CSV/JSON implementation of your MAP)

You will need to ensure that your metadata transformation workflow is implementing your map correctly. Note that you may need to work out some string transformation (formatting) to output each metadata field as you need it to appear in each presentation. If you use CSV as your ingest format, a relatively small number of changes should be required to modify your transformation from [](/labs/project-04-transform.md); if you use the Omeka S API and CollectionBuilder, there will be more significant differences.

### Digital Content (Images of as many objects as possible)

One challenge of this load step will be to prepare digital content (in most cases, largely images) for ingest, and then to load the content.
You will need to identify a way to match image files to the metadata records corresponding to that object, so in the presentation they will be linked together.
This should be possible by matching the object ID to the matching ID in the image file.

One new case that you may need to address is that multiple digital images may correspond
to one metadata record. Both Omeka S and CollectionBuilder can handle this case.
In Omeka S, you can ingest multiple files per item if you us the API,
or you can ingest images and match them individually to metadata records.
In CollectionBuilder, additional images are appended into the site data
records, without a new collection ID, [as described in the documentation for Compound Objects](https://collectionbuilder.github.io/cb-docs/docs/metadata/compound-objects/).

### Quality Control

You should have a basic way to check on your workflow's performance.
To do this, something along the lines of the "mini LOG" outputs of the transform step
would be sufficient. You should have a report that can show:

- how many resources you hoped to gather (in your Extract & Transform steps),
- how many resources you actually gathered (how many you plan to Load),
- how many resource files you identified (in the above steps),
- how many resource files were actually ingested.

These can be helpful indicators that you can use to track the process, or improve it later.
They can also be useful metrics in determining if process was successful, or how successful it was.

## Deliverables

1. The CSV or JSON file(s) that you use to load resources to your site.
2. The link to the site with metadata and resources loaded.
3. A quality control report (should be a text file or table, CSV or Excel).

Submit the assignment on Canvas.
