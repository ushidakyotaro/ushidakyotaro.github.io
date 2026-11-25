---
layout: default
title: "Notes"
permalink: /notes/
description: "研究の基礎知識をテーマ別にまとめたノート（身体性認知科学、機械学習など）。"
---

<h1>Notes</h1>
<p>研究に関わる基礎知識を、テーマごとにまとめたノートです。内容は随時更新しています。</p>

{% assign topics = site.notes | group_by: "topic" | sort: "name" %}
{% for topic in topics %}
  <h2 class="year-heading" id="{{ topic.name | slugify }}">{{ topic.name | default: "その他" }}</h2>
  <ul class="post-list-detailed">
    {% assign notes_in_topic = topic.items | sort: "order" %}
    {% for note in notes_in_topic %}
      <li class="post-item">
        <span class="post-date">{{ note.updated | date: "%Y.%m.%d" }}</span>
        <a href="{{ note.url | relative_url }}" class="post-link">{{ note.title }}</a>
      </li>
    {% endfor %}
  </ul>
{% else %}
  <p>まだノートはありません。</p>
{% endfor %}
