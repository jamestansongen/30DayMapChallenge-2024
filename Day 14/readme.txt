Image Source: https://commons.wikimedia.org/wiki/File:Flag-map_of_the_world_%282018%29.png

Steps:
1. Set Image CRS to EPSG: 4326
2. Vector>Geometry Tools>Create Grid. Select rectangle for Grid type and experiment with horizontal and vertical spacing
3. Zonal Statistics>Input Layer as Grid and Raster Layer as Image. Select Band 1 (Red) for Raster Band, Red for Output column prefix and majority for Statistics to calculate. Repeat the same for Band 2 (Green) and Band 3 (Blue) except changing the Input layer to the newly generated grid.
4. Vector>Geometry Tools>Centroids>Select the final grid from Step 3 as the input layer.
5. Use data-defined override to change the fill for both grids and centroids. Enter the formula color_rgb("Redmajority", "Greenmajority", "Bluemajority"). Can add a drop shadow for the centroids although it may appear quite dark when zoomed out so may need to adjust grid size. Alternatively, adjust brightness and contrast separately.

Note: this method is for any image from the internet. In the case of DEMs or other satellite images, zonal statistics is still relevant for the e.g. elevation, NDVI value. However, in the symbology in Step 5, you may have to use a graduated colour scheme.