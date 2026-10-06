---
layout: default
title: Home
---

## Welcome to My Capstone Portfolio

<ul class="post-tabs">
  {% for post in site.posts %}
    <li class="tab-item">
      <a href="{{ post.url | relative_url }}" class="tab-link">
        <span class="tab-title">{{ post.title }}</span>
        <span class="tab-date">{{ post.date | date: "%b %d, %Y" }}</span>
      </a>
    </li>
  {% endfor %}
</ul>
