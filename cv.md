---
layout: default
title: "CV"
---

<h1>CV</h1>
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
            {{ paper.authors }}. 
            <i>{{ paper.conference }}</i>, {{ paper.location }}.
            <span style="color: #666;">{{ paper.date }}</span>
        </div>
    </li>
  {% endfor %}
</ul>

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