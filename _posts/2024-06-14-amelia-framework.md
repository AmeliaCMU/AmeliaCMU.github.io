---
layout: post
author: Ingrid Navarro and Pablo Ortega-Kral
permalink: /amelia-framework/
title: Amelia Framework
subtitle: A framework for airport surface movement 
image: /assets/posts/2024-06-14-amelia-framework/klax.gif
link-new-tab: true
categories: publication
hero_image: /assets/posts/2024-06-14-amelia-framework/klax_header.gif
hide_hero: true
hide_footer: false
hero_height: is-medium
---

<h1> 
Amelia: A framework for airport surface movement
</h1>

<a class="button" itemprop="paper" href="https://arxiv.org/pdf/2309.08889" target="_blank">
  <i class="fas fa-database fa-lg"></i>    
</a> 
<a class="button" itemprop="paper" href="https://arxiv.org/pdf/2309.08889" target="_blank">
  <i class="fas fa-file fa-lg"></i>    
</a> 

<hr>

**Amelia** is a framework for airport surface movement consisting of toolkit for collecting an processing our large-scale dataset, and for building and training motion forecasting models. 

We release this toolkit to encourage research in this domain! Below we provide an overview of our **toolkit**. 

**Notes:**
* For more details on how to download and use our **dataset**, go to [Amelia-48](https://ameliacmu.github.io/amelia-dataset/)
* For more details on our trajectory forecasting **model**, go to [Amelia-TF](https://ameliacmu.github.io/amelia-model/)
* For even more details, please check out our **paper**!


# Overview of Our Framework

Our framework consists of 7 tools for processing, analyzing, visualizing and characterizing 
trajectory and map data for airport surface operations.  

<p align="center">
  <img width="1280" src="/assets/posts/2024-06-14-amelia-framework/amelia_framework.png" >
</p>


# Tools

<h3>Amelia-<span style="color:#e06666;">SWIM</span>
<span> <a class="button" itemprop="github" href="https://github.com/AmeliaCMU/AmeliaSWIM" target="_blank">
  <i class="fab fa-github fa-lg"></i>
</a></span> 
</h3>

<b>Amelia-<span style="color:#e06666;">SWIM</span></b> is a tool that uses the System Wide Information 
Management (SWIM) program to collect position reports for aircraft and vehicles operating within 48 
US airports. 

The tool produces clean, interpolated data in formats accepted by most recent ML-based trajectory 
forecasting dataloaders. The collected position reports cover both, approaching and ground movement 
events which are saved into hourly CSV files containing the following information:

<table align="center">
  <tr>
  <tr>
    <td><b>Field</b></td>
    <td><b>Unit</b></td>
    <td><b>Description</b></td>
  </tr><td>Frame</td><td>#</td><td>Timestamp</td></tr>
  <tr><td>ID</td><td>#</td><td>STDDS Agent ID</td></tr>
  <tr><td>Range</td><td>km</td><td>Distance from airport datum</td></tr>
  <tr><td>Bearing</td><td>rads</td><td>Bearing angle w.r.t North</td></tr>
  <tr><td>Altitude</td><td>feet</td><td>Agent altitude (Mean Sea Level)</td></tr>
  <tr><td>Speed</td><td>knots</td><td>Agent speed</td></tr>
  <tr><td>Heading</td><td>degrees</td><td>Agent heading</td></tr>
  <tr><td>Type</td><td>int</td><td>Agent type: {0: aircraft 1: vehicle, 2: unknown}</td></tr>
  <tr><td>Lat</td><td>decimal degrees</td><td>Agent's latitude</td></tr>
  <tr><td>Lon</td><td>decimal degrees</td><td>Agent's longitude</td></tr>
  <tr><td>x</td><td>km</td><td>Agent's local x Cartesian position</td></tr>
  <tr><td>y</td><td>km</td><td>Agent's local y Cartesian position</td></tr>
  <tr><td>Interp</td><td>boolean</td><td>Interpolated data point flag</td></tr>
</table>

<hr>

<h3>Amelia-<span style="color:#20948b;">Maps</span>
<span> <a class="button" itemprop="github" href="https://github.com/AmeliaCMU/AmeliaMaps" target="_blank">
  <i class="fab fa-github fa-lg"></i>
</a></span> 
</h3>

We use the <b>Amelia-<span style="color:#20948b;">Maps</span></b> tool to collect and produce airport 
surface maps. 

The tools converts OpenStreetMap (OSM) maps into light-weight, graph-based semantic 
maps through a series of automated steps that involve <b>a)</b> obtaining the raw graphs from OSM, <b>b)</b> 
filtering out irrelevant regions and assigning semantic labels for regions of interest, <b>c)</b> extending 
regions of interest, <b>d)</b> supersampling for obtaining a finer granularity, and <b>e)</b> obtaining the final 
data representation. 

<p align="center">
  <img width="1280" src="/assets/posts/2024-06-14-amelia-framework/map_processing.gif" >
</p>

<hr>

<h3>Amelia-<span style="color:#3c78d8;">DataTools</span>
<span> <a class="button" itemprop="github" href="https://github.com/AmeliaCMU/AmeliaDataTools" target="_blank">
  <i class="fab fa-github fa-lg"></i>
</a></span> 
</h3>

We provide <b>Amelia-<span style="color:#3c78d8;">DataTools</span></b> to validate and analyze our collected and pre-processed data via a set of scripts that provide visualizations and data statistics. 

As an initial step, we validate and analyze the trajectory and map data for **10 airports** with varying topological complexity and crowdedness:

