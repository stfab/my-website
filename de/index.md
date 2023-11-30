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
    <div class="right">
        <h3>Datenmigration</h3>
        <img src="/assets/img/cloud.jpg" alt="Image of a cloud">
        <p>Bei der Migration von Daten in neue Systeme benötigen Sie eine robuste und hochperformante Lösung. Ich erstelle für Sie ein Datenmapping und implementiere eine Lösung, die Ihre Daten sicher und zuverlässig in das Zielsystem überträgt. Gerne unterstütze ich Sie auch bei der Wartung existierender Lösungen.</p>
    </div>
</div>

<div class="home-section">
    <div class="left">
        <h3>Datenaufbereitung & Reinigung</h3>
        <img src="/assets/img/datamining.jpg" alt="Image of a mining site and pipes">
        <p>Um aussagekräftige Analysen durchzuführen, müssen Daten aufbereitet und gereinigt werden. Ich automatisiere die Transformation Ihrer Daten und stelle sicher, dass Sie die richtigen Daten zur Verfügung haben. So können Sie sich auf die Analyse konzentrieren und Ihre Entscheidungen auf eine solide Datenbasis stützen.</p>
    </div>
</div>

<div class="home-section">
    <div class="right">
        <h3>Qualitätssicherung</h3>
        <img src="/assets/img/interface-3593269_640.png" alt="Image of an interface">
        <p>Datenqualität ist ein wichtiger Faktor, wenn es darum geht langfristig gute Entscheidungen zu treffen. Ich unterstütze Sie bei der Einführung von Datenqualitätsprozessen und der Implementierung von Datenqualitätsmetriken. So erhalten Sie jederzeit einen Überblick über die Qualität Ihrer Daten und können auf Veränderungen reagieren.</p>
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
