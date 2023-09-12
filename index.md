---
layout: default
title: Home
description: "Fabian Stadler is a software engineer with multiple years of experience in research and development. They specialize in cloud development and data integration."
---

<br>

<div class="profile">
    <img src="/assets/img/fabian_stadler.jpg" alt="Profile image">
    <h1>Fabian Stadler</h1>
    <h5 class="post-date">Freelance Software Engineer</h5>
</div>


#### Recent Posts
<table class="home-table">
    {% for post in site.posts limit:5 %}
    <tr>
        <td><a href="{{ post.url }}">{{ post.title }}</a></td>
        <td>{{ post.date | date: "%b %-d, %Y" }}</td>
    </tr>
    {% endfor %}
</table>