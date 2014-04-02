VU Einführung in die Netzwerkanalyse
==============================
 
Die Lehrveranstaltung bietet eine Einführung in die Netzwerk Analyse, ins besondere von räumlichen Netzwerken.

Das Repository beinhaltet unsere Projektaufgabe: Erstellen eines Skriptums zur Einführung in die räumliche Netzwerkanalyse mit freier und offener Software. 

Das Skriptum wird gemeinsam von David Steinwender und [Stefan Kasberger](http://twitter.com/stefankasberger) erstellt.

**Das Repository ist noch stark im Aufbau und es fehlen noch einige zentrale Teile der Dokumentation!**

Sprache: Deutsch
- Dokumentation: [CC BY AT 3.0](https://creativecommons.org/licenses/by/3.0/at/)
- Code: [MIT License](http://opensource.org/licenses/MIT)

[VU Einführung in die Netzwerkanalyse](http://openscienceasap.org/education/courses/vu-einfuehrung-geo-netzwerkanalyse/) 

**Verwendete Software**
- [Ubuntu](http://www.ubuntu.com/) Linux 13.10 als Betriebssystem
- [Quantum GIS (QGIS)](http://qgis.org), v2.0.1 ([doc](http://qgis.org/de/docs/index.html)) als Desktop Geoinformationssystem.
- [GRASS GIS](http://grass.osgeo.org/) v6.4.3 ([doc](http://grass.osgeo.org/documentation/)) als Dekstop Geoinformationssystem.
- [R](http://www.r-project.org/) v3.0.2 als statistische Programmiersprache für statistische Berechnungen.
- [Python](http://www.python.org/) v2.7.5+ ([doc](http://www.python.org/doc/)) als Programmiersprache zur Datenmanipulation.
- [PostgreSQL](http://www.postgresql.org/) v9.3.2 ([doc](http://www.postgresql.org/docs/9.3/static/index.html)) als relationale Datenbank.
- [PostGIS](http://postgis.org/) v2.1.1 ([doc](http://postgis.net/docs/manual-2.1/)) als räumliche Erweiterung für PostgreSQL.
- [pgRouting](http://pgrouting.org/) v2.0.0 ([doc](http://pgrouting.org/documentation.html)) als Routing-Erweiterung für PostgreSQL.
- [Graphviz](http://www.graphviz.org/) v2.26.3 ([doc](http://www.graphviz.org/Documentation.php)) zum Zeichnen von Graphen.
- [Git]() und [GitHub]() zur Versionierung der Daten, der Dokumentation und des Quellcodes

**Verwendete Datensets**

Am besten via Shell Script runterladen:
```
sh code/shell/fetch-data.sh
```

## Aufbau Skriptum

**README.md:** Startpunkt für das Repo mit Informationen zu Aufbau, Inhalt, verwendeter Software und Daten und Urheberrecht.

**01_Grundlagen.md**
- Graphentheorie: Einführung in die Graphentheorie, dem mathematisch, statistischen Unterbau der Netzwerkanalyse
- Anwendungsfall Verkehr & Transport
- Openness: Verwendete Software, Daten, Dateiformate und Urheberrechts-Lizenzen
- Probleme lösen: Was mache ich, wenn ich nicht mehr weiter komme oder einen Fehler gefunden habe?

**02_Preprocessing.md**
- Erstellen eines eigenen Graphen
- Importieren und aufbereiten von Daten aus OpenStreetMap
- Importieren und aufbereiten von Daten aus dem OGD Portal der Stadt Wien

**03_Netzwerkanalyse**
- Erklärung von Tools zur Netzwerkanalyse
- Durchführen der Shortest Path, Closest Facility und Service Area Netzwerkanalyse

**04_Quellen:** Auflistung weiterer Quellen zu dem Themenfeld.

**05_Lehrveranstaltung:** Spezielle Informationen zur Lehrveranstaltung "Einführung in die geographische Netzwerkanalyse bei Susanne Janschitz.

**06_FAQ.md:** Frequently Asked Questions Liste


**ToDo.md:** Task List

**DEVELOP.md:** Nötige Informationen für Beitragende zum Repository. 

## ToDo
- Aufbau zu preprocessing und netzwerkanalyse kontrollieren


