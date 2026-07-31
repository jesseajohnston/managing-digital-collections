---
title: Getting Started
---

# Getting Started

This page aims to give you an introduction to the basic
tools, and some of the skills, used throughout the rest
of the book.

The setup covers the following: basics of working with text, including regular expressions and a few command line tools like `grep`; Git and GitHub; Jupyter notebooks; and what you'll need in your environment. As of 2026, this book assumes that readers are using Visual Studio Code, aka VS Code, as a development environment, but if you use another text editor or [IDE](wiki:Integrated_development_environment), you may need to make some minor translations into that environment as needed.

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

## Text as Interface (Using Plaintext and the Command Line)

### The Command Line

### Regular Expressions

### Searching through Files (grep)

:::{seealso}
Want to learn more about using `grep`? Check out the [Library Carpentry initiative's episode that covers it](https://librarycarpentry.github.io/lc-shell/05-counting-mining.html#mining-or-searching).
:::

### Using Basic Markdown

The concept of _markup_ is relatively widely known in authoring and publishing content on the Web. The concept ties digital publishing to earlier practices of editing and proofreading, where set text was "marked up" to make corrections or identify errors. This was ported to electronic text in the concept of a markup language, which operates by adding annotations (aka "tags") to text to mark certain elements computer readable. 

The most widely used digital markup is the hypertext markup language (HTML). Like many other digital markup languages, HTML indicates annotations with pointy brackets (`<>`) and short text declarations (`p`). For example, enclosing a string like this (`<p>A new paragraph.<p>`) marks the text as a paragraph, which can be styled or presented in particular ways. We will encounter markup again in eXtensible Markup Language (XML), a powerful markup language that also allows the processing of text documents as data. Both XML and HTML derive from the older Standard Generalized Markup Language (SGML), which is a source of this convention.

_Markdown_, on the other hand, uses plain text annotations to indicate text styling and structure. In markdown, instead of marking a paragraph with the `<p>` tag, any text on a new line is recognized as a paragraph and procssed by the system as such. Similarly, lists, text emphasis and weight, headings, tables, and other elements of text setting can be indicated with markdown. As there are different "flavors" (implementations) of regular expressions, so are there different flavors of markdown. For the most part, we will be using markdown that is compatible with GitHub. Markdown files are often identifed by the `.md` file extension.

Here are a few markdown basics that will be useful:

#### Headings

Headings are indicated by placing a pound sign at the beginning of the line, then adding the number of pound signs to correspond to the heading level: 

```markdown
# Heading 1
## Heading 2
### Heading 3
```

Unordered lists are generally indicated with an asterisk or hyphen at the beginning of each line:

```markdown
- Item 1
- Item 2
```

Text formatting like bold is indicated by surrounding a phrase with double asterisks (`**bold**`), while italics can be indicated with single asterisks (`*italics*`). 

A concept described as "fencing" is used in various places in markdown. This technique involves setting off a section by opening (preceding) and closing it with three repeated characters. Code blocks are indicated by fencing with three backticks (` ``` `), and file metadata blocks can be indicated with three hyphens (`---`). This technique is frequently used in plain text templates for static site generators, README files, configuration and other plain-text files that are often used in the platforms discussed in this book.

:::{seealso} More Markdown Guides
Here are a few guides that can help you learn more:

- [John Gruber's 2004 guide from Daring Fireball](https://daringfireball.net/projects/markdown/)
- [GitHub Guide to Basic Markdown Formatting](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [Markdown Guide's Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)
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
