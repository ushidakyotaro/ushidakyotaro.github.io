---
layout: default
title: "Blog Articles"
permalink: /article/
---

# Blog Articles

{% assign postsByYear = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}

{% for year in postsByYear %}
  <h2 class="year-heading">{{ year.name }}</h2>
  <ul class="post-list-detailed">
    {% for post in year.items %}
      <li class="post-item">
        <span class="post-date">{{ post.date | date: "%m.%d" }}</span>
        <div class="post-info">
          <a href="{{ post.url | relative_url }}" class="post-link">{{ post.title }}</a>
          <div class="post-meta">
            {% if post.categories %}
              <span class="post-tags">
                <i class="fa-solid fa-folder-open"></i> {{ post.categories | join: ", " }}
              </span>
            {% endif %}
          </div>
        </div>
      </li>
    {% endfor %}
  </ul>
{% endfor %}