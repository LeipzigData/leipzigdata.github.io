---
layout: default
title: Post_546
---


[Parent](Page_0)

# Open Streetmap

<h1>Leipzig Data und Open Streetmap</h1>
<a href="http://www.openstreetmap.de/">Open Streetmap</a> ist eines der großen praktischen Projekte, in dem offene Daten gesammelt werden. Im <a href="http://wiki.openstreetmap.org/wiki/Leipzig">Raum Halle/Leipzig</a> gibt es eine aktive Community von Mappern, die allerdings mehr praktisch mappend als theoretisch diskutierend unterwegs sind.

Im Rahmen von Open Streetmap werden auch Informationen über das lokale Geschehen gesammelt, allerdings sind diese Informationen in einem eigenen Standard abgelegt, der nicht unmittelbar mit Linked Data Standards kompatibel ist.

In diesem technologiegetriebenen Teilprojekt sollen die Verbindungen zwischen beiden Zugängen am Beispiel Leipziger Daten enger genüpft werden. Insbesondere sind Technologien zur Darstellung geolokaler Informationen von besonderem Interesse.
<h2>FAQ</h2>
<ul>
	<li><a href="http://wiki.openstreetmap.org/wiki/OpenLayers_osm_file_example" target="‘_blank’">Beispiel aus dem OSM Wiki:</a> Polygone aus einer OSM-Datei direkt auf einer OSM-Karte anzeigen</li>
	<li>OSM-Dumps
<ul>
	<li>OSM-Dumps werden von der <a href="http://www.geofabrik.de/">GEOFABRIK</a> bereitgestellt.</li>
	<li>Der kleinste offiziell verfügbare OSM-Dump mit Leipziger Informationen ist der <a href="http://download.geofabrik.de/europe/germany/sachsen.html">Sachsen-Dump</a> (sachsen-latest.osm.pbf, File size: 100 MB).</li>
	<li>Kleinere OSM-Dumps von Leipzig werden von uns über die overpass-API erzeugt und im <a href="https://github.com/LeipzigData/Tools/tree/master/OSM">Tools-git-Repo</a> gespeichert (kleines Bündel 12 MB, großes Bündel 17 MB, jeweils gzip-gepackt)</li>
</ul>
</li>
	<li>Mailingliste der regionalen OSM-Mapper: <a href="http://lists.openstreetmap.de/mailman/listinfo/halleipzig" target="‘_blank’">http://lists.openstreetmap.de/mailman/listinfo/halleipzig</a>.</li>
</ul>
<h2>Technologische Fragen</h2>
OSM-Daten lassen sich einfach über die <a href="http://wiki.openstreetmap.org/wiki/Overpass_API">Overpass-API</a> extrahieren, die als <a href="http://overpass-turbo.eu/">overpass_turbo</a> Web-Service zur Verfügung steht. Eine Reihe von Beispiel-Anfragen finden sich in der Datei <a href="https://github.com/LeipzigData/Tools/blob/master/OSM/Queries.txt">Queries.txt</a> im git-Repo. Die Overpass-API kann auch als lokaler Web-Service installiert werden, wenn umfangreichere Recherchen auf einem kleineren Datenbestand ausgeführt werden sollen.
<ul>
	<li>Mehr zur <a href="http://wiki.openstreetmap.org/wiki/Overpass_API/install">Installation</a> der API</li>
</ul>
<h2>Diskussion am 5.11.2013</h2>
Ein paar Schnipsel aus der Diskussion:
<ul>
	<li>Bei OSM sind zu unterscheiden Knoten, Polygonzüge, Multiploygone und Relationen</li>
	<li>Eine Verbindung zu Leipzig Data sollte die Entwicklungen bei <a href="http://www.wikidata.org">WikiData</a> berücksichtigen.</li>
	<li>Geoinformationen werden verbreitet in der <a href="http://de.wikipedia.org/wiki/Geography_Markup_Language">Geography Markup Language GML</a> abgelegt, sowohl im XML format als auch als SW Shape Files. Auch der <a href="http://en.wikipedia.org/wiki/Well-known_text">WKT-Standard</a> ist weit verbreitet.</li>
	<li>Weitere Werkzeuge: <strong>Nominatim</strong> (ein Tool der OSM Community) und <strong>LinkedGeoData</strong> (eine AKSW-Entwicklung), die beide semantische Informationen aus den weltweiten OSM-Daten extrahieren. Die bisher in Leipzig Data verfügbaren Geokoordinaten wurden über Nominatim gewonnen. Nominatim interpoliert Geokoordinaten, wenn die zugehörigen Adressen nicht in OSM erfasst sind.</li>
</ul>
Fabian schrieb im Nachgang:
<ul>
	<li>hier bekommst Du einen Eindruck, wie viele Adressen in Leipzig erfasst wurden und wo Gebäude keine Adressinformationen tragen. Rot sind auch Gebäude ohne Adressen markiert (z.B. Garagen). Wo keine Gebäude eingetragen sind, fehlt auch die rote Markierung:
