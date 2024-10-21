---
layout: default
title: Progra
---

# Índice de documentos

{% assign docs = site.static_files | where: "extname", ".md" %}
{% for doc in docs %}
  {% if doc.path contains "/" and doc.path contains ".md" and doc.basename != "index" %}
  - [{{ doc.basename }}]({{ doc.path }})
  {% endif %}
{% endfor %}