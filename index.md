---
layout: default
title: Home
---

<!-- Sticky Nav -->
<div class="kai-nav">
  <div class="kai-brand">Kai&nbsp;Stats</div>
  <div class="kai-links">
    {% for item in site.nav %}
      <a class="kai-chip" href="{{ item.url | relative_url }}">{{ item.title }}</a>
    {% endfor %}
  </div>
  <button class="theme-toggle" id="themeToggle">🌓</button>
</div>

<!-- Hero -->
<section class="hero">
  <h1>Systems for clarity.</h1>
  <p>Environmental engineering × statistics × intelligence — clean models, tidy data, and legible structure.</p>
  <div class="kai-btns">
    <a class="kai-btn" href="/projects">See Projects</a>
    <a class="kai-btn secondary" href="/blog/">Read Blog</a>
    <a class="kai-btn secondary" href="https://github.com/kai-stats">GitHub</a>
  </div>
</section>

<!-- Highlights -->
<section>
  <div class="grid">
    <div class="card">
      <h3>Models</h3>
      <p>Small, robust baselines for AQI/PM2.5, time-series risk, and simple ML tools.</p>
    </div>
    <div class="card">
      <h3>Notes</h3>
      <p>Short memos on math, structure, sustainability, and the craft of clarity.</p>
    </div>
    <div class="card">
      <h3>Toolkit</h3>
      <p>Env-data utilities, reproducible pipelines, and readable code snippets.</p>
    </div>
  </div>
</section>

<!-- Latest Posts -->
<section class="card post-list" style="margin-top:1rem;">
  <h3>Latest Posts</h3>
  {% assign posts = site.posts | slice: 0, 3 %}
  {% if posts.size > 0 %}
    <ul>
      {% for post in posts %}
        <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> — <small>{{ post.date | date: "%Y-%m-%d" }}</small></li>
      {% endfor %}
    </ul>
  {% else %}
    <em>No posts yet. Create one under <code>_posts/</code>.</em>
  {% endif %}
</section>

<div class="site-footer">
  © {{ site.time | date: "%Y" }} Kai Stats — Minimal systems, maximum clarity.
</div>

<!-- Theme toggle script -->
<script>
(function() {
  const key = "kai-theme";
  const prefersDark = window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches;
  const saved = localStorage.getItem(key);
  const html = document.documentElement;
  if (saved) html.classList.toggle('theme-dark', saved === 'dark');
  else if (prefersDark) html.classList.add('theme-dark');
  document.getElementById('themeToggle').onclick = () => {
    const isDark = html.classList.toggle('theme-dark');
    localStorage.setItem(key, isDark ? 'dark' : 'light');
  };
})();
</script>
