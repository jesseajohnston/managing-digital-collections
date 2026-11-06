# Data for _Managing Digital Collections_

_Note: this file was largely created and maintained automatically (by ClaudeAI or similar tools)._

Sample datasets used by the notebooks in this book. Files here are **inputs only** —
anything a notebook writes goes to `output/`, which is not tracked in git.

Datasets are organized by collection rather than by book part, because the same
collection is used in more than one part to show how a single body of metadata looks
in different serializations (CSV, XML, JSON).

See the "Data files" section of the top-level [README](../README.md) for the naming
conventions and for how notebooks should reference these paths.

_Provenance last checked 2026-11-05. "Course copy" below means the same-named or equivalent file in the
local-only SI 676 data repository (`si676-2025-data`); "identical" means a byte-for-byte comparison.
Entries marked **TODO** could not be verified from the files or the repo history._

## Data Samples

### True Samples

These are files that were created only to provide examples. They don't really have any "real world" correlate.
The naming convention is to begin filenames with `sample-`, then to provide data format and any other useful information.

| File | Records | Used in |
| --- | --- | --- |
| `sample-ead-superior.xml` | 1 finding aid | Part 2, introductory parsing XML example; in-class XML notebooks |
| `sample-ead-superior-full.xml` | 1 finding aid | Part 2, XML manipulation, validation and building notebooks |

- **Source:** fictional "Superior Papers" finding aids (EAD3). `sample-ead-superior-full.xml` lists the author as Jesse Johnston.
  `sample-ead-superior.xml` is a shorter version; the course repo has a similar `superior-papers-demo.xml`
  that differs from it by one line (an `xml-model` processing instruction).
- **Rights:** original teaching examples, no external source. TODO — state the license (the book is CC-BY-NC-SA-4.0).
- **Modifications:** `sample-ead-superior-full.xml` was added 2026-08-12 as "a full and valid EAD3", for the validation notebooks.
  TODO — note how its validity was checked (e.g., against `ead3.xsd`).

### Generic format examples

Small illustrative files for the CSV, JSON and XML primers. They do not follow the `sample-` naming convention.

| File | Records | Used in |
| --- | --- | --- |
| `animals.csv` | 8 rows, no header row | Part 1, working with CSV |
| `simple-book-list.csv` | 3 | Not currently referenced in a chapter or lab |
| `simple-book-list-with-authors.csv` | 3 | Part 1, working with CSV |
| `simple-book-list.xml` | 2 | Not currently referenced in a chapter or lab |
| `book-sample.xml` | 1 | Not currently referenced in a chapter or lab |

- **Source:** `animals.csv` is identical to the course copy; TODO — original source of the data (the file carries no attribution).
  The book-list files are short hand-made examples; TODO — confirm they are author-made.
- **Rights:** TODO.
- **Modifications:** none known.
- Note: `simple-book-list.xml` declares the namespace `http://www.nogood.com/Book` and `book-sample.xml` has none; these
  are likely intended for namespace demonstrations. TODO — confirm.

### Regex practice files

| File | Records | Used in |
| --- | --- | --- |
| `filenames-with-american-dates/` | 7 files (`.xls`, `.xlsx`, `.txt`, `.doc`, `.docx`, `.csv`, `.jpg`) | `labs/lab-01-regex-python.ipynb` |

- **Source:** files whose names embed US-format dates (e.g., `diary-04-23-19.doc`), for practicing regular expressions on file names.
  Added 2026-09-11. TODO — origin of the file contents (the `.jpg` is dated 2022-09-05 on disk).
- **Rights:** TODO.

### Library of Congress Web Archives (LCWA): sample MODS records

MODS records describing archived websites, used in Part 2 to introduce XML parsing.

| File | Records | Used in |
| --- | --- | --- |
| `lcwa-mods-1.xml` | 1 | Not currently referenced in a chapter or lab |
| `lcwa-mods-5.xml` | 5 | Part 2, introductory parsing of XML and MODS |
| `lcwa-mods-25.xml` | 25 | Part 2, advanced XML for subject analysis and record modification |

