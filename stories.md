---
layout: default
title: Stories
permalink: /stories/
pagination:
  enabled: true
  collection: stories
  per_page: 12
  permalink: /stories/page/:num/
---

<h1>Stories</h1>

<ul class="stories-list">
  {% for story in paginator.docs %}
    <li>
      <h2><a href="{{ story.url | relative_url }}">{{ story.title }}</a></h2>
      <p>{{ story.description }}</p>
      {% if story.tags %}
        <ul class="story-tags">
          {% for tag in story.tags %}
            <li>{{ tag }}</li>
          {% endfor %}
        </ul>
      {% endif %}
    </li>
  {% endfor %}
</ul>

<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path | relative_url }}">&laquo; Previous</a>
  {% endif %}
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path | relative_url }}">Next &raquo;</a>
  {% endif %}
</div>