<style>
.mySlides {display:none;}
</style>

<div align="center">
  <img class="mySlides" src="/assets/posts/2024-06-14-amelia-framework/data_panc.png" style="width:90%">
  <img class="mySlides" src="/assets/posts/2024-06-14-amelia-framework/data_kbos.png" style="width:90%">
  <img class="mySlides" src="/assets/posts/2024-06-14-amelia-framework/data_kdca.png" style="width:90%">
  <img class="mySlides" src="/assets/posts/2024-06-14-amelia-framework/data_kewr.png" style="width:90%">
  <img class="mySlides" src="/assets/posts/2024-06-14-amelia-framework/data_kjfk.png" style="width:90%">
  <img class="mySlides" src="/assets/posts/2024-06-14-amelia-framework/data_klax.png" style="width:90%">
  <img class="mySlides" src="/assets/posts/2024-06-14-amelia-framework/data_kmdw.png" style="width:90%">
  <img class="mySlides" src="/assets/posts/2024-06-14-amelia-framework/data_kmsy.png" style="width:90%">
  <img class="mySlides" src="/assets/posts/2024-06-14-amelia-framework/data_ksea.png" style="width:90%">
  <img class="mySlides" src="/assets/posts/2024-06-14-amelia-framework/data_ksfo.png" style="width:90%">

  <div align="center">
    <button class="button-slide" onclick="plusDivs(-1)">&#10094;</button>
    <button class="button-slide" onclick="plusDivs(1)">&#10095;</button>
  </div>
</div>

<script>
var slideIndex = 1;
showDivs(slideIndex);

function plusDivs(n) {
  showDivs(slideIndex += n);
}

function showDivs(n) {
  var i;
  var x = document.getElementsByClassName("mySlides");
  if (n > x.length) {slideIndex = 1}
  if (n < 1) {slideIndex = x.length}
  for (i = 0; i < x.length; i++) {
    x[i].style.display = "none";  
  }
  x[slideIndex-1].style.display = "block";  
}
</script>

<hr>

<h3>Amelia-<span style="color:#e69138;">Scenes</span>
<span> <a class="button" itemprop="github" href="https://github.com/AmeliaCMU/AmeliaScenes" target="_blank">
  <i class="fab fa-github fa-lg"></i>
</a></span> 
</h3>

We use <b>Amelia-<span style="color:#e69138;">Scenes</span></b> to extract scenes from the raw CSV
files. Our scene extraction is easily configurable to obtain different types of scenes in terms of 
number of agents of interest, scene length, and point-to-point granularity. 

We also provide scene characterization tools to analyze scene complexity w.r.t individual agent 
kinematic profiles, as well as level of agent-to-agent interactivity and crowdedness. 

<table align="center">
  <tr>
  <tr>
    <td><b>Boston Logan International Airport (KBOS)</b></td>
    <td><b>John F. Kennedy International Airport (KJFK)</b></td>
  </tr>
    <td><img src="/assets/posts/2024-06-14-amelia-framework/kbos.gif" width=565 ></td>
    <td><img src="/assets/posts/2024-06-14-amelia-framework/kjfk.gif" width=700 ></td>
  </tr>
</table>

The resulting scenes can be used for several downstream tasks such as <b>trajectory forecasting</b>. 

<hr>

<h3>Amelia-<span style="color:#c27ba0;">Viz</span>
<span> <a class="button" itemprop="github" href="https://github.com/AmeliaCMU/AmeliaViz" target="_blank">
  <i class="fab fa-github fa-lg"></i>
</a></span> 
</h3>

<b>Amelia-<span style="color:#c27ba0;">Viz</span></b> provides scripts for creating visualizations 
for ground truth scenes and model predictions. 

<table align="center">
  <tr>
    <td><img src="/assets/posts/2024-06-14-amelia-framework/predictions-1.gif" width=650 ></td>
    <td><img src="/assets/posts/2024-06-14-amelia-framework/predictions-2.gif" width=650 ></td>
  </tr>
</table>

<hr>

<h3>Amelia-<span style="color:#8e7cc3;">TF</span>
<span> <a class="button" itemprop="github" href="https://github.com/AmeliaCMU/AmeliaTF" target="_blank">
  <i class="fab fa-github fa-lg"></i>
</a></span> 
</h3>

We provide, <b>Amelia-<span style="color:#8e7cc3;">TF</span></b>, a framework for training and 
evaluating trajectory forecasting models that uses Hydra + Pytorch Lightning. This framework enables 
easy integration and implementation of existing and new models.

For more details on our proposed model, check out [Amelia-TF](https://navars.xyz/amelia-model)!

<hr>

<h3>Amelia-<span style="color:#ea738d;">Inference</span>
<span> <a class="button" itemprop="github" href="https://github.com/AmeliaCMU/AmeliaInference" target="_blank">
  <i class="fab fa-github fa-lg"></i>
</a></span> 
</h3>

Finally, we also release an inference tool for visualizing model predictions. 

<hr>


# BibTeX

If you find our work useful in your research, please cite us!

```
@article{navarro2024amelia,
  title={Amelia: A Large Model and Dataset for Airport Surface
Movement Forecasting},
  author={Navarro, Ingrid and Ortega-Kral, Pablo and Patrikar, Jay, and Haichuan, Wang and Park, Jong Hoon and Oh, Jean and Scherer, Sebastian},
  journal={arXiv preprint arXiv:2309.08889},
  year={2024}
}
```