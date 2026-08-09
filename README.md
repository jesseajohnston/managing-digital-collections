# Managing Digital Collections

This repo contains the base files for generating the
textbook _Managing Digital Collections_.
The book is intended as a practical, project-oriented primer
for people interested in learning about management of digital content in cultural heritage collections.
Thus, the text is written with the assumption that readers and users are working in, or interested in libraries, archives, museums, or other organizations that focus on collections.
In addition, the text assumes a functional level of knowledge about using
programmatic digital tools, including the Python programming language,
text-based command line interface, and other system-level tools that
facilitate the bulk and batch management of digital content in small-
and medium-sized collections.

The project was initially created to support a course of the same name
at the University of Michigan School of Information in fall 2026.

## Platform

The project has been built to publish an ebook using the MyST document
engine platform. The site is published using GitHub.

## Creating and Styling Text

### Callouts

There are a variety of callout styles, which are [described here at the MyST documentation](https://mystmd.org/guide/admonitions). Primarily `seealso` and `important`, or `caution` may be used.

These should be used not just for callouts, but also for referencing associated assignment content.
For example:

```
:::{seealso} Try it yourself
Practice these concepts in [](labs/lab-01-example.md)
:::
```

The above will pull the lab title and autopopulate the link. This is an inviting way to integrate the assignments, and all of the assignment information will be located in the lab section at the end.

Discussion questions or aside blocks may use `{hint}` (light bulb icon, green).

Activities/tasks/lab boxes may use `{tip}` (pencil on paper icon, green)

Chapters should also open with two standard callouts, in this order: `{important}` (lightning bolt, blue) for Learning Outcomes and `{attention}` (megaphone, orange) for Dependencies (tools/libraries used in that chapter) or `{note}` (info, blue) for skills you will need. For example:

```
:::{important} Learning Outcomes
- Bullet 1
- Bullet 2
:::

:::{attention} Dependencies
Tools/libraries used in this chapter: `lxml`, `requests`.
:::

:::{note} Skills You Need in this Section
Assumptions or skills needed in a section, like "Using Jupyter Notebooks"
:::
```

### Providing Code exercises and Code Solutions

Metadata can be added to individual notebook cells to control how they display, which is useful for demonstration purposes and teaching.
Display of these differs between the HTML display and the PDF display.
Additionally, the exercise/solution admonition available in MyST can be useful.

#### Code exercises

The admonitions pair `{exercise}` and `{solution}`
can be added to notebooks in markdown cells.
In these pairs, the `:label: ` tag of the exercise should match the
title of the solution exactly.
These will then be numbered consecutively.
The display of solution can also be modified to be expandable by
applying a `drowpdown` class.

A sample pair:

```
:::{exercise}
:label: ex-count-xml

Exercise content
:::
```

And corresponding solution:

```
:::{solution} ex-count-xml

Solution content
:::
```

#### Code Display (for examples and/or solutions)

In Jupyter notebook files, individual cells can be hidden or toggled to open and close using cell-specific tags. At the draft stage, fully built out code cells that illustrate exercises are given the `hide-cell` tag, which makes the cell expandable in the HTML display, and it hides the cell from the pdf generation.

Code output from a cell can be hidden by using the `hide-output` tag to a cell. This will then display as an expandable element in the HTML display, or be hidden in the generated pdf.

### Citations

Citations should be recorded in bibtex format, and entered in `references.bib`. Conventions and fields available for bibtex
can be searched at <https://www.bibtex.com/e/entry-types/>.

Citations and footnotes follow the [styles set out in pandoc](https://pandoc.org/MANUAL.html#citation-syntax).

In text citations can be referenced using MyST patterns, generally
including an @authordate reference in square brackets. More details on this usage in MyST can be found at the [MyST citation page](https://mystmd.org/guide/citations#markdown-citations).

### Publication Date (Typst PDF Cover)

The Typst PDF template (`templates/plain_typst_book_custom`) shows two separate dates on the cover, both driven by fields in `myst.yml`:

- **Edition line** (rendered near the authors' names): set by the top-level `project.edition` field (e.g. `edition: August 2026 edition`), used verbatim. If `edition` isn't set, it falls back to `project.date` (currently commented out at `myst.yml:11`), formatted as "[month] [year]" — set it to a full date, e.g. `date: 2026-07-29`.
- **Preferred Citation block**: set by `project.venue.date` (`myst.yml:16`, currently `"2026"`). Update this string to change the year/date shown in the citation.

## Data Files

Sample data, which is used in various activities throughout the book, live in a single, top-level `data/` folder:

```
data/
  README.md            # index of datasets, with provenance for each
  lcwa-mods-5.xml      # file names include a collection or identifier to show useful groupings
  lcwa-mods-25.xml
output/                # anything the notebooks write; gitignored
```

Under the main folder, data files are grouped by the source or data type, not according to the book's structure.
Several data elements are used or reused at different points
in the book.
Likewise, some data is used in different
serializations at various times.
The structure is designed to group similar data together to show their relatedness.

### Naming Data Files

Use lowercase, hyphenated names of the form `source-schema-count.ext`, for example
`lcwa-mods-25.xml`. Avoid embedding acquisition years or schema names in capitals; the
provenance and context information about the data belongs in `data/README.md`, which explains the data in more detail.

Every new data file should be listed in [`data/README.md`](data/README.md). The list, which is updated with automation tools, records data
source, how any subset was derived, any notable rights information, and any modifications made for
teaching.
This documentation about the data provenance is not just
a management detail. This book is about metadata management,
and data documentation is an essential practice, using an approach like that demonstrated in the data README files.

### Referencing data from notebooks

The book uses Jupyter notebooks to demonstrate code and data manipulation. Since book content lives one level below the repository root (e.g. `part02/`), executable notebooks reach up and over to the the data folder with `..`.
Each notebook thus contains a setup cell (this is visible in downloaded notebooks, but it is hidden in the web version and in the pdf version), which builds a file path structure to correctly reference the sample data:

```python
from pathlib import Path

DATA = Path('..', 'data')
OUT = Path('..', 'output')

MODS_collection = DATA / 'lcwa-mods-5.xml'
```

Using `pathlib` rather than string concatenation keeps the notebooks portable across
operating systems, and gives one place to update if the layout changes.

Note that this assumes notebooks are executed with the working directory set to the
notebook's own folder. That holds when running a notebook in Jupyter from within its
part folder. If notebooks are later executed as part of the MyST build, confirm the
working directory before relying on the relative paths.

### Inputs and outputs

`data/` holds inputs only, and files there should not be modified by a notebook. Anything
a notebook writes — updated records, exports, intermediate files — goes to `output/`,
which is gitignored so that re-running the notebooks does not produce spurious changes.
If the text needs to refer to a specific generated file, save a copy into `data/` under a
descriptive name and treat it as an input from then on.

### Size

Keep sample files small enough to commit directly to git; a few hundred kilobytes per
dataset is fine, and smaller files also keep printed output readable in the book. If a
dataset grows beyond a few megabytes, download it at runtime in a setup cell instead of
committing it. Avoid Git LFS, which adds a setup step for every reader who clones the
repository.

## Running Locally

To test and run the project locally, you will need at least MyST and NPM.
To run locally to test drafts and development, the following command will initiate the document generation engine and run configuration files:

```bash
myst
```

If the environment is already configured and you just want to start, run:

```bash
myst start
```

To build the site, run:

```bash
myst build
```

Note that the build command will build documents according to the instructions under the `export:` key in `myst.yml`, so if any previous version is desired to be saved, it should be renamed or update th instructions before running the command.

To create pdfs, you may need to run additional commands that
initiate the creation of specific templates, such as:

```bash
myst build --pdf
```

OR

```bash
myst build --typst
```

To build "everything" (that is, the html site, plus all exports), run:

```bash
myst build -a
```

## License

The book is open access, but it is requested that any
downstream products or versions also remain open and freely available,
while credit is also given for any inspiration that this book may offer.
This is expressed by a [Creative Commons BY-NC-SA license](https://creativecommons.org/licenses/by-nc-sa/4.0/) (as of publication, version 4.0).

[![License: CC BY-NC-SA 4.0](https://shields.io/badge/License-CC_BY--NC--SA-blue)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

## Contact

This book does take inspiration from, and at times reuse, examples and techniques
promoted or theorized by others. Credit is duly given in all cases.
Concerns or questions can be routed to _jajohnst_ (at umich dot edu).
