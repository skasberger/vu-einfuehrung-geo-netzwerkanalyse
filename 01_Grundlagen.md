# Grundlagen


## Einleitung
Kurzer einleitender Text, was in der Markdown file gemacht wird.

https://github.com/skasberger/vu-einfuehrung-geo-netzwerkanalyse

http://openscienceasap.org/education/courses/vu-einfuehrung-geo-netzwerkanalyse/

Fokussieren auf räumliche Netzwerke und Fragestellungen. Routing, Verkehr, Desease, Shortest Path, Service Areas, Erreichbarkeit, Standorte, etc.

## Graphentheorie

The theoretical basis for networks is the graph theory. By definition, a graph is a way of specifying relationships among a collection of items. It consists of a set of objects, called nodes, with certain pairs of these objects connected by links called edges \citep{easley_networks_2010}. Because of this flexible formalism, it is easy to find networks in many domains, like social sciences, micro-biology, psychology and engineering.

Different types of networks exist, depending on their structure and properties. Edges can be directed, from one node to another with a certain direction, or undirected, which means the relation is working in both directions and is symmetric. Typical undirected networks are links on webpages. Friendships for example are mostly undireced. The edges also can be weighted to give the relation a quantifiable dimension, like how often you met each other before or how big the bandwidth of a transmission channel is.\\

=> Multimodale Netzwerke!!!

Die Netzwerktheorie besch"aftigt sich mit gro"sen Netzwerken, die mit dem Aufkommen von Informations- und Kommunikationstechnologien (ICT) immer mehr an Relevanz bekommen. Der mathematische Unterbau dazu ist die Graphentheorie.

Die Graphentheorie ist die Erforschung von Netzwerk-Strukturen \cite[S. 23]{easley_networks_2010}. 
Ein Netzwerk ist ein abstraktes Konzept, welches Akteure und deren Beziehungen formalisiert und mathematisch berechenbar macht. Formal setzt sich ein Netzwerk aus einer Sammlung von Knoten und Verbindungen (Kanten) zusammen. Diese Definition ist sehr flexibel, wodurch viele verschiedene Arten von Beziehungen oder Verbindungen verwendet werden k"onnen, um Kanten zu definieren \citep[S. 2]{easley_networks_2010}.\\
Die verwendeten Begriffe f"ur diese beiden Elemente sind je nach Disziplin meist unterschiedlich \citep{latapy_basic_2008}:\\

\begin{itemize}
\item Mathematik: Vertices und Kanten
\item Physik: Sites und Bondes
\item Soziologie: Akteure und Verbindungen
\item Computer Sciences: Knoten und Links
\end{itemize}

Fortf"uhrend werden Knoten und Kanten verwendet.\\
Die Verbindungen zwischen den Knoten k"onnen entweder eine Richtung haben, dann spricht man von gerichteten Netzwerken, oder keine, welche ungerichtete Netzwerke hei"sen und symmetrisch sind. Um die Richtung zu signalisieren, sind gerichtete Kanten durch einen Pfeil dargestellt. Als Beispiel eines gerichteten Netzwerks seien Links auf Websites, das "Ubertragen von Information (Email, SMS, etc.) oder Stra"senfahrbahnen genannt. Stromnetzwerke oder Glasfasernetzwerke sind bi-direktional und somit ein ungerichtetes Netzwerk, es k"onnen in beide Richtungen Strom oder Daten '"ubertragen' werden. 

FIGURE BSP NETZWERK FORMALISMUS

FIGURE BSP BID NETWORK


**Bipartite**
Eher wenig Bedeutung in der Geographie.

This article focuses on bipartite networks: A particular class of networks, whose nodes are divided into two sets, X and Y, and only the connection between two nodes in different sets is allowed \citep{easley_networks_2010}. Nodes from set X are only connected with nodes from set Y, not with other nodes from X, and vice versa. The connections can be weighted/unweighted or directed/undirected.

