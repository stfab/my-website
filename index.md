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
    <div class="left">
        <h3>PostgreSQL</h3>
        <img src="/assets/img/hard_drive_disk.jpg" alt="Image of a hard drive disk">
        <p>PostgreSQL is one of the most popular and powerful open source databases. I can support you with the integration and maintenance of your database. I will also help you to manage and monitor your PostgreSQL instances so that you can access your data quickly and efficiently.</p>
    </div>
</div>

<div class="home-section">
    <div class="right">
        <h3>Message Brokers</h3>
        <img src="/assets/img/cloud.jpg" alt="Image of a cloud">
        <p>Distributed systems must be able to communicate with each other at all times. To make this possible, I implement a suitable message broker such as Apache Kafka or RabbitMQ for you. I will also assist you with the administration and maintenance of your message brokers.</p>
    </div>
</div>


<div class="home-section">
    <div class="left">
        <h3>NoSQL Databases</h3>
        <img src="/assets/img/interface-3593269_640.png" alt="Image of an interface">
        <p>NoSQL databases enable the processing of documents, graphs and other data structures that cannot be stored efficiently in relational databases. I support you with issues relating to MongoDB, Cassandra and Elasticsearch. This allows you to develop applications that are customised to your data.</p>
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

