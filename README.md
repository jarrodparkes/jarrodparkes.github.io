# JarrodParkes.com

This is the repository for [https://jarrodparkes.github.io/](https://jarrodparkes.github.io/).

## Style

The visual style is modeled on the editorial, newspaper-like look of [Ballotics](https://ballotics.com/): a warm paper background, ink-black serif display type with italic accents, monospaced uppercase labels, thin rules, and double-rule section breaks. The structure and wording of the site (posts, reviews, presentations) are unchanged; only the presentation is different.

The site was originally built on the [vida jekyll theme](https://github.com/syaning/vida). Its files were copied into this repository long ago, and they have since been restyled, so vida is now only the starting point.

## How the theme is applied

The theme isn't a gem or a `remote_theme`. It is made up of the standard Jekyll folders in this repository, so to change the look you edit these files directly:

| Path | Role |
| --- | --- |
| `_layouts/default.html` | Page shell: dateline, masthead and navigation, footer, font loading |
| `_layouts/post.html`, `review.html`, `presentation.html` | Article pages; each wraps itself in `default` |
| `_layouts/page.html` | Standalone pages such as `404.md` |
| `_includes/post-header.html` | Article header (type label, date, title, location, tags) |
| `_includes/entry.html` | One row in a list of posts, reviews, or presentations |
| `index.html`, `reviews.html`, `presentations.html` | Listing pages built from `site.posts` |
| `_sass/_variables.scss` | Design tokens: fonts, colors, sizes, widths |
| `_sass/_base.scss` | Element defaults (body, links, headings, tables, code) |
| `_sass/_layout.scss` | Masthead, hero, entry rows, articles, footer, mobile rules |
| `_sass/_syntax.scss`, `_sass/_custom.scss` | Code highlighting colors |
| `css/main.scss` | Sass entry point |

How the pieces fit together in Jekyll:

- Each file in `_posts/` sets `layout: post`, `layout: review`, or `layout: presentation` in its front matter. That picks the matching file in `_layouts/`, which renders the article and then nests itself inside `_layouts/default.html`.
- The layout name also sets the colored type label: `label-post`, `label-review`, or `label-presentation`.
- `css/main.scss` starts with empty front matter (`---`). That tells Jekyll to compile it, pulling in the partials from `_sass/` with `@import`, and write the result to `/css/main.css`. `@import` is used instead of `@use` so the same files compile on local Jekyll and on GitHub Pages, whose Sass compiler does not support `@use`.
- Fonts (Fraunces, Source Serif 4, IBM Plex Mono, Noto Serif JP) load from Google Fonts in `_layouts/default.html`.

Posts and URLs don't depend on the theme. Writing a new post works the same as always: add a Markdown file to `_posts/` with the right `layout`.

## Post languages

Posts can declare the languages in which they were written with a `languages`
array in their front matter:

```yaml
languages:
  - ja
  - en
```

The site shows `🇯🇵 日本語` and `🇺🇸 English` badges beside entries in lists and
in article headers. These badges describe the author's original writing; they
do not imply that a post was automatically translated. Existing posts without
the field default to English, so they do not all need to be updated at once.

The first value is the post's primary language. It sets the HTML `lang`
attribute on the document, article, and linked title so browsers and assistive
technology can handle the text correctly. Supported values are `ja` and `en`.
Noto Serif JP is loaded as the Japanese fallback for the site's existing
typefaces.

For a post written entirely in Japanese, use `languages: [ja]` and write
Markdown normally. For a genuinely bilingual post, identify each section's
language explicitly. A complete example post looks like this:

```markdown
---
layout: post
title: 日本語で書くこと
date: 2026-10-14
tags: japanese learning
languages:
  - ja
  - en
---

<section lang="ja" markdown="1">

## 日本語

これは日本語で書いた最初の記事です。まだ勉強中ですが、自分の言葉で
考えたことを少しずつ書いていきたいです。

</section>

<section lang="en" markdown="1">

## English

This is my first post written in Japanese. I am still learning, but I want to
gradually write about my experiences in my own words.

</section>
```

The `markdown="1"` attribute tells Kramdown to process Markdown inside each
HTML language section. Put the primary language first in `languages` and first
in the article.

## Setup

```bash
# ensure you have the proper ruby version and gems installed
brew install rbenv
rbenv install 3.4.9
rbenv local 3.4.9
gem install jekyll
rbenv rehash

# start the server
jekyll serve
```
