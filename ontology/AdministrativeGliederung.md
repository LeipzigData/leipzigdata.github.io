---
layout: default
title: ontology/AdministrativeGliederung
---

<h1>Administrative Gliederung der Stadt Leipzig</h1>

<h2>Allgemeines</h2>

Die Stadt Leipzig ist in 63 Ortsteile unterteilt, die zu 10 Stadtbezirken
zusammengefasst werden. Die Zusammenfassung zu anderen Strukturen wie
Wahlkreisen oder Planungsräumen folgt ebenfalls der Ortsteilstruktur. Die
PLZ-Bereiche dagegen sind nicht deckungsgleich mit Vereinigungsmengen von
Ortsteilen.

Es existieren weitere kleinteiligere Planunsstrukturen auf Blockebene, Straßen
und Straßenabschnitten, die in verschiedenen Ämtern zudem verschieden
zugeschnitten sind. Die kleinste Planungseinheit, die in Leipzig Data derzeit
erfasst ist, ist die <a href="ontology/adressen/">Adresse</a> (Grundstück).

Die Straßen der Stadt Leipzig sind in
einem <a href="https://www.leipzig.de/buergerservice-und-verwaltung/unsere-stadt/gebietsgliederung-und-strassennamen/strassennamen/">offiziellen
Straßenverzeichnis</a> erfasst. Es ist zu beachten, dass im Tiefbauamt ein
davon
verschiedenes <a href="https://www.leipzig.de/buergerservice-und-verwaltung/unsere-stadt/gebietsgliederung-und-strassennamen/strassennamen/">Straßenabschnittsverzeichnis</a>
verwendet wird.

<div style="padding-left:
30px;">Das <a href="https://www.leipzig.de/fileadmin/mediendatenbank/leipzig-de/Stadt/02.1_Dez1_Allgemeine_Verwaltung/12_Statistik_und_Wahlen/Raumbezug/Strassenabschnittsverzeichnis_2017.pdf">Straßenabschnittsverzeichnis</a>
enthält eine alphabetische Übersicht aller Straßenabschnitte der Stadt Leipzig
mit ausgewählten Gebietszuordnungen sowie ein Verzeichnis der Straßennamen, zu
denen seit dem letzten Veröffentlichungstermin Änderungen beschlossen worden
und in Kraft getreten sind.</div>

<h2>Relevante RDF-Graphen</h2>
<ul>
  <li><a href="http://leipzig-data.de/RDFData/AdministrativeGliederung.ttl">http://leipzig-data.de/RDFData/AdministrativeGliederung.ttl</a></li>
  <li><a href="http://leipzig-data.de/RDFData/Strassenverzeichnis.ttl">http://leipzig-data.de/RDFData/Strassenverzeichnis.ttl</a></li>
</ul>

<h2>Verwendete <a href="http://lov.okfn.org">Namensräume</a></h2>

<ul>
  <li>ld: &lt;http://leipzig-data.de/Data/Model/&gt;</li>
  <li>rdfs: &lt;http://www.w3.org/2000/01/rdf-schema#&gt;</li>
</ul>

<h2>Klassen</h2>

<ul>
  <li><strong>ld:JH-Planungsraum</strong> - Planungsraum Jugendhilfe der Stadt
    Leipzig.</li>
  <li><strong>ld:Ortsteil</strong> - Ortsteil der Stadt Leipzig.</li>
  <li><strong>ld:Planungsraum</strong> - Planungsraum Stadtentwicklung der
    Stadt Leipzig.</li>
  <li><strong>ld:Stadtbezirk</strong> - Stadtbezirk der Stadt Leipzig.</li>
  <li><strong>ld:Strasse</strong> - Straße im Straßenverzeichnis der
    Stadt</li>
  <li><strong>ld:Wahlkreis2014</strong> - Wahlkreis-Einteilung der Stadt
    Leipzig zur Stadtratswahl 2013</li>
</ul>

<h2>Beschreibung der Prädikate</h2>

