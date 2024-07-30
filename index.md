---
layout: page
title: Amelia
subtitle: A Large Model and Dataset for Airport Surface Movement Forecasting
hide_footer: false
hide_hero: false
hero_image: /assets/posts/2024-06-14-amelia-framework/klax_header.gif
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

#### A close call...

<!-- <div align="center">
  <video width="1000" autoplay loop muted playsinline>
  "/assets/video/sfo_incursion_red.webm"
  "/assets/video/sfo_incursion_red.mp4"
    <source src="" type="video/mp4" />
    <source src="" type="video/webm" />
  </video>
  <h5>A triple runway incursion at San Francisco International Airport (4x speed) </h5>
  <h7>July 11th, 2023 </h7>
</div> -->

<div align="center">
  <img src="/assets/video/bos_incursion_red.gif" alt="BOS Incursion" width="100%">
  <h5>A runway incursion at Boston-Logan Intl. Airport (2x speed) </h5>
  <h7>February 27, 2023</h7>
</div>

<br>

To improve airport safety and efficiency and encourage further research in this direction we introduce **Amelia**, a large-scale dataset of airport surface movement and a toolkit for data analysis, visualization, benchmarking, and behavior modeling.

Our dataset, **Amelia-48** comprises s a **year’s worth of data collection across 48 airports** and TRACON facilities within the US National Airspace System, totaling **∼30TB** of raw data.

Aditionally, inspired by the success of motion prediction models in the AV domain for safety monitoring and multi-agent coordination, we introduce **Amelia-TF**, a transformer-based large multi-agent multi-airport trajectory forecasting model **trained on 300 days or 11.36 billion tokens** of position data encompassing 10 different airports with varying topology.

<hr>

<div align="center"><h1 class="title">Keywords</h1>
<h3 class="title" style="color:#A1A4A8">
  Aviation | Machine Learning | Deep Learning | Data Science
</h3>
<h5 class="title" style="color:#BDBFC2">
  Trajectory Prediction | Anomaly Detection | Safety
</h5>
</div>

<hr>

<div align="center"><img class="center" src="assets/img/logos/amelia.png" width="30%" alt=""></div>
<br>

{% assign posts = site.posts | where:"categories","publication" %}
<div class="columns is-multiline">
    {% for post in posts %}
        <div class="column is-6-desktop is-6-tablet">
            {% include post-card.html %}
        </div>
    {% endfor %}
</div>

<br>

<hr>

{% include software.html %}

<hr>

{% include professors.html %}

{% include authors.html %}

{% include collaborators.html %}


<hr>

# Papers

<br>

#### &#128746; Amelia: A Large Model and Dataset for Airport Surface Movement Forecasting

[Ingrid Navarro](https://navars.xyz) *, [Pablo Ortega-Kral](https://paok-2001.github.io) *, [Jay Patrikar](https://www.jaypatrikar.me) *, Haichuan Wang,
Zelin Ye, Jong Hoon Park, [Jean Oh](https://cmubig.github.io/team/jean_oh/) and [Sebastian Scherer](https://theairlab.org/team/sebastian/)

*Denotes equal contribution

<a class="button" itemprop="code" href="https://github.com/AmeliaCMU" target="_blank">
  <i class="fas fa-code fa-lg"></i>
</a>
<a class="button" itemprop="paper" href="https://arxiv.org/pdf/2309.08889" target="_blank">
  <i class="fas fa-file fa-lg"></i>
</a>

```bash
@inbook{navarro2024amelia,
  author = {Ingrid Navarro and Pablo Ortega and Jay Patrikar and Haichuan Wang and Zelin Ye and Jong Hoon Park and Jean Oh and Sebastian Scherer},
  title = {AmeliaTF: A Large Model and Dataset for Airport Surface Movement Forecasting},
  booktitle = {AIAA AVIATION FORUM AND ASCEND 2024},
  chapter = {},
  pages = {},
  doi = {10.2514/6.2024-4251},
  URL = {https://arc.aiaa.org/doi/abs/10.2514/6.2024-4251},
  eprint = {https://arc.aiaa.org/doi/pdf/10.2514/6.2024-4251},
}
```

<hr>