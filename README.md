# Colin Lee

Source for [colinleeo.github.io](https://colinleeo.github.io), an English
technical blog and personal homepage focused on data systems.

The site uses [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) and
keeps the theme source in this repository. The current baseline is Chirpy
`v7.6.0`; the `theme` Git remote tracks the upstream project.

## Local development

Requirements:

- Ruby 3.4 (the repository includes a `.ruby-version` file)
- Node.js 24 LTS and npm

Initialize the static-assets submodule and install dependencies:

```console
git submodule update --init --recursive
npm install
npm run build
bundle install
```

Start the local development server:

```console
bundle exec jekyll serve
```

Build and validate the production site:

```console
JEKYLL_ENV=production bundle exec jekyll build
bundle exec htmlproofer _site --disable-external
```

## Writing

Posts live in `_posts` and use the filename format
`YYYY-MM-DD-title.md`. Each post starts with Jekyll front matter:

```yaml
---
title: Post title
date: YYYY-MM-DD HH:MM:SS +0800
categories: [Category]
tags: [tag]
---
```

## Deployment

Pushes to `master` trigger `.github/workflows/pages-deploy.yml`. The workflow
builds the site and deploys the generated artifact to GitHub Pages.

## Updating Chirpy

Fetch the upstream tags and merge a selected stable release:

```console
git fetch theme --tags
git merge <version-tag>
npm install
npm run build
bundle update
```

Resolve conflicts in favor of intentional site customizations, rebuild the
site, and validate it before pushing the upgrade.
