---
title:  "LAMP Servers: Adding Vocabularies to Omeka S"
---

This section describes the process of adding a Vocabulary to your Omeka S installation. Note that Omeka also provides instructions about using Vocabularies at [https://omeka.org/s/docs/user-manual/content/vocabularies/](https://omeka.org/s/docs/user-manual/content/vocabularies/). In addition to this step-by-step document, you may wish to review Omeka S documentation at [https://omeka.org/s/docs/user-manual/content/vocabularies/#add-a-vocabulary](https://omeka.org/s/docs/user-manual/content/vocabularies/#add-a-vocabulary).

To implement a vocabulary, Omeka needs the rules for the vocabulary scheme. These can be imported with a structured, ontology file that encodes the rules. Such rules are typically encoded in XML and may be an RDF schema file, RNG (Relax NG), or OWL (Web Ongology Language), to name a few. These formats contain the information that explains the allowed terms, classes, and relationships within the vocabulary, also known as the ontology.

The basic steps to import a vocabulary are as follows:

## Find a Schema File

First, find the RDF or schema file for the vocabulary that you want to add. Once you have the file, follow these steps:

- To import MODS, you can consult the MODS documentation from the Library of Congress, which provides the ontology in an RDF format. See: [https://www.loc.gov/standards/mods/modsrdf/](https://www.loc.gov/standards/mods/modsrdf/) (the OWL ontology encoding is an RDF document).
- Omeka [suggests](https://omeka.org/s/docs/user-manual/content/vocabularies/#add-a-vocabulary): "Note that you may have to research in order to find the prefix, namespace URI, and label for the vocabulary, as these are not standardized. In addition to the vocabulary's website, you might consult [https://lov.linkeddata.es/dataset/lov/vocabs](https://lov.linkeddata.es/dataset/lov/vocabs)."
- For MODS specifically, this thread explains how to find the importable MODS schema file: [https://forum.omeka.org/t/omeka-s-and-mods/9104](https://forum.omeka.org/t/omeka-s-and-mods/9104).
- You can find files to import DC Terms or other vocabularies in metadata registries, such as [https://rdamsc.bath.ac.uk/](https://rdamsc.bath.ac.uk/) (maintained by the Research Data Alliance [RDA]), or Digital Ocean's [http://metadataregistry.org/](http://metadataregistry.org/).

## Import the Vocabulary

Once you have the schema file, you can import the vocabulary.

- Click on the “Vocabularies” link in the navigation tab to the left under “RESOURCES”. When an Omeka S site is unconfigured, you will note that a few ontologies are already loaded, including the Bibliographic Ontology (`bibo`), Dublin Core (`dcterms`), DublinCore Type vocabulary (`dctype`), and Friend of a Friend (`foaf`).
- On the Vocabularies page, click the “Import new vocabulary” button on the upper right of the page.
- On the Import page, you will fill out the form explaining to Omeka S what to call the ontology (basically defining its namespace within your site), any notes you want to provide, and where to find the ontology file. In this case, you will find it at the link above (in step 1.a.).
- Fill in the form with the appropriate namespace and link to an ontology. See [](#servers-omeka-mods-vocab-form) for suggested values if you are importing the MODS ontology.

```{figure} /assets/part03-servers-omekas-mods-vocab-addition.jpg
:label: servers-omeka-mods-vocab-form
:alt: Omeka S New Vocabulary information form, with information entered for the MODS v1 vocabulary
:align: center

Omeka S New Vocabulary information form, with information entered for the MODS v1 vocabulary.
```

- After you complete the form, click the “import” button. If you are successful, you should see the list of Vocabularies, which now will include the additional Vocabulary (see [](#servers-omeka-mods-imported)).

```{figure} /assets/part03-servers-omekas-mods-imported.jpg
:label: servers-omeka-mods-imported
:alt: Omeka S Vocabulary import success screen for the MODS vocabulary
:align: center

Omeka S Vocabulary import success screen for the MODS vocabulary.
```
