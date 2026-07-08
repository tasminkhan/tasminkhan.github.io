---
layout: page
title: projects
permalink: /projects/
description: Hardware, VLSI, and embedded design projects.
nav: true
nav_order: 3
images:
  slider: true # loads the Swiper assets used by the image sliders below
---

<!-- pages/projects.md — inline cards (no separate detail pages).
     Content comes from _projects/*.md front matter with `category: hardware`,
     ordered by `importance`. Each card: auto-advancing image slider + bullet details. -->

<style>
  .card-list .item { padding-bottom: 1.5rem; margin-bottom: 1.5rem; border-bottom: 1px solid rgba(0,0,0,.1); }
  .card-list .item:last-child { border-bottom: 0; }
  .card-list swiper-container { width: 100%; }
  .card-list swiper-slide img { width: 100%; height: 260px; object-fit: contain; }
  .card-list .meta { opacity: .75; font-size: .9rem; margin-bottom: .2rem; }
</style>

<div class="card-list">
{% assign items = site.projects | where: "category", "hardware" | sort: "importance" %}
{% for project in items %}
  {% assign n = project.slides | size %}
  <div class="item row align-items-center">
    {% if n > 0 %}
    <div class="col-md-5 mt-3 mt-md-0">
      {% if n > 1 %}
      <swiper-container autoplay="true" autoplay-delay="3500" loop="true" navigation="true" pagination="true" pagination-clickable="true" pagination-dynamic-bullets="true">
        {% for img in project.slides %}
        <swiper-slide>{% include figure.liquid loading="eager" path=img class="img-fluid rounded z-depth-1" %}</swiper-slide>
        {% endfor %}
      </swiper-container>
      {% else %}
      {% include figure.liquid loading="eager" path=project.slides.first class="img-fluid rounded z-depth-1" %}
      {% endif %}
    </div>
    <div class="col-md-7 mt-3 mt-md-0">
    {% else %}
    <div class="col-12">
    {% endif %}
      <h3 class="mb-2">{{ project.title }}</h3>
      {% for m in project.meta %}<div class="meta">{{ m }}</div>{% endfor %}
      {% if project.highlights %}
      <ul class="mb-0 mt-2">
        {% for h in project.highlights %}<li>{{ h }}</li>{% endfor %}
      </ul>
      {% endif %}
    </div>
  </div>
{% endfor %}
</div>
