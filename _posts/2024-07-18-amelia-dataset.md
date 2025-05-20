---
layout: post
author: Ingrid Navarro and Pablo Ortega-Kral
permalink: /amelia-dataset/
title: Amelia-42
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
Amelia-42: An airport surface movement dataset
</h1>

<br>

<a class="button" itemprop="paper" href="https://huggingface.co/datasets/AmeliaCMU/Amelia42-Mini" target="_blank">
  <img src="/assets/img/logos/huggingface-color.png" alt="Hugging Face" style="height:1.5em; vertical-align:middle; margin-right:0.5em;">
  Amelia42-Mini
</a>
<a class="button" itemprop="paper" href="https://huggingface.co/datasets/AmeliaCMU/Amelia-10" target="_blank">
  <img src="/assets/img/logos/huggingface-color.png" alt="Hugging Face" style="height:1.5em; vertical-align:middle; margin-right:0.5em;">
  Amelia10-Bench
</a>

<hr>

**Amelia-42** is a large-scale airport surface movement dataset collected using the System Wide Information Management (SWIM) Surface Movement Event Service (SMES). With data collection beginning in December 2022, the dataset is continuously expanding. It covers surface movement events across 42 airports and TRACON facilities within the US National Airspace System.

<b>NOTE:</b> We provide instructions on how to access the <b>processed</b> trajectory data. Additionally, Below we provide instructions on how to download and convert the <b>raw</b> dataset, which contains everything captured by the SWIM system for 42 airports in the United States.


<div align="center">
  <img src="/assets/img/dataset.png" alt="The Amelia pipeline" width="70%">
  <h6>The Amelia data pipeline. </h6>
</div>
  <div align="left">
  <b>A)</b> Raw position reports from the FAA’s SWIM Terminal Data Distribution System are continuously logged and released as Amelia-42, from December 2nd, 2022, to the present.<br>
  <b>B)</b> Airport-specific geofences are defined to delimit movement areas as well as take-off and landing extensions to runways.<br>
  <b>C)</b> Data within the geo-fence is processed into clean tabular 1-Hz position reports.<br>
  <b>D)</b> As additional context, semantic routing graphs are created for each airport.<br>
  </div>

<hr>

# Processed Data

<div align="center" style="margin: 2em 0;">
  <img src="/assets/img/logos/huggingface-color.png" alt="Hugging Face" style="height:2.5em; vertical-align:middle; margin-right:0.5em;">
  <span style="font-size:1.5em; font-weight:bold; color:#ffb300;">
    We are on <a href="https://huggingface.co/AmeliaCMU" target="_blank" style="color:#ffb300; text-decoration:underline;">HuggingFace</a> now!
  </span>
</div>

## Amelia10-Bench


Click on the link below to go to the processed dataset:

<a class="button" itemprop="paper" href="https://huggingface.co/datasets/AmeliaCMU/Amelia-10" target="_blank">
  <img src="/assets/img/logos/huggingface-color.png" alt="Hugging Face" style="height:1.5em; vertical-align:middle; margin-right:0.5em;">
  Amelia10-Bench
</a>

We provide the processed trajectory data used for our trajectory forecasting experiments, which contains **1 month of data for each of the 10 airports**:

NOTE: The full dataset is significantly larger as described in the raw data section. The following 10 airports are selected to represent a diverse range of traffic levels and map topologies.

- Boston-Logan Intl. Airport - Jan 2023
- Newark Liberty Intl. Airport - Mar 2023
- Ronald Reagan Washington Natl. Airport - April 2023
- John F. Kennedy Intl. Airport - April 2023
- Los Angeles Intl. Airport - May 2023
- Chicago-Midway Intl. Airport - June 2023
- Louis Armstrong New Orleans Intl. Airport - July 2023
- Seattle-Tacoma Intl. Airport - Aug 2023
- San Francisco Intl. Airport - Sept 2023
- Ted Stevens Anchorage Intl. Airport - Nov 2023



## Amelia42-Mini

We provide the processed trajectory data for **15 days chosen randomly** for each of the **42 airports**:

NOTE: The full dataset is significantly larger as described in the raw data section.

Click on the link below to go to the processed dataset:

<a class="button" itemprop="paper" href="https://huggingface.co/datasets/AmeliaCMU/Amelia42-Mini" target="_blank">
  <img src="/assets/img/logos/huggingface-color.png" alt="Hugging Face" style="height:1.5em; vertical-align:middle; margin-right:0.5em;">
  Amelia42-Mini
</a>

<hr>


## Dataset Structure

The dataset follows this structure:

```bash
|-- amelia
    |-- assets
    |    | -- airport_icao
    |    |    | -- bkg_map.png
    |    |    | -- limits.json
    |    |    | -- airport_code_from_net.osm
    |    | ...
    |-- graph_data_axxvxxos
    |    | -- airport_icao
    |    |    | -- semantic_graph.pkl
    |    |    | -- semantic_airport_icao.osm
    |    |    | -- semantic_graph.png
    |    | ...
    |-- traj_data_axxvxx
    |    | -- airport_icao
    |    |    | -- AIRPORT_ICAO_<unix_timestamp>.csv
    |    |    | ...
    |    |    | ...
    |    | ...
```

### Assets

The `assets` folder has a subfolder for each airport (uses the airport's [ICAO](https://en.wikipedia.org/wiki/ICAO_airport_code)) containing the following:
* `bkg_map.png`: visual representation of the map, obtained using OpenStreetMap (OSM).
* `limits.json`: JSON file containing the Airport's extents.
* `airport_icao.osm`: the airport's map in OSM format.

### Graph Data (Processed Map Information)

To generate the processed map information, we used [AmeliaMaps](https://github.com/AmeliaCMU/AmeliaMaps).

The `graph_data_axxvxxos` folder has a subfolder for each airport containing semantic graphs representation obtained using [AmeliaMaps](https://github.com/AmeliaCMU/AmeliaMaps). Each sub-folder contains the following files:
* `semantic_graph.pkl`: contains the vectorized map graph with semantic attributes.
* `semantic_airport_icao.osm`: the semantic representation of the graph in OSM format
* `semantic_graph.png`: visual representation of the graph. Just shown for reference.

**NOTE** this folder contains the graphs for the 10 airports used in our training experiments. The full set of 42 maps is in the folder `graph_data_axxvxxos`.

### Trajectory Data

The `traj_data_axxvxx` folder has a subfolder for each airport containing the trajectory data in CSV format. Each file within an airport's subfolder represents an hour of data.

The files are named following the format ```AIRPORT_ICAO_<unix_timestamp>.csv```. Each contains trajectory information in **Table 1**.
<br>

<table align="center" style="width:70%">
  <caption><b>Table 1. </b>Trajectory Data Fields</caption>
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

## Downloading the Dataset from Hugging Face

You can easily download the Amelia datasets using the [Hugging Face Hub](https://huggingface.co/docs/hub/how-to-download-files) and the `datasets` library.

First, install the required package:

```bash
pip install datasets
```

Then, load the dataset in Python:

```python
from datasets import load_dataset

# For Amelia42-Mini
ds = load_dataset("AmeliaCMU/Amelia42-Mini")

# For Amelia10-Bench
ds = load_dataset("AmeliaCMU/Amelia-10")
```

Alternatively, you can download files directly from the Hugging Face website.

Click the "Download" button or use the "Files and versions" tab to access specific files.

<hr>

# Raw Data

The raw data contains everything captured by the SWIM system for 42 airports in the United States. A complete list of the airports is provided in **Table 2**.

In order to download and convert raw data into CSV files, please follow instructions below:

#### Downloading and Converting raw data

* To **download** the raw data, please follow the instructions in [AmeliaSWIM](https://github.com/AmeliaCMU/AmeliaSWIM) on how to use the `download_raw.py` script.

* To **convert** the raw data into CSV files, please follow the instructions in [AmeliaSWIM](https://github.com/AmeliaCMU/AmeliaSWIM) on how to use the `process.py` script. The resulting CSV files will contain the following information:



#### Downloading and Processing map data

* To **download** and **process** the map data, please follow the instructions in [AmeliaMaps](https://github.com/AmeliaCMU/AmeliaMaps) on how to use the processing scripts.

<hr>

# Data Tracker

{% include data_tracker.html %}

<hr>

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
