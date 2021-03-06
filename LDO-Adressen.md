---
layout: default
title: LDO-Adressen
---

<h1>LDO - Adressen und Geodaten der Stadt Leipzig</h1>
<h2>Allgemeines</h2>

Eine <em>Adresse</em> ist ein geolokaler Punkt in der Stadt Leipzig mit einer
Hausnummer, wo zum Beispiel eine Postzustellung möglich ist. Die Daten (über
65.000 Datensätze) wurden im Rahmen des API-Leipzig Projekts von der
Stadtverwaltung (einschließlich Referenzen auf das Straßenverzeichnis)
übernommen, im Rahmen des Leipzig Data Projekts in das RDF-Format
transformiert und in Adressen.ttl zusammengefasst.

Hausnummern
sind <a href="http://de.wikipedia.org/wiki/Grundst%C3%BCck"><em>Grundstücken</em></a>
zugewiesen, diese können aus mehreren <em>Flurstücken</em>
bestehen. Verschiedene Gebäude auf einem solchen Grundstück könnten später
durch URIs bezeichnet werden, die die Grundstücksadresse als Namenspräfix
haben. Damit folgt unsere Bezeichnung der
im <a href="http://www.leipzig.de/bauen-und-wohnen/bauen/geodaten-und-karten/">Kataster</a>.

Im Rahmen des Linked Geodata Projekts wurden diese Daten mit Geodaten
angereichert. Die Daten wurden initial
von <a href="http://aksw.org/ClausStadler.html">Claus Stadler</a>
über <em>nominatim</em> aus Open Streetmap extrahiert, danach weiter ergänzt
und aktualisiert.

Ausgewählte Adressen außerhalb von Leipzig sind in WeitereAdressen.ttl nach
demselben URI-Schema in einer verkürzten Ontologie erfasst.

Es gibt geolokale Punkte, die nicht durch eine solche Adresse referenziert
werden können, wie Treffpunkte, Kinderspielplätze u.ä. Dafür wurde das
Konzept <em>Treffpunkt</em> eingeführt, das aus einem Bezeichner und weiterer
geolokaler Information besteht.

In Anwendungen (etwa den <a href="LDO-Events">Events</a>) sind die
standardisierten Adressen bis auf die Hausnummer aufgelöst. Weitere
Informationen sind als Adresszusatz (ld:hasAddressAddendum) einzutragen.

Im Zuge der weiteren Standardisierung wurde am 12.11.2017 die Klassen
umbenannt
<ul>
  <li>ld:Adressen -&gt; ld:LeipzigerAdressen (konzeptionell rdfs:subClassOf
    ld:Adressen) und dabei das Prädikat ld:inStreet in ld:inStreetId
    umbenannt.</li>
  <li>ld:ExterneAdressen -&gt; ld:Adressen</li>
  <li>Ende 2017 wurden die Instanzen von ld:LeipzigerAdressen mit den
    Prädikaten ld:hasCity und ld:inStreet (in neuer Bedeutung)
    angereichert.</li>
</ul>
Es gibt weiter
ein <a href="https://www.leipzig.de/bauen-und-wohnen/bauen/liegenschaftskataster/">Liegenschaftskataster
der Stadt Leipzig</a> mit den Begriffen <em>Gemarkung</em> (nicht ganz
deckungsgleich mit den Ortsteilen), <em>Flurstück</em>
und <em>Grundstück</em>. Diese Informationen stehen noch nicht zur Verfügung.

<h2>Relevante RDF-Graphen</h2>

<h3>Adressen</h3>
<ul>
  <li><a href="http://leipzig-data.de/RDFData/Adressen.ttl">http://leipzig-data.de/RDFData/Adressen.ttl</a></li>
  <li><a href="http://leipzig-data.de/RDFData/GeoDaten.ttl">http://leipzig-data.de/RDFData/GeoDaten.ttl</a></li>
  <li><a href="http://leipzig-data.de/RDFData/WeitereAdressen.ttl">http://leipzig-data.de/RDFData/WeitereAdressen.ttl</a></li>
