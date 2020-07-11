---
title: This blog
date: 2020-06-08 12:19:00
tags:
- hexo
- blog
---

## Setup

This blog was created using [Hexo](https://hexo.io) and is hosted on GitHub pages.
I used this [tutorial](https://gist.github.com/btfak/18938572f5df000ebe06fbd1872e4e39) and the [Cactus](https://github.com/probberechts/hexo-theme-cactus) theme.

### Deploy
Instead of using hexo-deployer-git for deploying to GitHub Pages, I defined /docs to be the public folder for the site. This enables the source and the generate site to be in the same repository. A tutorial can be found [here](https://www.poweredbyjeff.com/2018/05/14/Deploying-Hexo-website-to-Github-Pages/).

### Domain
Bought from [namecheap](https://www.namecheap.com/). Setup described [here](https://richpauloo.github.io/2019-11-17-Linking-a-Custom-Domain-to-Github-Pages/).

### Icons
Icons made by [Freepik](https://www.flaticon.com/authors/freepik) from [flaticon.com](https://www.flaticon.com/").

## Quick Start

### Writing

Create a draft
```bash
hexo new draft "My Draft"
```

Publish a draft
```bash
hexo publish "My Draft"
```

Create a new post
```bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

### Run server

``` bash
$ hexo server --draft
```

More info: [Server](https://hexo.io/docs/server.html)

### Deployment

Generate static files
``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

Generate and deploy site
``` bash
$ npm run deploy
```

More info: [Deployment](https://hexo.io/docs/one-command-deployment.html)