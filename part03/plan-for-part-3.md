---
title: Plan for Part 3
---

## What Part 3 is

Networked computing for LAMs: how metadata moves over the network (HTTP, REST APIs, JSON, OAI-PMH) and how it is served (the LAMP stack, shown through Omeka S).

Current files (per `myst.yml`): `apis-01` to `apis-03` (REST/JSON, harvesting collection and item metadata; LOC API, OAI-PMH), `apis-04` (metadata application profile and crosswalk design), `servers-*` (5 files: logging in, Omeka S install, configuration, modules, vocabularies).

Done: LOC API and OAI-PMH; Omeka S setup activity.

## To do

1. **Fix `apis-04`** (2026-11-05 review):
   - [ ] Sample term table: `date` description says "scanned or digitized"; the walkthrough above chooses the creation date.
   - [ ] Crosswalk table: `creator`, `source_collection`, `languages` are absent from the sample item; `description`, `type`, `rights`, `languages`, `mime_type` are top-level, not under `metadata['item']`. Check each row's path.
   - [ ] Two H1 headings follow the front-matter title; decide levels.
   - [ ] Review the merge, then delete the superseded `part02/03-metadata-application-profile-design.md`. Its IIIF "Look for Structured Metadata" hint was not merged.
   - [ ] Decide Part 3 vs. Part 4. If it moves: `myst.yml` (`project.toc` and `exports[].articles`), `labs/project-02-map.md` links, plan docs.
2. [ ] **Networks basics chapter**: TCP/IP, DNS, HTTP. Adapt the existing SI 676 activity. Place before `apis-01`.
3. [ ] **LAMP stack chapter**: four components, Omeka S as the example, basis for publishing a local site. Place before `servers-omeka-s-install`; connect to `servers-logging-in`.
4. [ ] **Omeka S API / JSON chapter**: notebook reading from the instance built in `servers-*`. Check what `apis-01` already covers on JSON first.
5. [ ] **RDF / linked data activity**: decide in or out. Link point: `servers-omeka-s-add-vocabularies`.
6. [ ] **JSON Schema / JSON-LD material**: decide scope (see below). Not in the TOC.
7. [ ] Finish the `index.md` intro (second sentence is cut off) and decide where the Part 3 overview text lives.

## Open decisions

- `apis-04` location (Part 3 or 4).
- Whether RDF and JSON Schema are chapters, optional extensions, or cut.
- If JSON Schema is kept: target T1, T2, or T3 (below). Recommendation in the analysis is B + C, with D presented as the linked-data path. This is a recommendation, not a decision.

---

## Analysis: MODS XSD to JSON Schema / JSON-LD

Merged from `plan-for-json-schema-exx-part-3.md`.

:::{note} About this document
This is a Claude-generated plan and analysis, produced 2026-08-12 in response to the question:
*"If I wanted to use `data/mods-3-8.xsd` as a model to create a JSON schema for MODS-consistent
JSON-LD, what would that take?"*

Schema counts below were measured directly from `data/mods-3-8.xsd` and `data/lcwa-mods-25.xml`,
not estimated. Editorial judgments (which target to pick, how much work each path is) are
recommendations, not decisions.
:::

### What's actually in `data/mods-3-8.xsd`

Measured:

| | count |
|---|---|
| lines | 1,766 |
| global element declarations | 109 |
| named complexTypes | 61 — **36** are `simpleContent` (a string plus attributes), **25** carry a model group |
| named simpleTypes | 40 (mostly single-value or short enumerations; 76 `xs:enumeration` total) |
| attribute groups | 4 (`authorityAttributeGroup`, `languageAttributeGroup`, `altFormatAttributeGroup`, `IDAttributeGroup`) |
| local attribute declarations | 141 |
| mixed content types | 2 (`accessConditionDefinition`, `extensionDefinition`) |
| `xs:any processContents="lax"` | 1 (line 268) |

Shape facts that drive everything downstream:

- `modsDefinition` is `<xs:group ref="modsGroup" maxOccurs="unbounded"/>` over an `<xs:choice>` of
  20 top-level elements (lines 90, 137). Every top-level element is optional, repeatable, and
  order-free. **There is no required element in a MODS record** — not even a title.
- The schema is unusually regular: 36 of 61 types follow the same "string + attribute groups"
  pattern (`stringPlusLanguage` and its two extensions, line 1663). That regularity is what makes
  a port tractable.
- Two external imports with `schemaLocation` pointing at loc.gov (`xml.xsd`, `xlink.xsd`, lines
  11–14). Any offline conversion needs local copies; `xml:lang` and `xlink:href` are otherwise
  unresolvable.
- `nameDefinition` (line 563) encodes a co-occurrence constraint *structurally* — an `<etal>`
  branch that forbids `namePart`/`displayForm`/`nameIdentifier`. That's a `oneOf` in JSON Schema,
  not a property list.
