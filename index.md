---
layout: default
title: Home
---

## Welcome to My Capstone Portfolio
This is the main content of your index page.

## Recent Posts
<ul>
  {% for post in site.posts %}
    <li>
      <span class="post-date">{{ post.date | date: "%b %d, %Y" }}</span> — 
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
