# Netzwerkanalyse




## Einleitung

Hier wird nun beschrieben, was mit den entsprechend aufbereiteten Daten innerhalb einer Vektor-Netzwerkanalyse gemacht werden kann.
Die hier vorgestellten Methoden behandeln einige Analysen im Bereich des Routing auf Basis von Verkehrsnetzen.
Dazu werden einige Analysen mit gängigen Tools von QGIS und GRASS mit jeweiligen Erweiterung durchgeführt und es wird auf weiterführende Literatur verwiesen.
Infos zur Vorbereitung der Daten sind im File [zur Datenerstellung und -Aufbereitung](02_Daten-erstelle-und-aufbereiten.md) zu finden.

Weitere Materialien und Informationen erfährt ihr auf der [Übersichts-Seite](http://openscienceasap.org/education/courses/vu-einfuehrung-geo-netzwerkanalyse/)

## Daten modellieren und analysieren

## Daten präsentieren

## Vorbereitung
 ausführen

- WMS und OpenStreetMap als Hintergrundlayer importieren => da habe ich schon mal was dazu gemacht!

## Methoden der Netzwerkanalyse
Mit Methoden der Netzwerkanalyse können verschiedene Fragestellungen behandelt werden.
Hier sollen nun die XX bekanntesten Analysewerkzeuge vorgestellt werden.
Dazu gehören:

* [Shortest Path](#ShortestPath)
* [Closest Facility](#ClosestFacility)
* [Service Area](#ServiceArea)

Diese Methoden können mit verschiedenen FOSS-GIS Programmen durchgeführt werden.
Dazu gehören:

* [QGis](#QGis)
* [Grass](#Grass)
* [PGRouting](#PGRouting)

## Shortest Path
Im den kürzesten Pfad zwischen zwei Punkten (Nodes, Knoten) zu berechnen, gibt es verschiedene Tools.

**QGIS: Straßengraph-Plugin**

QGIS 2 bietet dabei das [Straßengraph-Plugin](http://qgis.org/de/docs/user_manual/plugins/plugins_road_graph.html) (engl. Road-Graph Plugin) on the fly. Bei älteren Versionen muss es über die Python-Erweiterungen dazu installiert werden.

![Picture Road Graph](http://example.com/myimage.jpg

Für die Durchführung der Analyse muss zuerst die Einstellung angepasst werden. Unter Vektor - Straßengraph-Plugin können gewisse Einstellungen - z.B. Impendanzen wie Geschwindigkeit und Richtungseinschränkung - mit Voreinstellungen (alle Einstellungen gelten für den gesamten Layer) und mit vordefinierten Feldern (Feld/Spalte im Layer für Geschwindigkeit und Richtung) bearbeitet werden. 
Sollten sich ... nicht berechnen lassen und das Plugin die Meldung zurückgibt, dass der Pfad nicht gefunden werden konnte, kann das einerseits daran liegen, dass es keinen Pfad gibt oder andererseits auch daran, dass die Kanten nicht richtig verbunden sind. Hier kann die Veränderung der Topologietoleranz (im Einstellungsfenster) helfen, d.h. wenn es im Netzwerk-Lücken gibt (z.B. nicht verbundene Kanten), können mit der Toleranz diese Lücken ausgeglichen werden. Es sollte beachtet werden, dass die Toleranz nicht zu großzügig angegeben wird, da es sonst zu fehlerhaften Auswertung kommen kann, beispielsweise durch die Schaffung einer Verbindung, wo sich keine befindet. Eine genauere Anleitung mit Screenshot und eine Info zur  Fehlerbehebung bietet die [QGIS-Dokumentation](http://www.qgis.org/en/docs/training_manual/vector_analysis/network_analysis.html) Abhilfe.


If, on clicking Calculate, you see an error stating that a path could not be found, make sure that the roads you digitized actually meet each other. If they’re not quite touching, either fix them by modifying the features, or set the Topology tolerance in the plugin’s settings. If they’re passing over each other without intersecting, use the Split features tool to “split” roads at their intersections:
ActionSplitFeatures

Remember that the Split features tool only works in edit mode on selected features, though!
***

Die Durchführung der Analyse verlangt nur einen Start- und Endpunkt, sowie die Auswahl ob nach Länge oder Zeit gerechnet werden soll.
Die Auswahl der Zeit erfordert die Einstellung einer Geschwindigkeitsangabe, die im Menü global für alle Straßen gilt oder aus einem Spalte in der Tabelle ausgelesen werden kann (sofern der Layer über so eine Spalte verfügt).
Nach dem die Einstellung gesetzt wurden, kann die Route berechnet werden.

**GRASS: v.net.path**

Verweis auf die Schritte zur Vorbereitung des Netzwerkes

Grass-Befehl
Grafik

**GRASS: d.path**



Verweis auf die Schritte zur Vorbereitung des Netzwerkes

Grass-Befehl
Grafik


**PG-Routing**

http://anitagraser.com/2011/02/07/a-beginners-guide-to-pgrouting/

Verweis auf Datenbank Vorbereitung

Analyse-Tool Erklären

SQL Befehl

SQL Befehl erklären

## Einzugsbereich (Service Area)
Der *Einzugsbereich* (auch Service Area) ist eine Zone um einen Knoten, der auf Basis von Kosten und Impedanzen berechnet wird. Alle Punkte innerhalb dieser Zone können den zentralen Knoten in dem gegebenen Zeitintervall erreichen. Es können über mehrere Zeitintervalle mehrere Zonen gezogen werden. Die Visualisierung von Einzugsbereichs zeigt beispielsweise, welche Gebiete einer Stadt gut erreichbar sind und welche nicht. Dazu gehören Erreichbarkeiten und Reichweiten.

Nach Vorlage aus Tutrial [Creating Catchment Areas with pgRouting and QGIS](http://anitagraser.com/2011/02/09/creating-catchment-areas-with-pgrouting-and-qgis/) von Anita Graser. [Für mehrere Targets](http://anitagraser.com/2011/02/12/drive-time-isochrones/)
[Begrenzte Distanz](http://anitagraser.com/2011/05/13/catchment-areas-with-pgrouting-driving_distance/)
[Erzeugen einer Rasterdatei](http://anitagraser.com/2011/07/24/infrastructure-coverage-based-on-open-data/)

das ganze mit beliebigen POIs machen: Apotheken, etc... => Heatmap, Isochronen oder Klassifikationen der Punkte erstellen.

BILD
Service Area


**GRASS: v.net.iso**
http://www.ing.unitn.it/~grass/docs/tutorial_64_en/htdocs/esercitazione/network_analysis/node5.html

**PG-Routing**


## Location - Allocation


## Closest Facility
*Closet Facility* ist eine Analyse, die von einem gegebenen Startpunkt den nächsten von mehreren gegebenen Endpunkten sucht. Als Startpunkt kann z.B. ein Unfallort dienen, die Endpunkte sind Krankenhäuser, gesucht wird das nächste Krankenhaus.
Bei der Analyse können Impedanzen festgelegt und die besten Routen, Fahrkosten und Wegbeschreibungen mit z.B. Shortest Path ermittelt werden.

**GRASS: v.net.distance**
v.net distance sucht für mehrere Punkte nächsten Einrichtungen

**GRASS: v.net.alloc**
http://www.ing.unitn.it/~grass/docs/tutorial_64_en/htdocs/esercitazione/network_analysis/node6.html

**PG-Routing**



## Vehicle Routing Problem
https://en.wikipedia.org/wiki/Vehicle_routing_problem

other Tools
https://github.com/mck-/Open-VRP
https://github.com/jsprit/jsprit
http://www.optaplanner.org/


## Häufige Fehler





