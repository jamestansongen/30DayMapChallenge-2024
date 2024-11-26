# 30DayMapChallenge 2024

This is my contribution to the #30DayMapChallenge for November 2024.\
About the #30DayMapChallenge , check out <https://30daymapchallenge.com/> !

## Introduction

### About me

I am an MSc Graduate in Urban Spatial Science from the Centre for Advanced Spatial Analysis (CASA), UCL. My specialisation is in Geographic Information Systems, Remote Sensing, Data Science and Agent-Based Modelling. \
My other interests include hiking, drone piloting/photography and board games. \
For opportunities or collaboration, I can be contacted via [LinkedIn](https://www.linkedin.com/in/james-tan-song-en-76b73418a/)

### Day 26: Map projections

I explored various projections using the Cartopy library to visualize the Köppen-Geiger climate classification projection for 2076 to 2100, based on the IPCC A1FI Tyndall SC 2.03 temperature and precipitation scenarios. I ultimately chose to visualize the data using three distinct projections: Gnomonic, Goode Homolosine, and Azimuthal Equidistant, each with its own use cases and distortions.

![Projections](Day%2026/Koppen_Geiger_Projections_projected_2076-2100.png)

Data Source: [World Bank](https://datacatalog.worldbank.org/search/dataset/0042325)

### Day 25: Heat

Revisited one of my remote sensing practicals in Google Earth Engine. This map visualises the Average Land Surface Temperature (LST) in Africa for 2023, derived from the MODIS Aqua and Terra satellites. MODIS is an excellent dataset for studying temperature patterns due to its high temporal resolution, providing nearly daily global coverage. The map highlights the temperature variability across Africa, with higher temperatures prevailing in the Sahara Desert in the north and cooler conditions observed in the central regions, influenced by dense vegetation, and parts of the south, where temperatures are moderated by the ocean.

![Heat Africa](Day%2025/Day%2025.png)

Tutorial Source: [CASA0023 Remotely Sensing Cities and Environments: Temperature](https://andrewmaclachlan.github.io/CASA0023/8_temperature.html)

Data Source: [MODIS Aqua](https://developers.google.com/earth-engine/datasets/catalog/MODIS_061_MYD11A1) ; [MODIS Terra](https://developers.google.com/earth-engine/datasets/catalog/MODIS_061_MOD11A1)

### Day 24: Only circular shapes

The theme of "circular shapes" sparked some flashbacks of last year's theme of "is it a map or is it a chart?" which had quite a few maps featuring pie charts and proportionate circles, blending data visualisation with geography. This year, I tried to recreate that style to explore renewable energy generation in South America. Brazil stands out as the largest renewable energy producer on the continent. Meanwhile, hydropower dominates the region's energy mix. This is largely due to South America's abundance of rivers like the Amazon, Paraná, and Orinoco, along with its mountainous landscapes, which provide the ideal conditions for hydropower production.

![Renewables South America](Day%2024/Day%2024.png)

Data Source: [Total Renewable Energy](https://ourworldindata.org/grapher/electricity-renewables) ; [Solar](https://ourworldindata.org/grapher/solar-energy-consumption) ; [Wind](https://ourworldindata.org/grapher/wind-generation) ; [Hydropower](https://ourworldindata.org/grapher/hydropower-consumption) ; [Boundaries](https://datacatalog.worldbank.org/search/dataset/0038272/World-Bank-Official-Boundaries)

### Day 23: Memory

At the start of my MSc, we were tasked with drawing a mental map of London. My initial map was quite simple, centering on Tufnell Park (where I lived), Euston Station (most accessible station to campus for me), the Pret there (thanks to a very worthwhile coffee subscription), Drayton House (the site of my Urban Systems Theory class), the UCL Quad, and the nearby Waterstones bookstore.

After spending a year in London, I decided to create a new mental map, this time starting with a basemap and populating it with icons representing key memories. As London is quite walkable, I often found myself walking back from Central London (after a meal/musical), or from campus towards Tufnell Park. This habit allowed me to recall and pinpoint locations with surprising accuracy. If I had more space, I would expand it to include spots south of the Thames, UCL East and Richmond Park.

![Memories of London](Day%2023/Day%2023_edited.png)

### Day 22: Two Colours

I originally planned to use red and blue to represent Iceland as the 'Land of Fire and Ice'. However, I forgot the white background would be considered a third colour and hence changed the colour scheme to be black and white. The resulting map has a retro aesthetic, with dashed lines representing boundaries, triangles marking volcanoes, and polygons styled with filled patterns to depict glaciers.

![Iceland](Day%2022/Day%2022_edited.png)

Data Source: [Volcanoes](https://osm4wiki.toolforge.org/cgi-bin/wiki/wiki-osm.pl?project=en&article=List_of_volcanoes_in_Iceland) ; [Glaciers](https://developers.google.com/earth-engine/datasets/catalog/GLIMS_20230607)

### Day 21: Conflict

This map focuses on the ongoing clashes along the Israel-Lebanon border, using data from The Washington Institute for Near East Policy, which tracks daily attacks since the conflict began. Inspired by the design of Minesweeper, the map divides the region into 5km by 5km grid cells, with each cell labeled to show the total number of attacks recorded. To highlight the dynamics of the conflict, a bivariate color scheme was applied, differentiating between Israeli and Hezbollah attacks. The resulting map visualises the intensity of the clashes and unrest in the region.

While making this map, I was reminded of the somber reality that, unfortunately, there will always be another conflict to map.

![Conflict](Day%2021/Day%2021_edited.png)

Data Source: [The Washington Institute for Near Policy East](https://www.washingtoninstitute.org/policy-analysis/mapping-clashes-along-israel-lebanon-border)

### Day 20: OpenStreetMap

Today was a bit of a 'cartography-block' as I encountered missing building height and age data in various region of interest I was experimenting with. In the end, I decided to keep it simple by focusing on plotting restaurants in George Town, Penang using the Firefly style. Buildings, road edges and the underlying area were the other layers extracted in Python using the OSMnx package.

Side Note: Happy GIS Day!

![OSM](Day%2020/Day%2020.png)

Data Source: [OpenStreetMap](https://www.openstreetmap.org/#map=12/1.3649/103.8229)

### Day 19: Typography

Decided to represent U.S. states using a collection of song titles that reference the states or their cities, arranged in a a manner to outline each state's boundaries. While the task proved more time-consuming than expected due to the effort required to find appropriate songs, I might incorporate symbols of iconic landmarks in the future to enhance the visual aspect.

![Typography](Day%2019/Day%2019.png)

### Day 18: 3D

For this year’s challenge, I recycled the base workflow from last year’s 3D map, but with a twist. Besides shifting the region of interest to Hong Kong, I applied a neon theme to both the map and added labels, enhancing the overall visual appeal. Furthermore, by narrowing the focus to a smaller region (instead of an American state), the areas with higher population density become more distinct and appear to resemble high-rise buildings.

![3DHK](Day%2018/Day%2018.png)

Tutorial Source: [Rayshader Tutorial—Florida Population Density](https://www.youtube.com/watch?v=zgFXVhmKNbU)

Data Source: [Kontur Population: Global Population Density for 400m H3 Hexagons](https://data.humdata.org/dataset/kontur-population-china-hong-kong-special-administrative-region)

### Day 17: Collaboration

I had the privilege of collaborating with two talented coursemates from the Centre for Advanced Spatial Analysis, [Soki Kimura](https://www.linkedin.com/in/soki-kimura/) and [Juan Esteban Lamilla Cuellar](https://www.linkedin.com/in/juanlamilla/). The approach was to create three maps each of the same area in London, working independently without full knowledge of what the others were designing. Once completed, the maps were divided into nine grid cells, which were rearranged and experimented with to create the final masterpiece. Can you guess who created which segments of the map?

Fun fact: While creating this map, the three of us were collaborating from three different continents!

![LondonCollaboration](Day%2017/Day%2017_final.png)


### Day 16: Choropleth

To create this map, I combined two techniques: hexagons (resolution = 8) and a bivariate map. Given Singaporeans' obsession with food, my goal was to visualise food accessibility based on the distribution of supermarkets and eating establishments. Plotting eating establishments alone would show the extensive availability of food options across the country. However, when combined with supermarket locations, two key patterns emerge. Firstly, the darker hexagons correspond with areas with higher population densities or town centers. Secondly, the absence of hexagons in certain regions suggests that the predominant land use may be industrial or natural, rather than residential. Overall, what began as a map of food accessibility highlights the interconnectedness of food access, demographics, and land use.

![SingaporeFood](Day%2016/Day%2016_edited.png)

Tutorial Source: [Bivariate choropleth maps in QGIS](https://bnhr.xyz/2019/09/15/bivariate-choropleths-in-qgis.html)

Data Source: [Supermarket](https://data.gov.sg/datasets?formats=GEOJSON|KML|SHP|KMZ&sort=relevancy&page=3&resultId=d_cac2c32f01960a3ad7202a99c27268a0) ; [Eating Establishments](https://data.gov.sg/datasets?formats=GEOJSON|KML|SHP|KMZ&sort=relevancy&page=4&resultId=d_795cd2ffc806f38da83b144a0ec2d64b)

### Day 15: My data

The inspiration behind this map comes from the song "Carolina in My Mind" by James Taylor (1968). I lived in Chapel Hill, North Carolina, from 2016 to 2017 as part of a Joint-Degree Programme, and those ~9 months are filled with cherished memories. Besides OSM data, I added old photos from my time in Chapel Hill and applied a polaroid-style border (photos count as data too!).

![UNC](Day%2015/Day%2015.png)


### Day 14: A World Map

I experimented with recreating the Lego symbology style in QGIS, which is currently available in ArcGIS but not directly in QGIS. I started with an image of the world map with national flags overlaid on each country. I experimented with various grid sizes and centroids followed by zonal statistics to calculate the predominant red, green, and blue pixel values from the base image for each grid cell to approximate each country’s color. The result successfully resembles the intended style for large, contiguous areas. However, narrow landmasses like New Zealand and parts of Southeast Asia are less visible. Overall, utilising this style requires careful balancing of grid size: if the grid cells are too large, smaller features may disappear, but if they’re too small, the Lego symbology becomes unclear and the shadow effect becomes too overpowering.

![Lego World_50](Day%2014/Day%2014_40.png)

Base Image Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Flag-map_of_the_world_%282018%29.png)

### Day 13: A New Tool

I initially started the day learning more about PostGIS before pivoting to Blender, as I could not decide on the type of map to make. I had previously only used Blender during my dissertation to generate 3D buildings using the [Blosm](https://github.com/vvoovv/blosm) plugin to export as .fbx file. This time I used the [BlenderGIS](https://github.com/domlysz/BlenderGIS) tool to generate a 3D terrain model of Madeira. I experimented with adjusting the colours and angles before rendering the image and adding labels in Illustrator. I first visited Madeira in 2022, and the landscape there is simply breathtaking. My top 3 recommendations are Vereda da Ponta de São Lourenço, Pico do Arieiro and Pico Ruivo (especially as a hiking enthusiast), though the island has many other attractions.

P.S. The locations of some key landmarks may vary across maps, as they cover large areas, and it can be challenging to identify exact mountain peaks for placing markers accurately.

![Madeira](Day%2013/Day%2013_edited.png)

Tutorial Source: [Blender as a gis visualization tool](https://charliearuaikosi.substack.com/p/blender-as-a-gis-visualization-tool)

### Day 12: Time and Space

To further refine my Google Earth Engine skills, I created an app to explore changes in land cover across the Galapagos Islands over time (accessible [here](https://jamestansongen94.users.earthengine.app/view/galapagos-30daymapchallenge-2024-day-12)). The map allows users to visually compare land cover between 2001 and 2023. While MODIS's 500m spatial resolution is relatively coarse compared to other satellite datasets, its extensive temporal coverage makes it valuable for long-term analysis. In comparing 2001 and 2022, some noticeable trends emerge such as deforestation, the loss of wetlands, and increased land homogeneity. The Galapagos Islands, renowned for their unique ecosystems and biodiversity, played a pivotal role in Charles Darwin's theory of evolution. Their ecological diversity continues to be critical for research on environmental change and geological processes. 

![GalapagosLC](Day%2012/Day%2012.gif)

Data Source: [MCD12Q1.061 MODIS Land Cover Type Yearly Global 500m](https://developers.google.com/earth-engine/datasets/catalog/MODIS_061_MCD12Q1)

### Day 11: Arctic

Last year's Day 25 theme was Antarctica so this year we are travelling to the opposite pole of the Arctic. Initially, I started the project in QGIS, but when projecting the basemap in EPSG: 3395, some distortions led to some gaps in the visualisation. I hence decided to try using Python, where the Cartopy package proved invaluable for plotting both land and ocean features in the Arctic region.

To enhance the map, I overlaid GEBCO's gridded bathymetry data, which provides global elevation data at a 15 arc-second grid resolution. I had to downscale the data to make it manageable for processing and visualisation. The final map highlights the intricate details of the Arctic's terrain.


![Arctic Topography and Bathymetry](Day%2011/arctic_topography_bathymetry.png)

Data Source: [GEBCO](https://www.gebco.net/data_and_products/gridded_bathymetry_data/#area)

### Day 10: Pen & Paper

I recently completed my MSc in Urban Spatial Science at the end of August and am actively navigating the job market in search of my next role. Besides reminding myself that I will be where I need to be eventually, constantly refining my application approach, I also allocate the time to practice/enhance my skills so that I don't become too rusty. While today's theme is not really about technical skills, I decided to exercise some creativity and convert some of the common phrases I’ve encountered, such as the “Unfortunately, we will not be moving forward with your application” bridge and the “Due to the high volume of applications received” forest into a map.

On that note, if anyone is aware of geospatial, remote sensing, data science, or analyst roles (I’m eligible to work in both the UK and Singapore), I’d be glad to connect and explore any opportunities. Thank you!

![Hire Me Please](Day%2010/Day%2010.png)

### Day 9: AI only

For this prompt, I asked ChatGPT to generate a land use map of Singapore complete with a legend and north arrow, and compared it against the [Master Plan 2019](https://www.ura.gov.sg/maps/?service=MP) as a benchmark. Some aspects of the model align to some degree such as the shape of the mainland, the islands (e.g. Pulau Ubin, Sentosa, Jurong Island), key green spaces (e.g. Central Catchment Area, Western Water Catchment Area), highway (e.g. Pan Island Expressway) and possibly the general shape of my neighbourhood. Where the map does not perform so well includes the fact that the waterways do not run that prominently through the island and it does not differentiate between residential and industrial land use. In addition, the airport is missing and the legend/labels are illegible. I also tested other AI map generators but as they are LLM models, they do not specialise in accurate, real-time maps or are able to access mapping APIs. In one instance, a Singapore town today was wrongly portrayed as a fishing village (perhaps a throwback to its past). This limitation highlights the ongoing importance of geospatial specialists and cartographers in validating maps. Their expertise not only ensures accuracy but also brings a personal creative touch to map design, as many AI-generated maps tend to follow similar patterns over time.

![Singapore Land Use](Day%209/ChatGPT/Singapore_Land%20Use_2.png)

Data Source: [ChatGPT](https://chatgpt.com/)

### Day 8: HDX

The Humanitarian Data Exchange has a wide repository of data and maps available. I decided to investigate the impacts of the floods in Senegal of October 2024. I ran some initial data analysis to calculate the percentage of people and buildings affected for each region in python before doing the final design in QGIS.

![Senegal Flood](Day%208/Day%208.png)

Data Source: [Flood Extent](https://data.humdata.org/dataset/floodwater-depth-in-saint-louis-and-matam-regions-senegal-as-of-23-october-2024) ; [Population](https://data.humdata.org/dataset/kontur-population-senegal) ; [Buildings](https://data.humdata.org/dataset/hotosm_sen_buildings) ; [Road](https://data.humdata.org/dataset/hotosm_sen_roads) ; [Administrative Divisions](https://data.humdata.org/dataset/whosonfirst-data-admin-sen)

### Day 7: Vintage

For a modern dataset presented with a vintage aesthetic, I visualised the distribution of Airbnb listings across Amsterdam's neighborhoods. A desaturated sepia color scheme was applied to both the data and basemap, creating an aged appearance. To enhance the vintage effect, I overlaid a subtle paper texture. Additional stylistic elements include a classic compass rose, a bordered map frame, and Garamond font for labels and titles.

![Airbnb](Day%207/Day%207_edited.png)

Data Source: [Inside Airbnb](https://insideairbnb.com/get-the-data/), [Municipality of Amsterdam](https://maps.amsterdam.nl/open_geodata/)


### Day 6: Raster

Last month, I came across an article from the [NASA Earth Observatory](https://earthobservatory.nasa.gov/images/153463/a-colorful-aurora-paints-the-night-sky) discussing how remote sensing can capture the Northern Lights. Inspired, I set out to recreate this effect in Google Earth Engine using the VIIRS sensor data. I selected a date range from 1st to 15th October to ensure comprehensive coverage across much of North America (although the peak was around 10th October). After testing various aggregation methods, including mean, median, and max pixel values, I chose the max pixel value for its ability to highlight the auroras more vividly. The final output captures the auroras alongside city lights against a dark background, creating a visual reminiscent of a star map, which I’m quite pleased with.

![Aurora](Day%206/Day%206.png)

Data Source: [VNP46A2: VIIRS Lunar Gap-Filled BRDF Nighttime Lights Daily L3 Global 500m](https://developers.google.com/earth-engine/datasets/catalog/NOAA_VIIRS_001_VNP46A2)

### Day 5: Journey

Was initially thinking of a pilgrimage route such as Shikoku Pilgrimage or Camino de Santiago before I decided to trace Abraham's footsteps in Genesis. Tracing his journey chronologically ended up with many intersecting lines around Hebron. Hence I decided to make the map a single line passing by key moments in his life instead, drawing some similarities to the existing [Abraham Path](https://www.abrahampath.org/) route.

![Abraham Path](Day%205/Day%205.png)

Data Source: [World Bank](https://datacatalog.worldbank.org/search/dataset/0038272/World-Bank-Official-Boundaries)


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
