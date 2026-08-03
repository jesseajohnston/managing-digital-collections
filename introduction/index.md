---
title: Introduction
---

_Managing Digital Collections: An Open-Source Guide to Digital Cultural Heritage Management with Python_ is an open-source textbook that supports
active learning and teaching for important technical skills of use to
digital content managers in cultural heritage organizations like archives, libraries, museums, and other collecting institutions.
The book is designed for staff who are engaged in digital collections management, managers who supervise and plan digital content management work,
and aspiring collections managers who want to learn more about open source tools for managing and presenting digital content.

## About the Book

The book is intended as a practical, project-oriented primer
for people interested in learning about management of digital content in cultural heritage collections.
Thus, the text is written with the assumption that readers and users are working in, or interested in libraries, archives, museums, or other organizations that focus on collections.
In addition, the text assumes a functional level of knowledge about using
programmatic digital tools, including the Python programming language,
text-based command line interface, and other system-level tools that
facilitate the bulk and batch management of digital content in small-
and medium-sized collections.

The book developed out of my course of "Networked Services for Libraries, Archives, and Museums,"
a graduate course at the University of Michigan School of Information that I taught from 2022 to 2025.
In 2026, I renamed the course "Digital Content Management,"
and the first edition of this book was written and published to support that course, with significant revisions and updates throughout 2026.

As a de facto "first edition," which was created to support
an active classroom environment, you may find placeholders in some locations.
If you are seeking to fill those gaps, on digital collections management or other topics, you may be able to find some information about related topics on Wikipedia.
For example, there are moderately to fully developed articles on related topics including [cultural heritage](wiki:Cultural_heritage), [digital preservation](wiki:digital_preservation), and [collections management](wiki:Collections_management), among other key ideas.

## Learning Approach

The book aims to give an overview of major functions for managing digital collections.
Specifically, the book aims to illustrate managing these collections using open source tools,
shared and open metadata and descriptive standards,
and to show medium to small sized collections might be managed with readily available software
that can be managed and configured by a "digitally savvy" collection manager. Just as @lyonetal2018 [pg. 7] have
described data savvy research management as a "blending of competencies in computer programming
and software engineering (hacking)" with data management and domain skills, digital collections management
may be seen as a blending of similar digital skills with library and archival perspectives,
including (meta)data standards and management, emphasis on trustworthy and ethical access,
clear and stable identification, and a dedication to reliability.

In its teaching philosophy, the book hews closely to that of the Carpentries,
which aims for an inclusive approach to technology instruction, empowering learners
with "[efficient, open, and reproducible](https://carpentries.org/about-us/)" digital practices.

## Structure of the Book

The book is sequenced in four major content parts, with supplementary materials
located at the end of sections or in the final Lab part.
The online version of the book has some additional elements, like a course calendar with additional readings, assignments, and due dates.

As a foundation, _Part 1_ introduces concepts of open source technology and culture
and links it to parallel work and values in library and archival organizations.
As an example of open source standards, this section also introduces plain-text data formats
like CSV, JSON, and XML, as well as some basic techniques for parsing and processing them. These are foundational for the next sections.

In _Part 2_, cultural heritage concepts of metadata are introduced. Specific standards for descriptive and technical information, such as Dublin Core, MODS, and EAD, are used as examples.
Hands on activities including the review and editing of sample metadata records with programmatic
tools are used.

_Part 3_, introduces some of the basic concepts of networked computing, including
a quick discussion of the WWW and its underlying protocols, notable open-source server stacks,
and progressing to the use of web-accessible APIs to retrieve and manage metadata.
Although the emphasis of the book's activities remains on tools and systems that can be run
locally on a laptop, this section also introduces cloud computing and illustrates
how many cultural collections use platforms and software "as a service" from cloud providers.

Finally, _Part 4_ discusses the presentation and publication of collections on the web.
As throughout, the emphasis is on open source platforms, including Omeka and CollectionBuilder.
These two examples illustrate open source approaches, as well as different network architectures,
which can be locally published or spun up through cloud services.
The section closes with an overview of similarities and differences that
may be considered when planning and managing these different service approahces.

Additional supporting material, which provides sample problems and worked examples, is included in the _Labs_ section.

## Using the Book

This book assumes a level of comfort with digital tools and systems.
While I hope that the book may appeal to newer staff and those who work with digital content but do not see themselves as "programmers" or "developers," there are many assumptions about the existing level of knowledge of potential readers and users.
Many students who took the course have already studied Python,
have worked already with system interfaces like the "[command line](wiki:Command-line_interface)" (aka CLI), and have worked with version management systems like Git.

:::{important} Hover Over Links
Note that at the above links, which go to Wikipedia, you can hover to see a quick preview for more information.
:::

Given these assumptions, this book may not be equally useful to all readers.
For those, however, who have a healthy curiosity, a modicum of  patience in learning new digital tools, and tenacity and perserverance
in trying things out and making them work, I hope that the book will be rewarding.
For those who have not already learned or worked with the above tools, the next "Getting Started" section offers some basic advice about how to set up your computing environment and outlines the major tools used throughout the book.

## Note on Using "AI"

Recent "artificial intelligence" tools, particularly large language models (LLMs)
and generative tools based on them, can be highly useful for
seeking technical advice, troubleshooting, and getting insights on platform configuration.
Such tools are also becoming more widely used in cultural heritage collection workflows
for significant tasks like transcription, content labeling and description, and metadata creation or evaluation.
A technical exploration of these tools is well beyond the scope of this book and its author,
but it is worth noting that these tools are already in wide use in many professional domains, including the development and deployment of library systems and platforms.

While these tools are widely used, and can be useful, I recommend
avoiding getting too much help from generative AI during class or while you are working on fundamental examples. This book contains plenty of basic code and examples, which are explained and available to use or reuse. You should aim to understand these first, before moving on to develop solely with an LLM.
As the Library Carpentry suggests, your goal should be first to learn "foundational knowledge and skills . . . by writing and fixing your own" code and tools. This is 

> essential to be able to evaluate the correctness and safety of any answers you receive from other people or a generative AI chatbot. If you choose to use these tools in the future, the expertise you gain from learning and practising these fundamentals on your own will help you use them more effectively.
> [Library Carpentry, "Introduction to Data Management"](https://librarycarpentry.github.io/lc-data-intro/01-regular-expressions.html#getting-help-with-regular-expressions)

# The Role of AI in Producing this Book

The author did use AI in generating this book. However, AI was used in very specific ways.
The composition and writing of the book's prose was undertaken entirely by the author,
using a very human process of drafting, editing, and rewriting.
All of the text was developed in previous iterations of the course and reflects the author's experience
teaching these concepts and tools in live teaching settings.

Beyond the text, AI was used to configure the web version of the book,
which runs on the MyST templating and document engine, as well as the Typst language for
templating and creating the pdf version.
In addition, LLMs were used to develop some of the sample code,
though all of the code developed prior to 2025 was "artisanal" (in the sens of it being
designed and written by the author, who is not a programmer).
For all of these tasks, the primary tool was Anthropic's claude (various models, including Sonnet 3.X and 4.X as well as Opus 4.X and 5.X). Some code was also created by earlier models of
OpenAI's ChatGPT, as accessible through the [University of Michigan's Maizey wrapper](https://its.umich.edu/computing/ai/maizey-in-depth), as available in 2024 and 2025.

***TODO?*** Possibly add an "activity" setion following this, e.g., set up your GitHub account activity.
