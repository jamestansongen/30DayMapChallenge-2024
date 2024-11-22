Google Earth Engine Code to obtain glaciers

// Define a bounding box for Iceland (approximate lat/lon bounds)
var icelandBounds = ee.Geometry.Rectangle([-25, 63, -13, 67]);

// Load the GLIMS dataset
var dataset = ee.FeatureCollection('GLIMS/20230607');

// Filter the dataset for Iceland using the bounding box
var icelandGlaciers = dataset.filterBounds(icelandBounds);

// Visualization parameters
var visParams = {
  palette: ['gray', 'cyan', 'blue'],
  min: 0.0,
  max: 10.0,
  opacity: 0.8,
};

// Create an image from the dataset and display it
var image = ee.Image().float().paint(icelandGlaciers, 'area');

// Set the map center on Iceland and add the layer
Map.setCenter(-18, 64.963, 7);
Map.addLayer(image, visParams, 'GLIMS/20230607 - Iceland');

// Export the filtered dataset as a GeoJSON
Export.table.toDrive({
  collection: icelandGlaciers,
  description: 'Iceland_Glacier_GLIMS',
  fileFormat: 'GeoJSON',
  folder: 'Iceland_Glacier_Export',  // Optional: specify a folder in your Google Drive
  fileNamePrefix: 'iceland_glaciers'
});

Data Source for Volcanoes: https://osm4wiki.toolforge.org/cgi-bin/wiki/wiki-osm.pl?project=en&article=List_of_volcanoes_in_Iceland
Data Source for Iceland boundaries: https://simplemaps.com/gis/country/is#all