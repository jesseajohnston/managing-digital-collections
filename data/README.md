# Data for _Managing Digital Collections_

_Note: this file was largely created and maintained automatically (by ClaudeAI or similar tools)._

Sample datasets used by the notebooks in this book. Files here are **inputs only** —
anything a notebook writes goes to `output/`, which is not tracked in git.

Datasets are organized by collection rather than by book part, because the same
collection is used in more than one part to show how a single body of metadata looks
in different serializations (CSV, XML, JSON).

See the "Data files" section of the top-level [README](../README.md) for the naming
conventions and for how notebooks should reference these paths.

## Data Samples

### Library of Congress Web Archives (LCWA): sample MODS records

MODS records describing archived websites, used in Part 2 to introduce XML parsing.

| File | Records | Used in |
| --- | --- | --- |
| `lcwa-mods-5.xml` | 5 | Part 2, introductory parsing |
| `lcwa-mods-25.xml` | 25 | Part 2, subject analysis and record modification |

The 5-record file is a subset of the same collection as the 25-record file, kept small
so that printed output stays readable in the book.

<!-- TODO: complete the provenance notes below. -->

- **Source:** TODO — where these records were obtained (collection name, URL, date retrieved).
- **Derivation:** TODO — how the 5- and 25-record subsets were selected from the source set.
- **Rights:** TODO — license or rights statement for redistributing these records here.
- **Modifications:** TODO — note any edits made to the records for teaching purposes, e.g. the
  `<!-- TODO: Insert name authority here -->` placeholders that appear inside some `<subject>`
  elements.

<!--
### `<next-collection>/` — short title

One or two sentences on what the collection is and which part uses it.

| File | Records | Used in |
| --- | --- | --- |

- **Source:**
- **Derivation:**
- **Rights:**
- **Modifications:**
-->
