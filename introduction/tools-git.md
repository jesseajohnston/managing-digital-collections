---
title: "Tools: Version Tracking with Git and GitHub"
---

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

:::{tip} Initialize a New Git Repo
To initialize a repo, start with a new directory. In a bash terminal, you can use the `mkdir` command:

```bash
$ mkdir test-test
```

Move the terminal to `test-test`, then run `git init`. The response will look something like this:

```bash
$ git init
Initialized empty Git repository in ~/Desktop/test-test/.git/
```

To learn more about the new repo, run `git status`:

```bash
$ git status
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

This indicates a blank repository.
:::

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

#### Creating and linking a remote repo

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
:::

```{exercise}
:label: git-challenge
**Challenge:** Find a site that is published and managed using Git and GitHub!
```

```{solution} git-challenge
:label:
:class: dropdown
Many sites are published this way. One indicator is a URL that contains `github.io`, which is the default domain for sites published with GH Pages.
Other indicators are a clickable GitHub icon, which may link to the source repo.
Or you may recognize that a site is a Jekyll (or other static site generator) theme or template, then look for its source.  
```

:::{seealso} Additional Git Resources
Want to learn more about Git? A few useful resources to check out:

- The [Library Carpentry initiative's lesson and setup guide for Git](https://librarycarpentry.github.io/lc-git/)
- GitHub Education offers a [one-page "cheat sheet" with common Git operations and commands](https://education.github.com/git-cheat-sheet-education.pdf)
:::
