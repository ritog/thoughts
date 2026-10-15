# Thoughts

A Quarto blog published at <https://ritoghosh.com/thoughts/>.

It is a separate GitHub Pages **project site** under the custom domain used by
[`ritog/ritog.github.io`](https://github.com/ritog/ritog.github.io). Do not add
a `CNAME` file to this repository: the user site owns `ritoghosh.com`, and this
project is served beneath it at `/thoughts`.

## Write a post

Each published post lives in a top-level directory named after its URL slug:

```text
my-post/
└── index.qmd
```

For example:

```yaml
---
title: "My post"
description: "A short summary used by the listing and social cards."
author: "Rito Ghosh"
date: "2026-03-07"
categories: [notes]
title-block-banner: true
---

Post content goes here.
```

That file is published at:

```text
https://ritoghosh.com/thoughts/my-post/
```

Post directories intentionally live at the repository root rather than under a
`posts/` directory. Quarto preserves source paths in the rendered site, so this
layout avoids URLs such as `/thoughts/posts/my-post/`.

The included `thoughts-about-this-site/index.qmd` is a starter post. Edit it,
replace it, or use it as the template for another post.

## Preview locally

Install [Quarto](https://quarto.org/) 1.10.18 or newer, then run:

```sh
quarto preview
```

To create the production output in `_site/`:

```sh
quarto render
```

## Enable publishing

The workflow in `.github/workflows/publish.yml` renders pull requests and
publishes pushes to `master` on the `gh-pages` branch.

After pushing the initial commit:

1. Open **Settings → Actions → General → Workflow permissions** and allow
   **Read and write permissions** if the repository does not allow the workflow
   token to write by default.
2. Let the **Publish Quarto site** workflow create the `gh-pages` branch.
3. Open **Settings → Pages** and choose **Deploy from a branch**.
4. Select the `gh-pages` branch and `/ (root)`, then save.

GitHub first exposes the project as `https://ritog.github.io/thoughts/`. Because
the user site already uses `ritoghosh.com`, the corresponding custom-domain URL
is `https://ritoghosh.com/thoughts/`.

## Theme

The light/dark themes, Courier Prime body font, Cascadia Code code font, and
KaTeX setup mirror the configuration in `ritog/ritog.github.io`.
