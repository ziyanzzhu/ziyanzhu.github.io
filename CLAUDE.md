# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a personal academic website for Prof. Ziyan (Zoe) Zhu, built with Jekyll (Jekyll Now theme) and hosted on GitHub Pages. The site is for the Zhu research group at Boston College, focused on computational physics and quantum materials.

The site is deployed from the `gh-pages` branch; `master` is the main development branch.

## Local Development

```bash
# Install dependencies (mirrors GitHub Pages plugins)
gem install github-pages

# Serve locally with live reload
jekyll serve

# View at http://127.0.0.1:4000/
```

Pushing to master triggers an automatic GitHub Pages rebuild and deploy.

## Site Structure

- `index.md` — Home page
- `Research.md` — Research projects (uses `.project-table` for image+text rows)
- `Publications.md` — Publication list (uses `.pub-list` with `<u>` tags to highlight Zoe's name)
- `group.md` — PI bio + group members (uses `.member-table` for photo+bio rows)
- `join.md` / `Contact.md` — Join and contact pages
- `_layouts/` — `default.html` (site shell with nav), `page.html`, `post.html`, `listed.html`
- `_includes/` — `meta.html`, `analytics.html`, `svg-icons.html`, `disqus.html`
- `_config.yml` — Site metadata (name, avatar, plugins)

## Styling

- `style.scss` — Main stylesheet; imports from `_sass/`
- `_sass/_variables.scss` — Color palette and font definitions (edit here to change theme colors)
- Fonts: **Roboto** (body) and **Roboto Mono** (headers/title), self-hosted in `/fonts/`
- Color scheme: off-white background (`$offWhite`), dark blue body text (`$darkBlue`), red accents (`$red`)
- Responsive breakpoints at 640px (via `@include mobile`) and 768px (via `@media` blocks)

---

## How to Update the Site

### Add a publication

Open `Publications.md`. Find the correct year section (or add a new `## YYYY` heading). Add a list item inside the `<div class="pub-list"><ul>` block:

```html
<li>
  <strong>Paper title</strong><br>
  <span>Author One, <u>Ziyan Zhu</u>, Author Three</span><br>
  <span>Journal Name Volume, Pages (Year)</span><br>
  <span>DOI: 10.xxxx/xxxxx | arXiv:XXXX.XXXXX</span>
</li>
```

Wrap Zoe's name in `<u>` tags — the CSS renders these as a pink highlight badge (not an underline).

---

### Add a group member

Open `group.md`. Add a `<tr>` inside the `<table class="member-table">` block. Place the member's photo in `/images/people/`:

```html
<tr>
  <td>
    <div class="image-container-member">
      <img src="/images/people/firstname.jpg" alt="Firstname">
    </div>
  </td>
  <td>
    <h5>Full Name</h5>
    <p><em>Role (e.g. Ph.D. Student)</em></p>
    Bio text here.
  </td>
</tr>
```

Photos should be square or portrait-oriented JPEGs. The CSS applies a 10% border-radius and a black border.

---

### Add a research project

Open `Research.md`. Add a `<tr>` inside the `<table class="project-table">`. The first column is the image (30% width) and the second is the text (70%):

```html
<tr>
  <td>
    <div class="image-container">
      <img src="/images/yourimage.png" alt="description" style="display: block;">
    </div>
  </td>
  <td>
    <h5>Project Title</h5>
    <p>Description text.</p>
  </td>
</tr>
```

For a video instead of an image, use a `<div class="video-container">` wrapping a `<video>` element.

---

### Change site colors or fonts

Edit `_sass/_variables.scss`. The main variables:

| Variable | Controls |
|---|---|
| `$backgroundColor` | Page background |
| `$bodyColor` | Body text and links |
| `$headerColor` | Headings |
| `$activeHeaderColor` | Active nav link |
| `$highlightColor` | Hover color on links |
| `$underlineColor` | Link underline color |
| `$bodyFont` | Body and paragraph text |
| `$headerFont` | Headings |
| `$titleFont` | Site name and nav |

Fonts are self-hosted from `/fonts/`. To use a different font, add the font files there, add `@font-face` rules in `_variables.scss`, and update the relevant font variable.

---

### Update site metadata

Edit `_config.yml` for the site name, avatar URL, footer social links, and analytics. Changes to `_config.yml` require restarting `jekyll serve` to take effect locally.