In order to show the direct relations among a particular set of nodes \citep{zhou_how_2007}, because of the lack of appropriate notions and tools to address bipartite networks and to compare a particular network to others, one generally transforms a bipartite network into its X- or Y-projection \citep{latapy_basic_2008}, only consisting of one type of nodes. This is shown best through an example. Let's take a bipartite network of actors (yellow) and movies (green) as shown in figure \ref{fig:bipartite-network}, which gets projected to an actor-actor unipartite network (figure \ref{fig:unipartite-network}). Actor-actor means, that the projection looks on the relations between actors through their connection to movies. When actor $x_{1}$ played with actor $x_{2}$, the nodes $x_{1}$ and $x_{2}$ get connected in the projected unipartite graph. This goes on as long as all actor-movie-actor paths were projected. The created unipartite network only exists of actors connected together, and the edges carry the information that the actors played together in a movie.

The projection, more precisely the information loss through it, leads to some serious problems. Some will be mentioned here: 1) It's lost if the actors played in more than one movie together, 2) the bipartite clustering coefficient differs from its unipartite counterpart and varies widely for given unipartite values, demonstrating the distinction between unipartite and bipartite embeddedness in the network \citep{piepenbrink_methodological_2013} and 3) in which movie(s) they played together and. The first problem is solved by the use of a weighted projection, where the resulting network carries the number of co-occurances as edge weight and the second can be tackled by looking at the clustering coefficient of the bipartite network. The last one is an unsolveable part of projections. Another blemish is, that the information contained by the edge whose adjacent X node (Y node) is of degree one, will be lost in X-projection (Y-projection) \citep{zhou_how_2007}. 
In sense of computation, the inflationary growth of edges through projection can cause troubles. Notice that each top node of degree $d$ induces links in the X-projection, and conversely \citep{latapy_basic_2008}. 
And empiricaly there are also issues: When the number of connections grow, the amount of interactions between the nodes normally decrease, but this information is lost through the projection. Generally this means, that the projection to unipartite networks ignores the possibility that bipartite networks have characteristics unique to their specific nature, which cannot be captured from a unipartite network perspective \citep{piepenbrink_methodological_2013}.

There are also specificities of the measurements. It is shown that the expected clustering coefficient in the projections is large, and give an efficient estimation formula; this means that a high clustering coefficient in a projection may be seen as a consequence of the underlying bipartite structure rather than a specific property of the network. Conversely, if the clustering coefficient of the projection is different from the expected one, it means that the underlying bipartite structure has nontrivial properties responsible for it (\cite{latapy_basic_2008}; \cite{newman_random_2001}; \cite{guillaume_bipartite_2004}; \cite{guillaume_bipartite_2006}).

In particular, there is a high heterogenity between degrees of nodes of at least one kind, and there are significant overlaps between neighbourhoods \citep{latapy_basic_2008}.

more on this => https://github.com/skasberger/se-networks

Ein bi-partites Netzwerk ist eine spezielle Art eines Netzwerkes, in dem die Knoten in zwei Gruppen, A und B, unterteilt sind: Verbindungen sind nur zwischen Knoten aus verschiedenen Gruppen erlaubt \citep[S. 1]{zhou_how_2007}. Knoten der Gruppe A sind nicht mit anderen Knoten der Gruppe A verbunden, sondern nur mit Knoten der Gruppe B - und umgekehrt. 

