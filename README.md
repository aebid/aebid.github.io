# aebid.github.io

Personal website built with [Jekyll](https://jekyllrb.com/) and the
[Slate](https://github.com/pages-themes/slate) theme, served by GitHub Pages at
<https://aebid.github.io>.

## Structure

```
_config.yml            site settings (title, description, author links, theme)
index.md               home page
about.md               /about/
research.md            /research/
blog.md                /blog/  — post index
contact.md             /contact/
_posts/                blog posts, named YYYY-MM-DD-title.md
_layouts/page.html     wraps the theme's default layout with nav + footer
_layouts/post.html     same, plus post title/date
_includes/nav.html     nav bar, built from each page's `nav_order`
_includes/footer.html  contact links, built from `site.author`
assets/css/style.scss  imports the Slate theme, then site-specific CSS
assets/img/            images (drop a profile.jpg here for the home page)
```

## Adding a page

Create `newpage.md` at the top level with front matter:

```yaml
---
title: Talks
nav_order: 4
permalink: /talks/
---
```

Any page with a `nav_order` shows up in the nav bar, sorted by that number.
Omit `nav_order` to keep a page out of the nav.

## Adding a post

Create `_posts/YYYY-MM-DD-some-title.md`:

```yaml
---
title: "Some title"
date: 2026-09-09
description: Shown on the blog index.
---
```

## Local preview

```bash
bundle install
bundle exec jekyll serve --livereload
```

Then open <http://localhost:4000>. Pushing to `main` is what actually deploys —
GitHub Pages builds the site itself, no `_site/` commit needed.
