---
title:  "Project 4: Transform Collection Data (Scripting and Implementing Your MAP)"
---

**Assignment Due: December 4**

The goal of this assignment is to implement the metadata transformation that was implied in your MAP document (see [](/part03/apis-04-map-design.ipynb)). Your task is to develop a batch workflow that will transform from the origin data, apply the rules for destination fields and formatting as established in your MAP, then transform it to a format that you can ingest into Omeka S and CollectionBuilder. It's possible that you may need to make some modifications by hand, but to the extent possible your script tools should automate as much of this process as possible so that the contents display in the new platforms as clearly and accurately as possible. The deliverables for this assignment are the Python script that accomplishes the transformation and the resulting CSV, JSON, or other files that your workflow generates. At this point, you will have all of the steps needed for importing the objects successfully into your site. In other words, your script(s) will pull data from the original metadata, transform that data, and you will be ready to batch upload the objects from a CSV or API.

:::{hint} Omeka S Tip
Create an item set for the import. This will make it easier to identify the materials from a specific import batch later, in case you need to isolate the batch or redo the import.
:::

## Deliverables

1. The script(s) that extracts & transforms the original data from UMMAA. For this part, you can turn in a `.py` or `.ipynb`.
2. The script outputs (that is, the transformed data likely in CSV or JSON).

Submit the assignment on Canvs. 

## Resources

- [](/part04/present-transform-metadata.ipynb)
