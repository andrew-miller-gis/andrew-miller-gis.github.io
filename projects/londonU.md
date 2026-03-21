---
layout: default
title: Walkable Tube
---

# The Walkable Tube Project

![QGIS map showing Northern Line walking route](../assets2/route.png)

I have always been excited by the London Underground, particularly the experience of going below ground, following the schematic map and emerging the other side of London with no tangible experience of the route. The desire to understand how this travel happens geographically has inspired this project. Using QGIS network analysis I have attempted to generate walkable, street-level routes than mimic the London Underground lines, starting with the Northern line. 



## Data Visualisation 

![QGIS map showing London MSOAs](../assets2/Londonbasic.png)

- All of the datasets have been projected into CRS: EPSG 27700, British National Grid for consistency.
- MSOAs for Greater London were used to provide geographic context.
- The River Thames has been manually traced using OS Open Rivers data as reference. 
- The tube lines have been colourised using the official TfL colour standard.
- The final map shows the computed walking route for the Northern line.


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

![QGIS map showing London Underground Network](../assets2/tube_network.png)

### Network Analysis
- Use QNEAT3 plugin to compute shortest path (point to point) between consecutive stations. (uses Dijkstra's algorithm).
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

## Reflection 
- This project taught me a lot about attribute tables. Particularly filtering, homogenising how data is presented.
- Also, Network analysis principles and how to query OSM for the correct data eg location parameters, tags.
  

- I would like to test the Northern line route. 38.660 km is approximately 24 miles. I estimate this will be walkable over about 8 hours.
- I'd like to export the data as directions, and to collect data using Strava to later analyse whether the time taken and distance estimates are accurate for each line segment.
- Ultimately I would like to extend the process to the remaining Tube lines, potentially automating the time-consuming process of entering parameters for 'shortest path' for each individual station.
- I'd then like to utilise the data to complete the goal of walking the entire network. 



