---
layout: page-de
title: Posts
description: "Diese Seite enthält eine Liste aller Beiträge von Fabian Stadler. Meistens geht es um Software-Entwicklung, manchmal um allgemeine Themen."
permalink: de/posts.html
---

{% for post in site.posts %}
  {% if post.lang == "de" %}
  {% include post-preview.html %}
  {% endif %}    
{% endfor %}
