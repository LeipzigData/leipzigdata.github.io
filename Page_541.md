---
layout: default
title: Post_541
---


[Parent](Page_0)

# Exhibit-Framework

<h1>Filtern und Suchen in RDF-basierten Informationen mit Exhibit</h1>
Web-Anwendungen müssen die erforderlichen Daten vom Webserver zum Browser übertragen, wobei insbesondere massive kleinteilige HTTP-Anfragen mit hoher Redundanz zu ernsthaften Performance-Problemen führen. Deshalb versucht man, strukturierte Informationen in größeren Stücken einmalig zu übertragen und mit entsprechender Logik auf der Browserseite (verschiedene Rich Client Konzepte) dort auch komplexere Szenarien wie Such- und Filterprozesse umzusetzen.

Die Präsentationsschicht moderner Web-Anwendungen verwendet dazu häufig Javascript-Frameworks und JSON-Datenobjekte. Diese Konzepte sind weitgehend unabhängig von der Datenhaltung einsetzbar. Das vom Server auszuliefernde JSON-Objekt kann aus RDF-basierten Daten über eine Sparql-Anfrage (konzeptionell vergleichbar mit einer SQL-Anfrage an eine lokale Datenbank) auf ähnliche Weise erzeugt werden wie in klassischen Webanwendungen auf SQL-Basis.

Dieser Ansatz wurde im Rahmen von Leipzig Data prototypisch mit dem Javascript-Framework <a href="http://simile-widgets.org/wiki/Getting_Started_with_Exhibit" target="‘_blank’">Exhibit</a> von <strong>Johannes Frey</strong> umgesetzt und in zwei konkreten Teilprojekten
<ul>
	<li>Teilprojekt Energiekarte (Präsentation ist aus Datenschutzgründen nicht online verfügbar)</li>
	<li>Teilprojekt <a href="http://www.leipzig-data.de/widget/">Events-Widget</a></li>
</ul>
eingesetzt.
<ul>
	<li><a href="http://leipzig-data.de/Upload/Event-Widget.pdf" target="‘_blank’">Dokumentation</a></li>
</ul>
Die Quellen sind im <a href="https://github.com/LeipzigData/Tools">Leipzig Data Tools Repo</a> verfügbar.

