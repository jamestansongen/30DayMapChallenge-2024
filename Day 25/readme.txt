//tutorial source: https://andrewmaclachlan.github.io/CASA0023/8_temperature.html

//1. Generate region of interest
//define the bounding box for Africa
var africaBounds = ee.Geometry.Rectangle([-25, -35, 55, 40]);

//style the bounding box as a feature
var africaBoxStyle = ee.FeatureCollection(africaBounds).style({
  color: '1e90ff',  //line color
  width: 2,         //line width
  fillColor: '00000033' //lightly transparent fill color
});

//add the bounding box to the map
Map.addLayer(africaBoxStyle, {}, 'Africa Bounding Box');

//center the map on Africa
Map.setCenter(20, 0, 3);

//2. Obtain MODIS data for 2023 and ROI
function MODISscale(image) {
  var temp = image.select('LST_.*').multiply(0.02).subtract(273.1);
  return image.addBands(temp, null, true);
}

var MODIS_Aqua_day = ee.ImageCollection('MODIS/061/MYD11A1')
  .filterDate('2023-01-01', '2023-12-31')
  .select('LST_Day_1km')
  .filterBounds(africaBounds)
  .map(MODISscale);

var MODIS_Terra_day = ee.ImageCollection('MODIS/061/MOD11A1')
  .filterDate('2023-01-01', '2023-12-31')
  .select('LST_Day_1km')
  .filterBounds(africaBounds)
  .map(MODISscale);

var mean_aqua_terra = MODIS_Aqua_day.merge(MODIS_Terra_day)
  .reduce(ee.Reducer.mean())
  .clip(africaBounds);

//3. Visualise the data
var landSurfaceTemperatureVis = {
  min: 10,
  max: 50,
  palette: [
    '040274', '040281', '0502a3', '0502b8', '0502ce', '0502e6',
    '0602ff', '235cb1', '307ef3', '269db1', '30c8e2', '32d3ef',
    '3be285', '3ff38f', '86e26f', '3ae237', 'b5e22e', 'd6e21f',
    'fff705', 'ffd611', 'ffb613', 'ff8b13', 'ff6e08', 'ff500d',
    'ff0000', 'de0101', 'c21301', 'a71001', '911003'
  ],
};

Map.addLayer(mean_aqua_terra, landSurfaceTemperatureVis,
    'MODIS Land Surface Temperature');

//4. Export the data
//export the mean land surface temperature as a GeoTIFF
Export.image.toDrive({
  image: mean_aqua_terra,
  description: 'MeanLandSurfaceTemperature_Africa',
  folder: 'EarthEngineExports',  // Optional: Specify a folder in your Google Drive
  fileNamePrefix: 'LST_Mean_Africa',  // File name
  region: africaBounds,  // Bounding box for Africa
  scale: 1000,  // Resolution in meters (adjust as needed)
  crs: 'EPSG:4326',  // Coordinate Reference System
  maxPixels: 1e13  // Allow exporting large images
});

