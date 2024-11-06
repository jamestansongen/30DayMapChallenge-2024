//1. Import Data and Set Study Area/Date Range
//import VNP46A2: VIIRS Lunar Gap-Filled BRDF Nighttime Lights Daily L3 Global 500m
//https://developers.google.com/earth-engine/datasets/catalog/NOAA_VIIRS_001_VNP46A2
var viirs = ee.ImageCollection('NOAA/VIIRS/001/VNP46A2').select('DNB_BRDF_Corrected_NTL');

//define date range
var startDate = '2024-10-01';
var endDate = '2024-10-15';

//filter by date range
var filteredViirs = viirs.filterDate(startDate, endDate);

//define the regional bounds for North America
var northAmerica = ee.Geometry.Polygon(
  [[[-168.0, 18.0],  //SW
    [-168.0, 71.0],  //NW
    [-53.0, 71.0],   //NE
    [-53.0, 18.0]]], //SE
  null, false
);

//set the center for North America
Map.setCenter(-95.0, 37.5, 4); //center coordinates for North America

//add the North America region to the map for visualization
//Map.addLayer(northAmerica, {color: 'blue'}, 'North America');

//clip each image in the filtered collection to North America
var clippedViirs = filteredViirs.map(function(image) {
  return image.clip(northAmerica);
});

//2. Create Image (e.g. mean, max, median)

//mean and clip the image in the filtered collection to North America
//var meanViirs = filteredViirs.filterBounds(northAmerica).mean().multiply(1.5).clip(northAmerica);
//mean not preferred as it will dim the aurora

//create a composite image using the max function to highlight the brightest areas
var compositeViirs = clippedViirs.max(); //use max to keep the brightest pixels

//3. Visualise and Export Results
//set visualisation parameters
var visParams = {
  min: 0,
  max: 30,
  palette: ['000000', '003366', '006699', '33cc33', '66ff33', 'ccff99', 'ffffff']
};

//add the VIIRS data to the map
Map.addLayer(clippedViirs, visParams, 'VIIRS 2024');

//add the composite image to the map
Map.addLayer(compositeViirs.visualize(visParams), {}, 'Composite Clipped VIIRS Image');

//export the composite image to Google Drive
Export.image.toDrive({
  image: compositeViirs.visualize(visParams), //visualize to get the color
  description: 'VIIRS_Composite_North_America', //name of the export task
  scale: 500, //scale
  region: northAmerica, //study area
  maxPixels: 1e13, 
  fileFormat: 'GEOTIFF' 
});