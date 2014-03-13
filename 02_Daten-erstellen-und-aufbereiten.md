# Preprocessing

## Einleitung
Kurzer einleitender Text, was in der Markdown file gemacht wird.

**Workflow**
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

## Daten besorgen

Das ganze wird am einfachsten mit dem get-data.sh Download Script runter geladen. Dazu ist das Packet unzip notwendig.

```
sh code/shell/fetch-data.sh
```

### von OGD Steiermark
Folgende Daten werden verwendet:
- [Städtisches und ländliches Straßennetz](http://data.steiermark.at/cms/beitrag/11822084/97108894/?AppInt_OGD_ID=53): [Shapefile](http://service.stmk.gv.at/ogd/OGD_Data_ABT07/geoinformation/Laendliches%20Strassennetz.zip)
- [Übergeordnetes Straßennetz](http://data.steiermark.at/cms/beitrag/11822084/97108894/?AppInt_OGD_ID=22): [Shapefile](http://service.stmk.gv.at/ogd/OGD_Data_ABT07/geoinformation/Verkehrsnetz_hochrangig.zip)
- [Bezirksgrenzen](http://data.steiermark.at/cms/beitrag/11822084/97108894/?AppInt_OGD_ID=32): [Shapefile](http://service.stmk.gv.at/ogd/OGD_Data_ABT07/geoinformation/Bezirksgrenzen.zip)
- [Gemeindegrenzen](http://data.steiermark.at/cms/beitrag/11822084/97108894/?AppInt_OGD_ID=4): [Shapefile](http://service.stmk.gv.at/ogd/OGD_Data_ABT07/geoinformation/Gemeindegrenzen.zip)

### von OpenStreetMap
Die Daten aus der [OpenStreetMap](http://wiki.openstreetmap.org/wiki/Map_Features) werden mittels [QGIS](http://qgis.org) runtergeladen und gespeichert.

Hintergrund Orthophoto importieren zur optischen Kontrolle

graz.osm

BILD

OpenStreetMap Daten aus XML in Spatialite Datenbank speichern.

osm-graz-all.db

mit lizenz text verpacken und upload (github dateigrößen limit 100mb)
[Download](http://courses.openscienceasap.org/vu-einfuehrung-geo-netzwerkanalyse/data/osm-wien-graz.tar.gz)

[Map Features](http://wiki.openstreetmap.org/wiki/Map_Features)

Attribut-Import bei Polylinien:
- [highway](http://wiki.openstreetmap.org/wiki/Key:highway)
- [cycleway](http://wiki.openstreetmap.org/wiki/Key:cycleway)
- noch weitere?

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



## Daten aufbereiten

### OGD Steiermark Zeichen Encoding auf UTF8 konvertieren

Leider sind die Daten vom Land nicht in dem UTF8 Zeichensatz codiert, sondern im Latin1, was zu Problemen mit ?, ö, ä, und weiteren Sonderzeichen führt. Daher unter "Eigenschaften" -> "Allgemein" im Punkt Datenquellenkodierung den verwendeten Zeichensatz auf "Latin1" setzen.


Welche Files sind davon betroffen?

=> file encoding von rohdaten auf latin1 stellen, dann als utf8 exportieren und laden (screeny).

Daten im besten Datenformat in QGIS rein laden. In selbem Dateiformat als UTF8 speichern und als Layer laden lassen. Den Layer dann direkt in postgresql importieren.
Steiermark: shape -> shape -> postgresql


BILD

**Speichern als spatialite und shapefile**
Um weiterfolgend besser arbeiten zu können, macht es Sinn die Daten lokal zu speichern, damit nicht bei jedesmal beim Zoomen die neuen Daten beim Server abgefragt werden müssen. 

```
Datenquelle: CC-BY-3.0: Land Steiermark - data.steiermark.gv.at
License: CC BY 3.0 AT http://creativecommons.org/licenses/by/3.0/at/deed.de

## Daten in postgresql importieren

**Datebank vorbereiten**

Folgende Tools stehen zur Auswahl:
- [shp2pgsql](http://www.bostongis.com/pgsql2shp_shp2pgsql_quickguide_20.bqg): this is the postgresql shapefile loader
- [ogr2ogr](http://www.gdal.org/ogr2ogr.html): this is a vector data conversion utility
- [osm2pgsql](http://wiki.openstreetmap.org/wiki/Osm2pgsql): this is a tool for loading OSM data into postgresql

Layer müssen geladen sein: aufpassen auf encoding.
via db manager in postgresql importieren (screeny) => einteilig wenns geht, index erstellen, srid target 4326
keine minus zeichen zum trennen sondern underbar, sonst postgresql fehler.


### Routingfähiges Netzwerk in pgRouting erstellen
**Erstellen eines Netzwerkgraphen (network graph), wo alle Kanten sämtlicher Netzwerke drinnen sind**
- Auszeichnen der Typen via Attribut
- Überschneidungen von Linien stelleb nicht automatisch Knoten dar, z.B. bei Brücken
- Wie bekomme ich haltestellen rein, so dass nicht jeder knoten für transfer möglich ist (ubahn, oev)

**Konnektivität herstellen**
- Multimodales Netzwerk - Verbindung mit mehreren Verkehrsmodi (ÖV, zu Fuß, Rad, Auto)
- Knoten stellen dem entsprechend dar: Fahrradständer, Abstellplätze, Füßgängerübergänge, Ausweichen für Busse, Kartenverkaufsstellen
- Stützpunkte - Anbindung von Kanten an lagegleichen Stützpunkten, z.B. Kreuzungen
- Endpunkte:  Kanten können nur an Endpunkten an das Netz angebunden werden; z.B. zur Definition von Unter- oder Überführungen (Brücken, Tunnel); „kreuzungsfrei“
- in Multimodalen Netzwerken können Hierachien eingebaut werden, welche bei der Analyse berücksichtigt werden können. Hierarchien haben massiven Einfluss auf das Ergebnis, z.B. die bevorzugte Wahl von Autobahn oder Gemeindestraßen.

**Kosten je nach Kategorie**
Kosten wirken sich wie Impedanzen auf die zurückzulegende Distanz und die dafür benötigte Zeit aus. Zu den Kosten gehören beispielsweise Gehzeit, Treibstoffverbrauch, Entfernung, Bedarf (wie viele Personen steigen an einer Haltestelle durchschnitt-lichein, Schneemenge, die geräumt werden muss).


**Impedanzen**
Impedanzen sind Einschränkungen, beispielsweise Geschwindigkeitsbeschränkungen, Einbahnen, Verbote (Fahrverbot, Gehverbot, Abbiegeverbot, Fahrverbot zu gewissen Uhrzeiten), Höheneinschr"ankungen, Gefahrengüter oder Baustellen. Sie werden über Verkehrstafeln vermittelt.
Wert ist von der Kantenlänge abhängig (Aufteilung!)

**Dekriptoren**
Deskriptoren sind jene Felder, die weitere Information über die jeweilige Kante bereitstellen. Im Verkehr sind das beispielsweise Geschwindikeiten, Anzahl der Fahrspuren, Beschaffenheit der Straße,...Sie gelten für die gesamte Kantenlänge.


## Häufige Fehler









