---
layout: page
title: honors
permalink: /honors/
nav: true
nav_order: 1
---

<!-- pages/honors.md — Education and Awards are pulled from _data/cv.yml so they
     stay in sync with the CV. -->

<style>
  .honors-block { margin-top: 1.5rem; }
  .honors-block:first-of-type { margin-top: 0; }
  .honors-block h2 { padding-bottom: .3rem; border-bottom: 1px solid rgba(128,128,128,.25); }
  .honors-block .honors-item { padding-bottom: 1rem; margin-bottom: 1rem; border-bottom: 1px solid rgba(128,128,128,.15); }
  .honors-block .honors-item:last-child { border-bottom: 0; margin-bottom: 0; }
  .honors-block .honors-head { display: flex; flex-wrap: wrap; justify-content: space-between; gap: .3rem 1rem; align-items: baseline; }
  .honors-block .honors-title { font-weight: 600; font-size: 1.05rem; }
  .honors-block .honors-dates { opacity: .7; font-size: .88rem; white-space: nowrap; }
  .honors-block .honors-org { opacity: .85; margin-top: .15rem; }
  .honors-block .honors-summary { opacity: .8; font-size: .92rem; margin-top: .4rem; }
  .honors-block ul { margin: .5rem 0 0; }
  .honors-block .honors-courses { margin-top: .7rem; }
  .honors-block .honors-courses-label { font-size: .72rem; font-weight: 700; letter-spacing: .08em; text-transform: uppercase; opacity: .6; margin-bottom: .15rem; }
  .honors-block .honors-courses-list { font-size: .92rem; opacity: .9; }
</style>

{% assign sections = site.data.cv.cv.sections %}

<div class="honors-block">
<h2>Education</h2>
{% for e in sections.Education %}
<div class="honors-item">
  <div class="honors-head">
    <span class="honors-title">{{ e.studyType }}{% if e.area %}, {{ e.area }}{% endif %}</span>
    {% if e.start_date %}<span class="honors-dates">{{ e.start_date }}{% if e.end_date %} &ndash; {{ e.end_date }}{% endif %}</span>{% endif %}
  </div>
  <div class="honors-org">{{ e.institution }}{% if e.location %} &middot; {{ e.location }}{% endif %}</div>
  {% if e.highlights %}
  <ul>
    {% for h in e.highlights %}<li>{{ h }}</li>{% endfor %}
  </ul>
  {% endif %}
  {% if e.courses %}
  <div class="honors-courses">
    <div class="honors-courses-label">Relevant Coursework</div>
    <div class="honors-courses-list">{{ e.courses }}</div>
  </div>
  {% endif %}
</div>
{% endfor %}
</div>

<div class="honors-block">
<h2>Awards</h2>
{% for a in sections.Awards %}
<div class="honors-item">
  <div class="honors-head">
    <span class="honors-title">{{ a.title }}</span>
    {% if a.date %}<span class="honors-dates">{{ a.date }}</span>{% endif %}
  </div>
  {% if a.awarder %}<div class="honors-org">{{ a.awarder }}</div>{% endif %}
  {% if a.summary %}<div class="honors-summary">{{ a.summary }}</div>{% endif %}
</div>
{% endfor %}
</div>
