---
layout: default
title: Post_264
---


[Parent](Page_0)

# Ein verteiltes semantisches soziales Netzwerk

<h1><span id="Das_LD_soziale_Netzwerk" class="mw-headline">Ein verteiltes semantisches soziales Netzwerk für Leipzig </span></h1>
Falls Sie hier Links zu unserem Facebook-Account oder ähnliches erwartet haben, dann sind Sie falsch. Open Data und Freie Sprache erfordern auch ein - technisch adäquat unterstütztes - Konzept Freier Kommunikation.
<h2>Hintergrund</h2>
Ein solches Konzept hat Sebastian Tramp mit <a class="external text" href="http://aksw.org/Projects/DSSN.html" target="‘_blank’">DSSN - Distributed Semantic Social Network</a> entwickelt und Natanael Arndt (beide AKSW-Gruppe an der Uni Leipzig) im Rahmen seines xodx-Projekts grundlegende Komponenten dieser Architektur implementiert.
<ul>
 	<li>Mehr zum Konzept im Aufsatz <a class="external text" href="http://www.semantic-web-journal.net/sites/default/files/swj201_4.pdf" target="‘_blank’">An Architecture of a Distributed Semantic Social Network</a></li>
 	<li>Natanael Arndts <a href="http://lips.informatik.uni-leipzig.de/pub/2013-3">Masterarbeit</a> "Xodx – Konzeption und Implementierung eines Distributed Semantic Social Network Knotens"</li>
 	<li><a href="http://www.leipzig-data.de/Upload/XODXGettingStarted.pdf">Nutzerhandbuch</a></li>
 	<li><a href="https://github.com/white-gecko/xodx/wiki/Issue-Workflow">Issue Reporting</a></li>
</ul>
Ein weiterer spannender Ansatz in dieser Richtung ist <a class="external text" href="http://www.askemos.org" target="‘_blank’">Askemos</a> - ein seit vielen Jahren von Jörg Wittenberger entwickeltes verteiltes System mit ähnlicher Ausrichtung, ohne dass allerdings dort die Frage eines "Social Semantic Stack" so auf den Punkt gebracht wurde wie bei Sebastian Tramp. Gleichwohl ist der Ansatz von Wittenberger fundamentaler: "Askemos enables reliable and justiciable distributed social networks based on executable contracts." und auch philosophisch tiefer verankert. Mehr
<h2>Kurzbeschreibung der Leistungsparameter</h2>
Im Gegensatz zu herkömmlichen sozialen Netzwerken kommen zwei neue Prinzipien zum Einsatz.
<ul>
 	<li>Die föderierte Struktur eines <i>verteilten Netzwerks</i> - die persönlichen Daten liegen auf verschiedenen Knoten im Netz verteilt, die Knoten kommunizieren miteinander über das DSSN-Protokoll. Alle kooperativen Strukturen (perspektivisch: Gruppen, strukturierte Freundeslisten usw.) existieren damit ausschließlich virtuell und können nur zusammengeführt werden, wenn die Knoten miteinander kooperieren.</li>
 	<li>Die <i>semantischen Ausdrucksmöglichkeiten</i> - für die Kommunikation zwischen den Teilnehmern steht (perspektivisch) eine große Bandbreite RDF-basierter Ausdrucksmöglichkeiten zur Verfügung, um spezifische Kommunikationsbedürfnisse auszudrücken.</li>
</ul>
Rico Feist hatte im Rahmen seines Praktikums im Sommersemester 2013 eine Produktivinstanz der xodx-Implementierung aufgesetzt und in einem <a href="http://www.leipzig-data.de/ld-2013-05-30/">Seminarvortrag am 30.5.2013</a> vorgestellt. Die Installation baute auf dem Protokoll auf, das in der AKSW-Gruppe entwickelt und in einer ersten PHP-Version auf der Basis des Ontowiki prototypisch implementiert wurde (Masterarbeit von Natanael Arndt). Alle kommunikativen Akte (Accounts, Friending, Subscription usw.) des jeweiligen Knotens waren als RDF-Sätze formuliert und wurden von der Ontowiki-Instanz des Knotens verwaltet.

Ziel des Probebetriebs war es,
<ul>
 	<li>eigene Erfahrungen mit dem Ansatz in einem komplexeren Feldversuch zu sammeln,</li>
 	<li>Betriebsfehler dieses Alpha-Releases zu finden und</li>
 	<li>Wünsche für weitere Features zu sammeln.</li>
</ul>
<strong>Aktuell wird dieses Teilprojekt nicht weiter verfolgt.</strong>

