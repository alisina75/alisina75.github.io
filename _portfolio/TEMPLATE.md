---
# ============================================================================
# COPY THIS FILE to add a new project. Rename it (e.g. my-new-project.md).
# The filename becomes part of the URL: /portfolio/my-new-project/
# Delete this line and the ones above the front matter is otherwise ready.
# ============================================================================

title: "Your Project Title Here"
collection: portfolio

# category controls which section it appears in on the Projects page:
#   research | course | misc
category: research

# order controls position within its section (lower = first)
order: 99

# Optional thumbnail shown on the card. Put the image in /images/ or /files/.
# thumbnail: /images/my-project-thumb.png

# One-sentence summary shown on the card (keep it short).
summary: "A one-line description of what this project is about."

# Optional coloured badge on the card. Pick a class:
#   badge--paper (blue) | badge--course (purple) | badge--wip (amber) | (none = green)
badge: "In Progress"
badge_class: "badge--wip"

# Optional external links shown as pills on the card AND usable in the page.
links:
  - label: "arXiv"
    url: "https://arxiv.org/abs/XXXX.XXXXX"
  - label: "Code"
    url: "https://github.com/alisina75/your-repo"

# Keep this line so the template itself never shows up on the live site.
published: false
---

Write the full project description here using normal Markdown.

You can include:

- **Bold text**, *italics*, and [links](https://example.com)
- Math with LaTeX: $\min_x f(x)$ subject to $g(x) \le 0$
- Images and figures:

<figure>
  <img src="/images/example.png" alt="describe the image">
  <figcaption>A caption for the figure.</figcaption>
</figure>

When you're ready to publish, change `published: false` to `published: true`
(or just delete that line).
