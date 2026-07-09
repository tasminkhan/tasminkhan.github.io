---
layout: page
title: projects
permalink: /projects/
description:
nav: true
nav_order: 3
images:
  slider: true # loads the Swiper assets used by the image sliders below
---

<!-- pages/projects.md — inline cards (no separate detail pages).
     Content comes from _projects/*.md front matter with `category: hardware`,
     ordered by `importance`. Each card: auto-advancing image slider + bullet details.
     Layout uses a self-contained flexbox (NOT Bootstrap col-*), because the theme
     does not give col-md-* a width and Swiper needs an explicit size or it collapses. -->

<style>
  .post-header { display: none; } /* hide the "projects" page title; use a section headline instead */
  .section-head { margin: 0 0 1.5rem; padding-bottom: .4rem; border-bottom: 1px solid rgba(128,128,128,.35); }
  .card-list .item { display: flex; flex-wrap: wrap; gap: 1.5rem; align-items: center; padding-bottom: 1.5rem; margin-bottom: 1.5rem; border-bottom: 1px solid rgba(128,128,128,.25); }
  .card-list .item:last-child { border-bottom: 0; margin-bottom: 0; }
  .card-list .media { flex: 0 0 340px; max-width: 100%; }
  .card-list .body { flex: 1 1 320px; min-width: 0; }
  .card-list swiper-container { display: block; width: 100%; height: 260px; }
  .card-list swiper-slide { display: flex; align-items: center; justify-content: center; height: 100%; }
  .card-list swiper-slide img { max-width: 100%; max-height: 260px; width: auto; height: auto; background: #fff; padding: .5rem; border-radius: .4rem; }
  .card-list .media > figure { margin: 0; text-align: center; }
  .card-list .media > figure img { max-width: 100%; max-height: 260px; width: auto; height: auto; background: #fff; padding: .5rem; border-radius: .4rem; }
  .card-list .meta { opacity: .75; font-size: .9rem; margin-bottom: .2rem; }
  .card-list .links { margin-top: .8rem; }
  .card-list .links a { display: inline-block; margin-right: .5rem; padding: .25rem .7rem; border: 1px solid currentColor; border-radius: .35rem; font-size: .85rem; text-decoration: none; }
  .card-list .links a:hover { opacity: .7; }
  .card-list .tag-ongoing { display: inline-block; padding: .22rem .6rem; border-radius: .35rem; font-size: .8rem; font-weight: 600; background: #e0a800; color: #000; }
</style>

<h2 class="section-head">Projects</h2>
<div class="card-list">
{% assign items = site.projects | where: "category", "hardware" | sort: "importance" %}
{% for project in items %}
  {% assign n = project.slides | size %}
  <div class="item">
    {% if n > 0 %}
    <div class="media">
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
    {% endif %}
    <div class="body">
      <h3 class="mb-2">{{ project.title }}</h3>
      {% for m in project.meta %}<div class="meta">{{ m }}</div>{% endfor %}
      {% if project.highlights %}
      <ul class="mb-0 mt-2">
        {% for h in project.highlights %}<li>{{ h }}</li>{% endfor %}
      </ul>
      {% endif %}
      {% if project.github or project.presentation or project.ongoing %}
      <div class="links">
        {% if project.github %}<a href="{{ project.github }}" target="_blank" rel="noopener noreferrer">GitHub</a>{% endif %}
        {% if project.presentation %}<a href="{{ project.presentation }}" target="_blank" rel="noopener noreferrer">View Presentation</a>{% endif %}
        {% if project.ongoing %}<span class="tag-ongoing">Ongoing</span>{% endif %}
      </div>
      {% endif %}
    </div>
  </div>
{% endfor %}
</div>
