---
title: "Getting Started: Setting Up Tools and Workspaces"
---

This section introduces the basic tools, configuration,
and some of the skills, used throughout the rest of the book.
The setup covers the following: basics of working with text, including regular expressions and markdown; some useful commands like `grep`; using Git and GitHub for static site publishing; Jupyter notebooks; and what you'll need in your environment.

As of 2026, this book assumes that readers are using [Visual Studio Code, aka VS Code](https://code.visualstudio.com/), as a development environment, and screenshots and figures mostly show this editor.
Though distributed and owned by Microsoft, VS Code is an open source editor ([see the code here](https://github.com/Microsoft/vscode)),
which is [made available under the MIT License](https://code.visualstudio.com/License).
Any full-featured text editor, however, can be used to develop or use similar tools.
If you use another text editor or [IDE](wiki:Integrated_development_environment), you may need to make some minor translations into that environment as needed.

## A Digital Collections Approach to Tooling

Because these are skills widely used in many
digital preservation tasks, digital humanities work,
and the like, there are many guides and tutorials for
some of these skills. This guide, therefore, intends to
explain unique or idiomatic uses of these tools as they appear in this book.
Keep in mind that these may be unique to this book or
to the digital cultural heritage community, such as it is,
not necessarily as they are used in other programming or development contexts.
There are often many existing guides or tutorials for use,
some of which are extensive and well maintained, so in most
cases the intent is to explain unique uses, then provide links to those external resources.

## Text as Interface

The developers of the UNIX operating system, particularly Ken Thompson, Dennis Ritchie, and Doug McIlroy,
articulated many design principles, which have become known as the "[UNIX Philosophy](wiki:Unix_philosophy).
While many of these are implicit to open source culture, of interest here is
the directive that UNIX programs should be able to handle plain text input,
and also to produce plain text outputs.
Text is sometimes thus referred to as a "universal interface."
Many of the tools that we will use in our open source cultural heritage projects
can be manipulated through plain text, whether on the command line,
searching, or basic formatting conventions of markdown.

:::{hint} Text as an Enduring Interface
Text interfaces are often critiqued as unintuitive or unappealing
by those of us accustomed to GUIs (graphical user interfaces).
However, text presents a highly accessible interface (it can be readily annotated and help text can be added).
Additionally, it is less ambiguous than graphical interfaces since it is declarative (it says exactly what you want in a given context, rather than "click here" or "click there").
And, interestingly, text has remained one of the most enduring interfaces.
Cloud platforms are often accessible through a browser interface or through command line variants.
Meanwhile, large language models and generative AI tools often use plain text to encode prompts, inputs, and outputs. Text as interface, then, appears to be highly enduring.
:::

### The Command Line

TODO: drop in from previous exercises in GH

### Regular Expressions

TODO: drop in from previous exercises in GH

:::{seealso} More About RegEx
The following provide more explanation of regex conventions and may be useful in developing and testing regex queries:

- [Library Carpentry's regex lesson](https://librarycarpentry.github.io/lc-data-intro/01-regular-expressions.html)
- [regularexpressions101](https://regex101.com/) - a highly useful tool to which you can provide text and test complex regex expressions

As noted previously, LLMs are highly capable at processing and producing text.
They can be very useful for developing regex queries and debugging patterns.
Before using an AI assistant, however, it is useful to have a basic grasp of how regex works
so that you can evaluate and test expressions.
:::

### Searching through Files (grep)

:::{seealso}
Want to learn more about using `grep`? Check out the [Library Carpentry initiative's episode that covers it](https://librarycarpentry.github.io/lc-shell/05-counting-mining.html#mining-or-searching).
:::

### Markdown Basics

The concept of _markup_ is relatively widely known in authoring and publishing content on the Web. The concept ties digital publishing to earlier practices of editing and proofreading, where set text was "marked up" to make corrections or identify errors. This was ported to electronic text in the concept of a markup language, which operates by adding annotations (aka "tags") to text to mark certain elements computer readable. 

The most widely used digital markup is the hypertext markup language (HTML). Like many other digital markup languages, HTML indicates annotations with pointy brackets (`<>`) and short text declarations (`p`). For example, enclosing a string like this (`<p>A new paragraph.<p>`) marks the text as a paragraph, which can be styled or presented in particular ways. We will encounter markup again in eXtensible Markup Language (XML), a powerful markup language that also allows the processing of text documents as data. Both XML and HTML derive from the older Standard Generalized Markup Language (SGML), which is a source of this convention.

_Markdown_, on the other hand, uses plain text annotations to indicate text styling and structure. In markdown, instead of marking a paragraph with the `<p>` tag, any text on a new line is recognized as a paragraph and procssed by the system as such. Similarly, lists, text emphasis and weight, headings, tables, and other elements of text setting can be indicated with markdown. As there are different "flavors" (implementations) of regular expressions, so are there different flavors of markdown. For the most part, we will be using markdown that is compatible with GitHub. Markdown files are often identifed by the `.md` file extension.

In [](#md-table), you will find a few basic markdown conventions that will be useful.
In the left and middle columns, you will see the plain text characters to use,
while the right-hand column shows the processed HTML result.
These illustrate some of the most frequently used shortcuts for formatting text,
embedding links or images, the use of lists, and the convention for short `code` examples.

:::{table} A few frequently shortcuts for basic formatting in markdown
:label: md-table
| Type this, | or this variation | for this result |
| --- | --- | ------ |
| `*italics*` | `_italics_` | _italics_ |
| `**bold**` | `__bold__` | __bold__ |
| `# Heading 1` | | output enclosed in `<h1>...</h1>` html tags |
| `## Heading 2` | | output enclosed in `<h2>...</h2>` html tags |
| etc. for add'l. levels | | |
| `[link](http://example.url)` | | [link](http://example.url) |
| `![alt text](http://path.to.source.file)` | | <img src="/assets/Windows_95_Help_page.png" height="150px" alt="Windows 95 Help image, Microsoft sourced from wikimedia commons"/> |
| `- unordered list item` | `* unordered list item` | <ul><li>unordered list item</li></ul> |
| `1. ordered list item` | `1) ordered list item` | <ol><li>ordered list item</li></ol> |
| \`text appears in monospace\` | | `text appears in monospace` |
:::

As noted above, remember that markdown is highly sensitive to spacing.
Paragraphs are indicated by the presence of blank lines in between them (like the ["block" style of a formal business letter](wiki:Business_letter#Block)).
Lists and blockquotes must also be preceded by a blank line.
The format of links and image syntax must not have spaces between the square brackets and parentheses.
Likewise image tags are frequently affected by where they are placed within text, on their own line,
or with blank lines before and after.

#### Fencing

An additional markdown convention described as "fencing" is worth noting since it is used in various places in the tools we will be using. This technique involves setting off a section by opening (preceding) and closing it with three repeated characters. Code blocks are indicated by fencing with three backticks (` ``` `), and file metadata blocks can be indicated with three hyphens (`---`). This technique is frequently used in plain text templates for static site generators, README files, configuration and other plain-text files that are often used in the platforms discussed in this book.

:::{seealso} More Markdown Guides
The basics of markdown are quick to learn, but many of the nuances or less frequent conventions, will take some testing. Here are a few guides that can help you learn more:

- [John Gruber's 2004 guide from Daring Fireball](https://daringfireball.net/projects/markdown/)
- The CommonMark Specification's [Guide to "Learn Markdown in 60 Seconds"](https://commonmark.org/help/) (Nota bene: they also have a longer, interactive tutorial)
- [Markdown Guide's Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)
- [GitHub Guide to Basic Markdown Formatting](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
:::

## Version tracking (Git) and Collaboration (GitHub)

:::{seealso}
Want to learn more about Git? Check out the [Library Carpentry initiative's lesson and setup guide for Git](https://librarycarpentry.github.io/lc-git/).
:::

## Annotating, Developing, and Reviewing Code (Jupyter notebooks)

Point: Jupyter notebooks allow you to run code blocks and write annotations or explanation in between blocks. You can also download and run them directly locally, which can be done in an IDE like VSCode or in a setup like JupyterLab.

TODO: add information on Jupyter notebooks here.

:::{seealso}
The Jupyter Notebook has been compared to the notebooks
of early scientific observers and theorists, like Isaac Newton.
Some have even suggested the notebook format may replace
scientific papers [@somers2015]. Read more about the [Jupyter Notebook format on Wikipedia](wiki:Project_Jupyter#Jupyter_Notebook).
:::
