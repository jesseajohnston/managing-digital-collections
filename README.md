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

To build and create pdfs, run:

```bash
myst build
```

Note that the build command will build documents according to the instructions under the `export:` key in `myst.yml`, so if any previous version is desired to be saved, it should be renamed or update th instructions before running the command.

## License

The book is open access, but it is requested that any
downstream products or versions also remain open and freely available,
while credit is also given for any inspiration that this book may offer.
This is expressed by a [Creative Commons BY-NC-SA license](https://creativecommons.org/licenses/by-nc-sa/4.0/) (as of publication, version 4.0).

This book does take inspiration from, and at times reuse, examples and techniques
promoted or theorized by others. Credit is duly given in all cases.
Concerns or questions can be routed to _jajohnst_ (at umich dot edu).
