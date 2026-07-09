---
layout: page
title: honors
permalink: /honors/
nav: true
nav_order: 1
---

<!-- pages/honors.md — Education and Awards are pulled from _data/cv.yml so they
     stay in sync with the CV. The page title is hidden; only the section
     headlines (Education, Awards) show. -->

<style>
  .post-header { display: none; } /* hide the "honors" page title; use section headlines only */
  .honors-block { margin-top: 2rem; }
  .honors-block:first-of-type { margin-top: 0; }
  .honors-block > h2 { padding-bottom: .3rem; border-bottom: 1px solid rgba(128,128,128,.25); }
  .honors-block .honors-item { padding-bottom: 1rem; margin-bottom: 1rem; border-bottom: 1px solid rgba(128,128,128,.15); }
  .honors-block .honors-item:last-child { border-bottom: 0; margin-bottom: 0; }
  .honors-block .honors-head { display: flex; flex-wrap: wrap; justify-content: space-between; gap: .3rem 1rem; align-items: baseline; }
  .honors-block .honors-title { font-weight: 600; font-size: 1.05rem; }
  .honors-block .honors-dates { opacity: .7; font-size: .88rem; white-space: nowrap; }
  .honors-block .honors-org { opacity: .85; margin-top: .15rem; }
  .honors-block .honors-summary { opacity: .8; font-size: .92rem; margin-top: .4rem; }

  /* Education award bullets — colored to stand out (the degree title stays neutral) */
  .education .edu-highlights { margin: .6rem 0 0; padding-left: 1.1rem; }
  .education .edu-highlights li { color: var(--global-theme-color, #b509ac); margin-bottom: .25rem; }

  /* Relevant coursework — standout box, two side-by-side columns (neutral, no accent color) */
  .edu-courses { margin-top: .9rem; padding: .7rem .95rem; border-left: 3px solid rgba(128,128,128,.35); background: rgba(128,128,128,.08); border-radius: .3rem; }
  .edu-courses-label { font-weight: 700; text-transform: uppercase; letter-spacing: .07em; font-size: .74rem; margin-bottom: .45rem; }
  .edu-courses-list { columns: 2; column-gap: 1.6rem; margin: 0; padding-left: 1.1rem; }
  .edu-courses-list li { margin-bottom: .25rem; break-inside: avoid; }
  @media (max-width: 576px) { .edu-courses-list { columns: 1; } }

  /* Award titles — colored (already bold) */
  .awards .honors-title { color: var(--global-theme-color, #b509ac); }
</style>

{% assign sections = site.data.cv.cv.sections %}

<div class="honors-block education">
<h2>Education</h2>
{% for e in sections.Education %}
<div class="honors-item">
  <div class="honors-head">
    <span class="honors-title">{{ e.studyType }}{% if e.area %}, {{ e.area }}{% endif %}</span>
    {% if e.start_date %}<span class="honors-dates">{{ e.start_date }}{% if e.end_date %} &ndash; {{ e.end_date }}{% endif %}</span>{% endif %}
  </div>
  <div class="honors-org">{{ e.institution }}{% if e.location %} &middot; {{ e.location }}{% endif %}</div>
  {% if e.highlights %}
  <ul class="edu-highlights">
    {% for h in e.highlights %}<li>{{ h }}</li>{% endfor %}
  </ul>
  {% endif %}
  {% if e.courses %}
  <div class="edu-courses">
    <div class="edu-courses-label">Relevant Coursework</div>
    {% assign course_items = e.courses | split: ", " %}
    <ul class="edu-courses-list">
      {% for c in course_items %}<li>{{ c }}</li>{% endfor %}
    </ul>
  </div>
  {% endif %}
</div>
{% endfor %}
</div>

<div class="honors-block awards">
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
