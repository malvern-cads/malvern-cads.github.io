# 🌐 CADS Website

This is the official website for CADS.

The website is available on the GitHub subdomain at [malvern-cads.github.io](https://malvern-cads.github.io/) and *soon* we might have a FQDN.

## ✔️ Todo

- [ ] Finish theme partials
- [ ] Remove unused theme partials
- [x] Change Hero Image to the Malvern Hills

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

## After making a pull request
It might take a few hours up to a couple of days for your pull request to get reviewed. Once it has, the site will be automatically rebuilt with your changes.