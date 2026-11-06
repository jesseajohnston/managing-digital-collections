---
title:  "Project 1b: Setting Up Your Omeka S Installation and a Collection"
---

**Assignment Due: November 20**

In this assignment, you will be working to add sample collection content to a new Omeka S
site on the previously installed instance on your LAMP Server [](/labs/lab-07-omeka-s-setup.md).

## Configuring Your Omeka S Installation

This assignment builds on the Omeka S site that you previously created.
Your site and content should be created in the Omeka S installation from [](/labs/lab-07-omeka-s-setup.md).
To the basic installation you already have, you will complete the site configuration, including:

:::{toc}
:context: section
:::

### 1. Add (Install) Omeka S Modules

In this step, you are adding new Omeka S modules, which will extend Omeka's functionality.
To add modules, follow the steps in [](/part03/servers-omeka-s-add-modules.md).

### 2. Add (Install) Vocabularies

In this step, you are adding a controlled vocabulary to Omeka S. The general idea is similar to adding a module, as it does add functionality, but this step can be completed within Omeka, it does not involve adding new files to your server. To add a vocabulary, follow the steps in [](/part03/servers-omeka-s-add-vocabularies.md).

### 3. Add (Create) a New Site in Omeka S for a Sample Collection

In this step, you will create a new site in your Omeka S install, which will be the home for the sample collection you gathered in Assignment 1a. You can follow the steps outlined in the [Adding an Omeka S Site guide]({{ site.baseurl }}{% post_url 2025-09-25-omeka-s-install-guide %}).

The [sample CSV template for Omeka](/data/omekas-csv-metadata-template.csv) demonstrates how to structure the CSV so it will import into Omeka S.

### 4. Load Sample Collection Content

Use the same collection items that you added to your CollectionBuilder site in Assignment 1a.
To do this, you can reuse the digital objects that you already gathered from the Library of Congress.
That is, use your small collection from [](/labs/lab-04-artisanal-metadata.md). Each item should publish on its own page.

Your task is to restructure all of this into a format that allows you
to load it into Omeka S using the Import CSV module, then republish it on the new Omeka site you created.
Alternatively, you can import the items by copying and pasting the metadata from your existing spreadsheet.

## Written Reflection

The final component of the Assignment 1 is to write a short reflection (300-500 words) about the process of collecting the collection items, and the difference between working with a serverless site (in this case, CollectionBuilder) and the sites on the server you're maintaining (in this case, your Omeka S installation). While you do not have to answer each question, please use the following questions to guide your reflection:

- What perspective on open source software does this give you? Have you changed any of your thoughts about the pros and cons of open source software?
- What steps were the easiest or most difficult? What was most confusing, or most clear?
- Given the work involved, how satisfied are your sites as they stand so far?
- If you have previously used Omeka (as a Software as a Service model), how do you feel about it now that you have had to set everything up (more like a Platform as a Service)?

## Deliverables

- Your Omeka S platform now includes the specified modules and vocabularies
- Link to your new Omeka S site, populated with the four items and their metadata
- Invite the course instructor as a user in your Omeka S site
- Short written reflection (300-500 words)

## Resources

- [](/part03/servers-logging-in.md)
- [](/part03/servers-omeka-s-install.md)
- [](/part03/servers-omeka-s-configuration.md)
- [](/part03/servers-omeka-s-add-modules.md)
- [](/part03/servers-omeka-s-add-vocabularies.md)
