---
layout: default
title: "CV"
---

<h1>CV</h1>

<h2>Keywords</h2>
<div style="margin-bottom: 20px;">
  {% for keyword in site.data.cv.keywords %}
    <span style="display: inline-block; background-color: #f0f0f0; color: #333; padding: 4px 10px; border-radius: 16px; margin: 0 5px 5px 0; font-size: 0.9em;">
      {{ keyword }}
    </span>
  {% endfor %}
</div>

<h2>Education</h2>
<table class="account-table">
  <tbody>
    {% for item in site.data.cv.education %}
      <tr>
        <th>{{ item.period }}</th>
        <td>
            <strong>
              {% if item.url %}<a href="{{ item.url }}" target="_blank">{% endif %}
              {{ item.institution }}
              {% if item.url %}</a>{% endif %}
            </strong><br>
            {{ item.degree }}
            {% if item.description %}<br><span style="font-size: 0.9em; color: #666;">{{ item.description }}</span>{% endif %}
        </td>
      </tr>
    {% endfor %}
  </tbody>
</table>

<h2>Experience</h2>
<table class="account-table">
  <tbody>
    {% for item in site.data.cv.experience %}
      <tr>
        <th>{{ item.period }}</th>
        <td>
            <strong>
              {% if item.url %}<a href="{{ item.url }}" target="_blank">{% endif %}
              {{ item.title }}
              {% if item.url %}</a>{% endif %}
            </strong><br>
            {{ item.organization }}
            {% if item.description %}<br><span style="font-size: 0.9em; color: #666;">- {{ item.description }}</span>{% endif %}
        </td>
      </tr>
    {% endfor %}
  </tbody>
</table>

<h2>Publications</h2>
<ul class="post-list-detailed">
  {% for paper in site.data.cv.papers %}
    <li class="post-item" style="display: block; padding: 10px 0;">
        <div style="font-weight: bold;">
          {% if paper.url %}<a href="{{ paper.url }}" target="_blank">{% endif %}
          {{ paper.title }}
          {% if paper.url %}</a>{% endif %}
        </div>
        <div style="font-size: 0.95rem;">
            {% if paper.authors %}{{ paper.authors }}. {% endif %}
            {% if paper.conference %}<i>{{ paper.conference }}</i>{% endif %}
            {% if paper.location %}, {{ paper.location }}.{% endif %}
            <span style="color: #666;">{{ paper.date }}</span>
        </div>
    </li>
  {% endfor %}
</ul>

<h2>Presentations</h2>
<table class="account-table">
  <tbody>
    {% for pres in site.data.cv.presentations %}
      <tr>
        <th style="min-width: 100px;">{{ pres.date }}</th>
        <td>
            <span style="font-size: 0.85em; color: #666; background: #eee; padding: 2px 6px; border-radius: 4px;">{{ pres.type }}</span><br>
            <strong style="display: inline-block; margin-top: 4px;">
              {{ pres.title }}
            </strong><br>
            
            {% if pres.event_url != "" %}
              <a href="{{ pres.event_url }}" target="_blank">{{ pres.event }}</a>
            {% else %}
              {{ pres.event }}
            {% endif %}
            
            {% if pres.news_url != "" %}
              <span style="margin-left: 10px; font-size: 0.9em;">[<a href="{{ pres.news_url }}" target="_blank">News</a>]</span>
            {% endif %}
        </td>
      </tr>
    {% endfor %}
  </tbody>
</table>

<h2>Awards</h2>
<table class="account-table">
  <tbody>
    {% for award in site.data.cv.awards %}
      <tr>
        <th>{{ award.date }}</th>
        <td>
            <strong>
              {% if award.url %}<a href="{{ award.url }}" target="_blank">{% endif %}
              {{ award.title }}
              {% if award.url %}</a>{% endif %}
            </strong><br>
            {{ award.organization }}
        </td>
      </tr>
    {% endfor %}
  </tbody>
</table>