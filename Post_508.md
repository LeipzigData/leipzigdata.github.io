---
layout: default
title: Post_508
---


# Seminar am 5.11.

<strong>Zeit:</strong> 5.11.2013, 11:15-12:45 Uhr
<strong>Ort:</strong> Raum A-531 im Augusteum der Universität Leipzig, Augustusplatz 10.

<em>Open Streetmap und Leipzig Data</em>
mit Claus Stadler (unser <a href="http://wiki.openstreetmap.org/wiki/Nominatim">Nominatim</a>-Experte) und Fabian Schmidt (Leipziger Mapper)

Anmerkungen zur Diskussion siehe unsere <a title="Open Streetmap" href="http://www.leipzig-data.de/open-streetmap/">OSM-Seite</a>.

<strong>Abstract</strong>

Leipzig Data enthält eine umfassende Sammlung von Adressen in der Stadt Leipzig (vom Typ ld:Adresse, derzeit 65.209), die initial aus API Leipzig und damit aus städtischen Daten übernommen und inzwischen mit weiteren Adressen angereichert wurden. Weitere Adressdaten (vom Typ ld:ExterneAdresse, derzeit 16) zu Orten im unmittelbaren Umfeld von Leipzig, die projektrelevant sind, wurden ebenfalls gesammelt. Im der letzten Leipzig Data Redesign (20.10.2013) wurden die URI-Namensraumstandards beider Sammlungen harmonisiert.

Claus Stadler hat zu diesen Adressdaten über Nominatim Geo-Koordinaten bestimmt (Wissensbasis GeoDaten). Dabei wurde ein weiterer Eintrag <em>geonames:nearbyFeatures</em> extrahiert, der auf ein OSM-Objekt verweist, welches nahe bei diesem Punkt liegt. Die genaue Semantik dieses Eintrags ist noch zu klären. Insbesondere ist abzuklären, was diese Semantik mit der "üblichen" Adress-Semantik zu tun hat, wie sie sich aus dem Begriff des <a href="http://de.wikipedia.org/wiki/Kataster">Katasters</a> ergibt. Zu 2167 Adressen und allen 16 externen Adressen ist ein solcher Eintarg noch zu bestimmen.

Derartige automatisch bestimmten Daten enthalten oft Fehler, zufällige und systematische, die im Zuge nachfolgender Qualitätskontrollen zu reduzieren sind. Dies geschah und geschieht vor allem im Zuge der Verwendung dieser Informationen im Events-Teilprojekt.

Daneben wurden weitere Geokoordinaten "per Hand" gesammelt und in einer Wissensbasis WeitereGeoDaten abgelegt, um deren Unabhängigkeit vom Neuaufbau der Wissensbasis GeoDaten aus Nominatim mit einem verbesserten Algorithmus zu gewährleisten. Aktuell sind Geokoordinaten zu 2163 Adressen und 15 externen Adressen nicht bekannt.

Im Seminar soll diskutiert werden, wie eine engere Verbindung zwischen den Datensammlungen von Leipzig Data und den Leipzig bezogenen Daten von OSM erreicht werden kann.

Siehe auch frühere Aufzeichnungen zu <a title="Open Streetmap" href="http://www.leipzig-data.de/open-streetmap/">Open Stretmap und Leipzig Data</a>.

