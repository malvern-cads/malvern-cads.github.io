# 🌐 CADS Website

[![GitHub last commit](https://img.shields.io/github/last-commit/malvern-cads/website/source.svg)](https://github.com/malvern-cads/website/commits/source) [![GitHub Actions Status](https://github.com/malvern-cads/website/workflows/Test%20Workflow/badge.svg)](https://github.com/malvern-cads/website/actions) [![GitHub Repository Size](https://img.shields.io/github/repo-size/malvern-cads/website.svg)](https://github.com/malvern-cads/website/tree/source)

<!-- TOC -->

- [🧱 Structure](#🧱-structure)
- [🎨 Custom Theme](#🎨-custom-theme)
    - [Structure](#structure)
- [🍀 Contributing](#🍀-contributing)
    - [Editing in your browser](#editing-in-your-browser)
    - [Editing using Dev Tools](#editing-using-dev-tools)
    - [After making a pull request](#after-making-a-pull-request)

<!-- /TOC -->

---

This is the official website for CADS, containing a little bit of information about CADS and also a blog with posts from weekly meeting writeups. The website is located at [cadscheme.co.uk](https://cadscheme.co.uk).

The website is powered by a static site generator [Hexo](https://hexo.io) which takes a bunch of templates and 'raw' content and combines them into a website. This makes the website easy to manage and simplifies things a bit.

## 🧱 Structure

As with all [Hexo](https://hexo.io) sites, there is 3 main directories:

* **`scaffolds`** where all the 'templates' for blog posts and pages are stored. These templates include placeholders for things like the date and title to be inserted.
* **`source`** where the 'raw' posts and pages are held. All these 'raw' posts and pages are written using Markdown, which is then converted to HTML and inserted into the theme once the site is generated.
* **`themes`** where all the site's HTML, CSS and JS is contained. In the `themes` folder there is a folder for each of the installed themes.

## 🎨 Custom Theme

This site uses a custom built theme which is in the themes folder (`themes/cads`).

### Structure

My custom theme is split up into 3 folders:

* **`layout`** where all of the HTML is contained, however, this isn't plain old HTML and is actually [EJS](https://ejs.co/). [EJS](https://ejs.co/) is an 'Embedded JavaScript templating' language which is essentially HTML with special tags (starting with `<%`) that let you embed server-side JavaScript. This server-side JavaScript allows us to insert the content from our `source` folder and insert them in.
  * **`_partial`** are smaller, reusable bits of EJS code. There is a couple of files for things that are used over a lot of the pages such as the footer, navigation bar, etc..
* **`scripts`** which are JavaScript files that get included in the build process. There is a file in there called `gitinfo.js` which is a little helper file which gets the current Git commit (which is shown in the footer).
* **`source`** which contains 'raw' files that are just placed into the generated code. There is some CSS and images in here which just get put into the root directory of the built website.

## 🍀 Contributing

First up, your're going to want to **fork** this repository. You can get more help on forking [here](https://help.github.com/articles/fork-a-repo/).

### Editing in your browser

If you're making a small change like adding or changing content you can do it all in your browser.

Simply go to your GitHub profile, and on the repositories tab, click on `malvern-cads.github.io`.

Once you're in the repository, open up the file you want to edit by clicking on it and then make your changes and save. You'll then need to make a **pull request** which you can find more help on [here](https://yangsu.github.io/pull-request-tutorial/).

### Editing using Dev Tools

Hexo Tools require [Node.js](https://nodejs.org/en/), you'll need to download and install the version suitable for your operating system and architecture.

Next install the tools by running:
```
npm install -g hexo-cli
```

Then open up the repository on your computer (you may want to use a tool like [GitHub Desktop](https://desktop.github.com/)).

Now open up the repository in a terminal and execute the commands to install everything required:
```
npm install
```

Then you can use the following commands:

| Command | Description |
| ------- | ----------- |
| `hexo server` | **Start a live server** so that you can see what your changes are doing. *Usually at `localhost:4000`.* |
| `hexo new post <name>` | **Make a new blog post in `source/_posts`.** Make sure that the name is lowercase. Posts are written in Markdown. |
| `hexo new page <name>` | **Make a new page in `source/_posts`.** Make sure that the name is lowercase. Pages are written in Markdown. Pages can be added to the navigation menus by editing `themes/cads/_config.yml` and adding a node to `nav`. |

### After making a pull request
It might take a few hours up to a couple of days for your pull request to get reviewed. Once it has, the site will be automatically rebuilt with your changes.