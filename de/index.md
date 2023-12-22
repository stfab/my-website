---
layout: default-de
title: Startseite
description: "Fabian Stadler ist Senior Software-Ingenieur*in und Datenschutzbeauftragte*r (TÜV). Durch langjährige Erfahrung unterstützt Fabian Sie bei der Umsetzung Ihrer IT-Projekte."
permalink: de/index.html
---

<section class="index-header">
    <img src="/assets/img/company_logo.jpg" alt="Logo von Fabian Stadler" loading="eager">
    <div class="centered"><h2>Enabling Data - Driving Results</h2></div>
</section>

## Lösungen

<div class="home-section">
    <div class="left">
        <h3>Softwareentwicklung</h3>
        <img src="/assets/img/lightbulb-3104355_640.jpg" alt="Bild einer Glühbirne">
        <p>Automatisierte Prozesse erfordern maßgeschneiderte Sofwaresysteme. Ich entwickle für Sie individuelle Software, die Ihre Prozesse optimal unterstützt. Dabei setze ich auf moderne Programmiersprachen und Frameworks. Gerne unterstütze ich Sie auch bei der Weiterentwicklung Ihrer bestehenden Software.</p>
    </div>
</div>

<div class="home-section">
    <div class="right">
        <h3>Systemintegration & Wartung</h3>
        <img src="/assets/img/interface-3593269_640.png" alt="Bild einer Schnittstelle">
        <p>Unternehmen nutzen eine Vielzahl von kommerziellen Softwaresystemen. Ich unterstütze Sie von der Auswahl der richtigen Systeme bis hin zur Integration in Ihre bestehende IT-Landschaft. Dazu biete ich langfristigen Support, die Schulung Ihrer Mitarbeitenden und die Anbindung von Sicherheitssystemen.</p>
    </div>
</div>

<div class="home-section">
    <div class="left">
        <h3>Datenschutzbeauftragte*r</h3>
        <img src="/assets/img/hard_drive_disk.jpg" alt="Bild einer Festplatte">
        <p>Ab einer Größe von 20 Mitarbeitenden sind Unternehmen verpflichtet, eine*n Datenschutzbeauftragte*n zu bestellen. Als Datenschutzbeauftragte*r (TÜV) unterstütze ich Sie bei der Umsetzung der Datenschutz-Grundverordnung (DSGVO) und der Einhaltung der datenschutzrechtlichen Vorgaben.</p>
    </div>
</div>

----

## Über

<div class="profile-section">
    <div class="profile">
        <img src="/assets/img/fabian_stadler.jpg" alt="Profilbild von Fabian Stadler">
        <h1>Fabian Stadler</h1>
        <h5 class="post-date">Senior Software-Ingenieur*in</h5>
    </div>
    <div class="profile-text">
        <p>Fabian Stadler ist Senior Software-Ingenieur*in mit mehr als 6 Jahren Erfahrung in der Softwareentwicklung. Nach dem Mathematikstudium hat Fabian unter anderem für Unternehmen in den Bereichen ÖPNV, Pharma und Chemie gearbeitet.</p>
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
