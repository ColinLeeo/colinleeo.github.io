# Personal Blog Initialization Design

## Context

The repository is a source fork of `cotes2020/jekyll-theme-chirpy`. It is on
the stable Chirpy `v7.6.0` release and currently contains the upstream theme's
sample configuration, demo posts, maintainer automation, and placeholder About
page. The repository is published as `ColinLeeo/colinleeo.github.io` and should
become Colin Lee's English technical blog and personal homepage.

## Goals

- Turn the source fork into a deployable personal site while preserving its
  relationship with the Chirpy theme upstream.
- Present Colin Lee's work under a clear data-systems identity.
- Keep the initial site intentionally small and easy to maintain.
- Verify the generated site locally before updating the public `master` branch.

## Non-goals

- Creating a first blog post or importing existing writing.
- Adding custom layouts, components, or visual redesigns.
- Enabling comments, analytics, page views, or social networks other than
  GitHub.
- Copying the full GitHub Profile README into the site.

## Chosen Approach

Initialize the existing full-source fork in place rather than replacing it with
`chirpy-starter`. This preserves the repository history and the `theme` remote,
supports future source-level customization, and follows Chirpy's documented
upgrade path for source forks. Future upgrades will fetch upstream release tags
and merge a selected stable release, resolving conflicts only where the site has
intentional customizations.

The work will happen on `feature/personal-blog`. Nothing will be pushed to the
public `master` branch until the site builds and validates successfully.

## Repository Initialization

Use Chirpy `v7.6.0`'s initialization flow on the clean feature branch. The flow
will:

- retain the full theme source;
- remove the four upstream demo posts;
- remove theme-maintainer issue templates and workflows;
- place the GitHub Pages deployment workflow at
  `.github/workflows/pages-deploy.yml`;
- build and track the generated theme CSS and JavaScript assets;
- retain the standard Chirpy tabs, including a customized About page.

The initialization script performs a hard reset and cleans untracked files.
This is acceptable only because the branch starts at the verified `v7.6.0` tag,
the worktree is clean, and the repository contains no personal posts or other
uncommitted site content. The operation will stop if those preconditions are no
longer true.

## Site Identity and Configuration

The initial `_config.yml` values will be:

| Setting | Value |
| --- | --- |
| Language | `en` |
| Timezone | `Asia/Shanghai` |
| Title | `Colin Lee` |
| Tagline | `Exploring data systems, from storage engines to distributed and AI workloads.` |
| Description | `Notes on data systems, storage engines, distributed systems, AI/ML workloads, and open-source engineering.` |
| URL | `https://colinleeo.github.io` |
| Base URL | empty |
| GitHub username | `ColinLeeo` |
| Social name | `Colin Lee` |
| Social links | `https://github.com/ColinLeeo` only |
| Avatar | `https://github.com/ColinLeeo.png` |
| Theme mode | follow the visitor's system preference |

The sample CDN and sample social identities will be removed. Email, Twitter,
comments, analytics, page views, and webmaster verification will remain unset.
PWA support and the table of contents will retain the Chirpy defaults.

## About Page

The About page will be a concise English introduction rather than a copy of the
GitHub Profile README. It will:

- identify Colin Lee as working on data systems;
- mention storage engines, distributed systems, AI/ML workloads, and
  open-source engineering;
- point readers to the GitHub profile for current projects, experience, and
  activity.

It will avoid time-sensitive education or employment claims so that it remains
accurate without frequent duplication of the GitHub profile.

## Repository Documentation

Replace the upstream theme-maintainer README with a short site README that
documents:

- the purpose and public URL of the repository;
- the Chirpy version and upstream relationship;
- local dependency, build, preview, and validation commands;
- the Markdown post location and filename convention;
- the stable-release upgrade workflow.

## Build and Deployment

Local verification will use Ruby 3.4 to match the GitHub Pages workflow and the
repository's existing Node.js toolchain. The validation sequence is:

1. Initialize the `assets/lib` submodule and install Node dependencies.
2. Run `npm run build` to generate the theme assets.
3. Install Ruby dependencies.
4. Build the production Jekyll site.
5. Run HTML link and structure validation against the generated `_site`.
6. Inspect the generated home and About pages for the configured identity and
   absence of demo content.

After validation, commit the personalized site, fast-forward `master` to the
feature branch, push `origin/master`, and verify the GitHub Pages workflow. The
workflow will deploy only from `main` or `master` and will use GitHub's Pages
artifact deployment mechanism.

## Failure Handling and Recovery

- Initialization or dependency failures will be fixed on the feature branch;
  the public branch remains unchanged.
- A failing build or HTML validation blocks merging and pushing.
- Generated build directories and dependency caches remain ignored unless
  Chirpy explicitly requires particular compiled assets to be tracked.
- The pre-initialization state remains recoverable through the `v7.6.0` tag and
  the existing `origin/master` reference until the final push.

## Acceptance Criteria

- The site builds successfully using the same Ruby major/minor version as CI.
- The generated site is English and displays the agreed title, tagline, avatar,
  description, GitHub link, and concise About content.
- No Chirpy demo posts, placeholder identities, or theme-maintainer workflows
  remain in the published site repository.
- Comments and analytics are disabled.
- `feature/personal-blog` contains only intentional initialization and
  personalization changes.
- `origin/master` is updated only after all local validation passes.
