# Website Upgrade Guide — alisina75.github.io

This turns your Projects page from one long text file into a **clean grid of project
cards**, where **each project is its own page**. Adding a new project becomes: copy one
file, edit the top, done. It also modernizes the color scheme and fixes a few config bugs.

Everything here is **non-destructive and easy to revert** (the visual changes live in one
new file). Work on a branch if you want to preview safely.

---

## What you're getting

1. A modern **blue/ink** color scheme (replaces the dated gray/teal).
2. A **Projects landing page** that auto-builds a card grid, grouped into
   *Research / Course / Talks & Misc*.
3. **One page per project** — perfect placeholders for new and existing work.
4. A **TEMPLATE file** so adding a project = copy, rename, edit 5 lines.
5. Small **config fixes** (your name, site title, description).

---

## Files in this package and where they go

| File in this package        | Copy it to (in your repo)          | Action  |
|-----------------------------|------------------------------------|---------|
| `_sass/_custom.scss`        | `_sass/_custom.scss`               | **new** |
| `assets/css/main.scss`      | `assets/css/main.scss`             | replace |
| `_includes/project-card.html` | `_includes/project-card.html`    | **new** |
| `_pages/projects.md`        | `_pages/projects.md`               | replace |
| `_portfolio/*.md`           | `_portfolio/`                      | **new** |
| `_data/navigation.yml`      | `_data/navigation.yml`             | replace |

You'll also make two small **manual edits** to files that stay in place:
`_sass/_variables.scss` and `_config.yml` (Steps 2 and 5 below).

---

## Step 1 — Add the card grid + new styling

Copy these three files in as-is:

- `_sass/_custom.scss`  (new)
- `_includes/project-card.html`  (new)
- `assets/css/main.scss`  (replace — the only change is one added line at the bottom:
  `@import "custom";`)

If you'd rather not replace `main.scss`, just open your existing one and add this line
at the very end:

```scss
@import "custom";
```

---

## Step 2 — Recolor the theme (2 lines)

Open `_sass/_variables.scss` and change these two lines.

Find:

```scss
$primary-color              : #7a8288;
```
Change to:
```scss
$primary-color              : #1f2937;   // dark slate — masthead / name
```

Find:
```scss
$link-color                 : $info-color;
```
Change to:
```scss
$link-color                 : #2563eb;   // modern blue — all links
```

That's the whole recolor. (The card accent color is set independently at the top of
`_custom.scss`, so if you want a different accent later, change `$accent` there.)

---

## Step 3 — Replace the Projects page

Replace `_pages/projects.md` with the one in this package. The new version contains **no
project content** — it just loops over your project files and renders cards. You never
edit this file again; you only add project files (Step 4).

---

## Step 4 — Add your project pages

Copy the whole `_portfolio/` folder from this package into your repo. It already contains
your five existing projects as individual pages:

- `cbf-resource-allocation.md`  (research)
- `statistical-rl.md`  (course)
- `computer-vision.md`  (course)
- `deep-sets-qual.md`  (misc)
- `midwest-poster-2023.md`  (misc)
- `TEMPLATE.md`  (the copy-me placeholder — never shows on the site)

**Delete the two old example files** that shipped with the theme so they don't appear:
`_portfolio/portfolio-1.md` and `_portfolio/portfolio-2.html`.

### To add a NEW project later
1. Duplicate `_portfolio/TEMPLATE.md`.
2. Rename it (e.g. `koopman-operators.md`). The name becomes the URL.
3. Edit the top: `title`, `category` (`research`/`course`/`misc`), `summary`,
   optional `badge`, optional `thumbnail`, optional `links`.
4. Write the description below the `---`.
5. Remove the `published: false` line. Commit. It appears automatically.

### Card front-matter reference
```yaml
title:        # shown on card + as the page heading
category:     # research | course | misc  (which section it lands in)
order:        # position within the section (lower = earlier)
summary:      # one-line card description
thumbnail:    # optional image path, e.g. /images/thumb.png  (16:9 looks best)
badge:        # optional label, e.g. "CDC 2025", "In Progress"
badge_class:  # badge--paper | badge--course | badge--wip  (blank = green)
links:        # optional list of {label, url} shown as pills
```

---

## Step 5 — Fix config bugs

Open `_config.yml` and fix these:

```yaml
title    : "Alisina Bayati"          # was "About Me"
name     : &name "Alisina Bayati"    # was "Alisina Bayati2"  (stray 2)
description : &description "Personal website of Alisina Bayati — PhD student at UIUC working on optimization, reinforcement learning, and control."
```

The `description` also improves how your site looks when shared on Google/LinkedIn/Twitter.

---

## Step 6 — Navigation

Replace `_data/navigation.yml` with the one in this package. It adds **About** and a
direct **CV** link alongside **Projects**. If your CV isn't at `/files/CV/CV.pdf`, update
that line to match your actual path.

---

## Step 7 — Preview and publish

Locally (optional but recommended):
```bash
bundle install          # if it errors, delete Gemfile.lock and retry
bundle exec jekyll serve
# open http://localhost:4000
```

Then commit and push to `master`. GitHub Pages rebuilds in ~1 minute.

```bash
git checkout -b website-refresh
git add -A
git commit -m "Modernize theme + convert projects to card grid with per-project pages"
git push origin website-refresh
```
Open a pull request (or push straight to `master` if you prefer), confirm it looks right
on the live site, and you're done.

---

## Nice-to-have next steps (optional)

- **Thumbnails**: add a small 16:9 image per project (`thumbnail:` field) — the grid looks
  much richer with them. Even a plot or diagram from the paper works well.
- **Dark-mode accent**: if you ever want to tweak the whole palette, everything traces
  back to `$accent` in `_custom.scss` and the two variables in Step 2.
- **A bigger visual overhaul**: if you ever want a fundamentally different look, the most
  popular modern academic Jekyll theme is **al-folio**. It's a larger migration (you'd
  re-enter content), so only consider it if you want a from-scratch redesign — the steps
  above give you a modern look while keeping all your current content.
