--
layout: default
title: Page_468
---

## Parent: [0](Page_0)

# Lizenzfragen

<h1>Offene Daten und Lizenzen</h1>
<h2>Grundlegende Herangehensweise</h2>
Der <a href="http://leipzig-data.de/RDFData/">Kernbestand von Daten</a>, der in unserem <a href="https://github.com/LeipzigData">github-Repo</a> frei verfügbar ist, besteht aus Daten, die innerhalb des Projekts und seiner Vorläufer selbst erhoben oder von Projektpartnern (insbesondere API Leipzig) unter der Bedingung übernommen wurden, dass diese Daten unter der <a href="http://creativecommons.org/publicdomain/zero/1.0/deed.de">CC_0-Lizenz</a> veröffentlicht werden. Dies ist zugleich die im Projekt präferierte Lizenz.

Allerdings können nicht alle Daten unter dieser Lizenz zur Verfügung gestellt werden, da einzelne Wissensbasen auf wesentlichen Vorarbeiten aufbauen (also <em>abgeleitete Werke</em> im Sinne des Urheberrechts sind), die nur unter strikteren Auflagen weiter verbreitet werden dürfen. Dies gilt vor allem für die Geodaten, die zum großen Teil aus dem Open Streetmap Projekt <a href="http://wiki.openstreetmap.org/wiki/Nominatim">Nominatim</a> extrahiert wurden, so dass diese Wissensbasis nur unter der (restriktiveren) <a href="http://www.openstreetmap.org/copyright">OSM-Lizenz </a>weiterverwendet werden darf.

Um diese Feinheiten zu berücksichtigen, werden Lizenzinformationen auf der Ebene von Wissensbasen in der Form
<blockquote><code>&lt;theDataBase&gt;
cc:license &lt;http://creativecommons.org/publicdomain/zero/1.0/&gt; ;
cc:attributionName "The Leipzig Open Data Project" ;
cc:attributionURL &lt;http://leipzig-data.de&gt; .
</code></blockquote>
verwaltet, wobei unter <code>cc:license</code> ein Link auf die für die jeweilige Wissensbasis gültige Lizenz eingetragen ist.
<h2>Allgemeine Überlegungen</h2>
Von Anfang legt das Leipzig Data Projekt ein klares Augenmerk auf die rechtlichen Fragen, um den Intentionen des freizügigen Zugangs und der freizügigen Verwendung der entsprechenden Daten im Kontext rechtlicher Rahmenbedingungen Ausdruck zu verleihen. Hierfür sind insbesondere relevant
<ul>
	<li>Das <a href="http://sciencecommons.org/projects/publishing/open-access-data-protocol">Science Commons Protocol</a></li>
	<li>Die <a href="http://opendatacommons.org/licenses/pddl/1-0/">ODC Public Domain Dedication and Licence</a> (PDDL)</li>
	<li>Die Erfahrungen des <a href="http://creativecommons.org/science">CC-Science-Projekts </a></li>
</ul>
Über passende rechtliche Rahmen eines Public Domain (Öffentlichen Bereichs) ist in den letzten Jahren <a href="http://wiki.creativecommons.org/Public_domain">viel diskutiert</a> worden. Im Ergebnis hat sich die <a href="http://creativecommons.org/publicdomain/zero/1.0/deed.de">CC_0-Lizenz</a> etabliert als die genaueste Weise, den Public Domain Gedanken im heutigen weltweiten Rechtssystem auszudrücken.
<blockquote>At present, one of the only ways to be certain that a particular work is in the public domain worldwide is to see if the copyright holder has dedicated all rights to the work to the public domain by using CCO. (<a href="http://wiki.creativecommons.org/Public_domain">Quelle</a>)</blockquote>
Ein im Rahmen der Initiative <em>Leipzig Data</em> zusammengetragener und fortgeschriebener Kerndatenbestand wird unter dieser Lizenz frei verfügbar sein.
<h2>Weitere Diskussionen und Links zum Thema</h2>
<ul>
	<li><a href="http://blog.offeneskoeln.de/2012/02/abmahnung-und-selbstzensur">Abmahnverfahren</a> für "Offenes Köln"</li>
	<li><a href="https://github.com/fraunhoferfokus/ogd-metadata/tree/master/lizenzen/BMI">Deutschlandlizenzen</a>, die für Open Government Data zum Einsatz kommen sollen (Januar 2013)
<ul>
	<li><a href="http://urheberrecht.wikimedia.de/2013/01/open-data-datenlizenz-bmi/ ">Debatte</a> dazu bei Wikimedia</li>
	<li><a href="http://www.e-demokratie.org/gedanken-ideen/bmi-reagiert-auf-kritik-an-den-vorgestellten-open-data-nutzungsbestimmungen/">Debatte</a> dazu bei e-demokratie.org</li>
</ul>
</li>
</ul>

