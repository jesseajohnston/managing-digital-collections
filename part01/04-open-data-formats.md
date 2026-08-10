---
title: Encoding Data in Open Formats
---

:::{warning}
This fits with the "openness" section, right?

TODO: This file is not completed. Remove this box when the file is drafted.
:::

This is a placeholder for a page that will introduce
open data encoding formats, including CSV, XML, and JSON.
It's worth noting that these formats are widely used
across the web, and the recent rise of generative AI and agentic AI systems have actually re-invigorated plain text as the most common interface. Agentic systems
frequently store prompts or output information in JSON structures, which can be readily shared across the web, presented in browsers, or read aloud.

## Tabular Data: Often in CSV or Spreadsheet Formats

Although we will encounter structures that can encode more complex relationships,
much basic metadata can be expressed as a list of attributes and corresponding values that correspond to the item being described.
This kind of data is usually expressed as tabular data, which can be encoded in a CSV file or in a spreadsheet.

### The Humble CSV: A Compatible Plain-Text Format

The most basic format of [metadata](/part02/01-metadata-for-digital-collections.md) may be the _attribute - value list_.
While this can be expressed as a multi-line text file, it also is easily serialized in a CSV format.

The short list example in [](#csv-sample) illustrates both an attribute value list as well as the CSV structure.
Note that each line includes a comma, which in this case separates the first piece of information in the line, the _attribute_, and the second piece of information in the line, the _value_. 

```{code} csv
:label: csv-sample
:linenos:
:emphasize-lines: 1
:caption: A snippet that illustrates a short _attribute - value_ list and basic concepts of the CSV structure.
attribute,value
title,wild turkey
creator,john james audubon
date,1827
```

Thus, in line 1, which acts like a _header_ line that sets the pattern for the rest of the list, the first element is _attribute_, the second is _value_, and these are separated by the comma.
This special and consistent use of a character (in this case `,`) is called a _delimiter_ character.
Subsequent lines list values for `title` (line 2), `creator` (line 3), and `date` (line 4). The second half of each line provides the value for each of those attributes.
As a reader, we should presume that this is describing some particular collection item (in fact, these may be referencing a [figure from the next section](/part02/01-metadata-for-digital-collections.md#an-example-item-an-image-file-and-metadata)).

As discussed previously, the CSV structure is a good example of a serialization format that can readily structure tabular data.

## XML: A Quick Introduction

Let's talk about XML!

## JSON: A Quick Introduction

Let's talk about JSON!
