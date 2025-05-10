---
layout: post
author: Ingrid Navarro and Pablo Ortega-Kral
permalink: /amelia-model/
title: Amelia-TF
subtitle: A large model for airport surface movement forecasting.
image: /assets/posts/2024-06-17-amelia-model/model.png
link-new-tab: true
hide_hero: true
hide_footer: false
categories: publication
hero_image: /assets/img/background.jpg
hero_height: is-large
---

<h1>
Amelia-TF: A Large Model for Airport Surface Movement Forecasting
</h1>

<a class="button" itemprop="paper" href="https://arxiv.org/pdf/2407.21185" target="_blank">
  <i class="fas fa-file fa-lg"></i>
</a>

<hr>

Predictive models for airport surface operations can be used for various downstream tasks like
collision risk assessment, taxi-out time prediction, departure metering, and emission estimations.
While data-driven methods have showcased marked improvements in predictive performance in recent
years, prior works have not addressed the lack of large-scale curated surface movement datasets
within the public domain and the development of generalizable trajectory forecasting models.

In response to this, we introduce **Amelia-TF** is a large transformer-based airport surface movement
trajectory forecasting model trained on the **[Amelia-42](https://ameliacmu.github.io/amelia-dataset/)**
dataset. We explore different scene representation and training strategies for our model varying from
single-airport to multi-airport settings in which we assess our model's generalization capabilities.

<div align="center">
  <img src="/assets/posts/2024-06-17-amelia-model/ksfo_results.gif" alt="ego_selection" style="width:800px;">
  <h5>Amelia-TF predicting aircraft future motions at San Francisco International Airport </h5>
</div>

<br>

Below, we provide an overview of our model and experiments. For more details, please check out our paper!

## Model Overview

Amelia-TF is an end-to-end motion prediction model that aims to characterize *relevant* surface
area operations. To do so, our model comprises three main submodules:
1. A **scene representation** module that determines the agents of interest in the scene using a scoring strategy, and encodes per-agent features,
2. A transformer-based **scene encoder**, which hierarchically encodes the *temporal*, *agent-to-agent* and *agent-to-context* relationships within a scene, and;
3. A **trajectory decoder** that models the set of possible futures with associated confidence scores using a Gaussian Mixture Model.

<div align="center">
<video width="1000" autoplay loop muted>
  <source src="/assets/posts/2024-06-17-amelia-model/amelia_overview.mp4" type="video/mp4" />
  <source src="/assets/posts/2024-06-17-amelia-model/amelia_overview.webm" type="video/webm" />
</video>
</div>

# Experiments and Results

We explored two main experiments to assess the performance of **Amelia-TF**. The first experiment
studies the benefit of our proposed scene representation strategy. The second experiment explores the generalization of our model across airports.

### Ego-selection strategy

We want to assess if our ego-selection strategy produces complex and interesting scene
representations since it prioritizes more critical agent-to-agent relationships and more dynamic agent motion profiles within a scene.


To do so we compare our proposed idea against a *random* agent selection strategy.

#### Quantitative Results

<div align="center">
<video width="1000" autoplay loop muted>
  <source src="/assets/posts/2024-06-17-amelia-model/ego_results.mp4" type="video/mp4" />
  <source src="/assets/posts/2024-06-17-amelia-model/ego_results.webm" type="video/webm" />
</video>
</div>

#### Qualitative Results

<style>
.egoSlides {display:none;}
</style>

<div align="center">
  <table align="center">
    <tr>
      <td><b>Random Ego-agent Selection Strategy</b></td>
      <td><b>Critical Ego-agent Selection Strategy</b></td>
    </tr>
  </table>
  <img class="egoSlides" src="/assets/posts/2024-06-17-amelia-model/ego_results_1.png" style="width:100%">
  <img class="egoSlides" src="/assets/posts/2024-06-17-amelia-model/ego_results_2.png" style="width:100%">
  <img class="egoSlides" src="/assets/posts/2024-06-17-amelia-model/ego_results_3.png" style="width:100%">
  <img class="egoSlides" src="/assets/posts/2024-06-17-amelia-model/ego_results_4.png" style="width:100%">
  <img class="egoSlides" src="/assets/posts/2024-06-17-amelia-model/ego_results_5.png" style="width:100%">

  <div align="center">
    <button class="button-slide" onclick="plusDivs(-1, 'egoSlides')">&#10094;</button>
    <button class="button-slide" onclick="plusDivs(1, 'egoSlides')">&#10095;</button>
  </div>
</div>

### Multi-Airport generalization

We also explore our model's generalization capabilities as we cover a wider variety of training data. We hypothesize that as we do so, our model will learn richer representations that would generalize better to unseen airport layouts and interactions.

This would eventually reduce the requirement for more training data and/or adaptation techniques, such as fine-tuning. Thus, we propose a *multi-airport* ablation to assess **Amelia-TF**'s performance in *unseen* airports as we vary the number of *seen* ones during training.


#### Quantitative Results

<div align="center">
<video width="1000" autoplay loop muted>
  <source src="/assets/posts/2024-06-17-amelia-model/gen_results.mp4" type="video/mp4" />
  <source src="/assets/posts/2024-06-17-amelia-model/gen_results.webm" type="video/webm" />
</video>
</div>

#### Qualitative Results

<style>
.genSlides {display:none;}
</style>

<div align="center">
  <table align="center">
    <tr>
      <td><b>Seen Airports&emsp;&emsp;</b></td>
      <td><b>Unseen Airports</b></td>
    </tr>
  </table>
  <img class="genSlides" src="/assets/posts/2024-06-17-amelia-model/ego_results_1.png" style="width:100%">
  <img class="genSlides" src="/assets/posts/2024-06-17-amelia-model/ego_results_2.png" style="width:100%">
  <img class="genSlides" src="/assets/posts/2024-06-17-amelia-model/ego_results_3.png" style="width:100%">
  <img class="genSlides" src="/assets/posts/2024-06-17-amelia-model/ego_results_4.png" style="width:100%">
  <img class="genSlides" src="/assets/posts/2024-06-17-amelia-model/ego_results_5.png" style="width:100%">
  <br>
  <div align="center">
    <button class="button-slide" onclick="plusDivs(-1, 'genSlides')">&#10094;</button>
    <button class="button-slide" onclick="plusDivs(1, 'genSlides')">&#10095;</button>
  </div>
</div>

<script>
var slideIndex = 1;
showDivs(slideIndex, 'egoSlides');
showDivs(slideIndex, 'genSlides');

function plusDivs(n, class_name) {
  showDivs(slideIndex += n, class_name);
}

function showDivs(n, class_name) {
  var i;
  var x = document.getElementsByClassName(class_name);
  if (n > x.length) {slideIndex = 1}
  if (n < 1) {slideIndex = x.length}
  for (i = 0; i < x.length; i++) {
    x[i].style.display = "none";
  }
  x[slideIndex-1].style.display = "block";
}
</script>

# BibTeX

If you find our work useful in your research, please cite us!

```bibtex
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