Um aus dieser speziellen Struktur ein Netzwerk mit nur einer Gruppe zu erhalten, muss das bi-partite in ein uni-partite Netzwerk projeziert werden. Dies ist am besten mit einem konkreten Beispiel illustriert. Es sei ein bi-partites Netzwerk von Schauspielern und Filmen gedacht und dieses wird in ein uni-partites Netzwerk aus Schauspielern umgewandelt. Bei der normalen Projektion wird zwischen den Knoten von zwei Schauspielern eine Verbindung hergestellt, wenn diese in dem selben Film mitgespielt haben. Zumeist wird dies gemacht um verschiedene Netzwerke miteinander vergleichen zu k"onnen \citep[S. 5]{latapy_basic_2008} und um deren empirisch besser erforschten Analysemethoden und Metriken nutzen zu k"onnen. Das Problem dabei ist, dass dadurch viel Information verloren geht \citep[S. 5]{latapy_basic_2008}. Zum Beispiel ist es egal, wenn zwei Schauspieler in mehreren Filmen miteinander gespielt haben. Um dieses Problem zu beheben, kann die Projektion gewichtet werden. Wenn zwei Schauspieler in mehreren unterschiedlichen Filmen miteinander gespielt haben, erh"oht sich der Wert der verbindenden Kante, das Gewicht, f"ur jeden gemeinsamen Film um eins. Ein weiteres Problem mit projezierten Netzwerken ist, dass durch die Projektion die Anzahl der Kanten inflation"ar ansteigt, was eine Erh"ohung des Bedarfs an Speicher- und Rechenleistung nach sich zieht.

**3D**

### Shortest Path
[Dijkstra](https://www.youtube.com/watch?v=Q5ebFH8Yho4)
[A*]

Dykstra Algorithmus, Kosten/Impendanz: Distanz (Weg), Zeit; Origin Destination (In ArcGis eine Möglichkeit, Daten nur in Tabellarform oder als Kartogramm wiederzugeben)

FIGURE BIPARTITE mit PROJEKTION


### Centralities
#### Degree

#### Betweeness


#### Closeness


### Modularity

Communities sind Gruppen von Knoten, die m"oglicherweise gemeinsame Eigenschaften besitzen und/oder "ahnliche Rollen innerhalb des Graphens innehaben \citep{fortunato_community_2014}.\\
Eine verbundene Komponente eines Graphen ist eine Untermenge der Knoten, wo es 1) von jedem Knoten einen Pfad zu jedem anderen Knoten gibt; und 2) die Untermenge nicht teil einer gr"o"seren Sammlung mit der Eigenschaft, dass jeder Knoten jeden anderen erreichen kann, ist \citep[S. 29]{easley_networks_2010}. Gro"se, komplexe Netzwerke haben oft einen sogenannten Giant Component, ein beabsichtigt formaler Begriff f"ur eine verbundene Komponente, die einen signifikanten Anteil aller Knoten enth"alt \citep[S. 31]{easley_networks_2010}.

## Anwendungen

Beispiele nennen, Bilder zeigen, Grundsätzliches Verständnis, kurze Beschreibung

Wissenschaft

Co-Citatin, Biblometric Coupling, 

BILD

Verkehr
BILD

Social Media / Web Science
https://de.wikipedia.org/wiki/Soziale_Netzwerkanalyse

=> Verweis, Grundlegendes (Wikipedia)

BILD

Elektrizitätsnetz

BILD

Wasserversorgung

BILD

Krankheiten

BILD

Neurowissenschaften

Neuronale Netze

BILD

### Verkehr
Evaluatoren: werden verwendet, um Attribute der Quelldaten den Netzwerkelementen zuzuweisen (z.B. verschiedene Angaben zu Kreuzungen (Wartezeit) werden aus einem jeweiligen Shape hinzugefügt; ebenso falls es unterschiedliche Einschränkungen gibt; auch Fahrzeit)

Euler Problem

Transport: Konnektivität, Kosten, Hierarchien, Turns, Schnellste vs kürzeste Route, Impedanzen: Einbahnen, Abbiegeverbote, Höhenbeschränkungen, Gewichtsbeschränkungen, Gefahrengüter, Nachtfahrverbote, Baustellen


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

## Offene Wissenschaft
BILD

