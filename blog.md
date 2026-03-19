---
layout: default
title: Blog
permalink: /blog/
---
<div class="section-wrap">
  <div class="section-head">
    <span class="section-num">03</span>
    <span class="section-title">Blog</span>
  </div>
  <div class="blog-grid">
    {% for post in site.posts %}
    <a class="post-card" href="{{ post.url }}">
      <span class="post-date">{{ post.date | date: "%Y — %m — %d" }}</span>
      <div class="post-title">{{ post.title }}</div>
      <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 130 }}</p>
      <span class="post-read">Leer</span>
    </a>
    {% endfor %}
  </div>
</div>
