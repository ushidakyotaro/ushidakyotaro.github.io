---
layout: default
title: "News"
permalink: /news/
---
<h1>お知らせ一覧</h1>
<ul class="post-list-detailed">
  {% for item in site.news reversed %}
    <li class="post-item">
      <span class="post-date">{{ item.date | date: "%Y.%m.%d" }}</span>
      <a href="{{ item.url | relative_url }}" class="post-link">{{ item.title }}</a>
    </li>
  {% endfor %}
</ul>