---
layout: default
title: Post_131
---


[Parent](Page_115)

# Events

<h1>Leipzig Data Events Framework</h1>

<hr />

<ul>
 	<li>Allgemeines</li>
 	<li>RDF-Struktur</li>
 	<li>Demo-Oberfläche als Wordpress-Plugin</li>
 	<li><a href="http://leipzig-data.de/widget/" target="‘_blank’">Leipzig Data Event Widget</a></li>
 	<li><a title="Event-Vorlage" href="http://www.leipzig-data.de/event-vorlage/">Event-Vorlage</a></li>
 	<li>Events in der <a href="http://leipzig-data.de/info/" target="‘_blank’">Leipzig Data Demonstations-Seite</a></li>
</ul>

<hr />

<h2>Allgemeines</h2>
<b>Ziel</b> dieses Teilprojekts ist es, eine <i>Infrastruktur</i> aufzubauen, in die Event-Daten in <i>einheitlichem Format</i> aus verschiedenen Quellen und von verschiedenen Akteuren eingespeist werden und der Allgemeinheit zum Gebrauch zur Verfügung stehen.

Die Infrastruktur bietet keinen elaborierten eigenen Service zur Präsentation dieser Event-Daten, sondern überlässt die Zusammenführung mit weiteren Event-Daten, Filterung und Präsentation den Anbietern, die auf diese Infrastruktur zugreifen möchten. Die prinzipiellen Möglichkeiten des Leipzig Data Events Frameworks demonstriert auch unser <a href="http://leipzig-data.de/widget/" target="‘_blank’">Leipzig Data Event Widget</a>.

Der primäre Zugriff erfolgt über Sparql-Anfragen auf einen <a href="http://leipzig-data.de/glossar/" target="‘_blank’">Sparql-Endpunkt</a>, in dem die Event-Daten mit weiteren Daten über Veranstalter und Veranstaltungsorte aus dem Leipzig Data Teilprojekt <a title="Gelbe Seiten" href="http://www.leipzig-data.de/gelbe-seiten/">Gelbe Seiten</a> angereichert und zusammengeführt sind. Dazu wurden über einen längeren Zeitraum die Event-Daten der assoziierten Partner (API Leipzig, MINT-Netzwerk) zusammengeführt und einmal wöchentlich aktualisiert. Beim Design des Gesamtprozesses sind wir davon ausgegangen, dass es (zukünftig) eine Betreibergruppe der Infrastruktur gibt, in der alle wichtigen Fragen abgestimmt werden. Allerdings sind die Quellen inzwischen weitgehend versiegt, eine Zusammenführung nicht gelungen.

Das derzeit vorliegende einheitliche Format (aka Protokoll) als Ergebnis eines längeren Entwicklungsprozesses ist weiter unten genauer beschrieben. Fragen der Weiterentwicklung des Protokolls werden in der Betreibergruppe abzustimmen sein.

Um Event-Daten in die Infrastruktur einzuspielen, müssen interessierte Akteure einen Service aufsetzen, mit dem relevante eigene Daten (verfügbar etwa als RSS- oder ical-Feed) in das vereinbarte Format überführt werden. Hierzu gibt es eine Reihe von Beispielskripten. Wir beraten interessierte Akteure im Rahmen unserer Möglichkeiten, wie eine solche (nicht schwierige) Bereitstellung erfolgen kann.

Termine werden drei Monate nach Ablauf aus der Datenbasis <em>Events</em> herausgenommen und in die Datenbasis <em>Alte Events</em> übernommen. Dort werden sie nach Jahresablauf endgültig gelöscht. Werden Daten lokal weiter benötigt, so müssen diese rechtzeitig aus dem Endpunkt ausgelesen und in eigener Verantwortung gespeichert werden. Auch hierfür gibt eine Reihe von Beispielskripten.
<h2>RDF-Struktur</h2>
<h3>Relevante RDF-Graphen</h3>
<ul>
 	<li><a href="http://leipzig-data.de/RDFData/Events.ttl">http://leipzig-data.de/RDFData/Events.ttl</a></li>
 	<li><a href="http://leipzig-data.de/RDFData/AlteEvents.ttl">http://leipzig-data.de/RDFData/AlteEvents.ttl</a></li>
</ul>
<h3>Verwendete <a href="http://lov.okfn.org">Namensräume</a></h3>
<ul>
 	<li>ical: http://www.w3.org/2002/12/cal/ical#</li>
 	<li>ld: http://leipzig-data.de/Data/Model/</li>
 	<li>rdfs: http://www.w3.org/2000/01/rdf-schema#</li>
</ul>
<h3>Klassen</h3>
<ul>
 	<li><b>ld:Event</b> - einzelne Events</li>
