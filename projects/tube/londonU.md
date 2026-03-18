# What why whys it interesting 

# Visualisation Data 
- tfl colour standards
- 

# Methodology
- Walkable street network: import relevant counties from geofabrik.
- merge vectors. create (shapefile) polygon roughly outlining tube network.
- clip to mask (polygon)
- exclude motorway and motorway_link. 

- add layers tube network and stations.
- clean station data. filter by station=subway.
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


# Additional notes. 
- enable snapping.
- CRS British National Grid
