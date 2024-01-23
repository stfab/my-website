---
layout: default
title: Home
description: "Fabian Stadler is a freelancer, senior software engineer and data protection officer (TÜV). Fabian has many years of experience in data protection, ETL development and cloud backend development."
---

<section class="index-header">
    <img src="/assets/img/company_logo.jpg" alt="Company logo of Fabian Stadler Solutions">
    <div class="centered"><h2>Enabling Data - Driving Results</h2></div>
</section>

## Services

<div class="home-section">
    <div class="left">
        <h3>Software Development</h3>
        <img src="/assets/img/lightbulb-3104355_640.jpg" alt="Bild einer Glühbirne">
        <p>Automated processes require customized software systems. I develop individual software for you that optimally supports your processes. I use modern programming languages and frameworks. I am also happy to support you in the further development of your existing software.</p>
    </div>
</div>

<div class="home-section">
    <div class="right">
        <h3>System Integration & Maintenance</h3>
        <img src="/assets/img/interface-3593269_640.png" alt="Bild einer Schnittstelle">
        <p>Companies use a variety of commercial software systems. I support you from the selection of the right systems through to integration into your existing IT landscape. I also offer long-term support, training for your employees and the integration of security systems.</p>
    </div>
</div>

<div class="home-section">
    <div class="left">
        <h3>Data Privacy</h3>
        <img src="/assets/img/hard_drive_disk.jpg" alt="Bild einer Festplatte">
        <p>As certified Data Protection Officer (TÜV), you can appoint me externally to fulfill the tasks for you in accordance with Art. 39 GDPR. Among other things, I can advise you on the implementation of the General Data Protection Regulation (GDPR) and the German Federal Data Protection Act (BDSG), as well as legally related regulations.</p>
    </div>
</div>
----

## About

<div class="profile-section">
    <div class="profile">
        <img src="/assets/img/fabian_stadler.jpg" alt="Profile image" loading="eager">
        <h1>Fabian Stadler</h1>
        <h5 class="post-date">Senior Software Engineer</h5>
    </div>
    <div class="profile-text">
        <p>Fabian Stadler is a Senior Software Engineer with more than 6 years of experience in software development. After studying mathematics, Fabian worked for companies in the public transport, pharmaceutical and chemical industries, among others.</p>
        {% for item in site.social %}
            {% assign first_char = item.link | slice: 0 %}
            {% if item.icon == 'mastodon' %}
            <a class="icon contact-button"  rel="me" href="{{ item.link }}" target="_blank"><i class="fa-brands fa-{{ item.icon }}" aria-hidden="true"></i></a>
            {% else %}
            <a class="icon contact-button" href="{{ item.link }}" target="_blank"><i class="fa-{{ item.icon-class }} fa-{{ item.icon }}" aria-hidden="true"></i></a>
            {% endif %}
        {% endfor %}
    </div>
</div>

----

## News

<table class="home-table">
    {% assign de_posts = site.posts | where_exp: "item", "item.lang == 'en'" %}
    {% for post in de_posts limit:5 %}
    <tr>
        <td class="home-post-title"><a href="{{ post.url }}">{{ post.title }}</a></td>
        <td class="home-post-date">{{ post.date | date: "%b %-d, %Y" }}</td>
    </tr>
    {% endfor %}
</table>

<p class="more-articles">
    <a href="/posts.html">All Articles</a>
</p>