</ul>
<h3>Beschreibung der Prädikate</h3>
<b>ld:Event</b> - einzelne Events
<ul>
 	<li>ld:contactPerson foaf:Person - Ansprechpartner für das Event</li>
 	<li>ical:contact Literal - Kontaktinformation als String</li>
 	<li>ical:description Literal - Beschreibung des Events</li>
 	<li>ld:hatVeranstaltungsort ld:Ort - Ort, an dem das Event stattfindet</li>
 	<li>ld:hatTreffpunkt ld:Treffpunkt - Treffpunkt für das Event</li>
 	<li>ld:hasAddressAddendum Literal - genauere Bezeichnung innerhalb von ical:location</li>
 	<li>ical:summary Literal - kurze Beschreibung (max. 100 Zeichen) des Events</li>
 	<li>Literale: ical:dtstart, ical:dtend (xsd:date oder xsd:datetime)</li>
 	<li>ld:hatVeranstalter org:Organization - Veranstalter des Events</li>
 	<li>ical:sentBy foaf:Agent - Quelle der Eventinformation</li>
 	<li>ld:hasTag ld:Tag - Tags für das Event</li>
 	<li>ld:zurReihe ld:Projekt - Zuordnung zu einer Veranstaltungsreihe</li>
 	<li>Orga-Literale ld:hasAPIRef</li>
 	<li>Weitere Literale: ld:Kosten</li>
</ul>
<h3>Änderungen</h3>
<ul>
 	<li>HGG 2018-02-17: Prädikate geändert
<ul>
 	<li>ical:location -&gt; ld:hatVeranstaltungsort und ld:hatTreffpunkt</li>
 	<li>ical:organizer -&gt; ld:hatVeranstalter (Wert muss nun org:Organization oder eine Unterklasse davon sein)</li>
</ul>
</li>
</ul>

<hr />

<h2>Eine Demo-Oberfläche als Wordpress-Plugin</h2>
Im Kalender sind die Events nach Eventdatum einsortiert, Klicken auf den Tag zeigt die Liste der Events für diesen Tag, Klick auf einen Event-Link zeigt eine (rohe) Übersicht über die Informationen zu diesem Event mit weiteren Links in die Leipzig Data Datenbasis. Hier kann (und da endet die Nutzerfreundlichkeit der prototypischen Implementierung, mit der allein die Möglichkeiten des Konzepts gezeigt werden) nach Linked Data Prinzipien weiter navigiert werden.

[sparqalendar] (Wordpress Plugin, aktuell nicht eingebunden)
<h2>Stand der Umsetzung</h2>
Die Basisentwicklungen wurden im Rahmen des Projekts <em>Leipzig Open Data </em>ausgeführt.

Folgender <b>Workflow</b> ist dazu mit den assoziierten Partnern besprochen:
<ul>
 	<li>Neue Einträge werden laufend aufgenommen und in <em>Events.ttl</em> eingearbeitet. Einträge, die mehr als einen Monat zurückliegen, werden in <em>AlteEvents.ttl</em> umgetragen und nach einem Jahr komplett entfernt.</li>
 	<li>Die Event-Daten werden in unregelmäßigen Abständen in den <a href="http://leipzig-data.de/widget/sparql.php" target="‘_blank’">Sparql-Endpunkt des Event-Projekts</a> übernommen, von dort (automatisiert) neu ausgerollt und die Widget-Sichten auf die Event-Daten aktualisiert:
<ul>
 	<li><a href="http://leipzig-data.de/widget/themes/theme-1/presentation.php" target="‘_blank’">einfache Ansicht</a> mit Karte</li>
 	<li><a href="http://leipzig-data.de/widget/themes/theme-2/presentation.php" target="‘_blank’">komplexe Ansicht</a> mit mehreren Such- und Filterfunktionen</li>
 	<li><a href="http://leipzig-data.de/widget/themes/theme-3/presentation.php" target="‘_blank’">experimentelle Ansicht</a> mit Features, die noch in der Erprobung sind</li>
</ul>
</li>
</ul>
<h2>Aktivitäten</h2>
<ul>
 	<li>12.10.2013: Einspielen der Wordpress-Demo als weitere Sicht auf die Daten (Johannes Frey)</li>
 	<li><a href="http://www.leipzig-netz.de/index.php5/LD.LOD.2013-04-26">26.04.2013</a>: Vorstellung des Projekts auf dem Abschlusstreffen des Leipzig Open Data Projekts (Andreas Nareike, Johannes Frey)</li>
 	<li><a title="LD.OpenInnovation-12.IdeenBoerse" href="http://www.leipzig-netz.de/index.php5/LD.OpenInnovation-12.IdeenBoerse">11.-19.01.2013</a>: Arbeiten im Rahmen der Ideenbörse</li>
 	<li><a title="LD.LOD.2012-07-20" href="http://www.leipzig-netz.de/index.php5/LD.LOD.2012-07-20">20.07.2012</a>: Vorstellung und Diskussion der Arbeiten an einer Präsentationsplattform basierend auf dem Exhibit-Framework (Johannes Frey)</li>
</ul>
<h2>Vom Projektteam entwickelte Lösungen</h2>
<ul>
 	<li><a title="LD.API-Leipzig" href="http://www.leipzig-netz.de/index.php5/LD.API-Leipzig">API Leipzig</a> Events - wird derzeit vor allem von <a href="http://www.kreatives-leipzig.de/termine" target="‘_blank’">Kreatives Leipzig</a> genutzt
