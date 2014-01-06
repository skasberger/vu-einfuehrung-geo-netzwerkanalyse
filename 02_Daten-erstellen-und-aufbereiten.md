


## Einleitung
Kurzer einleitender Text, was in der Markdown file gemacht wird.

## OpenStreetMap
Die Daten aus der [OpenStreetMap](http://wiki.openstreetmap.org/wiki/Map_Features) werden mittels [QGIS](http://qgis.org) runtergeladen und gespeichert.

Hintergrund Orthophoto importieren
OpenStreetMap Daten runterladen

BILD

OpenStreetMap Daten aus XML in Spatialite Datenbank speichern.

[Map Features](http://wiki.openstreetmap.org/wiki/Map_Features)

Attribut import bei Polylinien:
- [highway](http://wiki.openstreetmap.org/wiki/Key:highway)
- [cycleway](http://wiki.openstreetmap.org/wiki/Key:cycleway)

BILD


Als Shape, Spatialite und SQLite speichern
´´´
© OpenStreetMap contributors
The data is from the OpenStreetMap and is licensed under the Open Data Commons Open Database License (ODbL). 
OpenStreetMap copyright: http://www.openstreetmap.org/copyright
License: http://opendatacommons.org/licenses/odbl/
´´´

Es wird zum Speichern [SpatiaLite](https://www.gaia-gis.it/fossil/libspatialite/index) oder [SQLite](https://www.sqlite.org/) empfohlen, da die gesamte Länge der Strings der Attribute und Werte gesichert wird. Shapefiles kürzen hier nach XX Zeichen ab.

BILD


## OGD Wien
Auf Datenportal gehen und link markieren.

[U-Bahnnetz Bestand](https://open.wien.at/site/datensatz/?id=2d0e9a21-fa5f-441d-948a-fe97a453a827): [WFS GeoJSON](http://data.wien.gv.at/daten/geoserver/ows?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:UBAHNOGD,ogdwien:UBAHNHALTOGD&srsName=EPSG:4326&outputFormat=json)
BILD
[Öffentliches Verkehrsnetz - Haltestellenpunkte](https://open.wien.at/site/datensatz/?id=f1f6f15d-2faa-4b62-b78b-80599dd1c66e): [WFS GeoJSON](http://data.wien.gv.at/daten/geoserver/ows?service=WFS&request=GetFeature&version=1.1.0&srsName=EPSG:4326&outputFormat=json&typeName=ogdwien:OEFFHALTESTOGD)
[Öffentliches Verkehrsnetz - Liniennetz](https://open.wien.at/site/datensatz/?id=36a8b9e9-909e-4605-a7ba-686ee3e1b8bf): [WFS GeoJSON](http://data.wien.gv.at/daten/wfs?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:OEFFLINIENOGD&srsName=EPSG:4326&outputFormat=json)


Importieren
Die Url einfach als Vektorlayer importieren unter Protokoll [WFS GeoJSON](http://data.wien.gv.at/daten/wfs?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:OEFFLINIENOGD&srsName=EPSG:4326&outputFormat=json)

BILD

Speichern als spatialite
´´´
Datenquelle: Stadt Wien – data.wien.gv.at
License: CC BY 3.0 AT http://opendatacommons.org/licenses/odbl/
´´´

BILD