- `@ID`/`@IDREF` (line 1725) plus the string-keyed joins `altRepGroup` and `nameTitleGroup` are
  intra-record cross-references. **JSON Schema has no equivalent** — no ID uniqueness, no
  referential integrity.

For calibration, the sample data in `data/lcwa-mods-25.xml` (25 records) uses **35 of 109 elements
and 8 of 141 attributes**. Real MODS is a small subset of MODS.

### The thing to get straight first: this is three artifacts, not one

"A JSON schema for MODS-consistent JSON-LD" decomposes into:

1. **A JSON encoding of MODS** — a syntactic convention for turning MODS XML trees into JSON
   objects. The XSD *is* the right source here.
2. **A JSON-LD `@context`** — a mapping from JSON keys to IRIs, i.e. semantics. **The XSD is not a
   source for this.** An XSD says nothing about what anything *means*; it constrains a tree of
   strings. LoC's own answer to "what does MODS mean in RDF" is the MODS/RDF ontology
   (<http://www.loc.gov/standards/mods/rdf/v1/>) — a separate OWL artifact with a different
   structure from the XML.
3. **A JSON Schema validating the JSON-LD documents** — shape constraints over the output of
   (1)+(2). Only meaningful once a compaction profile is fixed, because JSON-LD is shape-unstable:
   `"x"`, `{"@value":"x"}`, and `["x"]` are the same graph.

The XSD gets you (1) mechanically, (3) with hand repair, and (2) not at all.

#### Why the XSD can't yield JSON-LD

- **RDF has no attribute/element distinction.** MODS uses attributes for two incompatible jobs:
  literal qualifiers (`@lang`, `@script`, `@encoding`) and actual semantic links (`@valueURI` *is*
  the IRI of the concept; `@authorityURI` identifies the scheme). A mechanical converter cannot
  tell those apart — one should become a language tag, the other should become the `@id` of an
  object.
- **MODS is a record format, not a graph.** `<titleInfo><title>` is a container holding a string.
  RDF wants `ex:record dcterms:title "…"`. The container must either vanish or become a blank
  node, and that is a per-element editorial decision.
- **Nodes have no identity.** Nearly every MODS sub-node becomes a blank node — legal RDF, poor
  linked data.
- **Order and mixed content are meaningless in RDF**, yet `<titleInfo>`'s `nonSort`/`title`/
  `subTitle` sequence and `<accessCondition>`'s mixed content carry display meaning.
- **`altRepGroup`/`nameTitleGroup` are joins**; reconstructing them requires interpretation.
- **Reserved-character collision.** Most XSD→JSON converters prefix attributes with `@`
  (`@type`, `@lang`). In JSON-LD, `@`-prefixed keys are reserved keywords. A default-configured
  converter produces output that is invalid or misinterpreted as JSON-LD on day one.

### Plan

#### Phase 0 — Pick the target

These are genuinely different projects:

- **T1 · MODS-shaped JSON** — JSON mirroring the XML tree, plus a thin `@context`. Cheap, lossless,
  round-trippable. The JSON-LD is largely nominal (blank nodes everywhere). *Best if the goal is
  "MODS in JSON for APIs."*
- **T2 · MODS/RDF-based JSON-LD** — real linked data over LoC's ontology. Structurally unlike the
  XML; requires an XML→RDF mapping pass. *Best if the goal is "MODS as linked data."*
- **T3 · Map out to an existing vocabulary** — BIBFRAME 2.0 (LoC publishes a MODS→BIBFRAME mapping
  at <https://www.loc.gov/standards/mods/modsrdf/mods-bibframe-mapping.html>), schema.org, or
  Linked Art. Best interoperability, most information loss, most editorial judgment.

#### Phase 1 — Write the encoding contract before writing any schema

This is the whole ballgame and it's about one page of decisions:

- attribute key convention — **must not be `@`**; use `_lang`, or a nested
  `{"value": …, "lang": …}` form
- text-content key (`value`? `#text`?)
- singleton vs. always-array. MODS's everything-repeatable model means "array when needed" forces
  `oneOf` on nearly every property; always-array is verbose but predictable — and
  `"@container": "@set"` in the context makes it clean on the JSON-LD side
- empty elements, mixed content, `xs:any` payloads in `<extension>`, namespace handling

#### Phase 2 — Generate the draft JSON Schema from the XSD

Mechanical, then hand-repair the constructs that don't survive (table below).

#### Phase 3 — Author the `@context` by hand

Against MODS/RDF or the chosen vocabulary. Non-mechanical: roughly 1–2 days for full coverage,
hours for a subset.

#### Phase 4 — Build a round-trip harness

Everything needed is already local: convert `data/lcwa-mods-25.xml` → validate with `jsonschema`
(installed) → JSON-LD expand → convert back to XML → validate against the XSD with `lxml` and diff.
This is what proves the port, and it makes a good notebook.

### Feasibility: construct by construct

| XSD construct | Ports? | Notes |
|---|---|---|
| `xs:enumeration` | yes | → `enum`, direct |
| `simpleContent` + attribute groups (36 types) | yes | → `{value, …attrs}`; add `oneOf` with bare string if the shorthand is allowed |
| `xs:sequence` | partly | → `properties`; **order is lost**. Fine for most, lossy for `titleInfo`, `part/detail` |
| `xs:choice maxOccurs="unbounded"` | partly | → object of optional arrays; loses interleaving order. Preserve order only by moving to an array-of-typed-objects encoding |
| `xs:anyURI`, `xs:positiveInteger`, `xs:date*` | yes | → `format`/`type` |
| MODS date semantics | no | Not in the XSD at all — dates are `xs:string` governed by `@encoding` (w3cdtf/iso8601/marc/edtf/temper). Real date validation must be authored fresh |
| `xs:ID` / `xs:IDREF` | no | No JSON Schema equivalent; needs a post-validation pass |
| `altRepGroup` / `nameTitleGroup` | no | Same |
| mixed content (2 types) | no | Needs a bespoke representation |
| `xs:any processContents="lax"` | partly | Trivially `true` / `additionalProperties: true` — i.e. unvalidated, same as in the XSD |
| `nameDefinition` etal branching | partly | Expressible as `oneOf`, but no generator will infer it |
| `xml:lang`, `xlink:*` imports | partly | Need local `xml.xsd` / `xlink.xsd` first |
| controlled vocabularies (MARC relators, ISO 639, RDA terms) | no | Never were in the XSD |

**Verdict:** a JSON Schema covering roughly 85% of MODS 3.8's constraint surface is a 1–2 day job.
The remaining 15% (IDs, groups, dates, mixed content, vocabularies) was never in the XSD, so no
converter recovers it. JSON-LD is a separate, judgment-heavy effort that the XSD does not shorten.

### Options for the port

**A · Off-the-shelf converter, then hand-edit.** Oxygen's XSD→JSON Schema converter (commercial,
most complete), the JetBrains XSD to JSON Schema plugin, `xsd2jsonschema` (npm; handles multi-file
and circular refs but is unmaintained — no npm release in 12+ months), Jsonix Schema Compiler
(Java, targets Jsonix's own JSON convention). **The catch:** each tool hardcodes *its own* XML→JSON
convention, so picking the tool picks the encoding — and they generally choose `@`-prefixed
attributes, which is exactly wrong for JSON-LD. Fastest to a draft, worst fit for the goal.

**B · Write a custom generator (recommended).** Roughly 250–400 lines with `lxml` (installed) or
`xmlschema` (not installed; one `pip install`). The 36/61 `simpleContent` regularity means one
function handles more than half the schema; the 4 attribute groups become 4 reusable `$defs`. This
gives control over the encoding contract, emits JSON-LD-safe keys, and is a legible notebook for
the book — "how a schema becomes another schema" is a better lesson than "run this tool."

**C · Hand-author a profile schema for the subset actually in use.** The 25-record sample touches
35 elements and 8 attributes. A hand-written schema for that is a few hours, is far more readable,
and can carry real constraints (required fields, controlled vocabularies) that full MODS cannot —
since full MODS requires nothing. This is how institutions use MODS in practice.

**D · Skip the XSD for the LD layer.** Generate the `@context` from the MODS/RDF OWL ontology, and
use **SHACL** rather than JSON Schema for constraints — SHACL validates graphs, so it is immune to
JSON-LD's shape instability. JSON Schema's job then shrinks to "does this document match our
compaction profile."

**Recommendation:** **B + C** — generate the full-MODS schema mechanically as the reference
artifact, hand-author the profile schema as the usable one, layer a hand-written `@context` on top,
and present D as the honest linked-data path. That sequence also works as a chapter arc.

### Sources

- MODS/RDF namespace document — <http://www.loc.gov/standards/mods/rdf/v1/>
- MODS to BIBFRAME mapping — <https://www.loc.gov/standards/mods/modsrdf/mods-bibframe-mapping.html>
- Oxygen XSD to JSON Schema converter — <https://www.oxygenxml.com/doc/ug-editor/topics/xsd-to-json-schema-converter-x.html>
- `xsd2jsonschema` — <https://github.com/andrewbober/xsd2jsonschema>
- Jsonix Schema Compiler — <https://github.com/highsource/jsonix-schema-compiler>
- JetBrains XSD to JSON Schema plugin — <https://plugins.jetbrains.com/plugin/19024-xsd-to-json-schema>
