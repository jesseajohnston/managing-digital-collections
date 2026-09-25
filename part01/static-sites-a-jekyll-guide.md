---
title:  "Getting Started with Static Sites"
---

This book illustrates digital collections management through multiple tasks and projects that
help you to set up a site using an open source frameworks.
The first of these is called Collection Builder, which uses a "static site" framework to publish
collections to a website. The architecture of static sites will be discussed more in [Part 3](/part03/index.html).

For now, the Jekyll framework for publishing a static site serves as an illustration of open source software.
Like many open source projects, Jekyll relies on a series, or _stack_, of other open source tools.
Setting up a basic Jekyll site illustrates how the framework functions,
and as you work toward setting up Collection Builder, this will be helpful knowledge.
Both Jekyll, and Collection Builder, draw on the open-source programming language called [Ruby](https://www.ruby-lang.org/en/),
a widely used language for web and app programming.

Once the stack is set up, both Jekyll and Collection Builder publish fully formed websites on a "static site" architecture.
This means that you write all of the content, usually in plain text or data files (like CSV and JSON),
then the site generator creates HTML that can be displayed by browsers on the web. That content is served to the web by a publishing platform (in our case, GitHub) without any direct server configuration or maintenance.
While you can add data files to a site, there is no underlying database, and all the pages
are generated in advance, none are generated on demand (that's what makes it "static").

The next sections demonstrate the process of creating and setting up a Jekyll-based site, then publishing it with GitHub.

:::{attention} Prerequisites / Dependencies
This page assumes that you have already set up a blank (or minimal) local Git repository.
It also assumes at the publishing stage that you have a GitHub account and can connect your local repository to a remote repo on GitHub.
In addition, the process assumes that you have installed and can run an up-to-date version of Ruby and Jekyll;
if you are not sure about those steps, consult [this helpful page on installation at the Jekyll documentation](https://jekyllrb.com/docs/installation/).
:::

## Installing and Setting Up a Blank Jekyll Site

This section begins with the process of setting up a basic Jekyll site,
which you can run and test locally.

### Confirm you have the required dependencies

Jekyll runs on Ruby, which is an open source programming language widely used for web applications.
Jekyll requires Ruby, Ruby Gems, and a few other helper programs.
These are all described at the Jekyll documentation under "[Requirements](https://jekyllrb.com/docs/installation/#requirements)".

### Confirm or Install Jekyll

This step installs two "gems," Jekyll and bundler, which will both run to create and serve the site.
If you have already installed Jekyll and bundler, you don't need to do it again. The following command will install both tools:

```
gem install jekyll bundler
```

### Create a New Jekyll site in an Empty Folder

Now you can use Jekyll to create a new directory and set up all the basic elements for your Jekyll site. This will create the basic directory structure and many of the configuration files you need. In this example, you can install at a directory within your current terminal location called "test-jekyll-site" (that is, `./test-jekyll-site`).

```
jekyll new test-jekyll-site
```

### Look around Your Site

Move to the directory using `cd test-jekyll-site`. When you view the structure, you will see something like [the directory structure schematic shown below](#jekyll-basic-structure).

```{code} bash
:label: jekyll-basic-structure
:caption: The basic files and folder structure created by the `jekyll new .` command when run in a a blank directory.
.
├── _config.yml
├── _posts
│   └── 2026-09-24-welcome-to-jekyll.markdown
├── 404.html
├── about.markdown
├── Gemfile
├── Gemfile.lock
└── index.markdown
```

Take a look around at structure that Jekyll has created.
In the basic default Jekyll structure, you will note one directory called `_posts`.
This directory contains files that generate "posts," which are displayed in reverse chronological order by date.
The default site contains a basic post dated when the `new` command was run.
The post is a markdown file, titled with the date and the post title in [kebab case](wiki:kebab_case) (here, "Welcome to Jekyll", see [the sample code from the beginning of the default post below](#jekyll-basic-post)).

```{code} markdown
:label: jekyll-basic-post
:caption: The first thirteen lines of the default "Welcome to Jekyll" post, here dated on 24 September 2026.
:linenos:
:emphasize-lines: 1-6
---
layout: post
title:  "Welcome to Jekyll!"
date:   2026-09-24 21:30:00 -0400
categories: jekyll update
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.
```

Note the post structure follows a pattern that is standard for Jekyll content pages: the first lines (in [](#jekyll-basic-post), lines 1&ndash;6) contain metadata, and the following lines contain the page content.
The content is formatted in markdown, which is rendered in HTML by Jekyll.

In the main directory, you will see files that generate the main site pages. These include `about.markdown` and `index.markdown`. Inspecting these files, note the standard file metadata, and the content of each page. Note that the `index.markdown` page displays at the site root when served, while the `about.markdown` is a similar page but appears in teh site's navigation menu. **Note:** the files that begin with `Gemfile` pertain to Ruby dependencies.
New pages can be created by copying from the `index.markdown` file
or by creating new markdown or HTML files.

:::{important} Don't forget page metadata
For any new pages, make sure you add page front matter gated by a three-hyphen line (`---`). You can copy this from existing pages or create your own. Common elements are `title`,
`permalink`, `date`, and `layout`, though every page will vary based on the content type and your site design.

Basic metadata is illustrated in [the post code sample above, lines 1&ndash;6](#jekyll-basic-post).
:::

### Serve Your Site Locally

As you develop the site and add content, you can "serve" it locally,
meaning that you can see how the site looks before you publish it to the public web.
To test your site and "serve" it locally, use the serve command from the terminal:

```{code} ruby
bundle exec jekyll serve
```

If things are working, you should see something like this print to your terminal window:

```{code} bash
:label: serve-jekyll
:caption: A response similar to this will appear when the Jekyll serve command successfully runs.
:linenos:
:emphasize-lines: 5
      Generating... 
       Jekyll Feed: Generating feed for posts
                    done in 0.19 seconds.
 Auto-regeneration: enabled for '/Users/jajohnst/Desktop/si676-assignments-2025'
    Server address: http://127.0.0.1:4000//
  Server running... press ctrl-c to stop.
```

The output contains useful information to review and evaluate your site contents and desing. To view the site, copy and paste the server address ([shown above on line 5](#serve-jekyll)) into a browser's navigation bar, and you should see your site. To stop the site generator, press `Ctrl + C`.

## Configure and Add Content in a Blank Jekyll Site

This section illustrates some of the basic set up tasks that you may want to undertake,
including configuration of site information, adding new content (posts and pages),
adding data files, and basic techniques for data display.

### Add site information (updating `_config.yml`)

The `_config.yml` file contains all of the information that is used to control preferences for the entire site.
As such, there are many options. This section only investigates a few changes, which will customize the site
title, creator information, and the description. 

The `_config.yml` file is writte in YAML, which is a general `key: value` structure.
Sub-properties are indicated by indentation. Below is a [snippet of principal site information from the config file](#jekyll-sample-config).
These fields may be modified to include a site name, creator, and description.
The values inserted in the config will appear in many places throughout the site. 

```{code} yaml
:label: jekyll-sample-config
:caption: A simple config file, which specifies a title, description, and creator inforamtion for an imagined Jekyll site.
:linenos:
# Site settings
# These are used to personalize your new site. If you look in the HTML files,
# you will see them accessed via {{ site.title }}, {{ site.email }}, and so on.
# You can create any custom variable you would like, and they will be accessible
# in the templates via {{ site.myvariable }}.

title: Your awesome title
email: your-email@example.com
description: >- # this means to ignore newlines until "baseurl:"
  Write an awesome description for your new site here. You can edit this
  line in _config.yml. It will appear in your document head meta (for
  Google search results) and in your feed.xml site description.
```

### Add a Post

Posts are intended for blog-like content, which might be added frequently or for which sorting by date is a primary concern.
Post can be categorized using keywords, called categories and tags.
Posts are generally composed in markdown. The files are stored in the `_posts` directory, and they are usually titled using date and the basic title. Although [basic text from the default post is offered above](#jekyll-sample-post), here is a sample idea for a planet page named `2026-09-25-mars.md`.

```{code} markdown
---
layout: post
title: Mars
author: Jesse Johnston
---
This page is about Mars, the red planet.
```

### Add a Page

Pages, which in the default `minima` theme appear in the main navigation bar,
may be composed in HTMl or markdown, and they appear in the top level of the directory.
Note that page files can be grouped in another directory for ease of organization in large sites,
but in general these pages are stored at the top level. Recall that every page requires content metadata to display.

A sample "Planet List" page appears in the [code sample below](#jekyll-sample-page):

```{code} markdown
:label: jekyll-sample-page
:caption: Sample markdown code for a basic page. This might be saved in a file named `about.md`.
---
layout: page
title: Planets List
date: 2026-09-25
---

This page provides information about the extensive planet list documented on this site! 
```

### Add Data

Data can be added in tabular formats like CSV or text formats like JSON. Data files are often used to provide support for list-like things, including navigation menus, personnel lists, and much more.
To add data, it must be placed in the `_data` folder. Data files are then referenced using a basic dot notation,
like `site.data.data-file-name-without-extension`.
If you were creating a list of planet attributes, for example, you might create the following in a `_data/planets-list.csv` file:

```{code} csv
:label: jekyll-sample-data
:caption: A basic CSV file for a list of data about two planets. The first line is a list of column headers.
:linenos:
name,atmosphere,color
earth,oxygen-nitrogen,blue
mars,,red
```

### Display data with an include

Layouts and page snippets can be modified through the `_layouts` and `_includes` directories, respectively.
The layout feature offers a sophisticated templating system for different types of content display,
which is selected using the `layout:` attribute in page or post metadata. In most themes, the `post` and `page` layouts are included.

Rather than getting into layout here, we will only look at the `include` feature. This Jekyll feature allows
for the creation of snippets or page sections, which can be composed in HTML or markdown, and then inserted
into a specific page using an include shortcut. Let's take a closer look.

Includes and layout can insert data variables using a templating language called [liquid](https://shopify.github.io/liquid/).
In basic use, liquid tags allow for logic control, variable assignment, and even basic data processing in some cases.
A liquid tag expression is indicated by a set of curly braces with percent symbols in between,
such as `{% liquid_expression_here %}`. Data variables can be directly inserted by typing their name
in between a set of curly braces, such as `{{ item.variable-value }}`.

Putting this all together, you might aim to create a list of the planets in your dataset,
which could be output as a list or table. The following code would produce those elements.
Include files are snippets, so they do not need gated metadata, and they may be composed in HTML or markdown.

```{code} liquid
:label: jekyll-basic-include
:caption: Example of an _include_ snippet, which references the site planet list data file, then outputs each row in a list and table.
:linenos:
<!-- display an unordered list of the planet data -->
<ul>
{% for planet in site.data.planet-list %}
  <li><strong>{{ planet.name }}</strong> has color {{ planet.color }}</li>
{% endfor %}
</ul>

<!-- display a table of the planet data -->
<table>
    <thead><th>Planet</th><th>Atmosphere</th><th>Color</th></thead>
    <tbody>
        {% for planet in site.data.planet-list %}
        <tr>
            <td>{{ planet.name }}</td>
            <td>{% if planet.atmosphere %}{{ planet.atmosphere }}{% endif %}</td>
            <td>{{ planet.color }}</td>
        </tr>
        {% endfor %}
    </tbody>
</table>
```

:::{seealso} Many ways to use Data files
The above approach to use an include template for publishing your data is only one way to do this.
Data files may also be referenced in page layout templates, pages, posts, and probably elsewhere.
They are great for publishing tables, lists, or creating series of posts that have consistent content.
More [information about using data files can be found at the Jekyll documentation](https://jekyllrb.com/docs/datafiles/).
:::

## Publish Your Site

This section describes how to publish your site so it is available on the Web!
Once the site looks good locally, you can publish it using a GitHub feature called _Pages_. GitHub Pages allows you to publish static HTML files to a unique URL, which will look like a published website, rather than a code repository.

### Set up GitHub Pages

### Set up an Actions Workflow

To notify your GitHub repo that you want it to publish the site when you push updates,
set up a GitHub Actions workflow. This is a special YAML file, which GitHub will generate for you,
which is contained in the invisible `.github/workflows/` directory, as shown below in [](#fig-gh-actions).

```{figure} /assets/part02-github-actions-deploy.png
:label: fig-gh-actions
:alt: Screenshot of suggested default Actions workflow created by GitHub when the Pages feature is set up.

Screenshot of suggested default Actions workflow created by GitHub when the Pages feature is set up.
```

### Configure Gemfile for GH Pages

Although your site may look fine when serving locally, GitHub has a different process of referencing different elements of the Jekyll ruby gem packages. To ensure that your site publishes correctly,
[update the Gemfile as noted in the comments](#jekyll-update-gemfile-to-publish); in essence, deactivate (comment out with a `#`) line 10
and activate (uncomment) line 15. You may now have to run `bundle update github-pages`
in your Jekyll site's directory for your site to serve locally.

:::{code} ruby
:label: jekyll-update-gemfile-to-publish
:caption: Modify the default `Gemfile` according to the instructions in the comments; your file should be similar to what appears in this example.
:linenos:
:emphasize-lines: 10,15
source "https://rubygems.org"
# Hello! This is where you manage which Jekyll version is used to run.
# When you want to use a different version, change it below, save the
# file and run `bundle install`. Run Jekyll with `bundle exec`, like so:
#
#     bundle exec jekyll serve
#
# This will help ensure the proper Jekyll version is running.
# Happy Jekylling!
# gem "jekyll", "~> 4.4.1"
# This is the default theme for new Jekyll sites. You may change this to anything you like.
gem "minima", "~> 2.5"
# If you want to use GitHub Pages, remove the "gem "jekyll"" above and
# uncomment the line below. To upgrade, run `bundle update github-pages`.
gem "github-pages", group: :jekyll_plugins
:::

### Update `baseurl` and `url`

Finally, to help Jekyll ensure that it can make correct references between the published site and necessary files, like CSS for styles and other related assets, [update](#jekyll-update-baseurl) the `baseurl` and `url` information in `_config.yml`.
While these are not needed to serve locally, GitHub pages needs them.
Note that when you serve the site locally, the `localhost` URL will now include `planets-test/` (or the name of your base URL) in the address.

:::{code}
:label: jekyll-update-baseurl
:caption: Update the `baseurl` and `url` variables so that Jekyll can create correct references between pages on the site when it goes live.
baseurl: "/planets-test" # the subpath of your site, e.g. /blog
url: "https://managing-digital-collections.github.io" # the base hostname & protocol for your site, e.g. http://example.com
:::

Now, the repo is ready to push to GitHub!
When the publication workflow completes successfully, you'll find your new site serving at the `github.io` domain (see [](#jekyll-add-gh-pages-url)) for the project! 🤞

### Publish: Push your local repo to the remote

To publish your site, push from the local repository to the remote.
When the push arrives on the branch specified in the Pages Actions publication workflow,
the site will update.
If you visit your repo on GitHub, you will see the status of the publication workflow.
If there is a yellow circle (🟡) next to the commit, then the workflow is still in progress.
If a green check mark (✅) displays, the workflow has completed successfully.
Shortly, the updates will be live on the web.
If a red cross mark (❌) displays, then the workflow has stopped without completing, and further investigation will be required.

:::{figure} /assets/part02-github-about-add-url.png
:label: jekyll-add-gh-pages-url

The form that displays when you select the repo's "About" settings. To automatically include the correct `github.io` URL for the project, click "Use your GitHub Pages website".
:::

## Some Challenges that You Might Encounter

Although there are many problems that you may encounter in the static site setup process,
here are a few that have been noted multiple times in the recent past:

- If you previously published an `index.html` in your repository, you may find that nothing appears to change when you have started up and configured Jekyll. For example if you typed "Hello, World!" on the html page, and you may still see plain text saying "Hello, World!" In this case, the 'old' index file is still publishing to your GitHub Pages site. You should delete the old index file, commit, and push the changes to your remote repo. You should see the updated Jekyll site once the publication workflow has finished running.
- The default Jekyll theme is called `minima`. You can change this if you'd like to experiment with the theming aspect of Jekyll. (For the purposes of SI 676, though, we won't work much with theming since Web design is beyond the scope of our course.) However, if you want to make changes in `minima`, or any other "gem based" theme (meaning the files are located in the Ruby package, and referenced when Jekyll builds the site, rather than the files being in your repo directory), [refer to this guide to find out where to find the theme files and how to import them for modification or customization](https://jekyllrb.com/docs/themes/#understanding-gem-based-themes).
- When you update to publish using GitHub pages, you may need to clear the earlier `Gemfile.lock` file. That file shows all of the current dependencies that the `bundle` command runs when it builds the jekyll site. Updating to the `github-pages` gem can create incompatibilities with other gem versions. To remove these, delete the old lock file, then run `bundle clean --force` and, to update the gem dependencies and create a new lock file, run `bundle install` again. This will update the packages for GH Pages deployment.
- The GitHub Pages guide to Jekyll has useful information about publishing your site to your GitHub repo, and ultimately on how to publish it live to the web. Before you get to that point, however, it may be easier to work from the Jekyll documentation, which offers lightweight ["Quickstart" instructions that are more streamlined and useful for initiating, setting up, serving, and configuring your site locally and for testing prior to publishing](https://jekyllrb.com/docs/).

:::{seealso} More Jekyll Resources
- How to Install Jekyll (locally), [https://jekyllrb.com/docs/installation/](https://jekyllrb.com/docs/installation/)
- Ruby 101 (as much as you need to know), [https://jekyllrb.com/docs/ruby-101/](https://jekyllrb.com/docs/ruby-101/)
- Serve and test your site locally [https://jekyllrb.com/docs/](https://jekyllrb.com/docs/)
- Information on using Jekyll with GitHub pages, [https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll)
:::
