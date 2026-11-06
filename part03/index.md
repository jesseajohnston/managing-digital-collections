---
title: "Part 3: Working with Networks"
---

The third part of the book explores basics of networked computing via the Internet,
with a focus on how metadata can be published and shared with APIs.
Additionally, as a worked example

% comment out sub-section TOC - only want to appear on online version
%## Parts in this Section

%:::{toc}
%:context: children
%:::

***TODO List for Section 3:***

- [ ] networks: basics of the networks, protcols for the Internet (TCP/IP & DNS), update an activity for this
- [ ] LAMP stack, as an open software example and also basis for publishing a local site
- [ ] An Example of Open, Networked Library Data: the LOC API - an example,
  - [x] Looking at LOC APi, and OAIPMH (XML-based)
  - [x] Activity: setting up Omeka S
- [ ] Data format: ~JSON, ~using the Omeka S API
- [ ] An activity with RDF and linked data?
- [ ] `apis-04-map-design.ipynb` remaining fixes (2026-11-05):
  - [ ] Sample term table: the Description row says the `date` value is when the resource was "scanned or digitized", but the date walkthrough above it chooses the creation date.
  - [ ] Crosswalk table: in the sample item, `creator`, `source_collection` and `languages` are not present, and `description`, `type`, `rights`, `languages` and `mime_type` sit at the top level of the JSON rather than under `metadata['item']`. Check each row's path.
  - [ ] Two H1 headings follow the front-matter title (`# Designing a Metadata Application Profile`, `# Draft and Design a metadata crosswalk Plan`); decide on the heading levels.
  - [ ] The old `part02/03-metadata-application-profile-design.md` is superseded and not in the TOC; delete it once the merge is reviewed. Its IIIF "Look for Structured Metadata" hint was not merged.
  - [ ] Decide whether this chapter moves to Part 4 (see the location discussion); update `myst.yml` (TOC and PDF export), `labs/project-02-map.md` links, and the plan docs if so.
