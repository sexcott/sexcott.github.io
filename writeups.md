---
layout: default
title: CTF Writeups
permalink: /writeups/
---
<div class="section-wrap">
  <div class="section-head">
    <span class="section-num">02</span>
    <span class="section-title">Writeups</span>
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
      {% for writeup in sorted_writeups %}
      <tr onclick="location.href='{{ writeup.url }}'">
        <td class="td-num">{{ forloop.index | prepend: '00' | slice: -2, 2 }}</td>
        <td class="td-machine">{{ writeup.title }}</td>
        <td class="td-platform">{{ writeup.platform }}<span>{{ writeup.date | date: "%Y-%m-%d" }}</span></td>
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
