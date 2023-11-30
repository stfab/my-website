---
layout: default
title: Home
description: "Fabian Stadler is a software engineer with multiple years of experience in research and development. They specialize in cloud development and data integration."
---

<section class="index-header">
    <img src="/assets/img/company_logo.jpg" alt="Company logo of Fabian Stadler Solutions">
    <div class="centered"><h2>Enabling Data - Driving Results</h2></div>
</section>

## Services

<div class="home-section">
    <div class="right">
        <h3>Data Migration</h3>
        <img src="/assets/img/cloud.jpg" alt="Image of a cloud">
        <p>When migrating data to new systems, you need a robust and high-performance solution. I will create a data mapping for you and implement a solution that transfers your data securely and reliably to the target system. I will also support you with the maintenance of existing solutions.</p>
    </div>
</div>

<div class="home-section">
    <div class="left">
        <h3>Data Preparation & Cleaning</h3>
        <img src="/assets/img/datamining.jpg" alt="Image of a mining site and pipes">
        <p>In order to carry out meaningful analyses, data must be prepared and cleaned. I automate the transformation of your data and ensure that you have the right data available. This allows you to concentrate on the analyses and base your decisions on solid data.</p>
    </div>
</div>

<div class="home-section">
    <div class="right">
        <h3>Quality Assurance</h3>
        <img src="/assets/img/interface-3593269_640.png" alt="Image of an interface">
        <p>Data quality is an important factor when it comes to making good decisions in the long term. I support you in the introduction of data quality processes and the implementation of data quality metrics. This gives you an overview of the quality of your data at all times and enables you to react to changes.</p>
    </div>
</div>

----

## About

<div class="profile-section">
    <div class="profile">
        <img src="/assets/img/fabian_stadler.jpg" alt="Profile image">
        <h1>Fabian Stadler</h1>
        <h5 class="post-date">Senior Software Engineer</h5>
    </div>
    <div class="profile-text">
        <p>Fabian Stadler is a senior software engineer with more than 6 years of experience in processing data. They have a university degree in mathematics and have worked for companies in the public transport, pharmaceutical and chemical industries.</p>
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
    <a href="/p/posts.html">All Articles</a>
</p>

