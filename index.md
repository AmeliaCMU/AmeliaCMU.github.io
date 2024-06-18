---
layout: page
title: Amelia
subtitle: A Large Model and Dataset for Airport Surface Movement Forecasting
hide_footer: true
hide_hero: false
hero_image: /assets/posts/2024-06-14-amelia-dataset/klax_header.gif
hero_height: is-large
---
<link href="assets/css/resume.css" rel="stylesheet">

{% include about.html %}

<hr>

{% assign posts = site.posts | where:"categories","publication" %}
<div class="columns is-multiline">
    {% for post in posts %}
        <div class="column is-6-desktop is-6-tablet">
            {% include post-card.html %}
        </div>
    {% endfor %}
</div>