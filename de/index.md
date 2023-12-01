---
layout: default-de
title: Startseite
description: "Fabian Stadler ist ein Software-Ingenieur mit mehrjähriger Erfahrung in Forschung und Entwicklung. Er ist spezialisiert auf Cloud-Entwicklung und Datenintegration."
permalink: de/index.html
---

<section class="index-header">
    <img src="/assets/img/company_logo.jpg" alt="Company logo of Fabian Stadler Solutions">
    <div class="centered"><h2>Enabling Data - Driving Results</h2></div>
</section>

## Lösungen

<div class="home-section">
    <div class="left">
        <h3>PostgreSQL</h3>
        <img src="/assets/img/hard_drive_disk.jpg" alt="Image of a hard drive disk">
        <p>PostgreSQL ist eine der beliebtesten und mächtigsten Open-Source-Datenbanken. Ich unterstütze Sie bei der Integration und Wartung Ihrer Datenbank. Gerne helfe ich Ihnen auch bei der Verwaltung und Überwachung Ihrer PostgreSQL-Instanzen, damit Sie schnell und effizient auf Ihre Daten zugreifen können.</p>
    </div>
</div>

<div class="home-section">
    <div class="right">
        <h3>Nachrichtenbroker</h3>
        <img src="/assets/img/cloud.jpg" alt="Image of a cloud">
        <p>Verteilte Systeme müssen jederzeit miteinander kommunizieren können. Um dies zu ermöglichen, übernehme ich die Implementierung eines geeigneten Nachrichtenbrokers wie Apache Kafka oder RabbitMQ für Sie. Auch bei der Verwaltung und Wartung von Nachrichtenbrokern stehe ich Ihnen gerne zur Seite.</p>
    </div>
</div>


<div class="home-section">
    <div class="left">
        <h3>NoSQL-Datenbanken</h3>
        <img src="/assets/img/interface-3593269_640.png" alt="Image of an interface">
        <p>NoSQL-Datenbanken ermöglichen die Verarbeitung von Dokumenten, Graphen und anderen Datenstrukturen, die in relationalen Datenbanken nicht effizient gespeichert werden können. Ich unterstütze Sie bei Themen zu MongoDB, Cassandra und Elasticsearch. So können Sie Anwendungen entwickeln, die auf Ihre Daten zugeschnitten sind.</p>
    </div>
</div>

----

## Über

<div class="profile-section">
    <div class="profile">
        <img src="/assets/img/fabian_stadler.jpg" alt="Profile image">
        <h1>Fabian Stadler</h1>
        <h5 class="post-date">Senior Software-Ingenieur</h5>
    </div>
    <div class="profile-text">
        <p>Fabian Stadler ist Senior Software-Ingenieur mit über 6 Jahren Erfahrung in der Verarbeitung von Daten. Nach seinem Mathematikstudium hat er unter anderem für Unternehmen in den Bereichen ÖPNV, Pharma und Chemie gearbeitet.</p>
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

## Neuigkeiten

<table class="home-table">
    {% assign de_posts = site.posts | where_exp: "item", "item.lang == 'de'" %}
    {% for post in de_posts limit:5 %}
    <tr>
        <td class="home-post-title"><a href="{{ post.url }}">{{ post.title }}</a></td>
        <td class="home-post-date">{{ post.date | date: "%b %-d, %Y" }}</td>
    </tr>
    {% endfor %}
</table>

<p class="more-articles">
    <a href="/de/posts.html">Alle Artikel</a>
</p>
