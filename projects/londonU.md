# What why whys it interesting 
- my intention was to use network analysis to devise walking routes on street level mimicking the underground tube lines.
- in the interests of limiting scope somewhat i decided to focus on the northern line as i am most familiar with it. 


# Visualisation Data 

![QGIS map showing Northern Line walking route](../assets2/route.png)

- tfl colour standards
- CRS: British National Grid 

# Methodology
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

# Data Sources
- QuickOSM Plugin query stations 
- Overpass turbo request network tube lines
- geofabrik OSM data extracts: Greater London, Hertfordshire, Buckinghamshire, Essex
- digitise trace Thames from sat layer
- data sources and acquisition. e.g. removing g london filter etc. 



# Skills 
- cleaning data inside QGIS
- GeoJSON, shapefile, Geopackage
- MSOAs UK datasets ONS

# Real life application 
- Hike!
- field calculator, filtering attribute tables.
- read in CSV file. compare to data. delimiting. 


# Additional notes. 
- enable snapping.