</ul>
<h3>Treffpunkte</h3>
<ul>
  <li><a href="http://leipzig-data.de/RDFData/Haltestellen.ttl">http://leipzig-data.de/RDFData/Haltestellen.ttl</a></li>
  <li><a href="http://leipzig-data.de/RDFData/Spielplaetze.ttl">http://leipzig-data.de/RDFData/Spielplaetze.ttl</a></li>
  <li><a href="http://leipzig-data.de/RDFData/Treffpunkte.ttl">http://leipzig-data.de/RDFData/Treffpunkte.ttl</a></li>
</ul>
<h2>Verwendete <a href="http://lov.okfn.org">Namensräume</a></h2>
<ul>
  <li>geo: &lt;http://www.w3.org/2003/01/geo/wgs84_pos#&gt;</li>
  <li>geonames: &lt;http://www.geonames.org/ontology#&gt;</li>
  <li>gsp: &lt;http://www.opengis.net/ont/geosparql#&gt;</li>
  <li>ld: &lt;http://leipzig-data.de/Data/Model/&gt;</li>
  <li>rdfs: &lt;http://www.w3.org/2000/01/rdf-schema#&gt;</li>
</ul>
<h2>Klassen</h2>
<ul>
  <li><strong>ld:LeipzigerAdresse</strong> - Adresse in der Stadt Leipzig in
    Adressen.ttl und Georeferenzen in GeoDaten.ttl
    <ul>
      <li>konzeptionell rdfs:subClassOf ld:Adressen</li>
    </ul>
  </li>
  <li><strong>ld:Adresse</strong> - Ausgewählte Adressen außerhalb der Stadt
    Leipzig in WeitereAdressen.ttl</li>
  <li><strong>ld:Treffpunkt</strong> - Geolokaler Ort in Leipzig, dem keine
    Adresse zugeordnet werden kann, etwa Spielplätze. Siehe Treffpunkte.ttl</li>
</ul>
<h2>Beschreibung der Prädikate</h2>
<strong>ld:LeipzigerAdresse</strong> - Adresse in der Stadt Leipzig
<ul>
  <li>URI-Struktur
    http://leipzig-data.de/Data/&lt;plz&gt;.Leipzig.&lt;Straßenname&gt;.&lt;Hausnummer&gt;</li>
  <li>rdfs:subClassOf ld:Adressen</li>
  <li>Weitere RDF-Prädikate in LeipzigerAdressen.ttl
    <ul>
      <li>ld:inOrtsteil ld:Ortsteil - Ortsteil, in welchem sich die Adresse
	befindet</li>
      <li>ld:inStreetId ld:Strasse - Straße, in welcher sich die Adresse
      befindet</li>
    </ul>
  </li>
  <li>gsp:asWKT Literal - Geokoordinaten im WKT-Format, z.B. "Point(12.3902485
    51.3210443)"
    <ul>
      <li>Damit werden Länge und Breite in <em>einem</em> Datenaggregat
	erfasst. Einer URI können damit <em>mehrere</em> Georeferenzen
	zugeordnet werden. Das ist insbesondere für die Qualitätssicherung
	relevant. Die Notation gehört zum GIS-Standard.</li>
      <li>2018-02-13: Im Zusammenhang mit der Übernahme von Adressdaten aus
	"Nachhaltiges Leipzig" wurde das Prädikat in Adressen.ttl
	übernommen.</li>
    </ul>
  </li>
  <li>Weitere Prädikate in GeoDaten.ttl - nicht regelmäßig gepflegt
    <ul>
      <li>geonames:nearbyFeatures URI - Link auf
	http://linkedgeodata.org/triplify/&lt;OSM-Struktur&gt; - Bezug auf
	eine OSM-Referenz, deren Geokoordinaten ausgewertet wurden</li>
      <li>geo:lat float - geografische Breite</li>
      <li>geo:long folat - geografische Länge</li>
    </ul>
  </li>
