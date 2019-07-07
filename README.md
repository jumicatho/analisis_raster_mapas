# analisis_raster_mapas
Guardando descripciones a utilizar en mapas y sig
Encontré este código sobre  el índice ndwi.  Lo guardo para tenerlo a la mano y utilizarlo en análisis de  rasters en el programa qgis.
Lo descargué de https://github.com/sentinel-hub/custom-scripts/blob/master/sentinel-2/ndwi/script.js
// Fuente: https://en.wikipedia.org/wiki/Normalized_difference_water_index

// opción 1, utilizada para monitorear los cambios en el contenido de agua de las hojas, propuesta por Gao
// http://ceeserver.cee.cornell.edu/wdp2/cee6150/Readings/Gao_1996_RSE_58_257-266_NDWI.pdf
var ndwi = ( B08 - B11 ) / ( B08 + B11 );

// opción 2, utilizada para monitorear cambios relacionados con el contenido de agua en cuerpos de agua, utilizando longitudes de onda verde y NIR, definidas por McFeeters (1996):
// var ndwi = (B03 - B08) / (B03 + B08);

si (ndwi <  - 0 ) {
  devuelve  colorBlend ( - ndwi, [ 0 , 1 ], [[ 1 , 1 , 1 ], [ 0 , 0.5 , 0 ]]);
  
} else {
  devuelve  colorblend ( Math . pow (ndwi, 0.25 ), [ 0 , 1 ], [[ 1 , 1 , 1 ], [ 0 , 0 , 0.8 ]]);
}
