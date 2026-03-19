---
layout: default
title: Certificaciones
permalink: /certs/
---
<div class="section-wrap">
  <div class="section-head">
    <span class="section-num">01</span>
    <span class="section-title">Certificaciones</span>
  </div>
  <div class="cert-grid">
    {% for cert in site.certifications %}
    <div class="cert-card">
      <div class="cert-status {{ cert.status }}">{{ cert.status_label }}</div>
      <div class="cert-title">{{ cert.short }}</div>
      <div class="cert-org">{{ cert.issuer }}</div>
      <p class="cert-body">{{ cert.description }}</p>
    </div>
    {% endfor %}
  </div>
</div>
