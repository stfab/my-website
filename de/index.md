---
layout: default-de
title: Startseite
description: "Fabian Stadler ist ein Software-Ingenieur mit mehrjähriger Erfahrung in Forschung und Entwicklung. Er ist spezialisiert auf Cloud-Entwicklung und Datenintegration."
permalink: de/index.html
---

<section class="index-header">
    <img src="/assets/img/company_logo.jpg" alt="Company logo of Fabian Stadler Solutions">
    <div class="centered"><h2>Mit Kontinuierlicher Integration zum Erfolg</h2></div>
</section>

## Lösungen

<div class="home-section">
    <div class="right">
        <h3>Planung & Integration</h3>
        <img src="/assets/img/interface-3593269_640.png" alt="Image of an interface">
        <p>CI/CD-Systeme fördern nachhaltig die kontinuierliche Qualitätssicherung und Auslieferung von Software. Ich unterstütze Sie bei der Planung und Implementierung solcher Lösungen. Dabei setze ich auf Enterprise-Produkte (GitLab, TeamCity) und quelloffene Lösungen (Buildbot, GoCD & Jenkins).</p>
    </div>
</div>

<div class="home-section">
    <div class="left">
        <h3>Administration & Verwaltung</h3>
        <img src="/assets/img/toolbox.jpg" alt="Image of a toolbox">
        <p>Um Software auf verschiedenen Plattformen auszuliefern, ist eine effiziente Verwaltung der Testsysteme unerlässlich. Gerne helfe ich Ihnen bei der Umsetzung Ihrer Build- und Teststrategie und erstelle eine wiederverwertbare Provisionierung Ihrer Maschinen mit Tools wie Ansible oder Docker.</p>
    </div>
</div>

<div class="home-section">
    <div class="right">
        <h3>Plugin Entwicklung</h3>
        <img src="/assets/img/lightbulb-3104355_640.jpg" alt="Image of a lightbulb">
        <p>Nicht immer decken vorhandene Softwarelösungen alle Anforderungen ab. Wenn Sie einmal mehr Funktionen benötigen, entwickle ich für Sie Plugins oder Services, die ihr System erweitern. Auch die Integration in weitere Systeme ihrer IT-Landschaft wie Ticketsysteme oder Kollaborationsplattformen ist möglich.</p>
    </div>
</div>

<div class="home-section">
    <div class="left">
        <h3>Wartung & Sicherheit</h3>
        <img src="/assets/img/hard_drive_disk.jpg" alt="Image of a hard drive disk"> 
        <p>Selbst das stabilste System benötigt Wartung und Pflege. Ich kontaktiere Sie bezüglich wichtiger Updates und helfe bei der Planung und Implementierung von Backup- und Recovery-Strategien. Auch um die Anbindung eines Überwachungssystems kümmere ich mich gerne. So erfüllen Sie stets die Anforderungen an Datenschutz und Datensicherheit.</p>
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
        <p>Fabian Stadler ist Senior Software-Ingenieur mit mehr als 6 Jahren Erfahrung mit CI/CD-Systemen. Nach seinem Mathematikstudium hat er unter anderem für Unternehmen in den Bereichen ÖPNV, Pharma und Chemie gearbeitet.</p>
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
