# 30DayMapChallenge 2024

This is my contribution to the #30DayMapChallenge for November 2024.\
About the #30DayMapChallenge , check out <https://30daymapchallenge.com/> !

## Introduction

### About me

I am an MSc Graduate in Urban Spatial Science from the Centre for Advanced Spatial Analysis (CASA), UCL. My specialisation is in Geographic Information Systems, Remote Sensing, Data Science and Agent-Based Modelling. \
My other interests include hiking, drone piloting/photography and board games. \
For opportunities or collaboration, I can be contacted via [LinkedIn](https://www.linkedin.com/in/james-tan-song-en-76b73418a/)

### Day 4: Hexagons

Earlier this year, my team participated in a hackathon and we spent quite a fair bit of time trying to figure out H3 for a data visualisation segment. This [H3 tutorial](https://uber.github.io/h3-py/polygon_tutorial.html#) was quite useful in covering the fundamentals. This time I applied the python code to map the occurences of 16 threatened and migratory marine species in the North Marine Bioregion of Australia. As the data ranges from a long timespan of 1905 to 2020, I chose to simply show where the occurrences are as the total count or count/year could be potentially misleading.

![Threatened Species Northern Australia](Day%204/Day%204.gif)

Data Source: [NESP A12: Northern Australia threatened species, Australia (1905-2020)](https://www.gbif.org/dataset/774c4fd0-fb00-41d2-8bdc-65fc1c809d21)

### Day 3: Polygons

Using the SRTM plugin in QGIS, I obtained the elevation data for the Isle of Skye before generating the contour polygons and adjusting the symbol levels. Isle of Skye has a lot of fascinating natural formations including the Old Man of Storr although I was met with heavy showers during my visit in April this year.

![Isle of Skye](Day%203/Designs/IsleofSkye50_100m_Edited.png)

### Day 2: Lines

What if the contiguous United States had a train network connecting all its National Parks? I experimented with network connectivity by linking parks based on nearest neighbour if there was no existing connection. This approach created a few isolated triangles, so I applied a minimum spanning tree algorithm to create a skeleton network. To further enhance connectivity and build in redundancy (to ensure disruptions at key nodes do not sever the entire network), I added two cross-country lines and transformed one segment into a loop. As much as possible, I tried to preserve the distance and direction of parks from one another in this topographical map. The design in Adobe Illustrator draws inspiration from the Tube map style, with line names inspired by quintessentially American themes.

![What if the US National Parks had a tube network?](Day%202/National%20Parks%20Map_Resized.png)

Data Source: [National Park Coordinates](https://osm4wiki.toolforge.org/cgi-bin/wiki/wiki-osm.pl?project=en&article=List_of_national_parks_of_the_United_States)

### Day 1: Points

For Day 1 with the theme of points, I decided to plot the distribution of Cherry Blossoms in Vancouver for 2021. The addresses for the trees were geocoded using the British Columbia (BC) Address Geocoder followed by adopting a pink firefly style to represent each tree.

![Sakura Blossoms in Vancouver 2021](Day%201/Designs/Day%201.png)

Data Source: [Sakura Distribution](https://maps.vcbf.ca/map/?utm_source=vancouver%20is%20awesome&utm_campaign=vancouver%20is%20awesome%3A%20outbound&utm_medium=referral
), [Parks](https://opendata.vancouver.ca/explore/dataset/parks-polygon-representation/map/?location=12,49.24528,-123.12721
), [Water Bodies](https://open.canada.ca/data/en/dataset/448ec403-6635-456b-8ced-d3ac24143add
), [Boundaries](https://opendata.vancouver.ca/explore/dataset/local-area-boundary/export/?disjunctive.name&location=12,49.2474,-123.12402) \
Geocoder: [BC Address Geocoder](https://www2.gov.bc.ca/gov/content/data/geographic-data-services/location-services/geocoder
)
