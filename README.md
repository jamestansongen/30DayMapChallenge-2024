# 30DayMapChallenge 2024

This is my contribution to the #30DayMapChallenge for November 2024.\
About the #30DayMapChallenge , check out <https://30daymapchallenge.com/> !

## Introduction

### About me

I am MSc Graduate in Urban Spatial Science from the Centre for Advanced Spatial Analysis (CASA), UCL. My specialisation is in Geographic Information Systems, Remote Sensing, Data Science and Agent-Based Modelling. \
My other interests include hiking, drone piloting/photography and board games. \
For opportunities or collaboration, I can be contacted via [LinkedIn](https://www.linkedin.com/in/james-tan-song-en-76b73418a/)

### Day 2: Lines

What if the contiguous United States had a train network connecting all its National Parks? I experimented with network connectivity by linking parks based on nearest neighbour if no existing connection existed. This approach created a few isolated triangles, so I applied a minimum spanning tree algorithm to create a skeleton network. To further enhance connectivity and build in redundancy (to ensure disruptions at key nodes do not sever the entire network), I added two cross-country lines and transformed one segment into a loop. The design draws inspiration from the Tube map style, with line names inspired by quintessentially American themes.

![What if the US National Parks had a tube network?](Day%202/National%20Parks_Resized%20Map.png)

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