<ul>
 	<li>Ein Beispiel-Perl-Skript (getAPIEvents.pl) greift auf die Webschnittstelle von APILeipzig zu</li>
 	<li>2017-09: API Leipzig wurde abgeschaltet.</li>
</ul>
</li>
 	<li>API Leipzig Rückbindung: Christoph Pieloth hat einen Beispiel-Client in Java geschrieben, der auf die LD.Events Schnittstelle (also den Sparql Endpunkt) eine calendarAPI aufsetzt, welche die API.Leipzig Event-API Spezifikation erfüllt. Damit können parallel Events aus LD.Events und aus API.Leipzig ausgelesen und zu einem Upstream federiert werden. Dieser Upstream wird von city:cult verwendet, um die eigene <a title="LD.Android" href="http://www.leipzig-netz.de/index.php5/LD.Android">Android-App</a> mit Daten zu füttern.
<ul>
 	<li><a href="https://github.com/LeipzigData/JavaExamples/tree/master/src/calendarApi" target="‘_blank’">https://github.com/LeipzigData/JavaExamples/tree/master/src/calendarApi</a></li>
 	<li>Es sind nicht alle Services implementiert, wer diese jedoch braucht, kann dies schnell per Copy &amp; Paste implementieren. Aktuell funktionieren z.B. die Venue-Details nicht und ohne Veranstaltungsort erscheinen die Events aktuell bei City:Cult auch nicht :( Daran werden wir bei Gelegenheit arbeiten.</li>
 	<li>(Aug 2017) Die Plattform API Leipzig ist nicht mehr am Netz.</li>
</ul>
</li>
 	<li><a href="http://www.mehr-als-chillen.de/de/2/p1/home.html" target="‘_blank’">Mehr als Chillen Grünau</a>
<ul>
 	<li>Beispiel-Perl-Skript (getMehrAlsChillenEvents.pl) greift auf einen lokal eingespielten Datenbank-Dump zu.</li>
 	<li>Mehr als Chillen hat die Zusammenarbeit inzwischen eingestellt.</li>
</ul>
</li>
 	<li><a href="http://www.energiemetropole-leipzig.de/index.php/netzwerk-energie-umwelt.html" target="‘_blank’">Netzwerk Energie und Umwelt</a>
<ul>
 	<li>Beispiel-Perl-Skripte greifen auf ics-Export (neu-ics.pl) sowie RSS-Feed (neu-xml.pl) zu.</li>
 	<li>Identifizierung der Events erfolgt über eine MD5-Summe als Wert des Prädikats ld:hasMD5Sum, die über DTSTART, SUMMARY und DESCRIPTION eines von NEU übernommenen ical-Events gebildet wird.</li>
 	<li>(2016) Nach der Neukonzeption der NEU-Plattform ist der Service nicht mehr verfügbar.</li>
</ul>
</li>
</ul>
Die Präsentationsschicht ist unabhängig von der Datenhaltung gestaltbar - über eine Sparql-Anfrage (konzeptionell vergleichbar mit einer SQL-Anfrage an eine lokale Datenbank) werden die relevanten Daten ausgelesen und auf die gewünschte Weise präsentiert.

Als <em>Proof of Concept</em> hat Johannes Frey das Javascript-Frameworks <a href="http://simile-widgets.org/wiki/Getting_Started_with_Exhibit" target="‘_blank’">Exhibit</a> für eine Widget-Lösung verwendet und <a href="http://leipzig-data.de/Upload/Event-Widget.pdf" target="‘_blank’">dokumentiert</a>, mit der sich schnell Webseiten mit Suchmasken und Tagwolken herstellen lassen. Die zur Präsentation verwendeten Widgets setzen dieses Framework ein.
<h2>Weitere Projekte ähnlicher Ausrichtung</h2>
<ul>
 	<li><a href="http://www.umweltbildung-sachsen.de" target="‘_blank’">http://www.umweltbildung-sachsen.de</a> - Datenbank Umweltbildung Sachsen, Ansprechpartnerin Annette Körner</li>
 	<li>Veranstaltungsdatenbank von <a href="http://mehr-als-chillen.de" target="‘_blank’">Mehr als Chillen</a></li>
 	<li>Veranstaltungsdatenbank des <a href="https://www.energiemetropole-leipzig.de/de/veranstaltungen" target="‘_blank’">Netzwerks Energie und Umwelt</a></li>
 	<li>Veranstaltungsdatenbank <a href="https://www.nachhaltiges-leipzig.de/" target="‘_blank’">Nachhaltiges Leipzig</a></li>
 	<li>Veranstaltungskalender von <a href="https://leipzig.afeefa.de/">Afeefa Leipzig</a></li>
 	<li>Veranstaltungsdatenbank des <a href="http://www.ingenieurnachrichten.vdi-leipzig.de/" target="‘_blank’">VDI Leipzig</a></li>
</ul>

