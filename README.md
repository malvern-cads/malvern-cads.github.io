<h1 align="center">
	<img
		width="300"
		alt="CADS"
		src="https://raw.githubusercontent.com/malvern-cads/malvern-cads.github.io/source/themes/cads/source/img/cads_logo.svg?sanitize=true">
</h1>

<h3 align="center">
	The main CADS website and blog
</h3>

<p align="center">
	<strong>
		<a href="https://cadscheme.co.uk/">Website</a>
		•
		<a href="https://cadscheme.co.uk/archives/">Blog</a>
		•
		<a href="https://cadscheme.co.uk/admin">Admin</a>
	</strong>
</p>
<p align="center">
	<a href="https://app.netlify.com/sites/cadscheme/deploys"><img alt="Netlify Build Status" src="https://img.shields.io/netlify/96846975-f8c9-4d17-80d3-a82036581bb7?style=flat-square"></a>
	<a href="https://github.com/malvern-cads/malvern-cads.github.io/actions?query=workflow%3ATest"><img alt="Build Status" src="https://img.shields.io/github/workflow/status/malvern-cads/malvern-cads.github.io/Test/source?style=flat-square"></a>
	<a href="https://github.com/malvern-cads/malvern-cads.github.io/commits/source"><img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/malvern-cads/malvern-cads.github.io/source?style=flat-square"></a>
	<a href="https://github.com/malvern-cads/website/tree/source"><img alt="GitHub Repository Size" src="https://img.shields.io/github/repo-size/malvern-cads/malvern-cads.github.io?style=flat-square"></a>
</p>

<!-- TOC -->

- [Technologies](#technologies)
- [Development](#development)
    - [Requirements](#requirements)
    - [Setup](#setup)
    - [Useful Commands](#useful-commands)
    - [Structure](#structure)

<!-- /TOC -->

---

This is the official website for CADS, containing information about CADS and also a blog with weekly blog posts. The website is located at [cadscheme.co.uk](https://cadscheme.co.uk).

## Technologies

For the CADS website, we have chosen to use [Hexo](https://hexo.io/) which is a [static site generator](https://learn.cloudcannon.com/jekyll/why-use-a-static-site-generator/) which takes templates and posts and combines them into HTML which can then be statically served. This means that we don't have to worry much about hosting because we can very easily host static files on [Netlify](https://www.netlify.com/) (which is the one that we are using at the moment) or [GitHub Pages](https://pages.github.com/) and have the website automatically redeploy once changes are made. This means that we don't have to have people constantly maintaining the website by redeploying it to a server.

This also complicated things for people who don't know how to use Git, Markdown and all of the other technologies that we use. For this reason, we have setup a tool called [Forestry](https://forestry.io/) which allows people to login to an admin page and write articles in a user-friendly way which behind the scenes seamlessly hook into the workflow that we have already setup with Git and Netlify.

## Development

These instructions help you to setup an environment for you to contribute to the website by editing the code directly (not through Forestry). If you are doing this, you want to have a good understanding of how to use Git.

### Requirements

- [Node.js](https://nodejs.org/en/)
- [Yarn](https://yarnpkg.com/lang/en/)
- [Git](https://git-scm.com/)
- A [GitHub](https://github.com/) Account

### Setup

1. Install the Hexo CLI:
	```
	yarn global add hexo-cli
	```
	This installs all of the tools you need for building and running the website on your computer.
2. Install the project dependencies:
	```
	yarn install
	```
	This installs all of the extra dependencies that are required for running the website.

### Useful Commands

- `hexo new post <name>` - creates a new blog post in the `source/_posts` directory using a template.
- `hexo new page <name>` - creates a new page in the `source` directory using a template.

We have a couple of extra scripts that are useful when working with the website:

- **Running tests**. Before committing, you should run tests on your computer which will check the code for spelling mistakes and other problems. Use the command `yarn run test`.
- **Running a development server**. You might also want to run a local version of the website with your changes. Use the command `yarn run preview` and open your browser to <http://localhost:8080/>.

### Structure

- **`scaffolds`** - this contains the templates which are used when running `hexo new post <name>` or `hexo new page <name>`. You probably won't need to edit these.
- **`source`** - this contains all of the 'raw' content such as pages and posts. Posts are stored in the `_posts` folder and pages are stored just in the `source` folder in a directory with the same name.
- **`themes/cads`** - this contains all of the templates that the content is injected into.
	- `layout` contains all of the [EJS](https://ejs.co/) templates which is rendered into HTML.
		- `partials` contain small snippets that are reused often
		- `sidebar` contains the widgets that are shown on the sidebar
		- `layout.ejs` is the **main** template which contains the `<html><head><body>` tags
	- `scripts` contains custom code that is run before rendering the pages. We have one that gets the commit information for the footer.
	- `source` contains static files that don't need to be rendered (e.g. logos, css, js, etc...)
	- `_config.yml` contains theme specific configuration. **You need to update this file after adding pages to put them onto the navigation bar!** Apart from that, this file is not used particularly as this is a custom theme.
- **`_config.yml`** contains site-wide configuration for Hexo. This probably doesn't need to be changed.
- **`.spelling`** contains a list of custom words that override the spell checker.