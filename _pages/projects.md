---
layout: single
title: "Projects"
permalink: /projects/
author_profile: true
---

{% include base_path %}

<p class="page__lead" style="color:#6b7280; font-size:1.02rem; margin-bottom:1.5rem;">
A selection of my research, course, and side projects. Click any card for details.
</p>

<!-- ============================ RESEARCH ============================ -->
{% assign research = site.portfolio | where: "category", "research" | sort: "order" %}
{% if research.size > 0 %}
<div class="section-label">Research Projects</div>
<div class="project-grid">
  {% for project in research %}
    {% include project-card.html project=project %}
  {% endfor %}
</div>
{% endif %}

<!-- ============================ COURSE ============================ -->
{% assign course = site.portfolio | where: "category", "course" | sort: "order" %}
{% if course.size > 0 %}
<div class="section-label">Course Projects</div>
<div class="project-grid">
  {% for project in course %}
    {% include project-card.html project=project %}
  {% endfor %}
</div>
{% endif %}

<!-- ============================ MISC ============================ -->
{% assign misc = site.portfolio | where: "category", "misc" | sort: "order" %}
{% if misc.size > 0 %}
<div class="section-label">Talks &amp; Miscellaneous</div>
<div class="project-grid">
  {% for project in misc %}
    {% include project-card.html project=project %}
  {% endfor %}
</div>
{% endif %}
