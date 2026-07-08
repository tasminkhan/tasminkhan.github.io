---
layout: page
title: research
permalink: /research/
description: Research projects in VLSI/EDA, medical imaging, and low-cost instrumentation.
nav: true
nav_order: 2.5
---

<!-- pages/research.md — full-width list: image left, description right, one per row.
     Entries live in _projects/*.md with `category: research`; ordered by `importance`. -->
<div class="projects">
{% assign items = site.projects | where: "category", "research" | sort: "importance" %}
{% for project in items %}
  <div class="row align-items-center my-3">
    {% if project.img %}
    <div class="col-sm-4 mt-3 mt-md-0">
      <a href="{{ project.url | relative_url }}">
        {% include figure.liquid loading="eager" path=project.img title=project.title class="img-fluid rounded z-depth-1" %}
      </a>
    </div>
    <div class="col-sm-8">
    {% else %}
    <div class="col-sm-12">
    {% endif %}
      <h3 class="mb-2"><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
      <p class="mb-0">{{ project.description }}</p>
    </div>
  </div>
  {% unless forloop.last %}<hr>{% endunless %}
{% endfor %}
</div>