<strong>ld:JH-Planungsraum</strong> - Die Jugendhilfeplanung teilt die 63
Ortsteile der Stadt Leipzig in 7 Planungsräume ein.
<ul>
  <li>URI-Struktur
  http://leipzig-data.de/Data/JH-Planungsraum/&lt;Bezeichnung&gt;</li>
  <li>RDF-Prädikate
    <ul>
      <li>ld:containsOrtsteil ld:Ortsteil - zugeordnete Ortsteile</li>
      <li>rdfs:label Literal - Bezeichnung, z.B. "JH-Planungsraum Grünau"</li>
    </ul>
  </li>
</ul>
<strong>ld:Planungsraum - </strong>Zur Konzentration der
Stadtentwicklungsmittel werden in Leipzig Ortsteile zu Planungsräumen
zusammengefasst.
<ul>
  <li>URI-Struktur
  http://leipzig-data.de/Data/Planungsraum/&lt;Bezeichnung&gt;</li>
  <li>RDF-Prädikate
    <ul>
      <li>ld:containsOrtsteil ld:Ortsteil - zugeordnete Ortsteile</li>
      <li>rdfs:label Literal - Bezeichnung, z.B. "JH-Planungsraum Grünau"</li>
    </ul>
  </li>
</ul>
<strong>ld:Ortsteil</strong> - Ortsteil der Stadt Leipzig<strong>
</strong>
<ul>
  <li>URI-Struktur
  http://leipzig-data.de/Data/Ortsteil/&lt;Bezeichnung&gt;</li>
  <li>RDF-Prädikate
    <ul>
      <li>ld:hasStadtRef URI - StadtId-URI,
	siehe <a href="ontology/referenzen/">Referenzen</a></li>
      <li>rdfs:label Literal - Bezeichnung, z.B. "Anger-Crottendorf"</li>
    </ul>
  </li>
</ul>
<strong>ld:Stadtbezirk</strong> - Stadtbezirk der Stadt Leipzig
<ul>
  <li>URI-Struktur
  http://leipzig-data.de/Data/Stadtbezirk/&lt;Bezeichnung&gt;</li>
  <li>RDF-Prädikate
    <ul>
      <li>ld:containsOrtsteil ld:Ortsteil - zugeordnete Ortsteile</li>
      <li>rdfs:label Literal - Bezeichnung, z.B. "Stadtbezirk Nord-Ost"</li>
    </ul>
  </li>
</ul>
<strong>ld:Strasse</strong> in Strassenverzeichnis.ttl - Straße im
Straßenverzeichnis der Stadt
<ul>
  <li>URI-Struktur
  http://leipzig-data.de/Data/Strasse/&lt;Straßenname&gt;</li>
  <li>Eine Straße kann durch mehrere Ortsteile verlaufen. Die entsprechende
    Information kann über die Klasse ld:Adresse inferiert werden.</li>
  <li>RDF-Prädikate
    <ul>
      <li>owl:sameAs ld:Referenz - Verweis auf die StadtId, etwa
	&lt;http://leipzig-data.de/Data/StadtId/Street.02140&gt;</li>
      <li>rdfs:label Literal - Bezeichner, etwa "Abtnaundorfer Straße"</li>
    </ul>
  </li>
</ul>
<strong>ld:Wahlkreis2014</strong> - Wahlkreis zur Stadtratswahl 2014
<ul>
  <li>URI-Struktur http://leipzig-data.de/Data/Wahlkreis2014/&lt;Nr&gt;</li>
  <li>RDF-Prädikate
    <ul>
      <li>ld:containsOrtsteil ld:Ortsteil - zugeordnete Ortsteile</li>
      <li>rdfs:label Literal - Bezeichnung, z.B. "Wahlkreis 2"</li>
    </ul>
  </li>
</ul>
<h2> Änderungen</h2>
<ul>
  <li>HGG 2018-02-23: Planungsraum.ttl aufgelöst</li>
</ul>

