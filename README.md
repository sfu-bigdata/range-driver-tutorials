# Range Driver - Acoustic Telemetry Analysis

This repository contains tutorials & demonstration notebooks illustrating how the [range-driver](https://github.com/sfu-bigdata/range-driver) acoustic telemetry toolkit can assist in analyzing what factors drive an underwater acoustic transmitter's detection range.

## Range test analysis workflow

The analysis methods provided in this toolkit are structured along different stages of data preparation and hypothesis generation. The basic steps are:

* Study setup
  * Etablish folder and file structure for detection and environmental data sources
  * Manage and adjust configuration options for data sources, processing, and analysis
* Load detection events and metdata about transmitter/receiver deployment
* Calculate detection rates for each observed transmitter/receiver combination
  * View and verify detection events and rates
  * Confirm proper study setup
* Combine detections with environmental data
  * Determine a region of interest in latitude, longitude, and applicable time range
  * Download data from third-party data sources via `kadlu`
  * Import custom data sources from NetCDF files
  * Obtain tidal data
* Invoke different views and visualizations to study relationships among variables and their effect on variation in detection performance
* Work with the combined dataframe of detection and environmental data to perform custom analyses and model building

As a starting point, adopt a pre-configured setup and then fine-tune parameters of different stages of the overall data gathering and analysis pipeline.
Beyond that, it is possible to add custom processing steps and visualizations. Once detections and environmental data are combined in one dataframe, pursue further ad-hoc analysis, for instance, using Jupyter notebooks.

## Quick Start Guide

## Building blocks

### Configuration

YAML configuration in layers: system defaults, view settings (merge with system?), study specific

TODO: documentation of all config options: establish cenral .rst for config options

### Field names used in the analysis

Field names (e.g. lat lon), configurability, and documentation

Detection data: detections + meta data, how to access you own detection file: a) use existing loaders, b) extend loaders
environmental data: kadlu (lightweight discussion, point to kadlu docs), netcdf files.
Low-level loading (load netcdf, do own interpolation), brief version (just use the config file)
what happens if my data is not netcdf or kadlu?

### Further stages

TODO: The bullets in the workflow above to add further detail component sections

## Use Cases

Goals, Methods, Results

### Mahone Bay

detection setup,
envos,
bi-variate distribution plots of DR vs. water velocity

### Georgia Straight

tbd
