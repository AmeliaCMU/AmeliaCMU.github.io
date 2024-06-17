---
layout: page
title: Contributions
permalink: /research-posts/
hero_height: is-small
hero_image: /assets/img/background.jpg
---
{% assign posts = site.posts | where:"categories","publication" %}
<div class="columns is-multiline">
    {% for post in posts %}
        <div class="column is-6-desktop is-6-tablet">
            {% include post-card.html %}
        </div>
    {% endfor %}
</div>