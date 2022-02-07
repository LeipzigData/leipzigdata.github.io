--
layout: default
title: Page_283
---

## Parent: [0](Page_0)

# Jugendstadtplan

<h1>Leipzig Data - Projekt "Jugendstadtplan"</h1>
Dieses Projekt wurde in der letzten Phase des <a title="Leipziger Initiative für Offene Daten" href="http://www.leipzig-data.de/leipziger-initiative-fur-offene-daten/">Leipzig Open Data Projekts</a> in Angriff genommen, da es im Datenbereich viele Überschneidungen mit dem P<a title="Gelbe Seiten" href="http://www.leipzig-data.de/gelbe-seiten/">rojekt Gelbe Seiten</a> gab und überdies mit den <em>MINT-Orten</em>, einer Sammlung von Leipziger Orten der außerschulischen MINT-Bildung, relevante Informationen in unserer Datensammlung bereits verfügbar sind.

Diese Daten sind ein weiteres Beispiel, wie geolokale Informationen in Karten dargestellt werden können. Da die in enge vertragliche Verpflichtungen eingebundenen Akteure des Stadtprojekts "Jugendstadtplan" keine Open Data Technologien einsetzten, wurde beschlossen, den eigenen Jugendstadtplan im Rahmen der studentischen Ausbildung im Sommersemester 2013 weiterzuentwickeln. Zur Vorbereitung und für das Anlaufen des Projekts konnte eine WHK für einen Monat aus Projektmitteln finanziert werden.
<ul style="margin-bottom: 1em;">
 	<li><a href="http://www.leipzig-data.de/JSP-15">Jugendstadtplan</a> der studentischen Projektgruppe in einer 2015 durch Immanuel Plath überarbeiteten Version (aktuell defekt)</li>
 	<li><a href="http://www.pulpmap-leipzig.de/site/show/overview">Online-Variante</a> des im Auftrag der Stadt erstellten Jugendstadtplans. (2018 nicht mehr erreichbar)</li>
</ul>
<h2>Hintergrund</h2>
Im Zusammenhang mit den <a href="http://www.worldskillsleipzig2013.com/" target="‘_blank’">World Skills 2013</a> wurde in einem städtisch finanzierten Projekt (Auftragnehmer: Stadtjugendring, Galerie f. zeitgenössische Kunst) ein Jugendstadtplan in Angriff genommen, der zur World Skills 2013 in gedruckter Form ausgereicht wird und für Jugendliche interessante Leipziger Orte samt Karte präsentiert.

In Zusammenarbeit mit einer Gruppe Jugendlicher (Koordinierung durch <a href="http://www.produktionsschuleleipzig.de">Das Schauplatz</a>) wurden Anfang 2013 relevante Informationen gesammelt. Dieser Projektteil wurde durch den Stadtjugendring (Teresa von Jan) koordiniert. Im Ergebnis lag Ende Februar 2013 eine Sammlung von über 100 Orten vor samt Schlagworten und weiteren Informationen vor, die auch uns als Excel-Liste zur Verfügung gestellt wurde.

Die weitere künstlerische und technische Fertigstellung sowohl der gedruckten als auch der Online-Variante erfolgt zusammen mit den beteiligten Jugendlichen durch ein Team der <a href="http://www.gfzk.de/">GfZK Leipzig</a> (Leitung: Alexandra Friedrich). Verantwortlich für die technische Umsetzung der Online-Lösung war Tristan Schulze (<a href="http://hellostudios.de/?p=1846" target="‘_blank’">Hello Studios</a>).
<ul style="margin-bottom: 1em;">
 	<li>Erste Version (März 2013) unserer <a href="http://leipzig-data.de/JSP-13/index.html" target="‘_blank’">OSM-Karte</a> mit Links zu den gesammelten Orten im Rahmen des Leipzig Data Projekts.</li>
 	<li>Tristan Schulze stellt am <a title="LD.Jugendstadtplan.2013-04-23" href="http://leipzig-netz.de/index.php5/LD.Jugendstadtplan.2013-04-23">23.04.2013</a> eine erste Version vor. Im Nachgang wird mit Herrn Hild besprochen, dass mit Blick auf weitere Umwägbarkeiten im Vorfeld des bevorstehenden Großereignisses eine Zusammenführung mit Daten aus dem MINT-Netzwerk und aus leipzig-data.de erst nach den Worldskills genauer besprochen werden soll.</li>
 	<li>Das studentische Projektteam (6 Studierende vorwiegend aus geisteswissenschaftlichen Studienrichtungen) konstituiert sich am 25.04.2013 und nimmt die Arbeit auf.</li>
 	<li>Am 22.05.2013 findet eine weitere Runde im Rathaus statt, auf der der aktuelle Stand der Arbeiten am Stadt-JSP vorgestellt wird. Neben den Projekt-Beteiligten sind dabei Ronald Hild und Claudia Förster (Referat für Beschäftigungsförderung), Gunnar Georgi (Stadtjugendring) und Hans-Gert Gräbe (MINT-Netzwerk und leipzig-data.de). Es wird vereinbart, sich in dieser Runde erst wieder nach den WorldSkills zu treffen.</li>
 	<li>Die <a href="http://www.pulpmap-leipzig.de/site/show/overview">Online-Variante</a> des im Auftrag der Stadt erstellten Jugendstadtplans ist pünktlich zu den WorldSkills am Netz.</li>
 	<li>Am 04.07.2013 präsentiert die studentische Gruppe die <a href="http://www.leipzig-data.de/JSP-15">Ergebnisse</a> ihrer Arbeit.</li>
