---
layout: default
title: Home
description: "Fabian Stadler is a software engineer with multiple years of experience in research and development. They specialize in cloud development and data integration."
---

<br>

<!-- insert a profile image and name and title in the center of the page -->
<div>
    <img src="/assets/img/fabian_stadler.jpg" alt="Profile image" style="width: 150px; height: 150px; border-radius: 50%; margin: 0 auto; display: block;">
    <h2 style="text-align: center; margin-bottom:10px; margin-top:10px">Fabian Stadler</h2>
    <h5 class="post-date" style="text-align: center; font-size:16px">Freelance Software Engineer</h5>
</div>


#### Recent Posts
<table class="home-table">
    {% for post in site.posts limit:5 %}
    <tr>
        <td style="text-align: left"><a href="{{ post.url }}">{{ post.title }}</a></td>
        <td style="text-align: left">{{ post.date | date: "%b %-d, %Y" }}</td>
    </tr>
    {% endfor %}
</table>