<a class="moz-txt-link-freetext" href="http://qa.poole.ch/?zoom=12&amp;lat=51.33495&amp;lon=12.38991&amp;layers=FTTFB0">http://qa.poole.ch/?zoom=12&amp;lat=51.33495&amp;lon=12.38991&amp;layers=FTTFB0</a></li>
	<li>Eine Art lokales OSM, aber ohne Verknüpfung zu einer API oder zu Veranstaltungen gibt es hier: <a class="moz-txt-link-freetext" href="http://stadtplan-ilmenau.de/?flag=gov#%21flag=eat&amp;string=Caf%C3%A9">http://stadtplan-ilmenau.de/?flag=gov#!flag=eat&amp;string=Caf%C3%A9</a></li>
</ul>
<h2>Aktualisierung der Straßennamen</h2>
Das ist auch für den Bestand relevant, der in Leipzig Data enthalten ist und ein Abgleich zwischen beiden Projekten sinnvoll. Unsere Initialdaten wurden über API Leipzig aus Beständen der Stadt Leipzig (Stand wohl ca. 2009) übernommen.

Aus der Debatte zu Straßennamen auf der OSM-Liste:
<ul>
	<li><a href="https://lists.openstreetmap.de/pipermail/halleipzig/2013-February/000763.html" target="‘_blank’">Fabian Schmidt, 27.02.2013</a>: Es gibt einen zentralen Abgleich der Straßen in OSM mit dem städtischen Verzeichnis von Anfang 2013.</li>
	<li><a href="https://lists.openstreetmap.de/pipermail/halleipzig/2013-February/000764.html" target="‘_blank’">Roman Grabolle, 27.02.2013</a>: Hat zusammen mit einigen anderen 2009 einige Zeit mit dem Straßenabgleich zugebracht.</li>
	<li><a href="https://lists.openstreetmap.de/pipermail/halleipzig/2013-February/000765.html" target="‘_blank’">Roman Grabolle, 28.02.2013</a>: Ausführliche Kommentare zur aktuellen Änderungsliste</li>
</ul>
Weitere Stadtratsbeschlüsse:
<ul>
	<li>RBV-1572/13 vom 20.03.2013</li>
</ul>
<h2>Schnipsel</h2>
Für die Region Mitteldeutschland wird ein Mobilitätsportal entwickelt. Auch der Einsatz von Open Data wird in dem Zusammenhang erwogen. OSM leistet hier einen guten Betrag dazu. Für den Bereich ÖPNV gibt es in der Region Leipzig-Halle bereits mehrere Ansätze:
<ul>
	<li><a href="http://www.%C3%B6pnvkarte.de/" target="‘_blank’">http://www.öpnvkarte.de/</a></li>
	<li><a href="http://wiki.openstreetmap.org/wiki/User:Oxomoa/%C3%96PNV-Schema" target="‘_blank’">http://wiki.openstreetmap.org/wiki/User:Oxomoa/%C3%96PNV-Schema</a></li>
	<li><a href="http://wiki.openstreetmap.org/wiki/Halle_%28Saale%29/Nahverkehr" target="‘_blank’">http://wiki.openstreetmap.org/wiki/Halle_%28Saale%29/Nahverkehr</a></li>
	<li><a href="http://wiki.openstreetmap.org/wiki/Leipzig/Transportation" target="‘_blank’">http://wiki.openstreetmap.org/wiki/Leipzig/Transportation</a></li>
	<li><a href="http://wiki.openstreetmap.org/wiki/Talk:Leipzig/Transportation#Halle_.2F_Leipzig_-.3E_MDV" target="‘_blank’">http://wiki.openstreetmap.org/wiki/Talk:Leipzig/Transportation#Halle_.2F_Leipzig_-.3E_MDV</a></li>
	<li><a href="http://www.openstreetmap.org/browse/relation/2793232" target="‘_blank’">http://www.openstreetmap.org/browse/relation/2793232</a></li>
</ul>
<h2>Semantische Interpretation von geonames:nearbyFeatures</h2>
Es gibt ein kleineres (logisches) Problem mit den Geokoordinaten:

Wenn du z.B. die Nikolaikirche oder das Gewandhaus anschaust, dann ist der Marker da nicht ganz exakt (also eigentlich total daneben). Das liegt daran, dass die Adresse nicht mit der Position übereinstimmt (die Adresse der Nikolaikirche ist Nikolaikirchhof 3 und diese wird auch korrekt angezeigt).

Ich bin mir nicht sicher, wie man das am besten fixt. Wahrscheinlich sollten einfach Orte optional auch Geokoordinaten haben, die Vorrang vor den Geokoordinaten der Adresse haben. Das wäre eigentlich auch ganz sinnvoll, da man ja meist die <em>Orte</em> auf einer Karte darstellen will und die Adresse nur nutzt, um an die Geokoordinaten zu kommen. -- Andreas, 2013-02-18

