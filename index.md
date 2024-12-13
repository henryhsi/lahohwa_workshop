---
layout: default
title: Welcome
---

# Welcome to LaHohwa's Workshop!

Explore our latest posts below. Here you'll find recipes, project notes, and more. Both English and Chinese content are supported for a wider audience.

<ul class="post-list">
  {% for post in site.posts %}
    <li class="post-list-item">
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p class="post-date">{{ post.date | date: "%B %d, %Y" }}</p>
      <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
    </li>
  {% endfor %}
</ul>