</ul>
<strong>ld:Adresse</strong> - Ausgewählte Adressen außerhalb der Stadt Leipzig
in WeitereAdressen.ttl
<ul>
  <li>URI-Struktur
  http://leipzig-data.de/Data/&lt;plz&gt;.&lt;Ort&gt;.&lt;Straßenname&gt;.&lt;Hausnummer&gt;</li>
  <li>RDF-Prädikate
    <ul>
      <li>ld:hasPostCode Literal - Postleitzahl</li>
      <li>ld:hasCity Literal - Stadt</li>
      <li>ld:hasStreet Literal - Straße, in welcher sich die Adresse
	befindet</li>
      <li>rdfs:label Literal - Bezeichner, etwa "Dresden, Messering 6"
	<ul>
 	  <li>2018-02-13: Postleitzahl wurde aus dem Label entfernt. Damit
 	    einheitliche Darstellung wie Leipziger Adressen.</li>
	</ul>
      </li>
      <li>gsp:asWKT Literal - Geokoordinaten im WKT-Format "Point(long
	lat)"</li>
    </ul>
  </li>
</ul>
<strong>ld:Treffpunkt</strong> - Geolokaler Ort in Leipzig, dem keine Adresse
zugeordnet werden kann, in Treffpunkte.ttl, Haltestellen.ttl, Spielplaetze.ttl
<ul>
  <li>URI-Struktur
  http://leipzig-data.de/Data/Treffpunkt/&lt;Bezeichner&gt;</li>
  <li>RDF-Prädikate
    <ul>
      <li>rdfs:label Literal - Bezeichner, etwa "Elsterbecken, Landauer
	Brücke, Hans-Driesch-Straße"</li>
      <li>gsp:asWKT Literal - Geokoordinaten im WKT-Format "Point(long
	lat)"</li>
    </ul>
  </li>
</ul>
<h2>Änderungen und Historie</h2>
<ul>
  <li>HGG 2018-08-12: Ergänzung weiterer Treffpunkte: Alle Spielplätze (aus
    codefor.de/leipzig), alle Haltestellen (aus opendata.leipzig.de)</li>
  <li>HGG 2018-02-21: QS der Adressdaten.</li>
  <li>HGG 2018-02-13: Übernahme von Adress- und Geodaten aus "Nachhaltiges
    Leipzig".
    <ul>
      <li>Dabei wurde das Prädikat gsp:asWKT in Adressen.ttl
	übernommen. Weiterhin wurden die Postleitzahlen aus dem Label in
	WeitereAdressen.ttl entfernt, um eine einheitliche Darstellung mit den
	Leipziger Adressen zu erreichen.</li>
    </ul>
  </li>
  <li>HGG 2017-12-13: ld:hasCity und ld:inStreet in ld:LeipzigerAdresse
    ergänzt
    <ul>
      <li>Frage: Können Geokoordinaten aus ld:hasCity, ld:hasPostCode,
	rdfs:label inferiert werden</li>
    </ul>
  </li>
  <li>HGG 2017-11-12: Umbenennung der Klassen in ld:LeipzigerAdresse und
    ld:Adresse zur Konsolidierung des Modells</li>
  <li>HGG 2015-02-09: Zuordnung zu Ortsteilen aus API-Leipzig erneut und
    diesmal korrekt übernommen.</li>
  <li>HGG 2014-04: Hausnummern wie "10-11" werden grundsätzlich auf die URI
    mit der kleinsten Hausnummer aus diesem Intervall gemapt, die im
    Adressverzeichnis der Stadt angegeben ist, um die Anzahl der URIs nicht zu
    sehr aufzublähen.</li>
  <li>HGG 2013-10-20: URIs nach einheitlichem neuen Konzept umgesetzt</li>
</ul>
<h3>Fragen:</h3>
<ul>
  <li>Gibt es eine sinnvolle externe Adress-Ontologie, die übernommen werden
    sollte? Wie löst das Open Street Map?</li>
</ul>

