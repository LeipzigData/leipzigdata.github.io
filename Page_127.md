---
layout: default
title: Post_127
---


[Parent](Page_0)

# Gelbe Seiten

<h1>Teilprojekt "Gelbe Seiten"</h1>
<h2>Worum geht es?</h2>
Ein wichtiger Bestandteil des Kernbestands von Leipzig Open Data ist die plattformübergreifende Identifizierung von Aktivitäten, natürlichen und juristischen Personen, Orten, Projekten und Events, über welche in Leipzig gesprochen wird. Um diese Gespräche technisch begleiten zu können, muss jede dieser "Ressourcen" (so der Oberbegriff in der Fachsprache) eine eindeutige URI zugewiesen bekommen, mit der sich erst Gespräche auf <i>Dasselbe</i> beziehen können. Für den Computer ist es weitgehend egal, ob URIs die Form 'xaferwgbatrceg12raf' oder 'Mueller_Peter' haben. Letztere sind für Menschen natürlich einfacher zu handhaben und tragen auch schon <i>ein gewisses Maß</i> an Information, auch wenn es in Leipzig mehrere "Peter Müller" geben mag. Deshalb auch "gelbe Seiten" - Anreicherung mit wenig allgemeiner Information, um die Ressource für einen "durchschnittlichen Leipziger Bürger" identifizierbar zu machen. Unsere erste Regel also: Wähle URIs, die "human readable" (und "machine readable" - also keine Umlaute etc.) und "sprechend" sind - folge also einem <i>Namensschema</i>, das im Bereich der <a title="Ontology" href="http://www.leipzig-data.de/ontology/">Ontologie</a> jeweils ausgewiesen ist.
<h2>Plattformen Leipziger Akteure</h2>
Jede Plattform hat eigene Methoden entwickelt, eine solche Identifizierung zu unterstützen. Meist werden hierfür <em>Primärschlüssel</em> in Datenbanken verwendet, die aber nicht von außen sichtbar sind. Derartige Primärschlüssel können - zusammen mit ausgewählten Informationen über das bezeichnete Objekt - über einen Webservice z.B. als JSON-Objekt verfügbar gemacht werden.

Das Leipzig Data Projekt unterstützt die Bemühungen, Plattformen einzelner Leipziger Akteure miteinander zu vernetzen. Dafür eignen sich semantische Technologien besonders gut. Im Rahmen der <a href="https://github.com/LeipzigData/Tools">Leipzig Tools</a> werden <strong>semantische Webservices</strong> für einzelne Plattformen als "best practise" Beispiele  entwickelt, die dort  ausgerollt werden können und relevante Informationen über Akteure, Events, Services usw. ausliefern.
<h3>Beschreibung des Webservice</h3>
Der Webservice kann auf die übliche Weise über &lt;Basisadresse&gt;/getdata.php?show=&lt;RDF-Graph&gt; angesprochen werden, unter Linux etwa als
<p style="text-align: center;">curl &lt;Basisadresse&gt;/getdata.php?show=events</p>
Mit dem Zusatzargument "embedded=true" wird der RDF-Graph als HTML-Seite zurückgegeben, die in eine Webseite zur Inspektion der Daten integriert werden kann. Eine solche Darstellung ist zu Demonstrationszwecken als Übersicht über die jeweils verfügbaren RDF-Graphen unter &lt;Basisadresse&gt;/index.php integriert. Zur direkten Weiterverwendung als RDF-Graph ist diese Darstellung aber nur bedingt geeignet.
<h3>Testinstallationen</h3>
Da es schwierig ist, Webservices in eine Plattform zu integrieren, die dafür ursprünglich nicht konzipiert wurde, haben wir einen Testserver aufgesetzt, mit dem die Möglichkeiten derartiger Datenintegrationen auf einem Dump der jeweiligen Plattform ausprobiert werden können. Da derartige Datentransformationen als sozio-technisches Projekt vor allem von der Kommunikation und gemeinsamen Entscheidungsfindung aller interessierter Seiten leben, bitten wir Interessenten, mit uns (<a href="http://bis.informatik.uni-leipzig.de/HansGertGraebe/">Prof. Hans-Gert Gräbe</a>, Matthias Petzold) Kontakt aufzunehmen, um das weitere gemeinsame Vorgehen abzustimmen.

Inzwischen haben die Leipziger Ecken den Webservice unter der Basisadresse auf ihrer Produktivinstanz ausgerollt, die Plattform "Nachhaltiges Leipzig" stellt einen (aktuell noch nicht öffentlich dokumentierten) REST-Service zur Verfügung. Wir sind dabei, die Webservices entsprechend umzubauen.

Aktuell sind Webservices zu folgenden Plattformen verfügbar:
<ul>
 	<li><a href="https://leipziger-ecken.de/">Leipziger Ecken</a>
<ul>
 	<li>Basisadresse Demo-Instanz: http://pcai042.informatik.uni-leipzig.de/~graebe/le-rdf/</li>
 	<li>Basisadresse Produktiv-Instanz: https://leipziger-ecken.de/Data/</li>
 	<li>RDF-Graphen: adressen, akteure, events, sparten</li>
 	<li>Link zur <a href="http://pcai042.informatik.uni-leipzig.de/~graebe/le-rdf/">Demo-Webseite</a> des Webservice</li>
</ul>
</li>
 	<li><a href="https://daten.nachhaltiges-leipzig.de/">Nachhaltiges Leipzig</a>
<ul>
 	<li>Basisadresse: http://pcai042.informatik.uni-leipzig.de/~graebe/nl-rdf/</li>
 	<li>RDF-Graphen: ld-adressen, akteure, ld-akteure, aktionen, changes, events, projects, services, stores</li>
 	<li>Link zur <a href="http://pcai042.informatik.uni-leipzig.de/~graebe/nl-rdf/">Demo-Webseite</a> des Webservice</li>
</ul>
</li>
</ul>
<h2>Relevante Teilprojekte</h2>
<ul>
 	<li><a title="LD.Events" href="http://www.leipzig-netz.de/index.php5/LD.Events">Eventsprojekt</a> (nicht aktuell)</li>
 	<li><a title="Jugendstadtplan" href="http://www.leipzig-data.de/jugendstadtplan/">Jugendstadtplan</a></li>
</ul>
<h2>Weitere Vorhaben</h2>
<ul>
 	<li>Kontakt mit <a href="http://www.sportinleipzig.de" target="‘_blank’">http://www.sportinleipzig.de</a> - Wollen Zugriff auf ihre Seiten über eine REST-API ermöglichen, dann kann man weiter schauen, wie das zu integrieren ist. Kontakt über Phillip Klose.</li>
 	<li>OSM-Projekte</li>
</ul>
&nbsp;

