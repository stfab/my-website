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
        <h3>Datenanalyse, Migration & Mining</h3>
        <img src="/assets/img/datamining.jpg" alt="Image of a mining site and pipes">
        <p>Viele Unternehmen nutzen Tracking-Software und CRM-Systeme, um Daten über ihre Kunden zu sammeln. Allerdings sind diese Daten oft über viele Dienste verteilt. Ich kann Ihre Daten in einen einzigen Langzeitspeicher bringen und eine Plattform schaffen, mit der Sie die wichtigsten KPIs reibungslos analysieren können. Hierfür verwende ich Tools wie Azure Data Factory, Databricks oder eigenen Code.</p>
    </div>
</div>

<div class="home-section">
    <div class="left">
        <h3>Cloud-Entwicklung & Migration</h3>
        <img src="/assets/img/cloud.jpg" alt="Image of a cloud that is shaped lika a heart">
        <p>Die Verlagerung Ihrer Geschäftsanwendungen in die Cloud kann Ihnen helfen, Kosten zu senken und Ihr Unternehmen flexibler zu machen. Ich kann Ihnen helfen, Ihre Anwendungen auf On-Demand-Dienste in der Microsoft Azure Cloud zu migrieren. Auf diese Weise können Sie Ihre Anwendungen nach Ihren Bedürfnissen skalieren und zahlen nur für das, was Sie nutzen.</p>
    </div>
</div>

<div class="home-section">
    <div class="right">
        <h3>Tool-Erstellung & APIs</h3>
        <img src="/assets/img/toolbox.jpg" alt="Image of a toolbox">
        <p>Desktop- oder webbasierte Tools können Ihnen helfen, Ihre Geschäftsprozesse zu automatisieren und Ihre Mitarbeiter produktiver zu machen. APIs können Ihnen helfen, Ihre Systeme mit denen Ihrer Partner zu integrieren. In der Vergangenheit habe ich an einer breiten Palette solcher Tools und APIs gearbeitet. Ich kann Ihnen helfen, solche Tools mit Programmiersprachen wie Python, C#, Java und gängigen Frameworks zu erstellen.</p>
    </div>
</div>

<div class="home-section">
    <div class="left">
        <h3>Datenbank Überwachung & Optimierung</h3>
        <img src="/assets/img/hard_drive_disk.jpg" alt="Image of a hard drive disk">
        <p>Datenbanken sind das Herzstück jeder datengesteuerten Anwendung. Allerdings neigen sie dazu, mit der Zeit und durch unsachgemäße Nutzung langsam und ineffizient zu werden. Um Ihnen bei der Lösung solcher Probleme zu helfen, biete ich eine Nutzungsanalyse, Optimierung und eine moderne Überwachungsplattform an. Mein Fachwissen umfasst Produkte wie MySQL, PostgreSQL und MS-SQL Server.</p>
    </div>
</div>

----

## Über

<div class="profile-section">
    <div class="profile">
        <img src="/assets/img/fabian_stadler.jpg" alt="Profile image">
        <h1>Fabian Stadler</h1>
        <h5 class="post-date">Freiberuflicher Software-Ingenieur</h5>
    </div>
    <div class="profile-text">
        <p>Fabian Stadler ist ein Senior Software-Ingenieur mit mehrjähriger Entwicklungserfahrung. Nach seinem Mathematikstudium hat er für Unternehmen in den Bereichen öffentlicher Verkehr, Pharma und Chemie gearbeitet.</p>
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
