---
layout: page
title: Amelia
subtitle: A Large Model and Dataset for Airport Surface Movement Forecasting
hide_footer: false
hide_hero: false
hero_image: /assets/posts/2024-06-14-amelia-dataset/klax_header.gif
hero_height: is-large
---

<div align="center"><h1 class="title">Our Motivation</h1></div>

The growing demand for air travel requires technological advancements in air traffic management as well as mechanisms for monitoring and ensuring **safe** and **efficient** operations.  

#### Some trends...
<div align="center">
  <video width="800" autoplay loop muted>
    <source src="/assets/video/trends.mp4" type="video/mp4" />
    <source src="/assets/video/trends.webm" type="video/webm" />
  </video>
</div>

#### A near miss...

<div align="center">
  <video width="1000" autoplay loop muted playsinline>
    <source src="/assets/video/sfo_incursion_red.mp4" type="video/mp4" />
    <source src="/assets/video/sfo_incursion_red.webm" type="video/webm" />
  </video>
  <h5>A triple runway incursion at San Francisco International Airport (4x speed) </h5>
  <h7>July 11th, 2023 </h7>
</div>

<br>

To improve airport safety and efficiency and encourage further research in this direction we introduce **Amelia**, a large-scale dataset of airport surface movement and a toolkit for data analysis, visualization, benchmarking, and behavior modeling. 

<hr>

<div align="center"><h1 class="title">Our Framework </h1></div>

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