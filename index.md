---
layout: default
title: Home
---

<section class="hero">
  <div class="hero-left">
    <p class="hero-label">
      <span class="hero-dot"></span>
      Offensive Security Specialist
    </p>
    <h1 class="hero-name">
      <div class="name-main">Hola, soy</div>
      <div class="name-handle">Angel Scott.</div>
    </h1>
    <p class="hero-bio">
     Curioso por naturaleza, apasionado de la seguridad ofensiva y aprendiz constante.
      Este sitio es, en su totalidad, un reflejo de mi amor por este campo.   
    </p>
    <div class="hero-chips">
    <span class="chip active">Pentester</span>
    <span class="chip active">Web AppSec</span>
    <span class="chip">Mobile</span>
    <span class="chip">Red Team</span>
    </div>
    <div class="hero-actions">
      <a class="btn btn-primary" id="btn-random" href="#">random.choice(posts)</a>
      <a class="btn btn-secondary" href="https://github.com/{{ site.author.github }}" target="_blank">GitHub</a>
    </div>
    <script>
      (function(){
        var urls = [
          {% for post in site.posts %}"{{ post.url }}"{% unless forloop.last %},{% endunless %}{% endfor %},
          {% for writeup in site.writeups %}"{{ writeup.url }}"{% unless forloop.last %},{% endunless %}{% endfor %}
        ];
        var btn = document.getElementById('btn-random');
        btn.href = urls[Math.floor(Math.random() * urls.length)];
      })();
    </script>
  </div>
  <div class="hero-stats">
    <div class="stat-item">
      <div class="stat-n">{{ site.posts | size }}</div>
      <div class="stat-l">Posts</div>
    </div>
    <!--<div class="stat-item">
    <div class="stat-n">{{ site.writeups | size }}</div>
      <div class="stat-l">Writeups</div>      
    </div>-->
  </div>
</section>


<!-- BLOG -->
<div class="section-wrap">
  <div class="section-head">
    <span class="section-num">01</span>
    <span class="section-title">Blog</span>
    <a class="section-more" href="/blog/">Ver todos</a>
  </div>
  <div class="blog-grid">
    {% for post in site.posts limit:3 %}
    <a class="post-card" href="{{ post.url }}">
      <span class="post-date">{{ post.date | date: "%Y — %m — %d" }}</span>
      <div class="post-title">{{ post.title }}</div>
      <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 120 }}</p>
      <span class="post-read">Leer</span>
    </a>
    {% endfor %}
  </div>
</div>

<!-- CTF  -->
<!--<div class="section-wrap">
  <div class="section-head">
    <span class="section-num">02</span>
    <span class="section-title">Writeups</span>
    <a class="section-more" href="/writeups/">Ver todos</a>
  </div>
  <table class="ctf-table">
    <thead>
      <tr>
        <th>#</th>
        <th>Máquina / Reto</th>
        <th>Plataforma</th>
        <th>Tags</th>
        <th style="text-align:right">Dificultad</th>
      </tr>
    </thead>
    <tbody>
      {% assign sorted_writeups = site.writeups | sort: 'date' | reverse %}
      {% for writeup in sorted_writeups limit:5 %}
      <tr onclick="location.href='{{ writeup.url }}'">
        <td class="td-num">{{ forloop.index | prepend: '0' | slice: -2, 2 }}</td>
        <td class="td-machine">{{ writeup.title }}</td>
        <td class="td-platform">{{ writeup.platform }}</td>
        <td class="td-tags">
          {% for tag in writeup.tags %}
          <span class="tag tag-{{ tag }}">{{ tag }}</span>
          {% endfor %}
        </td>
        <td class="td-diff diff-{{ writeup.difficulty | downcase }}">{{ writeup.difficulty }}</td>
      </tr>
      {% endfor %}
    </tbody>
  </table>
</div>
-->
