Data Source: NASA https://plugins.qgis.org/plugins/SRTM-Downloader/

Steps:
1. Download SRTM plugin and select for Canvas extent or add coordinates
2. Raster>Extraction>Clip Raster by Extent to reduce study area
3. Processing Toolbox>Contour Polygons (50m/100m)
4. Symbology>Categorised>Elev_Min>Advanced>Set Symbol Level to be different for each category. Add draw effects>drop shadow.