---
layout: default
title: Gebaeudenavigator
---

<h2>Gebäudenavigator</h2>
<h3>Allgemeines</h3>

Im Rahmen der Zusammenarbeit mit dem <a href="http://www.le-online.de/"
rel="nofollow">Behindertenverband Leipzig e.V.</a> wird ein Online-Stadtführer
entwickelt. Datenbasis ist eine vom BVL gepflegte Datenbank mit Informationen
über 2600 öffentliche Gebäude und Plätze in Leipzig. Jedes Gebäude und jeder
Platz wurde nach der Eignung für Menschen mit Mobilitätseinschränkungen
klassifiziert. Es wurden jedoch nicht nur Angaben zur Mobilität gemacht,
sondern auch Informationen über viele andere Zugangshilfen hinterlegt. Für
Menschen mit Sinnesbeeinträchtigungen (blind, gehörlos) gibt es, falls
vorhanden, genaue Beschreibungen der Angebote vor Ort.

<h3>Datenbasis</h3>

Die RDF Daten können mittlerweile wenigstens über den
<a href="https://opendata.leipzig.de/virt-sparql">SPARQL Endpunkt</a> des
Open Data Portals der Stadt Leipzig ausgelesen werden. Die folgende Anfrage
etwa listes alle 814 Orte auf<p>
<pre>PREFIX bvlo: &lt;https://github.com/AKSW/leds-asp-f-ontologies/raw/master/ontologies/place/ontology.ttl#&gt;
SELECT *
FROM &lt;https://opendata.leipzig.de/bvlplaces/&gt;
WHERE {
?s a bvlo:Place; dc:title ?t .
}</pre>
<a href="https://opendata.leipzig.de/virt-sparql?default-graph-uri=&amp;query=PREFIX+bvlo%3A+%3Chttps%3A%2F%2Fgithub.com%2FAKSW%2Fleds-asp-f-ontologies%2Fraw%2Fmaster%2Fontologies%2Fplace%2Fontology.ttl%23%3E%0D%0ASELECT+*%0D%0AFROM+%3Chttps%3A%2F%2Fopendata.leipzig.de%2Fbvlplaces%2F%3E%0D%0AWHERE+%7B%0D%0A%3Fs+a+bvlo%3APlace%3B+dc%3Atitle+%3Ft+.%0D%0A%7D"><span style="color: red; font-size: 16pt;"> Run this query</span></a></p>

<h3>Hintergrund und weitere Links</h3>

Das <a href="http://aksw.org/Projects/LEDS.html">LEDS-Projekts</a> der AKSW
zusammen mit dem <a href="http://www.le-online.de/"
rel="nofollow">Behindertenverband Leipzig e.V.</a>
von <a href="http://aksw.org/KonradAbicht.html">Konrad Abicht</a>
und <a href="https://github.com/simeonackermann">Simeon Ackermann</a>.
<ul>
  <li>Der <a href="https://behindertenverband-leipzig.de/gebaeude-navigator">Gebäudenavigator</a></li>
  <li><a href="https://www.leds-projekt.de/de/aktuelles/2017/Treffen-mit-Interessenvertretern-zur-Vorstellung-des-Gebaeude-Navigators.html">Mehr zum Projekt</a></li>
  <li><a href="https://github.com/AKSW/building-navigator">Quellen bei github</a></li>
</ul>
