---
layout: post
author: Ingrid Navarro and Pablo Ortega-Kral
permalink: /amelia-dataset/
title: Amelia-48
subtitle: A Large-Scale Dataset for Airport Surface Movement
image: /assets/posts/2024-06-14-amelia-framework/klax.gif
link-new-tab: true
categories: publication
hero_image: /assets/posts/2024-06-14-amelia-framework/klax_header.gif
hide_hero: true
hide_footer: false
hero_height: is-medium
---

<h1>
Amelia-48: An airport surface movement dataset
</h1>

<hr>

**Amelia-48** is a large-scale airport surface movement dataset collected using the System Wide
Information Management (SWIM) Surface Movement Event Service (SMES). With data collection beginning
in December 2022, the ~30TB dataset currently provides a year's worth of data and covers 48 airports and TRACON facilities within the US National Airspace System.

Below we provide instructions on how to get access to our dataset and provide a dataset tracker summarizing the available data for each airport.

The dataset consists of both RAW and processed data. In addition, we provide scripts to process data for any of the 48 airports for any time duration after 1 Dec 2022.

# Processed Data  
<a class="button" itemprop="paper" href="https://airlab-share-01.andrew.cmu.edu:9000/amelia-processed/amelia-10.zip" target="_blank">
  <i class="fas fa-file fa-lg"></i>
</a>

The processed data for 10 aiports can be downloaded using the [link](https://airlab-share-01.andrew.cmu.edu:9000/amelia-processed/amelia-10.zip).

The processed data contains **1 month of data for each of the 10 airports**. The airports are as follows:

- Boston-Logan Intl. Airport	- Jan 2023
- Newark Liberty Intl. Airport	- Mar 2023
- Ronald Reagan Washington Natl. Airport - April 2023
- John F. Kennedy Intl. Airport	- April 2023	
- Los Angeles Intl. Airport - May 2023	
- Chicago-Midway Intl. Airport - June 2023	
- Louis Armstrong New Orleans Intl. Airport - July 2023	
- Seattle-Tacoma Intl. Airport - Aug 2023
- San Francisco Intl. Airport - Sept 2023
- Ted Stevens Anchorage Intl. Airport	-	Nov 2023


The processed data follows the format

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

# Downloading and Processing Raw Dataset

In order to download and process data for the other airports, please follow instructions in the dataset [repository](https://github.com/AmeliaCMU/AmeliaSWIM).

<span> <a class="button" itemprop="github" href="https://github.com/AmeliaCMU/AmeliaSWIM" target="_blank">
  <i class="fab fa-github fa-lg"></i>
</a></span>

# Data Tracker

{% include data_tracker.html %}


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
