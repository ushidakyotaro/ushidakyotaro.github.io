---
layout: default
title: "CV"
---

<h1>Curriculum Vitae</h1>

<h2>Experience</h2>
<dl>
  {% for item in site.data.cv.experience %}
    <dt><strong>{{ item.period }}</strong></dt>
    <dd>{{ item.title }}{% if item.description %}<br>{{ item.description }}{% endif %}</dd>
  {% endfor %}
</dl>

<h2>Awards</h2>
<ul>
  {% for award in site.data.cv.awards %}
    <li>{{ award.date }}: {{ award.title }} ({{ award.organization }})</li>
  {% endfor %}
</ul>

<h2>Papers</h2>
<ul>
  {% for paper in site.data.cv.papers %}
    <li>{{ paper.date }}: {{ paper.title }} </li>
  {% endfor %}
</ul>
