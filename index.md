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

[Ingrid Navarro](https://navars.xyz) *, [Pablo Ortega-Kral](https://paok-2001.github.io) *, [Jay Patrikar](https://www.jaypatrikar.me) *, Haichuan Wang, 
Zelin Ye, Jong Hoon Park, [Jean Oh](https://cmubig.github.io/team/jean_oh/) and [Sebastian Scherer](https://theairlab.org/team/sebastian/) 

*Denotes equal contribution 

**This work is a collaboration between the Bot Intelligence Group ([BIG](https://cmubig.github.io)) and the [AirLab](https://theairlab.org) at Carnegie Mellon University!**

<a class="button" itemprop="paper" href="https://arxiv.org/pdf/2309.08889" target="_blank">
  <i class="fas fa-database fa-lg"></i>    
</a> 
<a class="button" itemprop="paper" href="https://arxiv.org/pdf/2309.08889" target="_blank">
  <i class="fas fa-file fa-lg"></i>    
</a> 

# Abstract

{% include about.html %}

<hr>

# Our Model and Dataset

{% assign posts = site.posts | where:"categories","publication" %}
<div class="columns is-multiline">
    {% for post in posts %}
        <div class="column is-6-desktop is-6-tablet">
            {% include post-card.html %}
        </div>
    {% endfor %}
</div>

<hr>

# Collaborators

<style>
.grid { 
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  grid-gap: 20px;
  align-items: stretch;
  }
.grid img {
  border: 1px solid #ccc;
  box-shadow: 2px 2px 6px 0px  rgba(0,0,0,0.3);
  max-width: 100%;
}
</style>
<main class="grid">
  <img src="/assets/img/member.jpg" alt="Sample photo">
  <img src="/assets/img/member.jpg" alt="Sample photo">
  <img src="/assets/img/member.jpg" alt="Sample photo">
  <img src="/assets/img/member.jpg" alt="Sample photo">
  <img src="/assets/img/member.jpg" alt="Sample photo">
  <img src="/assets/img/member.jpg" alt="Sample photo">
  <img src="/assets/img/member.jpg" alt="Sample photo">
  <img src="/assets/img/member.jpg" alt="Sample photo">
  <img src="/assets/img/member.jpg" alt="Sample photo">
</main>