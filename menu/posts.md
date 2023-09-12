---
layout: page
title: Posts
description: "This page contains a list of all of the posts written by Fabian Stadler. Usually, they are about software engineering, sometimes about general issues."
permalink: p/posts
---

{% for post in site.posts %}
  {% include post-preview.html %}
{% endfor %}
