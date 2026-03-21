---
layout: default
title: Walkable Tube
---

# The Walkable Tube Project

This project aims to use QGIS network analysis to generate walkable, street-level routes than mimic the London Underground lines.



## Data Visualisation 

- All of the datasets have been projected into CRS: EPSG 27700, British National Grid for consistency.

![QGIS map showing London MSOAs](../assets2/Londonbasic.png)

- MSOAs for Greater London were used to provide geographic context.
- The River Thames has been manually traced using OS Open Rivers data as reference. 

![QGIS map showing London Underground Network](../assets2/tube_network.png)

- The tube lines have been colourised using the official TfL colour standard.
- The final map shows the computed walking route for the Northern line.

![QGIS map showing Northern Line walking route](../assets2/route.png)


## Methodology
### Building the Walkable Street Network
- Import relevant OSM extracts from Geofabrik.
- Merge highway vector layers and clip to a custom polygon approximating the Tube network extent. 
- Exclude non-walkable features (motorway and motorway_link). 

### Tube network and station layers
- Add station and network datasets (.gpkg, .geojson)
- Clean station data: refactor to remove unnecessary fields, trim text, standardise case. 
- Split multi-line station entries using ; delimiter to ensure each served line became its own feature.
- Filter records by line e.g. 'northern', save selected features into individual layers.
- Adjust station locations to reflect real entrance positions rather than centroids.

### Network Analysis
- Use QNEST3 plugin to compute shortest path (point to point) between consequtive stations. (uses Dijkstra's algorithm).
- Merge resultant segments into single layer to form a continuous walking route.

### Cartographic Output
- Create a print layout and export as .png
  

## Data Sources
- ONS (MSOAs)
- OS Open Rivers (River Thames)
- QuickOSM plugin query (Tube station data)
- Overpass turbo request (Tube network)
- Geofabrik OSM data extracts: Greater London, Hertfordshire, Buckinghamshire, Essex (street network)



## Skills Demonstrated
- Cleaning spatial data inside QGIS: refactoring, field calculation, filtering attributes
- Handling of GeoJSON, shapefile, Geopackage formats
- Spatial data acquisition of UK datasets: OS, ONS
- Network analysis using QNEAT3 plugin, shortest path algorithm
- Attribution creation and calculation
- Print layout production
