---
layout: default
title: Home
---

<div class="nav">
  {% for item in site.nav %}
    <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
  {% endfor %}
</div>

# Kai Stats

<div class="section">
<p>Building systems at the intersection of <strong>environmental engineering</strong>, <strong>statistics</strong>, and <strong>intelligence</strong>.</p>
<p>Notes, models, and clean structures — all in one place.</p>
</div>

## Highlights
<div class="section">
- 🧪 <strong>Models</strong>: time-series risk, air-quality analytics, robust baselines  
- 📚 <strong>Blog</strong>: concise memos on math, structure, and sustainability  
- 🔬 <strong>Projects</strong>: Kaggle notebooks, env-data pipelines, small ML tools
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
