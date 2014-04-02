


# 01 Grundlagen
#### Postgresql und postGIS
BILDER

[Install/Setup in Ubuntu 13.10](http://trac.osgeo.org/postgis/wiki/UsersWikiPostGIS21UbuntuPGSQL93Apt)

[pgRouting](http://pgrouting.org/)
[Anleitung](http://docs.pgrouting.org/2.0/en/pgRoutingDocumentation.pdf)

[OSM2PO](http://www.bostongis.com/?content_name=pgrouting_osm2po_1#305)
[Part 1: Loading OpenStreetMap data into PostGIS: An Almost Idiot's Guide](http://www.bostongis.com/?content_name=loading_osm_postgis#229)

packete installieren
sudo make installt install libboost-graph-dev
sudo apt-get install libcgal*

download pgrouting

von source compilieren


in cmake ordner gehen
```
cmake ..
make
sudo make install
```

[QGIS pgrouting tag](http://planet.qgis.org/planet/tag/pgrouting/)
https://github.com/pgRouting/workshop
http://anitagraser.com/tag/pgrouting/
http://workshop.pgrouting.org/

[PostGIS](http://postgis.org/)
[PostgreSQL](http://www.postgresql.org/)

http://anitagraser.com/tag/pgrouting/
http://anitagraser.com/2011/02/07/a-beginners-guide-to-pgrouting/

### R
BILD

http://www.r-project.org/

Benötigte Plugins
http://cran.r-project.org/web/packages/foreign/index.html
Traveling Salesman http://cran.r-project.org/web/packages/TSP/index.html
http://cran.r-project.org/web/packages/maps/index.html
http://cran.r-project.org/web/packages/sp/index.html
http://cran.r-project.org/web/packages/RJSONIO/index.html
http://cran.r-project.org/web/packages/shapefiles/index.html
http://cran.r-project.org/web/packages/spatial/index.html
http://cran.r-project.org/web/packages/sna/index.htm
http://cran.r-project.org/web/packages/igraph/index.html
http://igraph.sourceforge.net/

### Python
BILD

[Python und Fernerkundung](http://www2.geog.ucl.ac.uk/~mdisney/teaching/3051/hdf_prac/)

[shapely](https://pypi.python.org/pypi/Shapely)
For geometry handling. This is the de facto  package for geometry handling and manipulation.

[pysal](https://code.google.com/p/pysal/)
For all your spatial econometrics needs (and more). This is a really great package that is also under constant development. It covers everything from exploratory spatial data analysis (ESDA) right up to heavy duty spatial econometric models.

[networkX](http://networkx.github.io/)
http://networkx.github.io/documentation/latest/tutorial/

[iGraph](http://igraph.sourceforge.net/)
http://igraph.sourceforge.net/documentation.html
http://igraph.wikidot.com/installing-python-igraph-on-linux

[cartopy](http://scitools.org.uk/cartopy/)
or plotting spatial data. This is a pretty new package, and is actively being developed. It makes for really nice publication quality maps already, and plays really nicely with shapely geometries and matplotlib (see below).

[geopy](https://code.google.com/p/geopy/)
For geolocating addresses and things like that. It is a small wrapper around various web-based geocoding APIs.

[GDAL](https://pypi.python.org/pypi/GDAL/)
For reading, writing, and transforming geospatial data formats. This has all sorts of nice ways to work with geospatial data, though fiona (see below) is much nicer for reading and writing different geospatial formats.

[pyshp](http://code.google.com/p/pyshp/)
For reading and writing shapefiles in pure Python. Nice API and works great.

[pyproj](https://code.google.com/p/pyproj/)
For conversions between projections. This package provides an intuitive way of interacting with the Proj4 library for transforming data between coordinate reference systems.

[QGIS](http://www.qgis.org/en/docs/pyqgis_developer_cookbook/intro.html)
For anything and everything GIS. This is the Python API for Quantum GIS. You can work directly within QGIS via its intergrated Python console, or create standalone GIS apps using this powerful Python package.

[fiona](http://toblerity.org/fiona/)
For making it easy to read/write geospatial data formats. Really, really nice API for reading and writing GIS formats.

[descartes](https://pypi.python.org/pypi/descartes)
For plotting geometries in matplotlib. This is a nice, clean, GeoJSON style data helper for matplotlib and shapely.

[psycopg2](http://zetcode.com/db/postgresqlpythontutorial/)
http://initd.org/psycopg/install/
postgresql API

rtree
For efficiently querying spatial data. This is a relatively simple spatial index package that really speeds up spatial bounding box queries.

#### networkX
http://www.clear.rice.edu/comp200/resources/howto/networkx.shtml
http://www.cl.cam.ac.uk/~cm542/teaching/2011/stna-pdfs/stna-lecture11.pdf

#### iGraph
#### iPython

#### Beschreibung
#### Nachschlagen
#### Installieren
#### Lernen
#### Sonstiges


## Data Repos
**OGD Graz**

**OGD Steiermark**

### data.gov

### data.uk

### OGD Wien
BILD

### Landsat
[Bands](http://landsat.usgs.gov/band_designations_landsat_satellites.php)
[YOUTUBE VIDEO: Downloading Landsat GeoTiff Images and Viewing them in Quantum GIS](https://www.youtube.com/watch?v=xyRrPEb3IPM)

### MODIS

### Tiger


# 02 Daten aufbereiten

#### Wien
Die aktuellen Daten vom Wiener OGD Server importieren ist ganz einfach: "Vektorlayer hinzufügen" klicken, auf Protokoll gehen, GeoJSON auswählen und als URI die URL unter WFS GeoJSON einfügen. Nach dem OK Klicken dauert der Import ein bisschen, bis der Layer zu sehen ist.

[Straßengraph](https://open.wien.at/site/datensatz/?id=1039ed7e-97fb-435f-b6cc-f6a105ba5e09): [WFS GeoJSON Knoten](http://data.wien.gv.at/daten/geoserver/ows?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:STRASSENKNOTENOGD&srsName=EPSG:4326&outputFormat=json), [WFS GeoJSON Kanten](http://data.wien.gv.at/daten/geoserver/ows?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:STRASSENGRAPHOGD&srsName=EPSG:4326&outputFormat=json)
[Straßengraph ASFINAG](https://open.wien.at/site/datensatz/?id=db389f75-56c3-4d61-9bb7-1f1c675edeaf): [WFS GeoJSON Knoten](http://data.wien.gv.at/daten/geoserver/ows?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:ASFINAGKNOTENOGD&srsName=EPSG:4326&outputFormat=json) & [WFS GeoJSON Kanten](http://data.wien.gv.at/daten/geoserver/ows?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:ASFINAGSTRASSEOGD&srsName=EPSG:4326&outputFormat=json)
[U-Bahnnetz Bestand](https://open.wien.at/site/datensatz/?id=2d0e9a21-fa5f-441d-948a-fe97a453a827): [WFS GeoJSON](http://data.wien.gv.at/daten/geoserver/ows?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:UBAHNOGD,ogdwien:UBAHNHALTOGD&srsName=EPSG:4326&outputFormat=json)
BILD
[Öffentliches Verkehrsnetz - Haltestellenpunkte](https://open.wien.at/site/datensatz/?id=f1f6f15d-2faa-4b62-b78b-80599dd1c66e): [WFS GeoJSON](http://data.wien.gv.at/daten/geoserver/ows?service=WFS&request=GetFeature&version=1.1.0&srsName=EPSG:4326&outputFormat=json&typeName=ogdwien:OEFFHALTESTOGD)
[Öffentliches Verkehrsnetz - Liniennetz](https://open.wien.at/site/datensatz/?id=36a8b9e9-909e-4605-a7ba-686ee3e1b8bf): [WFS GeoJSON](http://data.wien.gv.at/daten/wfs?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:OEFFLINIENOGD&srsName=EPSG:4326&outputFormat=json)


### Daten importieren

BILD

Leider sind die Daten des OGD Wien Servers zumeist nicht in dem UTF8 Zeichensatz codiert, sondern im Latin1, was zu Problemen mit ?, ö, ä, und weiteren Sonderzeichen führt. Dies ist unter "Eigenschaften" -> "Allgemein" im Punkt Datenquellenkodierung zu auf den verwendeten Zeichensatz "Latin1" zu setzen. => ist das auch bei Steiermark so ???
Encoding auf Latin1 stellen

BILD

Speichern als spatialite und shapefile
Um weiterfolgend besser arbeiten zu können, macht es Sinn die Daten lokal zu speichern, damit nicht bei jedesmal beim Zoomen die neuen Daten beim Server abgefragt werden müssen. 

```
Datenquelle: Stadt Wien – data.wien.gv.at
License: CC BY 3.0 AT http://opendatacommons.org/licenses/odbl/
```
data/raw/
wien-oeffis-haltestellen.sqlite
wien-oeffis-liniennetz.sqlite
wien-ubahn-points.sqlite

BILD

**Daten Stmk via Shell Skripts importieren**
Erweiterungen zur Datenbank installieren 
```
psql routing_graz -c "create extension postgis"
psql routing_graz -c "create extension pgrouting"
```


### Daten testen
Ziel ist es zu schauen, wie genau die Geometrien übereinstimmen. Dies ist für das Verknüpfen der Layer (Netzwerke) nötig. Sowie kontrollieren, ob beim Importieren und Konvertieren irgendwelche Fehler passiert sind. => Attribut Table ansehen

BILD

Knoten des Straßengraph kontrollieren: ob die auf den Kanten liegen
Knoten des Liniennetzes kontrollieren: ob die auf den Kanten liegen
Knoten des U-Bahn-Netzes kontrollieren: ob die auf den Kanten liegen
Knoten der Autobahn kontrollieren: ob die auf den Kanten liegen

BILD

Kanten OSM Polylines mit Straßengraph vergleichen.
Kanten OSM Polylines mit Linien-Netz vergleichen.
Kanten U-Bahn mit Liniennetz vergleichen.

Vergleich Straßen: OpenStreetMap Polylines mit Straßengraph (Kanten) und Öffentlichen Verkehrs-Liniennetz (Kanten). Beispiel Autobahnabfahrt, Beispiel Straße, Beispiel U-Bahn

BILD

Vergleich Haltestellen: OpenStreetMap Points mit Strassengraph (Knoten) und Öffentlichen Verkehrs-Liniennetz (Kanten). Beispiel Haltestelle U-Bahn, Haltestelle Öffentlicher Verkehr, 


### networkX
- Node muss erster Graph bei union sein, zweiter dann Edges Graph



# 03 Netzwerkanalyse




# Visualisierung im Web
Software
    Python: 
    networkX
    R: iGraph
    Quantum GIS
    GRASS GIS
    Gephi
Daten:
    OpenStreetMap
    http://wiki.openstreetmap.org/wiki/QGIS
    data.gov
    data.gov.uk



