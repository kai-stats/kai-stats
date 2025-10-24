---
layout: default
title: Home
---

<div class="nav">
  {% for item in site.nav %}
    <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
  {% endfor %}
</div>

## Latest Posts
<div class="section">
{% assign posts = site.posts | slice: 0, 3 %}
{% if posts.size > 0 %}
  <ul>
  {% for post in posts %}
    <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> — <small>{{ post.date | date: "%Y-%m-%d" }}</small></li>
  {% endfor %}
  </ul>
{% else %}
  <em>No posts yet. Coming soon.</em>
{% endif %}
</div>

<div class="site-footer">
© {{ site.time | date: "%Y" }} Kai Stats — Minimal systems, maximum clarity.
</div>
