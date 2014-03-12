# TODO
- Shortest Path, Communities und Centralities recherchieren
- Zitationen einfügen
- Bilder erstellen und einbinden => David
- lektorat => David
- benötigte QGIS plugins checken

# Grundlagen

Im folgenden Dokument gibt es grundlegende, einführende Informationen zu 1) Graphentheorie und deren Anwendungsmöglichkeiten in der Mobilitätsforschung, 2) den Prinzipien von offener Wissenschaft mit Open Source Software, Open Data Repositories für die Daten und offene Datenformate für den Austausch räumlicher Inforamtionen und Graphen und 3) Lösungsansätze bei Problemen und Fragen.

Weitere Materialien und Informationen erfährt ihr auf der [Übersichts-Seite](http://openscienceasap.org/education/courses/vu-einfuehrung-geo-netzwerkanalyse/).

## Graphentheorie

Die theoretische Grundlage für Netzwerke ist die Graphentheorie und beschäftigt sich mit der Erforschung von Netzwerk-Strukturen \cite[S. 23]{easley_networks_2010}. Nach Definition spezifiziert ein Graph Beziehungen zwischen verschiedenen Elementen. Er besteht aus einer Sammlung von Objekten, Knoten genannt, mit bestimmten Paaren dieser Objekte verbunden durch Links, genannt Kanten. \citep{easley_networks_2010} Wegen diesem flexiblen Formalismus ist es einfach Netzwerke in den verschiedensten Domainen in der echten Welt zu finden, wie Sozialwissenschaften, Mikro-Biology, Psychology oder Elektrotechnik.

Die verwendeten Begriffe für diese beiden Elemente sind meist je nach Disziplin unterschiedlich \citep{latapy_basic_2008}:
- Mathematik: Vertizes und Kanten
- Physik: Sites und Bonds
- Soziologie: Akteure und Verbindungen
- Computer Sciences: Knoten und Links

BILD
grundkonzept graph

Die Netzwerktheorie beschäftigt sich mit großen Netzwerken, die mit dem Aufkommen von Informations- und Kommunikationstechnologien (ICT) immer mehr an Relevanz bekommen. Der mathematische Unterbau dazu ist die Graphentheorie. !ZITAT!

BILD
großer Graph

### Arten von Graphen
Es gibt verschiedene Unterscheidungsmerkmale für Graphen/Netzwerke, abhängig von deren Struktur und Eigennschaften.

**Directed/Undirected**
Kanten können eine Richtung haben (directed) oder auch keine (undirected), wodurch die Beziehung in beide Richtungen gleich ist, also symmetrisch. Typische ungerichtete Netzwerke sind Links auf Websites. Freundschaften sind zumeist symmetrisch. Um die Richtung zu signalisieren, sind gerichtete Kanten durch einen Pfeil dargestellt.

BILD 
Gerichteter Graph

**Gewichtet/Ungewichtet**
Die Kanten können auch eine Gewichtung haben, also das Verhältnis kann quantitativ bemessen werden. Wie oft haben sich zwei Menschen getroffen oder wie groß ist die Bandbreite einer Datenverbindung. Um so höher die Zahl, desto höher ist die Gewichtung des Verhältnisses.

BILD

**Multimodale Graphen**
Es können zwischen einem Paar von Knoten auch mehrere verschiedene Kanten bestehen. Ein Netzwerk mit diesen Eigenschaften wird multimodal genannt und ist ins besondere in der Mobilitätsforschung weit verbreitet.

BILD
multimodaler graph

**Bipartite**
Eher wenig Bedeutung in der Geographie.

Bipartite Graphen sind eine spezielle Klasse von Netzwerken, bei denen die Kanten in zwei Mengen, X und Y, unterteilt sind und wo nur Verbindungen zwischen zwei Knoten aus verschiedenen Sets bestehen \citep{easley_networks_2010}. Die Kanten können gerichtet/ungerichtet oder gewichtet/ungewichtet sein.

BILD
konzept bipartite

Bipartite Netzwerke haben in der Mobilitätsforschung kaum Verwendung.

**3D**

### Shortest Path

Shortest Path bezeichnet Algorithmen, die die kürzeste Verbindung zwischen zwei Knoten sucht und somit die zentrale Aufgabe zum Lösen eines Routing-Problems ist. Es gibt verschieden Arten (Algorithmen) solche Shortest Path Probleme zu lösen. Ein sehr weit verbreiteter ist der Dijkstra Algorithmus ([Video](https://www.youtube.com/watch?v=Q5ebFH8Yho4)). Weitere sind [A*](), [A*]() und [A*]().

?? können alle mit impedanzen, also mit gewichtungen arbeiten ??

### Centralities
#### Degree

#### Betweeness


#### Closeness


### Community Detection

Communities sind Gruppen von Knoten, die möglicherweise gemeinsame Eigenschaften besitzen und/oder ähnliche Rollen innerhalb des Graphens inne haben \citep{fortunato_community_2014}.

Eine verbundene Komponente eines Graphen ist eine Untermenge der Knoten, wo es 1) von jedem Knoten einen Pfad zu jedem anderen Knoten gibt; und 2) die Untermenge nicht teil einer größeren Sammlung mit der Eigenschaft, dass jeder Knoten jeden anderen erreichen kann, ist \citep[S. 29]{easley_networks_2010}. Große, komplexe Netzwerke haben oft einen sogenannten Giant Component, ein beabsichtigt formaler Begriff für eine verbundene Komponente, die einen signifikanten Anteil aller Knoten enthält \citep[S. 31]{easley_networks_2010}.

## Anwendungen 


### Verkehr
Evaluatoren: werden verwendet, um Attribute der Quelldaten den Netzwerkelementen zuzuweisen (z.B. verschiedene Angaben zu Kreuzungen (Wartezeit) werden aus einem jeweiligen Shape hinzugefügt; ebenso falls es unterschiedliche Einschränkungen gibt; auch Fahrzeit)

Euler Problem

Transport: Konnektivität, Kosten, Hierarchien, Turns, Schnellste vs kürzeste Route, Impedanzen: Einbahnen, Abbiegeverbote, Höhenbeschränkungen, Gewichtsbeschränkungen, Gefahrengüter, Nachtfahrverbote, Baustellen
Kosten
Impedanzen
Konnektivität
Turns
alles nötige aus Skriptum

Dykstra Algorithmus, Kosten/Impendanz: Distanz (Weg), Zeit; Origin Destination (In ArcGis eine Möglichkeit, Daten nur in Tabellarform oder als Kartogramm wiederzugeben)

### Weitere

=> Verweis, Grundlegendes (Wikipedia)

Beispiele nennen, Bilder zeigen, Grundsätzliches Verständnis, kurze Beschreibung

Co-Citation, Biblometric Coupling, 

BILD

https://de.wikipedia.org/wiki/Soziale_Netzwerkanalyse
Internet

BILD

Elektrizitätsnetz

Wasserversorgung

BILD

Krankheiten

BILD

Neuronale Netze

BILD

## Offenheit

Das gesamte Repository ist nach den Prinzipien von [Open Science](http://openscienceasap.org/open-science/) erstellt.

BILD
Open Science

Somit sind alle Inhalte, sofern nicht anders angegeben, nach den Vorgaben der [Open Definition](http://opendefinition.org/) lizenziert. Texte und Bilder sind unter der [Creative Commons BY](https://creativecommons.org/licenses/by/3.0/at/) lizenziert. 

BILD
Creative Commons

### Open Source Software

Es wurde nur [Open Source Software](https://de.wikipedia.org/wiki/Open_Source) verwendet und der selbst erstellte Quellcode ist unter der [MIT Lizenz](http://opensource.org/licenses/MIT) freigegeben. 

Folgend nähere Infos zur Software.

#### QGIS
[QGIS](http://www.qgis.org/) ist ein benutzerfreundliches Geoinformationssystem zum Betrachten, Bearbeiten und Erfassen von räumlichen Daten und ist GNU General Public License lizenziert. Wesentliche Merkmale der Applikation sind die breite Unterstützung gängiger Vektordaten und Rasterdaten wie Shapefile oder GeoTIFF, aber auch räumlicher Datenbanken wie PostGIS und SpatiaLite, ausgereifte Digitalisier-Werkzeuge zum Erfassen von Vektordaten sowie eine Druckzusammenstellung zum einfachen Erstellen von Kartenausdrucken.

Die QGIS-Architektur baut stark auf Erweiterungen auf, nennenswert sind die fTools-Werkzeuge für allgemeine vektorbasierte Aufgaben oder die GRASS-Erweiterung für anspruchsvolle räumliche Analysen. Eine GPS-Erweiterung erlaubt es, GPX-Dateien zu lesen oder direkt auf ein GPS-Gerät zuzugreifen. Andere Erweiterungen erlauben das Einbinden von WMS- und WFS-Diensten.
ZITAT http://de.wikipedia.org/wiki/QGIS

BILD
Qgis screenshot
http://commons.wikimedia.org/wiki/File:QGIS_2.2_Valmiera_showing_new_menu_design.png

**Benötigte Plugins**
- [DB Manager]()
- fTools
- GRASS

**Starten mit QGIS**
Informationen zum Runterladen und Installieren findet man auf [qgis.org](http://qgis.org/). 

Erste Schritte mit QGIS werden einem auf qgis.org unter Documentation näher gebracht. Besonders zu empfehlen sind die beiden Screencast Serien [Tutorial von MrHiddin1](http://www.youtube.com/playlist?list=PLedvCUusOD_nxprzIwuDSA5oH61vUCP_w) und [Tutorial von jarretttotton](http://www.youtube.com/playlist?list=PLedvCUusOD_khPbVeSouD3jYcAv-0GUkU) zu Beginn, welche einen schnellen und umfassenden Überblick in QGIS geben.

#### GRASS GIS

[GRASS GIS](http://grass.osgeo.org/) ist eine hybride, modular aufgebaute Geoinformationssystem-Software mit raster- und vektororientierten Funktionen. GRASS steht für Geographic Resources Analysis Support System, GIS für Geographical Information System.

Es steht unter der GNU General Public License und ist damit eine frei verfügbare Software. Das System bietet Raster- und topologische Vektordatenfunktionalität, 3D-Raster-Voxelbearbeitung, Bildverarbeitung, Visualisierungsmöglichkeiten und den Im- und Export verschiedener GIS-Datenformate. Als portable Software läuft es auf verschiedenen Betriebssystemen mit einer graphischen Benutzeroberfläche sowie optional per Kommandozeile.
ZITAT http://de.wikipedia.org/wiki/GRASS_GIS

**Starten mit GRASS GIS**

Informationen zum Runterladen und Installieren sowie Tutorials und die Dokumentation gibt es auf [grass.osgeo.org](http://grass.osgeo.org/).

Um einen Überblick zur zu Beginn doch meist gewöhnungsbedürtigen Oberfläche und Datenverwaltung zu bekommen empfiehlt sich der [Workshop von Markus Neteler](http://geostat-course.org/Topic_NetelerMetz_2011)([Videos](https://archive.org/details/GeostatSummerSchoolGrassGisTutorial)).

#### Git und GitHub

**[Git](http://git-scm.com/)** ist eine freie Software zur verteilten Versionsverwaltung von Dateien, die ursprünglich für die Quellcode-Verwaltung des Linux-Kernels entwickelt wurde. Git ist ein verteiltes Versionsverwaltungssystem, das sich in einigen Eigenschaften von traditionellen Versionskontrollsystemen unterscheidet:
- Nicht-lineare Entwicklung: Sowohl das Erstellen neuer Entwicklungszweige (branching) als auch das Verschmelzen zweier oder mehrerer Zweige (merging) sind integraler Bestandteil der Arbeit mit Git, fest in die Git-Werkzeuge eingebaut und sehr performant
- Kein zentraler Server: Jeder Benutzer besitzt eine lokale Kopie des gesamten Repositorys, inklusive der Versionsgeschichte (history). So können die meisten Aktionen lokal und ohne Netzwerkzugriff ausgeführt werden
- Datentransfer zwischen Repositories: Daten können mit einer Reihe verschiedener Netzwerkprotokolle zwischen Repositories übertragen werden.
- Kryptographische Sicherheit der Projektgeschichte: Die Geschichte eines Projektes wird so gespeichert, dass der Hash einer beliebigen Revision (commit) auf der vollständigen Geschichte basiert, die zu dieser Revision geführt hat.
- Speichersystem und Dateiversionierung: Im Gegensatz zu CVS, wo jede Datei eine eigene Revisionsnummer besitzt, speichert Git bei einem Commit das gesamte Dateisystem ab
- Säubern des Repositories: Die Daten gelöschter und zurückgenommener Aktionen und Entwicklungszweige bleiben vorhanden (und können wiederhergestellt werden), bis sie explizit gelöscht werden.
- Interoperabilität: Es gibt Hilfsprogramme, die Interoperabilität zwischen Git und anderen Versionskontrollsystemen herstellen.
- Web-Interface

BILD
logo

**[GitHub](https://github.com/)** ist ein webbasierter Hosting-Dienst für Software-Entwicklungsprojekte. Namensgebend ist das Versionsverwaltungs-System Git. 

BILD
logo

Im Gegensatz zu anderen Open-Source-Hostern wie SourceForge ist auf GitHub nicht das Projekt als Sammlung von Quellcode zentral, sondern der Nutzer mit seinen Repositories (Verzeichnissen, die von Git kontrolliert werden). Gleichzeitig wird das Erstellen und Wiedervereinigen von Abspaltungen (Forks) besonders propagiert. Forks dienen weiterhin dazu, einfach bei anderen Projekten mitentwickeln zu können. Um einem Repository/Projekt einen Beitrag beizusteuern, wird das Repository zunächst aufgespalten, dann werden die zu übernehmenden Änderungen hinzugefügt und dem Besitzer des Ur-Repositorys ein Pull-Request gestellt (alles über die Weboberfläche). Damit soll den Besonderheiten verteilter Versionskontrollsysteme besonders Rechnung getragen und zugleich ein soziales Netzwerk geschaffen werden, was sich auch in dem Slogan des Unternehmens und den aus „echten“ sozialen Netzwerken bekannten Funktionen „Beobachten“ oder „Folgen“ niederschlägt.

Während Open-Source-Projekte GitHub kostenfrei nutzen können, gibt es auch kostenpflichtige Angebote für proprietäre Software, die zum Beispiel erlauben, sogenannte Private Repositorys zu erstellen, die nicht öffentlich einsehbar sind. Kostenfreie Accounts dürfen nur öffentliche Repositorys erstellen. 
ZITAT http://de.wikipedia.org/wiki/GitHub

**Starten mit Git/GitHub**
Zu Beginn sollte man sich in die Verwendung von Git zum Versionieren einlesen und -üben. Hier empfiehlt sich das Buch [Pro Git von Scott Chacon](http://git-scm.com/book) sowie das Durchgehen der [Dokumentation](http://git-scm.com/doc).

Um Versionierung mit Git und GitHub interaktiv zu lernen, bietet sich der [Online-Workshop tryGit](http://try.github.io//levels/1/challenges/1). Am besten ist es aber wie so oft, lokal am eigenen Rechner zu üben und herum zu spielen (Backup davor nicht vergessen!).

#### spatialSQL: postgresql, postGIS, pgRouting und pgAdmin3

Zum Arbeiten mit räumlichen Daten wird eine Geodatenbank aufgesetzt. Hierzu wird postgresql als Datenbankmanagementsystem verwendet, welches mittels den Erweiterungen postGIS mit räumlichen Funktionen und und pgRouting mit Routing Funktionen für Mobilitätsforschung vorbereitet ist.

[postgreSQL](http://www.postgresql.org/) ist ein freies, objektrelationales Datenbankmanagementsystem (ORDBMS). Seine Entwicklung begann in den 1980er Jahren, seit 1997 wird die Software von einer Open-Source-Community weiterentwickelt.

PostgreSQL ist weitgehend konform mit dem SQL-Standard ANSI-SQL 2008,[4] d. h. der Großteil der Funktionen ist verfügbar und verhält sich wie definiert. PostgreSQL ist vollständig ACID-konform (inklusive der Data Definition Language), und unterstützt erweiterbare Datentypen, Operatoren, Funktionen und Aggregate[5]. Obwohl sich die Entwicklergemeinde sehr eng an den SQL-Standard hält, gibt es dennoch eine Reihe von PostgreSQL-spezifischen Funktionalitäten, wobei in der Dokumentation bei jeder Eigenschaft ein Hinweis erfolgt, ob dies dem SQL-Standard entspricht, oder ob es sich um eine spezifische Erweiterung handelt. Darüber hinaus verfügt PostgreSQL über ein umfangreiches Angebot an Erweiterungen durch Dritthersteller, wie z. B. PostGIS.
ZITAT http://de.wikipedia.org/wiki/PostgreSQL

[SQL](http://de.wikipedia.org/wiki/SQL) ist eine Datenbanksprache zur Definition von Datenstrukturen in relationalen Datenbanken sowie zum Bearbeiten (Einfügen, Verändern, Löschen) und Abfragen von darauf basierenden Datenbeständen.

Die Sprache basiert auf der relationalen Algebra, ihre Syntax ist relativ einfach aufgebaut und semantisch an die englische Umgangssprache angelehnt. Fast alle gängigen Datenbanksysteme unterstützen SQL – allerdings in unterschiedlichem Umfang und leicht voneinander abweichenden „Dialekten“. Durch den Einsatz von SQL strebt man die Unabhängigkeit der Anwendungen vom eingesetzten Datenbankmanagementsystem an.

Die Bezeichnung SQL wird im allgemeinen Sprachgebrauch als Abkürzung für „Structured Query Language“ aufgefasst, obwohl sie laut Standard ein eigenständiger Name ist. 
ZITAT http://de.wikipedia.org/wiki/SQL

[postGIS](http://postgis.org/) ist eine Erweiterung für die objektrelationale Datenbank PostgreSQL, die geografische Objekte und Funktionen umfasst. PostgreSQL mit PostGIS bildet eine Geodatenbank, die in Geoinformationssysteme eingebunden werden kann. Das Projekt implementiert die Simple Feature Access-Spezifikation des [Open Geospatial Consortium](http://de.wikipedia.org/wiki/Open_Geospatial_Consortium) und wird von der [Open Source Geospatial Foundation](http://de.wikipedia.org/wiki/Open_Source_Geospatial_Foundation) betreut.
ZITAT http://de.wikipedia.org/wiki/PostGIS

[pgRouting](http://pgrouting.org/) erweitert die PostgreSQL und postGIS um eine räumliche Routing-Funktionalität, steht unter der GPLv2 Lizenz. So können Daten durch verschiedene Clients verändert werden und sind sofort anwendbar. Kosten können dynamisch via SQL berechnet werden.
ZITAT http://pgrouting.org/

[pgAdmin](http://www.pgadmin.org/) ist eine Open-Source-Software zur Entwicklung und Administration von PostgreSQL-Datenbanken. Eine graphische Benutzeroberfläche erleichtert die Administration von Datenbanken. Der Editor für SQL-Abfragen enthält ein graphisches EXPLAIN, mit dessen Hilfe sich performantere Abfragen erstellen lassen. Durch eine native Anbindung an PostgreSQL ermöglicht das GUI den Zugriff auf die gesamte PostgreSQL-Funktionalität.
ZITAT http://de.wikipedia.org/wiki/PgAdmin

**Starten mit postgreSQL, postGIS und pgRouting**

Das Installieren von postgreSQL mitsamt den beiden Erweiterungen kann etwas komplizierter sein je nach Betriebssystem. Mit der aktuellen Ubuntu Version 13.10  sollte es aber relativ einfach und schnell gehen ([Install/Setup in Ubuntu 13.10](http://trac.osgeo.org/postgis/wiki/UsersWikiPostGIS21UbuntuPGSQL93Apt)). pgRouting muss kompiliert werden, was je nach Betriebssystem unterschiedlich funktioniert.

Um postgreSQL verwenden zu können, muss man die Abfragesprache [SQL](http://de.wikipedia.org/wiki/SQL) beherrschen. Erste Schritte können mittels [W3CSchool](http://www.w3schools.com/sql/) oder [Youtube Tutorials](http://www.youtube.com/results?search_query=learn%20sql&sm=3) erlernt werden.

Zu postGIS ist die [Dokumentations-Seite](http://postgis.net/documentation/) ein guter Startpunkt. SpatialSQL unterscheidet sich ja in der Anwendung zu normalen SQL ja nur durch neue räumliche Abfragen und dem Verwenden von geographischen Elementen.

Zu pgRouting ist die Website mit [Dokumentation](http://docs.pgrouting.org/) und [Workshop](http://workshop.pgrouting.org/) zu empfehlen, sowie [Anita Graser's Tutorials]([QGIS pgrouting tag](http://anitagraser.com/tag/pgrouting/).

#### Weitere Tools

**[Graphviz](http://www.graphviz.org/)** ist ein plattformübergreifendes Open-Source-Programmpaket zur Visualisierung von Objekten und deren Beziehungen untereinander. Mathematisch ausgedrückt visualisiert Graphviz gerichtete und ungerichtete Graphen.

Graphviz entnimmt alle zur Erzeugung der Grafik benötigten Anweisungen einer Textdatei, die eine Beschreibung der Knoten und Kanten des Graphen enthält. Die Positionen der einzelnen Knoten sowie die Krümmungen der Kanten werden aus dieser Beschreibung automatisch berechnet und dabei so optimiert, dass die Struktur des Graphen gut erkennbar ist. Zur Beschreibung des darzustellenden Graphen wird die Auszeichnungssprache DOT verwendet. Sie ist syntaktisch an die Programmiersprache C angelehnt. Graphviz bietet bei Bedarf auch zusätzliche Möglichkeiten zur Veränderung des Layouts sowie der Form und Farbgebung des Graphen.

Graphviz bietet verschiedene Verfahren zur Visualisierung von Graphen an:
- dot: Zur Darstellung hierarchischer Strukturen. Alle Kanten verlaufen dabei in etwa in dieselbe Richtung, von oben nach unten oder von links nach rechts. Überschneidungen der Kanten werden möglichst vermieden und die Kantenlänge wird so kurz wie möglich gehalten.
- neato und fdp: Visualisiert Graphen im so genannten „spring model“ Layout. Der Startknoten wird mittig angelegt. Neato benutzt dabei den Kamada-Kawai-Algorithmus. Fdp implementiert die Fruchterman-Reingold-Heuristik für größere Graphen.
- twopi: Radiales Layout, nach Graham Wills.
- circo: Circuläres Layout, nach Six and Tollis.

Als Standard erzeugt Graphviz eine Textdatei als DOT-Quelltext in der die Attribute für die Position und Größe der Knoten und Kanten mit angegeben werden. Über Graphviz kann als Ausgabe aber auch eine Bilddatei erstellt werden. Unterstützt werden unter anderem die Dateiformate Postscript, SVG, JPEG, PNG und PDF.
ZITAT http://de.wikipedia.org/wiki/Graphviz

**[Gephi](http://gephi.org/)** ist ein Open Source Netwerk Analyse Software Packet in Java. Gephi wird sowohl in der Wissenschaft, wie auch im Journalismus und anderswo verwendet.
ZITAT http://en.wikipedia.org/wiki/Gephi

Plugins:
- [GeoTools](http://geotools.org/)
- [Export 2 Shp](https://marketplace.gephi.org/plugin/export-to-shp/)
- [Spatial Ranking](https://marketplace.gephi.org/plugin/spatial-ranking/)
- [Multimode Networks Transformations](https://marketplace.gephi.org/plugin/multimode-networks-transformations-2/)
- [ExportToEarth](https://marketplace.gephi.org/plugin/exporttoearth/)
- [GeoLayout](https://marketplace.gephi.org/plugin/geolayout/)
- [Maps of Countries](https://marketplace.gephi.org/plugin/maps-of-countries/)

Die **[Geospatial Data Abstraction Library (GDAL)](http://www.gdal.org/)** ist eine freie Programmbibliothek für die Übersetzung räumlicher Rasterdaten. Als Programmbibliothek bietet es den aufrufenden Programmen ein einheitliches Datenmodell für alle unterstützten Formate. Es sind jedoch auch verschiedene Kommandozeilen-Programme enthalten, mit denen Daten direkt bearbeitet und umgewandelt werden können. Ebenfalls enthalten ist die Programmbibliothek OGR (OGR Simple Features Library)[3], welche ähnliche Funktionen für Vektordaten bietet.

Neben den gängigen Formaten für Rasterdaten, nämlich JFIF, GIF, PNG und GeoTIFF, kann GDAL noch über 60 weitere Datenformate lesen. Jedoch können nicht alle diese Formate auch geschrieben werden. OGR unterstützt über 20 Vektordatenformate, kann aber ebenfalls nicht in alle unterstützten Formate konvertieren.

ZITAT http://de.wikipedia.org/wiki/Geospatial_Data_Abstraction_Library

### Open Data Formats

Ein [Offenes Dateiformat](https://de.wikipedia.org/wiki/Offenes_Format) ist eine publizierte Spezifikation zum Speichern digitaler Daten, welche ohne rechtliche oder technische Einschränkungen genutzt werden kann. Die Entwicklung offener Formate steht üblicherweise unter der Aufsicht eines offen zugänglichen Gremiums. Offene Formate müssen sowohl von proprietärer als auch von freier Software bzw. Open-Source-Software implementierbar sein. Offene Formate, Dateiformate wie Container, sind eine Untermenge offener Standards.

Das Primärziel von Formatoffenheit ist es den ungehinderten Umgang mit Daten zu ermöglichen, ohne rechtliche (z.B. Lizenzen) oder technische (z.B. DRM) Restriktionen oder Abhängigkeiten zu kreieren. Ein häufig formuliertes Sekundärziel ist es, Wettbewerb zu ermöglichen, da die Nutzung proprietärer digitaler Formate leicht zum sog. Vendor Lock-in führen kann. Regierungen zeigen zunehmend Interesse am Einsatz offener Formate.
ZITAT https://de.wikipedia.org/wiki/Offenes_Format

#### Shapefile
[Shapefile](http://www.esri.com/library/whitepapers/pdfs/shapefile.pdf) (oft Shapedaten oder Shape genannt) ist ein ursprünglich für die Software ArcView der Firma ESRI entwickeltes Format für Geodaten. Das Shapefile ist als Quasi-Standard im Desktop-GIS-Umfeld verbreitet, da es ein recht einfaches und bezüglich der Datenqualität nur wenig anspruchsvolles Format darstellt. Dennoch ist es das Format, in dem am meisten Kartendaten zur Verfügung stehen. Die Unterstützung von freien sowie kommerziellen Programmen und Programm-Bibliotheken (z. B. GeoTools und Deegree) ist bei keinem Format so gut wie bei den Shapefiles. Viele Open-Source-Programme wandeln Daten von Shapefiles in SQL für raumbezogene Datenbanken um. 

Ein Shapefile ist keine einzelne Datei, es besteht aus mindestens drei Dateien:
- .shp dient zur Speicherung der Geometriedaten
- .dbf Sachdaten im dBASE-Format
- .shx dient als Index der Geometrie zur Verknüpfung der Sachdaten (auch Attributdaten genannt)

Optionale Dateien:
- .atx Attributindex
- .sbx und .sbn Index für Tabellenverbindungen (Joins)
- .aih und .ain Index für Tabellenverknüpfungen (Links)
- .shp.xml Metadaten zum Shapefile
- .prj Projektion der Daten
- .cpg um den in der .dbf verwendeten Zeichensatz zu spezifizieren. [1]

In einem Shapefile können jeweils nur Elemente eines Typs enthalten sein, z. B.:
- Punkte,
- Linien,
- Flächen (Polygone)
- oder Multi-Punkte

Zusätzlich zu dem jeweiligen Typ darf das Shapefile immer auch sogenannte Null Shapes enthalten. Diese haben keine Geometrie, aber wie jeder andere Typ einen Datensatz in der zugehörigen DBF Datei. Weiterhin kann unterschieden werden zwischen 2D-Geometrien und 3D-Geometrien.

**Formatbeschränkungen**
Die Größe der Shp- und DBF-Dateien darf 2 Gigabyte (oder 2^31 Bit) nicht überschreiten.[2]

Das Attribut-Datenbankformat für die DBF-Komponentendatei beruht einem früheren dBase-Standard. Damit einher gehen folgende Einschränkungen:
- Während das aktuelle dBase-Format wie auch GDAL / OGR (als Open-Source-Software-Bibliothek zum Lesen und Schreiben von Shapefiles) leere Felder als Null-Werte von der Ziffer 0 unterscheidet, nimmt ESRI Software diese Unterscheidung nicht vor.
- eingeschränkte Unterstützung für Unicode-Feldnamen
- Maximale Länge der Feldnamen: 10 Zeichen
- Maximale Anzahl der Felder: 255
- Zulässige Feldtypen sind Floating Point (13 Zeichen), Ganzzahl / Integer, Datum ohne Zeitspeicherung (8 Zeichen) und Text (254 Zeichen)
- Fließkommazahlen können Rundungsfehler enthalten, da sie als Text gespeichert werden
ZITAT https://de.wikipedia.org/wiki/Shapefile

#### SQLite

[SQLite](https://www.sqlite.org/) ist eine Programmbibliothek, die ein relationales Datenbanksystem enthält. SQLite unterstützt einen Großteil der im SQL-92-Standard festgelegten SQL-Sprachbefehle. Unter anderem implementiert SQLite Transaktionen, Unterabfragen (subselects), Sichten (views), Trigger und benutzerdefinierte Funktionen. Public Domain
ZITAT https://de.wikipedia.org/wiki/SQLite

#### SpatiaLite

[SpatiaLite](https://www.gaia-gis.it/fossil/libspatialite/index) ist ein freies, OpenGIS kompatibles geografisches Informationssystem welches die Datei-basierte Datenbank SQLite um geografische Objekte und Funktionen erweitert.
ZITAT https://de.wikipedia.org/wiki/SpatiaLite

[A quick tutorial to SpatiaLite - a Spatial extension for SQLite](http://www.gaia-gis.it/gaia-sins/spatialite-tutorial-2.3.1.html)

[Part 1: Getting Started with SpatiaLite: An almost Idiot's Guide](http://www.bostongis.com/PrinterFriendly.aspx?content_name=spatialite_tut01)

#### GeoJSON
[GeoJSON](http://geojson.org/) ist ein offenes Format zum Encodieren einer Vielzahl von geographischen Datenstrukturen. Der Name stammt von [JSON](http://www.json.org/) (JavaScript Object Notation). Daher ist ein jedes GeoJSON Object auch ein JSON Object, wodurch JSON Tools für das Verarbeiten von GeoJSON Daten verwendet werden können. GeoJSON erlaubt es geographische Daten in einer von Mensch lesbaren Sprache zu speichern die kompakter ist als XML. Räumliche Datenformat-Typen die GeoJSON unterstützt sind mitunter point, polygon, multipolygons, features, geometry collections und bounding boxes, welche zusammen mit charakteristischen Informationen und Attributen gespeichert werden. Die Geometrien und deren Verhältnisse besitzen Eltern-Objekte, wie z.B. feature collections. GeoJSON erlaubt auch das spezifizieren von geographischen Koordinatensystemen mittels OGC CRS (coordinate reference system) oder mit EPSG Code. Wenn kein CRS definiert wird, verwendet GeoJSON den WGS84 Geoid.
REF: übersetzt aus [Spezifikation](http://geojson.org/geojson-spec.html)

http://wiki.alpine-geckos.at/wiki/GeoJSON

#### GeoTIFF
Ein [GeoTIFF](http://de.wikipedia.org/wiki/GeoTIFF) ist eine spezielle Form eines [TIFF-Bildes](http://de.wikipedia.org/wiki/Tagged_Image_File_Format), also ein Dateiformat zur Speicherung von Bilddaten (Dateinamenserweiterung .geotiff, oft auch nur .tif). Da das TIF-Format eine verlustfreie Speicherung zulässt, eignet es sich gut zur Verarbeitung von geographischen Daten, da es bei Satelliten- und Luftbildern bzw. anderen Rasterdaten oft auf hohe Abbildungsgenauigkeit ankommt.

Die Besonderheit von GeoTIFF gegenüber dem normalen TIF-Format liegt darin, dass spezielle Daten über die Georeferenz zusätzlich zu den sichtbaren Rasterdaten in die Bilddatei eingebettet werden. Dazu zählen Koordinaten zur Georeferenzierung des Bildausschnitts sowie zur verwendeten Kartenprojektion: Die Datei enthält spezifische Angaben über das Koordinatenreferenzsystem.

Die Informationen werden im Gegensatz zum GeoJPEG oder normalem TIF-Format nicht in einer separaten Datei (world file), sondern direkt in den Metatags des Bildes gespeichert, wobei sechs Tags für die Geoinformationen genutzt werden. Bei Bedarf sind diese Tags um weitere Felder erweiterbar.

GeoTIFF-Dateien können mit allen Algorithmen komprimiert werden, die für das TIF-Format möglich sind, neben diversen verlustfreien Verfahren also auch mit einer verlustbehafteten JPEG-Komprimierung, mit der sich ggf. auf Kosten der Bildqualität eine deutliche Reduktion der Dateigröße erreichen lässt. Allerdings unterstützt nicht jede Applikation alle vom TIF-Format erlaubten Kompressionsalgorithmen.

Die Initiative zur Schaffung des GeoTIFF-Formats geht auf das Unternehmen Intergraph zurück. Seit den frühen 1990er Jahren beschäftigte man sich mit diesem Thema und konnte eine Vielzahl von Unternehmen und Vertretern von Regierungsorganisationen als Unterstützer gewinnen. Zu ihnen zählen namhafte Unternehmen und Institutionen des GIS-Sektors wie ESRI, ERDAS und die USGS. GeoTIFF hat sich als Quasi-Standard zur Darstellung von Rasterdaten entwickelt und wird von den meisten Rasterdaten verarbeitenden GIS-Programmen sowie einigen Bildbearbeitungsprogrammen (u.a. Adobe Photoshop) unterstützt. Die Bildinformationen sind in jedem Programm darstellbar, welches den normalen TIFF-Standard unterstützt.
ZITAT http://de.wikipedia.org/wiki/GeoTIFF

**TIFF** ist, neben PDF und EPS, ein wichtiges Format zum Austausch von Daten in der Druckvorstufe in Verlagen und Druckereien, weil es das von ihnen verwendete CMYK-Farbmodell unterstützt. Außerdem kann man TIFF-Bilder mit hoher Farbtiefe (bis zu 32 Bit pro Farbkomponente) speichern, weshalb TIFF gern zum Datenaustausch bei der RAW-Konvertierung verwendet wird.

Im Internet wird TIFF genutzt, um Anwendern, wie etwa Verlagen, hochaufgelöste Bilder in druckfähiger, verlustfreier Qualität zur Verfügung zu stellen. Dabei wird in Kauf genommen, dass diese Dateien ein Mehrfaches der Größe eines verlustbehaftet komprimierten JPEG-Bildes haben. TIFF hat sich so als Quasi-Standard für Bilder mit hoher Qualität etabliert.

Für den Bereich der rasterbasierten Geoinformationen etabliert sich mehr und mehr eine mit zusätzlichen Tags versehene TIFF-Variante, das sogenannte GeoTIFF. Es erlaubt, etwa bei Kartenbildern, Luftbildern und ähnlichen Informationen, anzugeben, wo auf der Erde die im Bild dargestellte Situation exakt koordinatenbezogen liegt.

TIFF wird auch zum Archivieren von monochromen Grafiken (z. B. technischen Zeichnungen) verwendet, da in Verbindung mit der „Fax Group 4“-Komprimierung sehr kompakte Dateien entstehen.

Um den Printmedien ihre Arbeit zu erleichtern, werden von manchen Organisationen, zum Beispiel ESA oder NASA, hochaufgelöste Bilder neben dem JPEG-Format stellenweise auch in TIFF angeboten, während bei niedrigen Auflösungen normalerweise nur das verlustbehaftete JPEG-Format zum Einsatz kommt.

Die Kodierung von Zahlen (Byte-Reihenfolge) kann entweder als Big Endian oder Little Endian erfolgen. In einer Datei können mehrere Bilder abgelegt werden (Multipage-TIFF). Das können z. B. verschiedene Versionen desselben Bildes sein, wie Vorschaubild („Thumbnail“) und Originalbild. TIFF kennt verschiedene Farbräume und Algorithmen zur Datenkompression. Die meisten von ihnen sind verlustfrei (z. B. LZW, Lauflängenkodierung), allerdings kann TIFF auch als Containerformat für JPEG-Bilder dienen, welche verlustbehaftet (DCT) komprimiert sein dürfen. Es ist auch möglich, IPTC-Metadaten in die TIFF-Datei einzubetten.

Einzelne Bildpunkte können bei TIFF aus beliebig vielen Einzelwerten (Samples) bestehen. Samples können neben dem Standardfall „ein Byte gleich ein Sample“ auch Teile eines Bytes einnehmen (z. B. 1, 2 oder 4 Bits) oder aus mehreren Bytes bestehen. Neben Ganzzahlen können auch Gleitkommazahlen als Bilddaten abgelegt werden. Die Möglichkeit zur Speicherung von Transparenz-Information (Alphakanal) existiert ebenfalls.

Bilddaten werden in Gruppen von Pixelzeilen, sogenannten Stripes (Streifen), oder als rechteckige Tiles (Kacheln) abgelegt. Die Speicherung erfolgt dabei für jeden Streifen beziehungsweise für jede Kachel unabhängig von den anderen, so dass Bildteile, je nach Wahl der Größe der Streifen beziehungsweise Kacheln, relativ schnell geladen werden können. Andere Formate erfordern hier das Laden sämtlicher Bilddaten vor dem gewünschten Ausschnitt. Ziel der Unterteilung beim Entwurf war vor allem, dass Einzelteile komplett im Speicher gehalten werden können. Die 1992er-Spezifikation empfiehlt dafür acht Kilobyte Maximalgröße.

Programme wie Photoshop bieten an, TIFF-Dateien mit separaten Ebenen zu erstellen. Ferner gibt es die Möglichkeit, TIFFs mit einer Bildpyramide abzuspeichern. Dadurch sind innerhalb einer Datei mehrere Auflösungen des Bildes enthalten. Damit können zum Beispiel Layout-Programme oder Bildbetrachter eine kleine Vorschau des Bildes schneller anzeigen, da sie das Bild nicht in der vollen Auflösung zu laden brauchen.

#### Markdown

https://en.wikipedia.org/wiki/Markdown

[GitHub Flavoured Markdown](http://github.github.com/github-flavored-markdown/)

### Open Data Repositories
[Open Data](https://de.wikipedia.org/wiki/Open_data) bedeutet die freie Verfügbar- und Nutzbarkeit von, meist öffentlichen, Daten. Sie beruht auf der Annahme, dass vorteilhafte Entwicklungen unterstützt werden wie Open Government, wenn Daten für jedermann frei zugänglich gemacht werden und damit mehr Transparenz und Zusammenarbeit ermöglichen. Dazu verwenden die Ersteller Lizenzmodelle, die auf Copyright, Patente oder andere proprietäre Rechte weitgehend verzichten. Open Data ähnelt dabei zahlreichen anderen „Open“-Bewegungen, wie zum Beispiel Open Source, Open Content, Open Access oder Open Education und ist eine Voraussetzung für Open Government.
REF: Wikipedia
Open Data Repositories werden häufig mit der "data" Bezeichnung in der URL angegeben. Eine zentrale Stelle, die Daten von mehreren OGD-Portalen sammeln ist unter [data.gv.at](http://data.gv.at/) abrufbar. Nicht nur Städte und Länder geben Teile ihrer Daten frei, auch Ministerien, Gemeinden und staatsnahe Betriebe sind darunter.

BILD

### OGD Graz
Das [OGD-Portal der Stadt Graz](http://data.graz.gv.at/) bietet statistische und geographische sowie Verwaltungsdaten an.
Dazu geh"oren beispielsweise EinwohnerInnen- oder Finanzstatistiken in Form von CSV-Daten oder auch Karten mit Standorten in verschiedenen von GI-Systemen lesbaren Dateiformaten wie Shape oder WMS.
Der verwendete Zeichensatz ist bei den meisten Daten *'utf8'*.

BILD

### OGD Steiermark
Das [OGD-Portal des Landes Steimerark](http://data.steiermark.at/) ist ähnlich aufgebaut wie das OGD-Portal der Stadt Graz. Zeichensätze sind allerdings vorwiegend in *'latin-1'* aka *'ISO-8859-1'*.

BILD

### OGD Wien
Das [OGD-Portal der Stadt Wien](http://data.wien.gv.at/) bietet derzeit das größte Open Data Repository. Was es gegenüber den anderen OGD-Portalen hervorhebt, ist beispielsweise die Verfügbarkeit von Daten zu öffentlichen Verkehrsmitteln und einigen Planungsdaten (z.B. geplante ÖV-Netzwerkerweiterung). Ebenso gibt es ein breites Sortiment an Daten wichtiger Standorte der öffentlichen Versorgung. Der verwendete Zeichensatz ist bei den meisten Daten *'utf8'*.

BILD

### OpenStreetMap
BILD

[OpenStreetMap](http://wiki.openstreetmap.org/wiki/Map_Features) stellt die gesamten Daten unter der [Open Database License (ODbL)](http://opendatacommons.org/licenses/odbl/) zur Verfügung.
[OpenStreetMap mit QGis](http://www.qgis.org/en/docs/user_manual/osm/openstreetmap.html)


**Cloudmade**
[Cloudmade Steiermark](http://downloads.cloudmade.com/europe/western_europe/austria/steiermark#downloads_breadcrumbs)
[Terms and Conditions](http://cloudmade.com/website-terms-conditions) => [Creative Commons Attribution Share-Alike 2.0 License](http://creativecommons.org/licenses/by-sa/2.0/)

**Geofabrik**
[Daten](http://download.geofabrik.de/) - [Open Data Commons Open Database License (ODbL)](http://opendatacommons.org/licenses/odbl/)

## Probleme lösen
google schoolar
stackoverflow: helfen und geholfen werden, themenspezifisch
suchmaschine: wie stellt man dort fragen
	"How to XXXX" als suchtext
	Fehlermeldung kopieren: spezifika raus nehmen
Verhalten in Foren
zuerst suchen, wenn nicht gefunden selber fragen. zumeist gibt es das eigene problem schon mehree male
je nach community (wiss. disziplin, software projekt) unterschiedlich. zumeist auf website mehr infos zu finden.

1. Documentation nachsehen
2. Suchmaschine


Keine Scheu, im Internet bei anderen abzusehen. Dies ist eine hervorragende und weit verbreitete Methoden voneinander zu lernen.




