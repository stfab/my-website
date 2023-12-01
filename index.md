---
layout: default
title: Home
description: "Fabian Stadler is a software engineer with multiple years of experience in research and development. They specialize in cloud development and data integration."
---

<section class="index-header">
    <img src="/assets/img/company_logo.jpg" alt="Company logo of Fabian Stadler Solutions">
    <div class="centered"><h2>Success Through Continuous Integration</h2></div>
</section>

## Services

<div class="home-section">
    <div class="right">
        <h3>Planning & Integration</h3>
        <img src="/assets/img/interface-3593269_640.png" alt="Image of an interface">
        <p>CI/CD systems sustainably promote the continuous quality assurance and delivery of software. I support you in the planning and implementation of such solutions. For this, I rely on open source and extensible products such as Jenkins, Buildbot, Travis CI or GitLab.</p>
    </div>
</div>

<div class="home-section">
    <div class="left">
        <h3>Administration & Management</h3>
        <img src="/assets/img/toolbox.jpg" alt="Image of a toolbox">
        <p>In order to deliver software on different platforms, efficient management of test systems is essential. I will help you implement an efficient build and test strategy and create a reusable provisioning of your machines with tools such as Ansible or Docker.</p>
    </div>
</div>

<div class="home-section">
    <div class="right">
        <h3>Plugin Development</h3>
        <img src="/assets/img/lightbulb-3104355_640.jpg" alt="Image of a lightbulb">
        <p>Existing software solutions do not always cover all requirements. If you ever need more functions, I can develop plugins or services for you that extend your system. Integration into other systems in your IT landscape, such as ticket systems or collaboration platforms, is also possible.</p>
    </div>
</div>

<div class="home-section">
    <div class="left">
        <h3>Maintenance & Safety</h3>
        <img src="/assets/img/hard_drive_disk.jpg" alt="Image of a hard drive disk"> 
        <p>Even the most stable system requires maintenance and care. I will contact you about important updates and help with the planning and implementation of backup and recovery strategies. I am also happy to take care of the connection of a monitoring system. This ensures that you always fulfil the requirements for data protection and data security.</p>
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
        <p>Fabian Stadler is a senior software engineer with more than 6 years of experience in CI/CD systems. They have a university degree in mathematics and have worked for companies in the public transport, pharmaceutical and chemical industries.</p>
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