</ul>
<h2>Der Leipzig Data Jugendstadtplan</h2>
<h3>Relevante RDF-Graphen</h3>
<ul>
 	<li><a href="http://leipzig-data.de/RDFData/Jugendstadtplan.ttl">http://leipzig-data.de/RDFData/Jugendstadtplan.ttl</a></li>
</ul>
<h3>Verwendete <a href="http://lov.okfn.org">Namensräume</a></h3>
<ul>
 	<li style="list-style-type: none;">
<ul>
 	<li>ld: http://leipzig-data.de/Data/Model/</li>
 	<li>rdfs: http://www.w3.org/2000/01/rdf-schema#</li>
 	<li>jsp: http://leipzig-data.de/Data/Jugendstadtplan/</li>
</ul>
</li>
</ul>
<h3>Klassen</h3>
Zentral ist die Klasse <strong>jsp:Ort</strong>, die 142 Instanzen von Einrichtungen in Leipzig beschreibt, die für Jugendliche interessant sind. Die Daten wurden 2013 von einer studentischen Projektgruppe gesammelt.Die Informationen sind in vielen Fällen in Englisch und Deutsch vorhanden.

Weitere Klassen:
<ul>
 	<li><strong>foaf:Person</strong> - Autorinnen und Autoren des Jugendstadtplans</li>
 	<li><strong>jsp:ArtDerFreiheit</strong> - Klassifizierung der Barrierefreiheit (gehört zur Klasse jsp:Allgemein - das ist noch nicht weiter konsolidiert)</li>
</ul>
Die restlichen Klassen beschreiben ein Modell zur Einrodnung der einzelnen Einrichtungen, das noch nicht weiter konsolidiert wurde. <strong>
</strong>
<h2>Beschreibung der Prädikate</h2>
<strong>jsp:Ort </strong>- Einrichtung in Leipzig, die für Jugendliche interessant ist. (Stand der Datenerhebung 2013)<strong>
</strong>
<ul>
 	<li>Zentrale Prädikate zur Beschreibung der Einrichtung selbst
<ul>
 	<li>rdfs:label Literal - Bezeichnung</li>
 	<li>foaf:homepage URL - Webseite der Einrichtung</li>
 	<li>jsp:describes ld:Ort, ld:Verein, ld:Unternehmen, ld:Treffpunkt - Verweis auf einen anderen LD-Eintrag, über den insbesondere Adresse und Geokoordinaten inferiert werden können.</li>
 	<li>jsp:hasIrregularOpeningHours Literal - Öffnungszeiten (Stand der Datenerhebung 2013)</li>
</ul>
</li>
 	<li>Barrierefreiheit
<ul>
 	<li>jsp:hasAccessibility <strong>jsp:ArtDerFreiheit</strong> - mit Instanzen jsp:barrierefrei, jsp:eingeschraenktBarrierefrei, jsp:nichtBarrierefrei</li>
 	<li>jsp:AccessibilityComment Literal - Kommentar zur Barrierefreiheit</li>
</ul>
</li>
 	<li>jsp:suppliedBy foaf:Person - Autor des Eintrags</li>
</ul>
<strong>foaf:Person</strong> - Autorinnen und Autoren des Jugendstadtplans
<ul>
 	<li>foaf:name Literal - Name</li>
</ul>