[Open Definition](http://opendefinition.org/)

https://en.wikipedia.org/wiki/Open_science

https://creativecommons.org/licenses/by/3.0/at/

http://openscienceasap.org/education/courses/se-networks/

[Open Database License (ODbL)](http://opendatacommons.org/licenses/odbl/)

BILD

[Creative Commons](http://de.creativecommons.org/)

Open Data und Open Source sind Teil von offener Wissenschaft


## Open Source Software

[Open Source Software](https://de.wikipedia.org/wiki/Open_Source)

[MIT Lizenz](http://opensource.org/licenses/MIT)

### Quantum GIS (QGIS)
BILD

[VRT](http://www.gdal.org/gdal_vrttut.html)
[YOUTUBE VIDEO: Downloading Landsat GeoTiff Images and Viewing them in Quantum GIS](https://www.youtube.com/watch?v=xyRrPEb3IPM)


Benötigte Plugins

#### Beschreibung
#### Nachschlagen
#### Installieren
#### Lernen
#### Sonstiges

### GRASS GIS
BILD

[Landsat und GRASS](http://toroid.org/ams/landsat-and-grass)
[GRASS Image Processing](http://grasswiki.osgeo.org/wiki/Image_processing)
[GRASS Atmospheric correction](http://grasswiki.osgeo.org/wiki/Atmospheric_correction)
[GRASS und LANDSAT](http://grasswiki.osgeo.org/wiki/LANDSAT)
[Processing Landsat 8 data in GRASS GIS 7: Import and visualization](http://courses.neteler.org/processing-landsat8-data-in-grass-gis-7/)
[Processing Landsat 8 data in GRASS GIS 7: RGB composites and pan sharpening](http://courses.neteler.org/processing-landsat-8-data-in-grass-gis-7-rgb-composites-and-pan-sharpening/)
[How to color-balance false-composites of pan-sharpened Landsat images in GRASS?](https://gis.stackexchange.com/questions/39174/how-to-color-balance-false-composites-of-pan-sharpened-landsat-images-in-grass)
[How to color-balance false-composites of pan-sharpened Landsat images in GRASS?](https://gis.stackexchange.com/questions/39174/how-to-color-balance-false-composites-of-pan-sharpened-landsat-images-in-grass)

http://geostat-course.org/Landau_2011
http://www.uni-koblenz-landau.de/landau/fb7/umweltwissenschaften/landscape-ecology/Teaching/geostat

Jede Location hat genau eine Projektion.
Ein Mapset ist zum Zusammenarbeiten von mehren Leuten in einem Netzwerk gedacht. Also eine spezielle Zusammenstellung, aber alle die gleiche Projektion.

Computational Region: Anwendung von Raster Operationen. Definiert durch Ausbreitung der Region und Auflösung des Rasters. Besonders bei Massenverarbeitungen nützlich, um Berechnungen bei überschaubaren, kleinen Regionen zu testen, bevor der ganze Datensatz berechnet wird. 

[Vector Network Analysis](http://grasswiki.osgeo.org/wiki/Vector_network_analysis)

Benötigte Plugins


#### Befehle
Erklärung
- g.* general
- d.* display
- r.* raster
- v.* vector
- i.* imagery
- r3.* voxel
- db.* database
- ps.* postscript

mit <tab> command completion

start:
- ```grass -gui```: start mit GUI
- ```grass -text```: start als text
- ```g.manual FUNCTION```: Hilfe anzeigen für einen Befehl
- ```g.proj -p```: verwendete Projektion anzeigen
- ```g.list rast```: listet alle Raster Layer auf, geht auch mit Vektor.
- ```r.info <MAP> -h```: Zeigt die Historie der Karte an, wo auch der Erstellungsbefehl dokumentiert ist.

GRASS GIS dokumentiert sämtliche Operationen in den Karten in der Historie mit. So kann die Erzeugung auch noch Jahre nach dem Erstellen einer Karte nachvollzogen und wieder ausgeführt werden. Es wird nämlich der gesamte Befehl abgespeichert.

Vektorgeometrien sind alle echt 3D!

Beachten bei Vektorimport: Nummer der inkorrekten Grenzen yyy, Nummer der Zentroiden ausserhalb Flächen zzz, Nummer an doppelten Zentroiden www.


#### Beschreibung
#### Nachschlagen
#### Installieren
#### Lernen
**1. [VIDEO: GEOSTAT Summer School GRASS GIS Tutorial](https://archive.org/details/GeostatSummerSchoolGrassGisTutorial) ansehen**: Starten, Sample Data Set, Installieren, Übersicht Funktionen, NVIZ, Raster Import/Export, Watershed, Vector Import/Export, 

[Youtube Suche](https://www.youtube.com/results?search_query=grass+gis)

#### Sonstiges

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
#### iGraph
#### iPython

#### Beschreibung
#### Nachschlagen
#### Installieren
#### Lernen
#### Sonstiges

### Git und GitHub
- [Fork A Repo](https://help.github.com/articles/fork-a-repo)
- [How to Use GitHub to Contribute to Open Source Projects](http://www.lockergnome.com/web/2011/12/13/how-to-use-github-to-contribute-to-open-source-projects/)
Pro Git Buch 

http://git-scm.com/
https://github.com/

#### Beschreibung
#### Nachschlagen
#### Installieren
#### Lernen
#### Sonstiges

### Postgresql, postGIS, pgRouting und pgAdmin3
BILDER

kurz erklären und verlinken

[Install/Setup in Ubuntu 13.10](http://trac.osgeo.org/postgis/wiki/UsersWikiPostGIS21UbuntuPGSQL93Apt)

[pgRouting](http://pgrouting.org/)
[Anleitung](http://docs.pgrouting.org/2.0/en/pgRoutingDocumentation.pdf)

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


### Gephi

http://gephi.org/

gibts da nicht ein shape plugin?

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

### GDAL
[GDAL Data Model](http://www.gdal.org/gdal_datamodel.html)
[GDAL Tools Plugin](http://qgis.org/en/docs/user_manual/plugins/plugins_gdaltools.html)
[gdalbuildvrt](http://www.gdal.org/gdalbuildvrt.html)
[gdal_merge.py](http://www.gdal.org/gdal_merge.html)
[gdalinfo](http://www.gdal.org/gdalinfo.html)
[gdalwarp](http://www.gdal.org/gdalwarp.html)


### Weitere
- [Graphviz](http://www.graphviz.org/) v2.26.3 ([doc](http://www.graphviz.org/Documentation.php)): [Using graphviz to draw graphs](http://avedo.net/338/using-graphviz-to-draw-graphs/)


## Open Data Formats

[Offene Dateiformate](https://de.wikipedia.org/wiki/Offenes_Format)

### SpatiaLite
[SpatiaLite](https://www.gaia-gis.it/fossil/libspatialite/index): SpatiaLite ist ein freies, OpenGIS kompatibles geografisches Informationssystem welches die Datei-basierte Datenbank SQLite um geografische Objekte und Funktionen erweitert.
https://de.wikipedia.org/wiki/SpatiaLite

[A quick tutorial to SpatiaLite - a Spatial extension for SQLite](http://www.gaia-gis.it/gaia-sins/spatialite-tutorial-2.3.1.html)

[Part 1: Getting Started with SpatiaLite: An almost Idiot's Guide](http://www.bostongis.com/PrinterFriendly.aspx?content_name=spatialite_tut01)

### SQLite
[SQLite](https://www.sqlite.org/): SQLite [ˌɛskjuːɛlˈlaɪt] ist eine Programmbibliothek, die ein relationales Datenbanksystem enthält. SQLite unterstützt einen Großteil der im SQL-92-Standard festgelegten SQL-Sprachbefehle. Unter anderem implementiert SQLite Transaktionen, Unterabfragen (subselects), Sichten (views), Trigger und benutzerdefinierte Funktionen. Public Domain
https://de.wikipedia.org/wiki/SQLite

### Shapefile
[Shapefile](http://www.esri.com/library/whitepapers/pdfs/shapefile.pdf): Das Dateiformat Shapefile (oft Shapedaten oder Shape genannt) ist ein ursprünglich für die Software ArcView der Firma ESRI entwickeltes Format für Geodaten.
https://de.wikipedia.org/wiki/Shapefile

### GeoJSON
[GeoJSON](http://geojson.org/) 
ist ein offenes Format zum Encodieren einer Vielzahl von geographischen Datenstrukturen. Der Name stammt von [JSON](http://www.json.org/) (JavaScript Object Notation). Daher ist ein jedes GeoJSON Object auch ein JSON Object, wodurch JSON Tools für das Verarbeiten von GeoJSON Daten verwendet werden können. GeoJSON erlaubt es geographische Daten in einer von Mensch lesbaren Sprache zu speichern die kompakter ist als XML. Räumliche Datenformat-Typen die GeoJSON unterstützt sind mitunter point, polygon, multipolygons, features, geometry collections und bounding boxes, welche zusammen mit charakteristischen Informationen und Attributen gespeichert werden. Die Geometrien und deren Verhältnisse besitzen Eltern-Objekte, wie z.B. feature collections. GeoJSON erlaubt auch das spezifizieren von geographischen Koordinatensystemen mittels OGC CRS (coordinate reference system) oder mit EPSG Code. Wenn kein CRS definiert wird, verwendet GeoJSON den WGS84 Geoid.
REF: übersetzt aus [Spezifikation](http://geojson.org/geojson-spec.html)

http://wiki.alpine-geckos.at/wiki/GeoJSON

### Markdown

https://en.wikipedia.org/wiki/Markdown

[GitHub Flavoured Markdown](http://github.github.com/github-flavored-markdown/)

## Open Data Repositories
Open Data bedeutet die freie Verfügbar- und Nutzbarkeit von, meist öffentlichen, Daten. Sie beruht auf der Annahme, dass vorteilhafte Entwicklungen unterstützt werden wie Open Government, wenn Daten für jedermann frei zugänglich gemacht werden und damit mehr Transparenz und Zusammenarbeit ermöglichen. Dazu verwenden die Ersteller Lizenzmodelle, die auf Copyright, Patente oder andere proprietäre Rechte weitgehend verzichten. Open Data ähnelt dabei zahlreichen anderen „Open“-Bewegungen, wie zum Beispiel Open Source, Open Content, Open Access, Open Education und ist eine Voraussetzung für Open Government.
REF: Wikipedia

[Open Data](https://de.wikipedia.org/wiki/Open_data)

BILD

### OGD Graz

### OGD Steiermark

### data.gov

### data.uk

### OGD Wien
BILD

### Landsat
[Bands](http://landsat.usgs.gov/band_designations_landsat_satellites.php)
[YOUTUBE VIDEO: Downloading Landsat GeoTiff Images and Viewing them in Quantum GIS](https://www.youtube.com/watch?v=xyRrPEb3IPM)

### MODIS

### Tiger

### OpenStreetMap
BILD

[OpenStreetMap](http://wiki.openstreetmap.org/wiki/Map_Features) stellt die gesamten Daten unter der [Open Database License (ODbL)](http://opendatacommons.org/licenses/odbl/) zur Verfügung.
[OpenStreetMap mit QGis](http://www.qgis.org/en/docs/user_manual/osm/openstreetmap.html)

## Improvements
- GRASS GIS und QGIS aus Python heraus ansprechen
- http://pysclint.sourceforge.net/pyhdf/install.html
- http://cosmicproject.org/links.html
- http://www.rsgislib.org/
- http://www.digital-geography.com/python-for-geospatial-data-analysis-part-ii/
- http://www.digital-geography.com/python-for-geospatial-data-analysis-part-iii/
- http://www.digital-geography.com/python-for-geospatial-data-analysis-part-iv/
- qgis python console in qgis nutzen




