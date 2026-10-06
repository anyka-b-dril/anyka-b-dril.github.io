---
layout: default
title: Home
---

## Welcome to My Capstone Portfolio

<div class="post-boxes">
  {% for post in site.posts %}
    <a href="{{ post.url | relative_url }}" class="post-box">
      <h3 class="box-title">{{ post.title }}</h3>
      {% if post.excerpt %}
        <p class="box-excerpt">{{ post.excerpt | strip_html | truncatewords: 20 }}</p>
      {% endif %}
      <span class="box-date">{{ post.date | date: "%b %d, %Y" }}</span>
  {% endfor %}
</div>
