---
layout: page
title: Amelia
subtitle: A Large Model and Dataset for Airport Surface Movement Forecasting
hide_footer: false
hide_hero: false
hero_image: /assets/posts/2024-06-14-amelia-dataset/klax_header.gif
hero_height: is-large
---

# Our Motivation

Within the US National Airspace System (NAS), the first two months of 2023 saw more aircraft close-calls than they had during all of the previous five years combined.

<div align="center">
  <video width="1000" autoplay loop muted>
    <source src="/assets/video/sfo_incursion.webm" type="video/mp4" />
  </video>
  <h4>A triple runway incursion at San Francisco International Airport </h4>
  <h6>July 11th, 2023 </h6>
</div>

<br>

The year of 2023 also broke the record for the most number of travelers processed by TSA by screening 2.9 million passengers in a single day. This growing demand for air travel along with the planned introduction of Advanced Aerial Mobility (AAM) concepts like eVTOLs require technological advancements in air traffic management, including mechanisms for monitoring and ensuring **safe** and **efficient** operations.  

Our work, **Amelia**, aims to contribute toward improving airport safety and efficiency and encourage further research in this direction. 

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

{% include software.html %}

<hr>

{% include authors.html %}

{% include professors.html %}

<hr>

# Papers

#### Amelia: A Large Model and Dataset for Airport Surface Movement Forecasting

[Ingrid Navarro](https://navars.xyz) *, [Pablo Ortega-Kral](https://paok-2001.github.io) *, [Jay Patrikar](https://www.jaypatrikar.me) *, Haichuan Wang, 
Zelin Ye, Jong Hoon Park, [Jean Oh](https://cmubig.github.io/team/jean_oh/) and [Sebastian Scherer](https://theairlab.org/team/sebastian/) 

*Denotes equal contribution 

<a class="button" itemprop="code" href="https://github.com/AmeliaCMU" target="_blank">
  <i class="fas fa-code fa-lg"></i>    
</a> 
<a class="button" itemprop="paper" href="https://arxiv.org/pdf/2309.08889" target="_blank">
  <i class="fas fa-file fa-lg"></i>    
</a> 

```
@article{navarro2024amelia,
  title={Amelia: A Large Model and Dataset for Airport Surface
Movement Forecasting},
  author={Navarro, Ingrid and Ortega-Kral, Pablo and Patrikar, Jay, and Haichuan, Wang and Park, Jong Hoon and Oh, Jean and Scherer, Sebastian},
  journal={arXiv preprint arXiv:2309.08889},
  year={2024}
}
```

<hr>