# Range-driver Acoustic Telemetry Analysis Tutorials

This repository contains tutorials & demonstration notebooks illustrating how the [range-driver](https://github.com/sfu-bigdata/range-driver) acoustic telemetry toolkit can help to answer what factors drive the underwater acoustic transmitter detection range in the context of a specific field study.

As entry points to working with this library, consider the [quick start guide](#quick-start), [range test field study use cases](#use-cases), or the following [workflow overview](#blocks).

* [Study setup and configuration](#configuration)
  * Manage and adjust [configuration options](#configuration) for data sources, processing, and analysis
  * Know [which files and field names](#field-names) are expected to contain specific information for the [data loader](#detection-loader) and other processing modules
* [Load detection events and metdata](#detection-loader) including information on transmitter/receiver deployment
* [Calculate detection rates](#detection-rates) for each observed transmitter/receiver combination
  * View and verify detection events and rates
  * Confirm proper data configuration
* Combine detections with [environmental data](#envos)
  * Determine a [region of interest in latitude, longitude, and time range](#roi)
  * Download data from [third-party data sources](#envos) via `kadlu`
  * Import [custom data sources](#custom-data), NetCDF files
  * Obtain [tidal data](#tidal-data)
* Invoke different views and [visualizations to study relationships](#analysis) among variables and their effect on variation in detection performance
* Perform further analyses and model building using the combined dataframe of detection and environmental data, consider event-based, and aggregation in time bins. Detailed examples are provided in our collection of [use cases](#use-cases).

## Design goals

Since field study data is usually located with researchers who plan and conduct field experiments, the goals of this tool are to:
* run on researchers' desktops where acoustic telemetry data is available, 
* collect further relevant data of environmental conditions from external data sources, and 
* provide data analysis and visualization methods that can be tailored for unique study settings.

## <a name="quick-start"></a>Quick start guide

TODO: entry-level examples of loading data from scratch with a small example

To get started, you can adopt a pre-configured setup by copying an example notebook and the YAML config and adjust input file paths and other parameters of the data gathering and analysis steps.  
Once detections and environmental data are combined in one dataframe, you can use it in your own scripts or notebooks for further analysis with Python or R.

## <a name="blocks"></a>Step-by-step tutorials for detection analysis

The tutorials here show relevant functions of the toolkit as they are used in practical workflows, consisting of a mix of manual and automated steps. We try to make workflows reproducible and reusable by capturing their setup with pieces of code and configuration text files. The result is an analysis report with generated figures, possibly including user interaction.

### <a name="configuration"></a> Manage configuration options

Configuration options are organized in YAML files - text files that contain `key: value` pairs of strings, numbers, and lists, where keys can be nested via indentation, to organize information hierarchically. The main-level keys of such a file are:
* `reader`
* `data`
* etc.

TODO: documentation of all config options: establish cenral .rst for config options

To separate the definitions of default values and study specific settings, configurations can be loaded in layers, where a later file can update settings from an earlier file. It is also possible to merge all information into a single config file, if that is preferred.

YAML configuration in layers: system defaults, view settings (merge with system?), study specific

Etablish folder and file structure for detection and environmental data sources

### <a name="field-names"></a>Field names used in the analysis

The main tables used in the analysis are:
* detection events,
* meta data, and
* environmental data.

To work with these tables, information has to be provided under specific column names and formats.

Field names (e.g. lat lon), configurability, and documentation

Detection data: detections + meta data, how to access you own detection file: a) use existing loaders, b) extend loaders
environmental data: kadlu (lightweight discussion, point to kadlu docs), netcdf files.
Low-level loading (load netcdf, do own interpolation), brief version (just use the config file)
what happens if my data is not netcdf or kadlu?

TODO: The bullets in the workflow above to add further detail component sections (partly done)

### <a name="detection-loader"></a> Detection data loaders

See [use cases](#use-cases) for examples on the OTN format and NSOG study.

### <a name="detection-rates"></a> Calculate detection rates

* View and verify detection events and rates
* Confirm proper data configuration

### <a name="roi"></a>Region of interest in latitude, longitude, and time range

### <a name="envos"></a>Fetch environmental variables

Combine detections with environmental data  
Download data from third-party data sources via `kadlu`

### <a name="custom-data"></a>Custom data sources, CSV, NetCDF, etc.

Import custom data sources, NetCDF files

### <a name="tidal"></a> 

Obtain tidal heights either via API access or by interpolation of tidal time tables

### <a name="analysis"></a>Data visualization and EDA

Invoke different views and visualizations to study relationships among variables and their effect on variation in detection performance

Perform further analyses and model building using the combined dataframe of detection and environmental data, consider event-based, as well as, aggregation within time windows, e.g. as used to compute detection rates

## <a name="use-cases"></a> Use Cases

Goals, Methods, Results

### Mahone Bay

**Range test study setup**  
deployment info in OTN metadata format  
coverage of the data:
* transmitter and receiver types and settings
* location, time range
* number of detections
TODO: These details would be provided in a notebook section.

**Environment variables**

**Results**  
bi-variate distribution plots of DR vs. water velocity

### Georgia Straight

tbd
