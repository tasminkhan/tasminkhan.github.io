---
layout: page
title: work
permalink: /work/
nav: true
nav_order: 4
---

<!-- pages/work.md — content is pulled from _data/cv.yml (RenderCV format),
     so the CV and this page stay in sync. The `show` list below controls which
     sections appear here: industry and teaching roles. Research positions live
     on the research tab, so they are intentionally left out. -->

<style>
  .post-header { display: none; } /* hide the "work" page title; the Industry/Teaching headings serve as headlines */
  .exp-list .exp-section { margin: 1.8rem 0 1rem; padding-bottom: .3rem; border-bottom: 1px solid rgba(128,128,128,.25); }
  .exp-list .exp-section:first-child { margin-top: 0; }
  .exp-list .exp-item { padding-bottom: 1.2rem; margin-bottom: 1.2rem; border-bottom: 1px solid rgba(128,128,128,.15); }
  .exp-list .exp-item:last-child { border-bottom: 0; margin-bottom: 0; }
  .exp-list .exp-head { display: flex; flex-wrap: wrap; justify-content: space-between; gap: .3rem 1rem; align-items: baseline; }
  .exp-list .exp-role { font-weight: 600; font-size: 1.05rem; }
  .exp-list .exp-dates { opacity: .7; font-size: .88rem; white-space: nowrap; }
  .exp-list .exp-org { opacity: .85; margin-top: .15rem; }
  .exp-list .exp-summary { opacity: .8; font-size: .92rem; margin-top: .4rem; }
  .exp-list ul.exp-highlights { margin: .5rem 0 0; }
</style>

{% assign sections = site.data.cv.cv.sections %}
{% assign show = "Industrial Experience|Teaching Experience" | split: "|" %}
<div class="exp-list">
{% for name in show %}
  {% assign entries = sections[name] %}
  {% if entries and entries != empty %}
  <h2 class="exp-section">{{ name }}</h2>
  {% for e in entries %}
  <div class="exp-item">
    <div class="exp-head">
      <span class="exp-role">{{ e.position }}</span>
      {% if e.start_date %}<span class="exp-dates">{{ e.start_date }}{% if e.end_date %} &ndash; {% if e.end_date == 'present' %}Present{% else %}{{ e.end_date }}{% endif %}{% endif %}</span>{% endif %}
    </div>
    <div class="exp-org">{{ e.company }}{% if e.location %} &middot; {{ e.location }}{% endif %}</div>
    {% if e.summary %}<div class="exp-summary">{{ e.summary }}</div>{% endif %}
    {% if e.courses %}<div class="exp-summary"><strong>Courses taught:</strong> {{ e.courses }}</div>{% endif %}
    {% if e.highlights %}
    <ul class="exp-highlights">
      {% for h in e.highlights %}<li>{{ h }}</li>{% endfor %}
    </ul>
    {% endif %}
  </div>
  {% endfor %}
  {% endif %}
{% endfor %}
</div>
