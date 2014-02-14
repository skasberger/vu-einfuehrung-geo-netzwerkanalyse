# Preprocessing

Strassennetz Steiermark ansehen http://data.steiermark.at/cms/beitrag/11822084/97108894/?AppInt_OGD_ID=53


## Einleitung
Kurzer einleitender Text, was in der Markdown file gemacht wird.

## Workflow


* Daten besorgen: 
	Grundlage zumeist Shapefile
	Rohdaten sichern
* Daten aufbereiten: 
	Fehler bereinigen
	Daten verknüpfen/vereinen
	mit Attributen anreichern
	Standardisieren/harmonisieren
	auf eine Datei / auf ein passendes Dateiformat zusammen führen	
	routing spezifisches
		konnektivitäten, impedanzen, costs, turns festlegen	
		brücken, überführungen, tunnel, unterführungen
* Daten modellieren und analysieren: 
	Routing
	Service Areas
	Shortest Paths
* Daten präsentieren: 
	Karte zeichnen
	Daten für weiter Analysen exportieren

## OpenStreetMap
Die Daten aus der [OpenStreetMap](http://wiki.openstreetmap.org/wiki/Map_Features) werden mittels [QGIS](http://qgis.org) runtergeladen und gespeichert.

Hintergrund Orthophoto importieren zur optischen Kontrolle

OpenStreetMap Daten runterladen

graz.osm
wien.osm

BILD

OpenStreetMap Daten aus XML in Spatialite Datenbank speichern.

osm-graz-all.db
osm-wien-all.db

mit lizenz text verpacken und upload (github dateigrößen limit 100mb)
[Download](http://courses.openscienceasap.org/vu-einfuehrung-geo-netzwerkanalyse/data/osm-wien-graz.tar.gz)

[Map Features](http://wiki.openstreetmap.org/wiki/Map_Features)

Attribut import bei Polylinien:
- [highway](http://wiki.openstreetmap.org/wiki/Key:highway)
- [cycleway](http://wiki.openstreetmap.org/wiki/Key:cycleway)

osm-wien-points.sqlite
osm-wien-polygons.sqlite
osm-wien-polylines.sqlite

BILD


Als Shape, Spatialite und SQLite speichern
```
© OpenStreetMap contributors
The data is from the OpenStreetMap and is licensed under the Open Data Commons Open Database License (ODbL). 
OpenStreetMap copyright: http://www.openstreetmap.org/copyright
License: http://opendatacommons.org/licenses/odbl/
```

Es wird zum Speichern [SpatiaLite](https://www.gaia-gis.it/fossil/libspatialite/index) oder [SQLite](https://www.sqlite.org/) empfohlen, da die gesamte Länge der Strings der Attribute und Werte gesichert wird. Shapefiles kürzen hier nach XX Zeichen ab.

BILD

Dateien öffnen und Encoding kontrollieren (Table Button)

## OGD Wien
Auf Datenportal gehen und link markieren.

### Daten importieren
Die aktuellen Daten vom Wiener OGD Server importieren ist ganz einfach: "Vektorlayer hinzufügen" klicken, auf Protokoll gehen, GeoJSON auswählen und als URI die URL unter WFS GeoJSON einfügen. Nach dem OK Klicken dauert der Import ein bisschen, bis der Layer zu sehen ist.
[Straßengraph Wien](https://open.wien.at/site/datensatz/?id=1039ed7e-97fb-435f-b6cc-f6a105ba5e09): [WFS GeoJSON Knoten](http://data.wien.gv.at/daten/geoserver/ows?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:STRASSENKNOTENOGD&srsName=EPSG:4326&outputFormat=json), [WFS GeoJSON Kanten](http://data.wien.gv.at/daten/geoserver/ows?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:STRASSENGRAPHOGD&srsName=EPSG:4326&outputFormat=json)
[Straßengraph ASFINAG](https://open.wien.at/site/datensatz/?id=db389f75-56c3-4d61-9bb7-1f1c675edeaf): [WFS GeoJSON Knoten](http://data.wien.gv.at/daten/geoserver/ows?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:ASFINAGKNOTENOGD&srsName=EPSG:4326&outputFormat=json) & [WFS GeoJSON Kanten](http://data.wien.gv.at/daten/geoserver/ows?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:ASFINAGSTRASSEOGD&srsName=EPSG:4326&outputFormat=json)
[U-Bahnnetz Bestand](https://open.wien.at/site/datensatz/?id=2d0e9a21-fa5f-441d-948a-fe97a453a827): [WFS GeoJSON](http://data.wien.gv.at/daten/geoserver/ows?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:UBAHNOGD,ogdwien:UBAHNHALTOGD&srsName=EPSG:4326&outputFormat=json)
BILD
[Öffentliches Verkehrsnetz - Haltestellenpunkte](https://open.wien.at/site/datensatz/?id=f1f6f15d-2faa-4b62-b78b-80599dd1c66e): [WFS GeoJSON](http://data.wien.gv.at/daten/geoserver/ows?service=WFS&request=GetFeature&version=1.1.0&srsName=EPSG:4326&outputFormat=json&typeName=ogdwien:OEFFHALTESTOGD)
[Öffentliches Verkehrsnetz - Liniennetz](https://open.wien.at/site/datensatz/?id=36a8b9e9-909e-4605-a7ba-686ee3e1b8bf): [WFS GeoJSON](http://data.wien.gv.at/daten/wfs?service=WFS&request=GetFeature&version=1.1.0&typeName=ogdwien:OEFFLINIENOGD&srsName=EPSG:4326&outputFormat=json)


BILD

Leider sind die Daten des OGD Wien Servers zumeist nicht in dem UTF8 Zeichensatz codiert, sondern im Latin1, was zu Problemen mit ?, ö, ä, und weiteren Sonderzeichen führt. Dies ist unter "Eigenschaften" -> "Allgemein" im Punkt Datenquellenkodierung zu auf den verwendeten Zeichensatz "Latin1" zu setzen.
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



## Daten testen
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


## Routingfähiges Netzwerk erstellen
Layer verknüpfen

### Netzwerke vereinen
Konnektivität herstellen

### Kosten
je nach Kategorie


### Impedanzen


### Exportieren
als shapefile, als spatialite file




## Häufige Fehler









