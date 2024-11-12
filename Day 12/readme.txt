//1. Setup maps
//define the Galapagos Islands bounding box
var galapagos = ee.Geometry.Polygon([
  [
    [-92.681, 1.3534],    //NW
    [-88.4989, 1.3534],   //NE 
    [-88.4989, -3.1135],  //SE
    [-92.681, -3.1135]    //SW
  ]
]);

//load the MODIS Land Cover dataset and filter for the study area
var modisLandCover = ee.ImageCollection('MODIS/061/MCD12Q1')
                        .filterBounds(galapagos);

//list of years to select from 2001 to 2023
var years = [];
for (var i = 2001; i <= 2023; i++) {
  years.push(i.toString());
}

//load default land cover images for the years (e.g. 2001 and 2023)
var landCover2001 = modisLandCover.filterDate('2001-01-01', '2001-12-31').first();
var landCover2023 = modisLandCover.filterDate('2023-01-01', '2023-12-31').first();

//select the land cover classification band
var landCover2001Vis = landCover2001.select('LC_Type1').clip(galapagos);
var landCover2023Vis = landCover2023.select('LC_Type1').clip(galapagos);

//visualization parameters for MODIS land cover
var landCoverVisParams = {
  min: 1,
  max: 17,
  palette: [
    '05450a', '086a10', '54a708', '78d203', '009900', 'c6b044', 'dcd159', 
    'dade48', 'fbff13', 'b6ff05', '27ff87', 'c24f44', 'a5a5a5', 'ff6d4c',
    '69fff8', 'f9ffa4', '1c0dff'
  ]
};

//create two maps centered on the Galapagos
var leftMap = ui.Map();
var rightMap = ui.Map();

//remove UI controls from both maps, but leave zoom control on the left map
leftMap.setControlVisibility(false);
rightMap.setControlVisibility(false);
leftMap.setControlVisibility({zoomControl: true});

//center the maps on the Galapagos Islands
leftMap.centerObject(galapagos, 8);
rightMap.centerObject(galapagos, 8);

//add the land cover images to each map
leftMap.addLayer(landCover2001Vis, landCoverVisParams, 'Land Cover 2001');
rightMap.addLayer(landCover2023Vis, landCoverVisParams, 'Land Cover 2023');

//create a split panel with the two maps
var splitPanel = ui.SplitPanel({
  firstPanel: leftMap,
  secondPanel: rightMap,
  orientation: 'horizontal',
  wipe: true
});

//remove the default map from the root panel
ui.root.clear();

//add the split panel to the root panel
ui.root.add(splitPanel);

//2. Create image selection UI
//create two selectors for image selection
var imageSelect_1 = ui.Select(years, "Select Year for Left Map");
var imageSelect_2 = ui.Select(years, "Select Year for Right Map");

//image 1 Label
var image1Label = ui.Label("Select Year for Left Map:");

//panel for Image 1 select widget
var query1Panel = ui.Panel([imageSelect_1]);

var image1Panel = ui.Panel({ 
  widgets: [image1Label, query1Panel],
  style: {position: 'top-left'}
});

//add image panel to the left map
leftMap.add(image1Panel);

//image 2 Label
var image2Label = ui.Label("Select Year for Right Map:");

//panel for Image 2 select widget
var query2Panel = ui.Panel([imageSelect_2]);

var image2Panel = ui.Panel({ 
  widgets: [image2Label, query2Panel],
  style: {position: 'top-right'}
});

//add image panel to the right map
rightMap.add(image2Panel);

//link the two maps to move together
var linker = ui.Map.Linker([leftMap, rightMap]);

//function to update maps based on the selected year
function updateMap() {
  //get the selected years for both maps
  var year1 = imageSelect_1.getValue();
  var year2 = imageSelect_2.getValue();
  
  //check if the selected years are valid
  if (year1 === null || year2 === null) {
    //if any year is null, return without updating the map
    return;
  }

  //load the MODIS Land Cover dataset and filter for the selected years
  var landCoverYear1 = modisLandCover.filterDate(year1 + '-01-01', year1 + '-12-31').first();
  var landCoverYear2 = modisLandCover.filterDate(year2 + '-01-01', year2 + '-12-31').first();
  
  //check if the images for the selected years exist
  if (landCoverYear1 === undefined || landCoverYear2 === undefined) {
    //if either of the land cover images doesn't exist, return without updating the map
    print('Land cover image not found for selected years.');
    return;
  }

  //select the land cover classification band and clip to the Galapagos region
  var landCoverYear1Vis = landCoverYear1.select('LC_Type1').clip(galapagos);
  var landCoverYear2Vis = landCoverYear2.select('LC_Type1').clip(galapagos);
  
  //update the map layers
  leftMap.layers().set(0, ui.Map.Layer(landCoverYear1Vis, landCoverVisParams, 'Land Cover ' + year1));
  rightMap.layers().set(0, ui.Map.Layer(landCoverYear2Vis, landCoverVisParams, 'Land Cover ' + year2));
}

//update the maps when the year is selected from the drop-downs
imageSelect_1.onChange(updateMap);
imageSelect_2.onChange(updateMap);

//initialize maps with default values (2001 and 2023)
updateMap();

//3. Legend for land cover

//define the legend panel
var legend = ui.Panel({
  style: {position: 'bottom-right', padding: '8px'}
});

//add title to the legend
legend.add(ui.Label({
  value: 'Land Cover Classification',
  style: {fontWeight: 'bold', fontSize: '16px'}
}));

//add legend color and labels
var palette = landCoverVisParams.palette;
var names = [
  'Evergreen Needleleaf Forest', 'Evergreen Broadleaf Forest', 'Deciduous Needleleaf Forest', 
  'Deciduous Broadleaf Forest', 'Mixed Forest', 'Closed Shrublands', 'Open Shrublands', 
  'Woody Savannas', 'Savannas', 'Grasslands', 'Permanent Wetlands', 'Croplands', 
  'Urban and Built-up Lands', 'Cropland/Natural Vegetation Mosaics', 'Permanent Snow and Ice', 'Barren', 'Water Bodies'
];

var makeRow = function(color, name) {
  var colorBox = ui.Label({
    style: {
      backgroundColor: color,
      padding: '8px',
      margin: '2px',
      width: '16px',
      height: '16px'
    }
  });
  var description = ui.Label({
    value: name,
    style: {padding: '8px'}
  });
  return ui.Panel([colorBox, description], ui.Panel.Layout.Flow('horizontal'));
};

//add each row to the legend
for (var i = 0; i < palette.length; i++) {
  legend.add(makeRow(palette[i], names[i]));
}

//add the legend to the map
ui.root.add(legend);
