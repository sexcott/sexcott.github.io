---
layout: default
title: Certificaciones
---

<section class="page-section">
  <div class="sec-head">
    <span class="sec-title">Certificaciones</span>
  </div>

  <div class="cert-grid">
    {% for cert in site.certifications %}
    <div class="cert-cell" data-abbr="{{ cert.abbr }}">
      <span class="cert-badge cert-{{ cert.status }}">
        {% if cert.status == 'done' %}Obtenida
        {% elsif cert.status == 'wip' %}En progreso
        {% else %}Pendiente{% endif %}
      </span>
      <div class="cert-name">{{ cert.abbr }}</div>
      <div class="cert-org">{{ cert.issuer }}</div>
      <p class="cert-desc">{{ cert.description }}</p>
    </div>
    {% else %}
    <p class="empty-msg">Agrega tus certificaciones en <code>_certifications/</code></p>
    {% endfor %}
  </div>
</section>
