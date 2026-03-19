---
layout: default
title: Home
---

<section class="hero">
  <div class="hero-left">
    <p class="hero-label">
      <span class="hero-dot"></span>
      Security Researcher
    </p>
    <h1 class="hero-name">
      <div class="name-main">Hola, soy</div>
      <div class="name-handle">sexcott.</div>
    </h1>
    <p class="hero-bio">
      Apasionado por la seguridad ofensiva, CTFs y el aprendizaje continuo.
      Aquí documento certificaciones, resolución de retos y reflexiones del camino.
    </p>
    <div class="hero-chips">
      <span class="chip active">Pentesting</span>
      <span class="chip active">CTF Player</span>
      <span class="chip">Red Team</span>
      <span class="chip">Web Security</span>
      <span class="chip">Reversing</span>
    </div>
    <div class="hero-actions">
      <a class="btn btn-primary" href="{{ '/writeups/' | relative_url }}">Ver writeups</a>
      <a class="btn btn-secondary" href="https://github.com/{{ site.author.github }}" target="_blank">GitHub</a>
    </div>
  </div>
  <div class="hero-stats">
    <div class="stat-item">
      <div class="stat-n">{{ site.writeups | size }}</div>
      <div class="stat-l">Writeups</div>
    </div>
    <div class="stat-item">
      <div class="stat-n">{{ site.posts | size }}</div>
      <div class="stat-l">Posts</div>
    </div>
    <div class="stat-item">
      <div class="stat-n">{{ site.certifications | size }}</div>
      <div class="stat-l">Certs</div>
    </div>
  </div>
</section>

<!-- CERTIFICACIONES -->
<div class="section-wrap">
  <div class="section-head">
    <span class="section-num">01</span>
    <span class="section-title">Certificaciones</span>
    <a class="section-more" href="/certs/">Ver todas</a>
  </div>
  <div class="cert-grid">
    {% for cert in site.certifications limit:3 %}
    <div class="cert-card">
      <div class="cert-status {{ cert.status }}">{{ cert.status_label }}</div>
      <div class="cert-title">{{ cert.short }}</div>
      <div class="cert-org">{{ cert.issuer }}</div>
      <p class="cert-body">{{ cert.description }}</p>
    </div>
    {% endfor %}
  </div>
</div>

<!-- CTF WRITEUPS -->
<div class="section-wrap">
  <div class="section-head">
    <span class="section-num">02</span>
    <span class="section-title">CTF Writeups</span>
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

<!-- BLOG -->
<div class="section-wrap">
  <div class="section-head">
    <span class="section-num">03</span>
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
