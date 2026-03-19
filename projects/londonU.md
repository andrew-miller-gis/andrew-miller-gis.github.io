# The Walkable Tube Project

- my intention was to use network analysis to devise walking routes on street level mimicking the underground tube lines.
- i've decided to first focus on the northern line as i am most familiar with it. 


## Data Visualisation 

- All of the data has been visualised in CRS: EPSG 27700, British National Grid 

![QGIS map showing London MSOAs](../assets2/Londonbasic.png)

![QGIS map showing London Underground Network](../assets2/tube_network.png)

- The tube lines have been colourised using the TfL colour standard, available: https://content.tfl.gov.uk/tfl-colour-standard.pdf

![QGIS map showing Northern Line walking route](../assets2/route.png)

- tfl colour standards
- CRS: British National Grid 

## Methodology
- Walkable street network: import relevant counties from geofabrik.
- merge vectors. create (shapefile) polygon roughly outlining tube network.
- clip to mask (polygon)
- exclude motorway and motorway_link. 

- add layers tube network and stations.
- clean station data. filter by station=subway. Refactoring data. Lower trim 
- split features by character: duplicate for multiple lines served.
- separate by line. e.g. northern.
- vertex editiing comparing with map data, station entrances rather than centroids.
- 


- Networking: QNEST3 plugin. Shortest path (point to point).
- between each station northern line.
- Merge these lines segments into single layer.
- Dijkstra?

- exporting and publish. 

## Data Sources
- QuickOSM Plugin query stations 
- Overpass turbo request network tube lines
- geofabrik OSM data extracts: Greater London, Hertfordshire, Buckinghamshire, Essex
- digitise trace Thames from sat layer
- data sources and acquisition. e.g. removing g london filter etc. 



## Skills 
- cleaning data inside QGIS
- GeoJSON, shapefile, Geopackage
- MSOAs UK datasets ONS

## Real world application 
- Hike!
- field calculator, filtering attribute tables.
- read in CSV file. compare to data. delimiting. 


- enable snapping.

