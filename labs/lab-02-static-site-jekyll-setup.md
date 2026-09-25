---
title: "Setting Up a Jekyll Site"
---

_**NOTE:** If you already published your site during class, there may not be much to complete for this section._

This lab activity accompanies the [Guide to Getting Started with Static Sites](/part01/static-sites-a-jekyll-guide.md).

## Task 1: Set Up Jekyll and Publish Your Site

_**NOTE:** The workflow outlined here differs from the steps outlined on GitHub's pages. These are, nonetheless, functionally the same process. You can use either sequence of steps to accomplish the task._

1. Create a new folder/directory on your local computer. This will be the location you use for building and developing your Jekyll site. It's likely you won't want to keep this around long term, so give it a name like `jekyll-test-site-1` (or something similarly generic)
1. Initiate Jekyll in your local folder. To do this, navigate your command prompt to the folder you just created (use the `cd`) command. Then, create your Jekyll shell using the command `jekyll new --skip-bundle .`. This will create the Jekyll site within the current directory.
3. Configure your Jekyll site:
  * Visit the `_config.yml` file, change the site name, description, and contact information.
  * Add at least one page (preferably modify the `index.markdown` or `about.markdown`): see <https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-content-to-your-github-pages-site-using-jekyll#adding-a-new-page-to-your-site>
  * Add at least one "post" (more like a blog site): <https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-content-to-your-github-pages-site-using-jekyll#adding-a-new-post-to-your-site>
4. To see how your site looks and if things are working, run `bundle exec jekyll serve` and paste the provided location and port and in your browser's navigation bar. 

## GitHub Pages

Once you have a working Jekyll-based site, you can publish it as a live website using GitHub's "Pages" settings.
Follow these steps to set up a new GitHub repository and connect it to a repo on your local machine.

1. Create a Git repo in the folder where your site is already working (run `git init`). Stage all of the files (run `git add .` or `git add *.*`), and then commit the files to the repo (run `git commit -m "adding initial jekyll site files`).
2. Next, set up a new GitHub repository, which you will connect to the repo on your local machine. For ease of management, I suggest naming this repo the same thing as the folder where your Jekyll template site was created. Connect the local to the remote (use a command like `git add origin <URL to your GitHub repo>`). Then, push the files (run `git push -u origin main`).
2. Activate GitHub pages for the repo you've created (see <https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site#creating-your-site>). NOTE: My recommendation is to use the GitHub Actions workflow (for most cases, you can use the default `.yml` configuration file that GitHub will offer to you).
4. Invite GitHub user `@morskyjezek` to your repo as a collaborator.
5. To complete the assignment, please provide the URL to the live Jekyll site with your changes.

### Additional Resources
  
  * How to Install Jekyll (locally), [https://jekyllrb.com/docs/installation/](https://jekyllrb.com/docs/installation/)
  * Ruby 101 (as much as you need to know), [https://jekyllrb.com/docs/ruby-101/](https://jekyllrb.com/docs/ruby-101/)
  * Serve and test your site locally [https://jekyllrb.com/docs/](https://jekyllrb.com/docs/)
  * Information on using Jekyll with GitHub pages (follows a slightly different workflow but accomplishes the same task of setting up and publishing a Jekyll static site) <https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll> - choose options for your operating system!
