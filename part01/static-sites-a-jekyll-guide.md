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

The rest of this section walks through the process of setting up a basic Jekyll site.

:::{attention} Prerequisites / Dependencies
This page assumes that you have already set up a blank (or minimal) local Git repository.
It also assumes at the publishing stage that you have a GitHub account and can connect your local repository to a remote repo on GitHub.
In addition, the process assumes that you have installed and can run an up-to-date version of Ruby and Jekyll;
if you are not sure about those steps, consult [this helpful page on installation at the Jekyll documentation]().
:::

## Installing and Setting Up a Blank Jekyll Site

The next sections demonstrate the process of creating and setting up a Jekyll-based site, then publishing it with GitHub.

### Confirm you have the required dependencies

Jekyll runs on Ruby, which is an open source programming language widely used for web applications.
Jekyll requires Ruby, Ruby Gems, and a few other helper programs.
These are all described at the Jekyll documentation under "[Requirements](https://jekyllrb.com/docs/installation/#requirements)".

### Before you use Jekyll, install it

This step installs two "gems," Jekyll and bundler, which will both run to create and serve the site.
If you have already installed Jekyll and bundler, you don't need to do it again.

```
gem install jekyll bundler
```

### Create a New Jekyll site in an Empty Folder

Now you can use Jekyll to create a new directory and set up all the basic elements for your Jekyll site. This will create the basic directory structure and many of the configuration files you need. In this example, you can install at a directory within your current terminal location called "test-jekyll-site" (that is, `./test-jekyll-site`).

```
jekyll new test-jekyll-site
```

### Look around, change, and serve your site

Move to the directory using `cd test-jekyll-site`.

Once there, look for the basic folders, such as `_posts` or `_data`.
Depending on the Jekyll version and theme, you may not see all of the folders.
New pages can be created by copying from the `index.markdown` file
or by creating new markdown or HTML files.

***Tip:*** For any new pages, make sure you add page front matter gated by a three-hyphen line (`---`). You can copy this from existing pages or create your own. Common elements are `title`,
`permalink`, `date`, and `layout`, though every page will vary based on the content type and your site design.

To test your site and "serve" it locally, use the serve command from the terminal:

```{code} ruby
bundle exec jekyll serve
```

If things are working, you should see something like this print to your terminal window:

```{code} bash
:label: serve-jekyll
:caption: A response similar to this will appear when the Jekyll serve command successfully runs.
:linenos:
      Generating... 
       Jekyll Feed: Generating feed for posts
                    done in 0.19 seconds.
 Auto-regeneration: enabled for '/Users/jajohnst/Desktop/si676-assignments-2025'
    Server address: http://127.0.0.1:4000//
  Server running... press ctrl-c to stop.
```

The output contains useful information to review and evaluate your site contents and desing. To view the site, copy and paste the server address ([shown above on line 5](#serve-jekyll)) into a browser's navigation bar, and you should see your site. To stop the site generator, press `Ctrl + C`.

## Add and Configure a Blank Jekyll Site

### Add a Post

### Update the `_config.yml`

### Add a Page

### Add Data

## Publish Your Site

Once the site looks good locally, you can publish it using a GitHub feature called _Pages_. GitHub Pages allows you to publish static HTML files to a unique URL, which will look like a published website, rather than a code repository.

### Set up Pages

### Set up Actions

### Publish: Link your local repo to the remote

## Some Challenges that You Might Encounter

* If you previously published a site in the repository using a file called `index.html`,
  you may find that nothing appears to change when you have started up and configured Jekyll.
  For example if you typed "Hello, World!" on the html page, and you still see plain
  text saying "Hello, World!" than you are likely in this situation.
  The 'old' index file is still publishing to your GitHub Pages site,
  and you should delete the old index file and push the changes to your remote repo.
  Hopefully you'll now see the updated Jekyll site.
* You will probably have `minima` as the default theme. You can change this if you'd like to experiment with the theming aspect of Jekyll. (For the purposes of SI 676, though, we won't work much with theming since Web design is beyond the scope of our course.) However, if you want to make changes in `minima`, or any other "gem based" theme (meaning the files are located in the Ruby package, and referenced when Jekyll builds the site, rather than the files being in your repo directory), [refer to this guide to find out where to find the theme files and how to import them for modification or customization](https://jekyllrb.com/docs/themes/#understanding-gem-based-themes).
* The GitHub Pages guide to Jekyll has useful information about publishing your site to your GitHub repo, and ultimately on how to publish it live to the web. Before you get to that point, however, it may be easier to work from the Jekyll documentation, which offers lightweight ["Quickstart" instructions that are more streamlined and useful for initiating, setting up, serving, and configuring your site locally and for testing prior to publishing](https://jekyllrb.com/docs/).

:::{seealso} More Jekyll Resources
- How to Install Jekyll (locally), [https://jekyllrb.com/docs/installation/](https://jekyllrb.com/docs/installation/)
- Ruby 101 (as much as you need to know), [https://jekyllrb.com/docs/ruby-101/](https://jekyllrb.com/docs/ruby-101/)
- Serve and test your site locally [https://jekyllrb.com/docs/](https://jekyllrb.com/docs/)
- Information on using Jekyll with GitHub pages, [https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll)
:::