- **Source:** records are marked `recordContentSource` `dlc` (Library of Congress); `recordCreationDate` values in the
  25-record file are 2015, 2017 and 2018. `lcwa-mods-5.xml` carries the comment "these MODS records are based on records
  provided by the Library of Congress in 2018. They were modified for teaching purposes." The first record is _Slate Magazine_
  (`lcwaN0010234`, <http://www.loc.gov/item/lcwaN0010234>). TODO — the URL or service the records were retrieved from, and the retrieval date.
- **Derivation:** `lcwa-mods-25.xml` and `lcwa-mods-1.xml` are identical to the course copies `2018_lcwa_MODS_25.xml` and
  `2018_lcwa_MODS_single.xml`. All five records in `lcwa-mods-5.xml` also appear in the 25-record file. TODO — how the
  25 records were selected from the source set.
- **Rights:** TODO — LoC rights statement for redistributing these records. The records' `accessCondition` is "None",
  which describes access to the archived site, not rights in the record.
- **Modifications:** `lcwa-mods-5.xml` differs from the course copy `2018_lcwa_MODS_5.xml` in two `languageTerm` elements
  (`authority="marc"` and no `authority`, where the course copy has `authority="iso639-2b"`) and in the added attribution comment.
  `lcwa-mods-25.xml` contains 10 `<!-- TODO: Insert name authority here -->` placeholders (none in the 5-record file).
  TODO — whether other teaching edits were made before the course copies.

### Bentley Historical Library (BHL): sample EAD finding aids

Finding aids retrieved from University of Michigan's online search at https://findingaids.lib.umich.edu/catalog/umich-bhl-9744.

| File | Records | Used in |
| --- | --- | --- |
| `bhl-ead-toy-papers.xml` | 1 | Extensive EAD finding aid, for ET introduction |

- **Status:** the file is not yet committed to git. TODO — retrieval date, rights statement, and whether the file was edited.

### Schemas

Schemas used for validation notebooks and for the JSON Schema plan.

| File | Version | Used in |
| --- | --- | --- |
| `ead3.xsd` | EAD3 release 1.1.1, dated 2019-12-16 (from the file header) | `xml-04-validation.ipynb`, `xml-05-building-xml.ipynb` |
| `mods-3-8.xsd` | MODS 3.8 (from the file header) | `part03/plan-for-part-3.md` |

- **Source:** `ead3.xsd` is hosted by the Library of Congress at <http://www.loc.gov/ead/> and developed by the Society of American Archivists'
  Technical Subcommittee for Encoded Archival Description. `mods-3-8.xsd` is the Library of Congress MODS schema
  (<http://www.loc.gov/standards/mods/>); the header lists Ray Denenberg as editor. Both were added 2026-08-12 and are identical to the course copies.
  They have not been compared with the current versions at loc.gov. TODO — download URLs and dates.
- **Rights:** neither file's header states a license. TODO — confirm terms from the LoC pages.
- **Modifications:** none known. `mods-3-8.xsd` imports `xml.xsd` and `xlink.xsd` from loc.gov (`schemaLocation`), which are not stored here.

### University of Michigan Library: Audubon wild turkey plate

One plate from John James Audubon's _The Birds of America_, used in Part 2 to illustrate descriptive, technical and administrative metadata.

| File | Description | Used in |
| --- | --- | --- |
| `sclaudubon_sclib_B464540_AUDUBON_V1_1_P1_audubon_v1_1_p1_2702x4086.jpg` | JPEG, 2702 × 4086 px | `part02/01-metadata-for-digital-collections.md` |
| `digital-turkey-exif.csv`, `digital-turkey-exif.json` | EXIF/file metadata for the image above, in two serializations | Not currently referenced in a chapter or lab |
| `digital-turkey-iiif.json` | IIIF Presentation 2 manifest for the same item | Not currently referenced in a chapter or lab |
| `digital-turkey-iiif-readable.json` | The same manifest, formatted for reading (parses equal to `digital-turkey-iiif.json`) | Not currently referenced in a chapter or lab |

- **Source:** University of Michigan Library Digital Collections (Special Collections Research Center). The manifest `@id` is
  `https://quod.lib.umich.edu/cgi/i/image/api/manifest/sclaudubon:B464540` and its attribution is "University of Michigan Library
  Digital Collections". The EXIF files were generated with ExifTool 13.55 from the local image (2026-08-06). TODO — image download
  date and the manifest retrieval date.
- **Rights:** the manifest has no `license` field. TODO — copy the rights statement from the item's record page.
- **Modifications:** none known to the image. The EXIF `SourceFile` paths are local paths from the machine that ran ExifTool.

### Library of Congress APIs and collection-site materials

Used in Part 3 (API extraction and MAP design) and in the CollectionBuilder and Omeka S projects.

| File | Description | Used in |
| --- | --- | --- |
| `apis-02-collection-list.json` | Response for the LoC "Free to Use and Reuse" collection page (the portal manifest is `portals/free-to-use/manifest.yaml`); `timestamp` field is 2026-10-29 23:00 UTC | `part03/apis-02-harvesting-metadata.ipynb` |
| `collection_set_list.csv` | 62 rows (`image`, `link`, `title`), links like `/resource/cph.3f05183/`; image paths under `.../free-to-use/public-domain/libraries/` | `apis-02-harvesting-metadata.ipynb`, `apis-03-harvesting-item-metadata.ipynb` |
| `item_metadata-cph.3f05183.json` | LoC item record for "For greater knowledge on more subjects use your library more often" (<https://www.loc.gov/item/98508155/>) | `apis-03-harvesting-item-metadata.ipynb`, `apis-04-map-design.ipynb` |
| `cb-csv-metadata-template.csv` | CollectionBuilder metadata CSV: header row plus one example row (a suffrage broadside, LoC handle `loc.rb/rbcmil.scrp7005601`) | `labs/lab-04-artisanal-metadata.md`, `labs/project-01a-collectionbuilder.md` |
| `omekas-csv-metadata-template.csv` | Omeka S CSV import template: header row plus one example row (Carnegie Library, Cordele, Georgia; LoC item 91787443) | `labs/project-01b-omeka-s.md` |

- **Source:** all derive from Library of Congress web and API output. `collection_set_list.csv` and `omekas-csv-metadata-template.csv` are
  identical to the course copies. `item_metadata-cph.3f05183.json` carries LoC's own `extract_timestamp` of 2022-09-03; it is not in the
  course `collection-site-materials/item-metadata/` folder. TODO — the API URLs and retrieval dates for each file.
- **Rights:** the item record's `rights_advisory` reads "No known restrictions on publication", and its `rights` text states the Library of Congress
  does not own rights in the material and that researchers must assess restrictions. TODO — rights for the other files; the template
  rows were not checked against their LoC records. The CollectionBuilder example row's `rights` value ("CC-0") is copied as written and is unverified.
- **Modifications:** `cb-csv-metadata-template.csv` differs from the course copy `metadata-template-cb.csv` (first difference in the header row);
  TODO — what changed. `item_metadata-cph.3f05183.json` is not yet committed to git.

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
