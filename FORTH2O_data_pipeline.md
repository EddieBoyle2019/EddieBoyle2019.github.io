## FORTH2O Data Lab
### Data pipeline

#### 1. Postgres

* Add dataset metadata to 'f2o' Postgres database

#### 2. QGIS

* Open dataset Shapefile in QGIS
* Clip data to Forth basin AOI polygon (if not already clipped) and save/export as new Shapefile
* Import dataset Shapefile into PostGIS database (create db if necessary) and add spatial index to 'Geom' attribute in new table
* Create symbology/styling for data with 1) QGIS GUI or 2) PyQGIS - see examples at:
<https://github.com/EddieBoyle2019/f2o_pyqgis>
* Save/export styling as SLD file

#### 3. GeoServer

* Add dataset in PostGIS database as Store and Layer in GeoServer
* Add Styling to Layer in GeoServer using SLD file with 1) GeoServer GUI or 2) GeoServer REST API Linux shell scripts - see examples at:
<https://github.com/EddieBoyle2019/f2o_shell>

#### 4. Laravel

* Add OpenLayers JavaScript code for the GeoServer dataset WMS interface to:
/resources/js/f2o_openlayers.js
* Use the dataset ID contained in the 'f2o' Postgres database
* Add Ajax/jQuery JavaScript code (dataset ID) for the dataset to:
/resources/views/explore.blade.php
