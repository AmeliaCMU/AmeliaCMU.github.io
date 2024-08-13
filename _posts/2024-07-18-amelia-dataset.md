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

**Amelia-48** is a large-scale airport surface movement dataset collected using the System Wide Information Management (SWIM) Surface Movement Event Service (SMES). With data collection beginning in December 2022, the ~30TB dataset currently provides a year's worth of data and covers 48 airports and TRACON facilities within the US National Airspace System.

<p style="color:red"> 
<b>NOTE:</b> Below we provide instructions on how to access the <b>pre-processed</b> trajectory data which was used for trajectory forecasting. This data corresponds to the 10 airports we used for our experiments in the paper.
</p>

<p style="color:red"> 
Additionally, we provide instructions on how to download the general <b>raw</b> dataset, which contains the full 48 airport data. 
</p>

Finally, we also provide a dataset tracker which summarizes the available assets for each airport.

<hr>

# Pre-processed Data

We provide the pre-processed trajectory data used for our trajectory forecasting experiments. 

Click the link below to download our dataset:

<a class="button" itemprop="paper" href="https://airlab-share-01.andrew.cmu.edu:9000/amelia-processed/amelia-10.zip" target="_blank"> <i class="fas fa-database fa-lg"></i></a>

The downloaded dataset follows this structure:
```bash
|-- amelia
    |-- assets
    |    | -- airport_icao
    |    |    | -- bkg_map.png
    |    |    | -- limits.json
    |    |    | -- airport_code_from_net.osm
    |    | ...
    |-- graph_data_a10v01os
    |    | -- airport_icao
    |    |    | -- semantic_graph.pkl
    |    |    | -- semantic_airport_icao.osm
    |    |    | -- semantic_graph.png
    |    | ...
    |-- graph_data_a48v01os
    |    | -- airport_icao
    |    |    | -- semantic_graph.pkl
    |    |    | -- semantic_airport_icao.osm
    |    |    | -- semantic_graph.png
    |    | ...
    |-- traj_data_a10v08
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

The `graph_data_a10v01os` folder has a subfolder for each airport containing semantic graphs representation obtained using [AmeliaMaps](https://github.com/AmeliaCMU/AmeliaMaps). Each sub-folder contains the following files:
* `semantic_graph.pkl`: contains the vectorized map graph with semantic attributes.
* `semantic_airport_icao.osm`: the semantic representation of the graph in OSM format
* `semantic_graph.png`: visual representation of the graph. Just shown for reference.

**NOTE** this folder contains the graphs for the 10 airports used in our training experiments. The full set of 48 maps is in the folder `graph_data_a48v01os`.

### Trajectory Data

The `traj_data_a10v08` folder has a subfolder for each airport containing the trajectory data in CSV format. Each file within an airport's subfolder represents an hour of data.

The files are named following the format ```AIRPORT_ICAO_<unix_timestamp>.csv```. Each contains trajectory information in the following format: 
<br>

<table align="center" style="width:70%">
  <caption><b>Table 1. </b> Processed Trajectory Data Fields</caption>
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


<hr>

# Raw Data

In order to download and process data for the other airports, please follow instructions below:

#### Downloading and processing raw trajectory data

* To **download** the raw data, please follow the instructions in [AmeliaSWIM](https://github.com/AmeliaCMU/AmeliaSWIM) on how to use the `download_raw.py` script.  

* To **process** the raw data, please follow the instructions in [AmeliaSWIM](https://github.com/AmeliaCMU/AmeliaSWIM) on how to use the `process.py` script. The resulting data will be saved as CSV files containing the information in **Table 1**.

#### Downloading and processing map data

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
