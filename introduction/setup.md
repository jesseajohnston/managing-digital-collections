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
| `![alt text](http://path.to.source.file)` | | <img src="/assets/Windows_95_Help_page.png" height="50px" alt="Windows 95 Help image, Microsoft sourced from wikimedia commons"/> |
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

Tracking changes in a document are challenging when you're working on your own,
and they become even more difficult to manage if you are working with a group of writers and editors.
Version tracking systems help to answer questions like "what is the most current version?", "can we change this back to an earlier point?",
and to help manage coordination between different people working simultaneously in different parts of a project.
The system that this book uses is [Git](wiki:Git), a distributed version control system, which can be used locally or amongst multiple collaborators on a network. **Git** was developed to manage and coordinate the development and maintenance of software source code (specifically, during the development of the Linux open-source operating system code).

Git refers to the version tracking software when it is used to track and log changes. The tool is often taught and used on the command line, where Git commands usually begin with `git`, such as `git init` (to initialize, or begin using Git in a project) or `git commit` (to "commit" or save the changes to the projects Git tracking log).

Although developed to manage versions of source code, Git has become widely used for managing writing projects,
including documentation, standards, blogs, and many other projects. (This book, for example, was originally published online using
a digital publishing suite, which was published online using GitHub.)

### Git Basics: Starting and Tracking a Project

To start using Git, you need to install it on your computer. This process frequently changes as the software is updated. Currently, the [setup instructions provided by the Library Carpentry project are useful](https://librarycarpentry.github.io/lc-git/#installing-git), and they provide a good starting point to download and configure Git on your computer. The following steps assume that you have already installed Git and configured your Git user profile.

#### Starting a Repository

When running on your own computer, or "locally," Git will usually run in a folder/directory, where it will track changes when you ask it to.
This local usage is called a _repository_, or "repo," which is the basic container for a Git project.

To start tracking a project with Git, first check to ensure you are not already in a Git repo (see below). When you are ready, run the command `git init`, which will "initialize" Git tracking in the current directory. This does a number of things, but the main one is to create a hidden directory named `.git`, which will track the changes. You can see this directory in a terminal window by running the `ls -a` command.

If you initialized a Git repo in an empty directory, you will see a message like `Initialized empty Git repository` and the location of the repo.

:::{attention} Avoid Recursive Git Repos (aka, repos in repos)
Because local Git repos typically operate within a folder, you may want to check to make sure that you are not initiating a Git repo inside an already existing one! That will create complications in updating or linking repos. So if you're not sure whether you're in a Git repo, always run `git status` before initiating a new repository. If you see a response like `fatal: not a git repository`, then it should be okay to inituate a new repo.
:::

In addition to the tracking folder, Git creates a "branch," which is called `main` by default. When working in the main branch, all changes are grouped together. Additional branches can be created to track work on different elements or by different users as work becomes more complicated. For now, it is sufficient to run `git status` and note that you are on the main branch. You will see a message like

```git
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

This indicates a blank repository. 

#### Commiting Changes and Updating a repo

The basic process of tracking changes in Git is called a _commit_.
When you have made the changes that you want to track, save all of your work, and then begin the commit process. This is intentionally more complex than hitting the Save button, because Git keeps a log of the changes, and as the committer, you are responsible for explaining what the changes are.

The commit process is multi-step. The process involves preparing (staging or adding) the changes, then commiting the changes. Let's got step by step:

1. Prepare the changes. As you add files or update work, save files as you would normally. Once the changes are ready, you need to add them to the tracking log.
2. Track, or "stage," the changes. To do this, run `git add` and provide the path to the desired changed files that you want to stage. This can be a multi-step process as you work, or you can add multiple files at a time.
3. Commit the changes. When ready, the basic command is `git commit`, which is run with a message flag (like `-m "Your commit message"`) to commit the changes. This step requires a "commit message," which briefly describes the changes. As a rule, these are short and descriptive; because Git will track who's making the changes, the files changed, and the date/time, you don't need to include that information. But you may want to explain why the changes are made, such as an update, feature, or new section.

When changes are made, run `git status` to see if any files remain untracked or if additional updates are pending.

:::{tip} Track and Commit a README file
Git repos typically have a README file, which explains what the repo contains, or how to use it. The following steps will create a README file, stage it, and then commit it.

Create a README using `echo`:

```
echo 'Welcome to this new Git repo' > README.md
```

Stage the file with `git add`:

```
git add README.md
```

Finally, commit the file with `git commit`:

```
git commit -m 'adding README file to the new repo'
```
Following the above steps, a response similar to the following will print to the terminal:

```bash
[main (root-commit) b884921] adding README file to the new repo
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
```

The first line states the commit branch, a partial has value (`b884921`)
that is used to track the commit, and then the commit message.
Next, it says how many files have changed and summarizes what has happened (insertions and removals).
Finally, it confirms that the new files have been created in the log and lists the files.
:::

### Git Basics: Connecting to a Remote Project (Basic Collaboration)

To illustrate the "remote" use of Git, this book assumes that the reader is using GitHub. To use GitHub, you need to create an account (free) using an email address. You will need this to log in to track your changes and update them in the remote repository.

#### Creating a linking a remote repo

To connect your local repo to a remote, you need to create a repo in the remote system. In GitHub, you can create a repo with the same name as the local folder. Although you can create a repo with any name, it is easiser to track the connections later if the names are the same or similar.

Once the remote is created, connect the local repo to the remote with the `git remote add` command.

#### Uploading changes to the remote

If you work on your project locally, keep tracking the changes in Git.
When ready, upload, or "push," these changes to the remote. This is done using the `git push` command.

All of these processes are documented and demonstrated in detail in many places online, including at the [Library Carpentry initiative's Git lesson](https://librarycarpentry.github.io/lc-git/), in [GitHub's Git Guides](https://github.com/git-guides), or in GitHub's documentation (for example, [how to connect a remote](https://docs.github.com/en/get-started/git-basics/managing-remote-repositories)), as well as in many other places.

%### Git Intermediate: Using Branches

:::{note}
Although developed to manage source code, many projects now use Git and various platforms that operate remote Git (like GitHub, GitLab, BitBucket, and others) to publish documentation or manage research data and workflows. Here are a few examples:

- The Society of American Archivists uses GitHub to publish and track changes for _Describing Archives: A Content Standard_ (DACS), the standard documenting archival description. Find the [published version of DACS here](https://saa-ts-dacs.github.io/), and the [source GitHub repository here](https://github.com/saa-ts-dacs/saa-ts-dacs.github.io).
- The BitCurator project uses GitHub to publish and collaborate on the maintenance of its documentation of the BitCurator Environment. Find [the published docs here](https://bitcurator.github.io/documentation/) and the [source GitHub repository here](https://github.com/BitCurator/documentation).
- The Library Carpentry project, an initiative of The Carpentries, which supports open educational resources for technical tools of interest to librarians and archivists, maintains its lessons via GitHub. Their lesson on Git, for example, is [readable and accessible as a standalone website](https://librarycarpentry.github.io/lc-git/), but the source is managed through [this GitHub repository](https://github.com/librarycarpentry/lc-git/).

*Challenge:* Find a site that is published and managed using Git and GitHub!
:::

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
