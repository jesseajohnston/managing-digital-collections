---
title:  "Project: Setting Up CollectionBuilder"
---

This task, which comprises Assignment 1, builds on last week's: you are setting up a Jekyll site,
but this time you will use an existing site structure and framework called CollectionBuilder (CB).
There will be a few large steps (each with multiple substeps):

1. Copy the CollectionBuilder files into a repo that you control. This assignment follows the steps in the "CSV" flavor of CB because you will be adding data using a CSV file. The source repo is at <https://github.com/CollectionBuilder/collectionbuilder-csv>.
2. Configure your CB site, and ensure it is up and running locally as well as via a GH Pages endpoint.
3. Collect and add your collection items. This is "by hand," which will demonstrate the need for more efficient batch processes later on.

## 1. Setting Up CB

First, you will need to set up a new repo that's running CollectionBuilder.
This is done with a GitHub "fork," or creating a new version of a repo that runs in your
GitHub space, but has the same files as the previous one. While your repo can track the original GH
repo, changes there will no longer affect your repo. For our purposes, this should be no problem, although
in a development environment where you need to make updates, this can add a layer of complexity, particularly if your site is highly customized beyond the original platform.

## 2. Configuring CB

When you create the new site, name it something to indicate it is temporary, such as `collection-builder-test` or `demo-collection`).
Make sure it's publishing (with Jekyll) via GitHub Pages.

Finally, configure the CollectionBuilder platform.
To do this, follow the instructions at CollectionBuilder: [CSV Walkthrough](https://collectionbuilder.github.io/cb-docs/docs/walkthroughs/csv-walkthrough/).

Once set up, make basic modifications to your site, as you did with your previous Jekyll site (most of these can be changed in the `_config.yml` file):

- Give your site an original name
- Selecting an alternative featured image (what appears on the main page behind the site title)
- Modify the text on the "About" page (note that in the CB Builder framework, all of the top-level pages are in a folder called `pages`) and you should see some markup text there already as a placeholder (remove that text and add in something of your own)

## Adding Collection Items

This is a complex step. First, you need to identify the five items you want to include.
Although it is your choice as the creator, I would suggest choosing a subset of an existing collection,
such as five things from the ["Free to Use Libraries" set from the Library of Congress](https://www.loc.gov/free-to-use/libraries/).

## Notes

- **Keep your thinking hats on.** There are a few steps in the CB guide that you won't need to follow exactly (for example, you don't need to sign up for a GitHub account, you already have that). Your goal is a working site, the instructions give you the steps to get there, but there may still be some specific issues you will need to address for your site.
- **Some Errors or Notes** If you see any errors about missing packages or helpers, note that you should not need ImageMagick or GhostScript at this point, unless you want to experiment with adding objects and metadata of your own.

## Lab 4: Deliverables

- A CSV with the metadata for your items
- Digital images corresponding to your items
- Submit both by uploading to your course github repo in a folder titled `lab-04`, provide the URL via the Canvas assignment

## Project Deliverables

- Link to a published, and working CollectionBuilder site, using the sample content from CB, publishing from a GitHub owned by your account, and the corresponding GH repository.
- Invite the course instructor to collaborate on the repo
