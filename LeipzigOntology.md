---
layout: default
title: LeipzigOntology
---

<h1>LEO - Die Leipzig Ontology</h1>

Das Leipzig Data Projekt hat sich das Ziel gestellt, einen gewissen Grundstock
an Referenzdaten und insbesondere URIs im RDF-Format zu sammeln, mit denen
sich Ereignisse und Aktiviäten in der Leipziger Stadtlandschaft referenzieren
und damit beschreiben lassen. Mit Blick auf die geringen verfügbaren
Ressourcen liegt der Schwerpunkt dabei auf Daten mit geringem Änderungsbedarf,
die in unserem <a href="https://github.com/LeipzigData/RDFData/">git Repo</a>
vorgehalten werden.

Mit dem Projekt wird der Ansatz verfolgt, Daten möglichst aktuell vorzuhalten,
was nur im Rahmen der verfügbaren Personalressourcen gelingt. In jedem Fall
bedeutet diese Policy,

<p style="text-align: center;"><strong>dass Daten, die als nicht mehr aktuell
identifiziert wurden, aus dem Datenbestand gelöscht werden </strong></p>

und höchstens noch über die git-Historie rekonstruiert werden können.

Nach Abschalten der Linked Data Strukturen nach mehrfachen DOS-Attacken im
August 2017 sind die aus unserem <a
href="https://github.com/LeipzigData/RDFData/">git Repo</a> herunterladbaren
Quellen die primären Datenquellen, die regelmäßig in einen <a
href="https://leipzig-data.de:8890">RDF Data Store</a> geladen werden, über
dessen <a href="https://leipzig-data.de:8890/sparql">SPARQL Endpunkt</a> auf
die Daten zugegriffen werden kann.

<h2>Inhalt dieser Seite</h2>

<ul>
  <li>Übersicht über die einzelnen RDF-Graphen</li>
  <li>Allgemeine Übersicht über den Datenbestand</li>
  <li>Vorhaben in der Diskussion und Bearbeitung</li>
</ul>

<h2>Übersicht über die einzelnen RDF-Graphen</h2>

Die Daten liegen jeweils als RDF-Graphen im Turtleformat vor und werden
außerdem über unseren <a href="http://www.leipzig-data.de:8890/sparql">Sparql
Endpunkt</a> ausgeliefert. Sie sind auch in unserem <a
href="https://github.com/LeipzigData/RDFData">git-Repo</a> verfügbar. Sie sind
nach Sachthemen geordnet:

<ul>
<li><a href="/ontology/AdministrativeGliederung">Administrative Gliederung der
    Stadt Leipzig</a></li>
<li><a href="/ontology/Adressen">Adressen und Geokoordinaten</a></li>
<li><a href="/ontology/Akteure">Akteure, Einrichtungen, Unternehmen, Vereine
    in der Stadt Leipzig</a></li>
<li><a href="/ontology/Events">Ausgewählte Events in der Stadt
    Leipzig</a></li>
<li><a href="/ontology/Hochschulen">Leipziger Hochschuleinrichtungen</a></li>
<li><a href="/ontology/Jugendstadtplan">Jugendstadtplan</a></li>
<li><a href="/ontology/MINTBroschuere">MINT-Broschüre</a></li>
<li><a href="/ontology/Orte">Orte in der Stadt Leipzig</a></li>
<li><a href="/ontology/Referenzen">Referenzen</a></li>
<li><a href="/ontology/Schulen">Schulen der Stadt Leipzig</a></li>
<li><a href="/ontology/sonstiges">Sonstiges</a></li>
<li><a href="/ontology/Stadtverwaltung">Stadt Leipzig
    Verwaltungsstruktur</a></li>
<li><a href="/ontology/Tags">Tags für verschiedene Auszeichnungen</a></li>
</ul>

<h2>Allgemeine Übersicht über den Datenbestand</h2>

Kern dieses Datenbestands sind aktuell <em>Akteure, Orte, Adressen</em> und
<em>Geodaten</em>, die zusammen ein System von <strong>White Pages</strong>
bilden, mit denen Geolokalität auf einheitliche Weise referenzierbar (und
damit auch aufeinander beziehbar) wird. Basis dieses Systems sind die aus dem
API-Leipzig Projekt und damit letztlich von der Stadt Leipzig übernommenen und
weiter aktualisierten über 65.000 Datensätze Adressdaten, von denen knapp
63.000 mit Geokoordinaten (Übernahme aus Nominatim mit anschließender weiterer
Konsolidierung und Qualitätssicherung) versehen sind. Damit lassen sich
Leipziger Orte an Geodaten binden und so auf Karten lokalisieren. Die höhere
Qualität gegenüber eine reinen Referenzierung der Geokoordinaten etwa über die
Google-API ergibt sich aus der vorgenommenen Disambiguierung, die etwa dem
Unterschied zwischen der Verwendung von Rechneradressen und Rechnernamen
entspricht, sowie der Möglichkeit, an diese Adress- oder Orts-URIs weitere
Information zu binden. 

Leipzig Data ist nicht das einzige Projekt mit diesem Anspruch. So kennt etwa
API Leipzig ebenfalls eine größere Zahl von "Hosts" und "Venues" und
OpenStreetMap taggt als "Ways" im Kartenmaterial präsente Gebäude mit
Zusatzinformationen. Für Referenzzwecke ist es wichtig, hier entsprechende
Übersetzungstabellen vorzuhalten und zu verwalten, was für API Leipzig mit den
"API-References" und für OSM mit einem <em>geonames:nearbyFeatures</em>
Verweis nach <a href="http://linkedgeodata.org/About">linkedgeodata.org</a>
erfolgt.

Daneben gibt es <strong>Einzelprojekte</strong>, mit denen Daten aus
verschiedenen Quellen aufbereitet worden sind wie MINT-Orte, Schulen,
Polizeidirektion, Seniorenbüros.

<hr />

Zur Herstellung von Interoperabilität auf Datenebene ist es erforderlich, sich
über das dabei verwendete Vokabular zu einigen. Der relevante
Abstimmungsprozess wurde im Rahmen der Leipzig Data Initiative wenigstens für
längerfristig persistente Datenbestände im <a href="LD-Seminar">Leipzig Data
Seminar</a> verhandelt.

<hr />

<h2>Vorhaben in der Diskussion und Bearbeitung</h2>

<h3>Vorgenommene Änderungen</h3>

Siehe auch die Änderungsanmerkungen in den untergeordneten Webseiten.

<ul>
  <li>HGG 2018-01-07: Aktualisierung der Links in Jugendstadtplan.ttl und
    Ergänzung einiger Geodaten</li>
  <li>HGG 2017-09-12: Einarbeiten von Informationen, die aus jedeschule.de
    extrahiert wurden, in Schulen.ttl</li>
  <li>HGG 2017-09-10: Erweiterung UniversitaetLeipzig.ttl zu Hochschulen.ttl,
    Umbenennungen API-Referenzen.ttl zu Referenzen.ttl sowie StadtLeipzig.ttl
    zu Stadtverwaltung.ttl</li>
  <li>HGG 2017-09-04: Traeger.ttl aufgelöst,
    siehe <a href="ontology/akteure/">Akteure</a></li>
  <li>HGG 2017-08: Abschalten des Linked Data Zugangs zu unseren Daten über
    OntoWiki wegen dauernder DOS-Attacken</li>
  <li>HGG 2013-10-20: Adress-URIs einheitlich in die Form
    Data/&lt;plz&gt;.&lt;ort&gt;.&lt;strasse&gt;.&lt;nr&gt; gebracht,
    Straßenübersicht aus Adressen.ttl entfernt</li>
  <li>HGG 2013-03-24: ical:sentBy foaf:Agent ergänzt. foaf:Agent Instanzen bei
    Traeger.ttl ergänzt</li>
  <li>ld:relatedBundle hat als rdfs:range nun ld:Ort oder ld:Traeger</li>
  <li>ical:contact als Literal für Kontaktinformation</li>
  <li>HGG 2013-03-10: Strassenverzeichnis.ttl aus Adressen.ttl</li>
  <li>HGG 2013-03: WeitereAdressen.ttl aufgebaut</li>
  <li>HGG 2013-04-12: Personen nach foaf transformiert</li>
  <li>Namensraum 'cal:' nach standardmäßiger Benennung 'ical:' umgesetzt.</li>
</ul>
<h3>Fragen und Vorhaben in Diskussion</h3>
<ul>
  <li>Das Adressverzeichnis ist nicht vollständig, es fehlt zum Beispiel die
    gesamte Georg-Schwarz-Straße.</li>
  <li>Tagging in Richtung Key-Value-Paare weiterentwickeln wie bei den OSM Map
    Features <a href="http://wiki.openstreetmap.org/wiki/Map_Features"
    target="‘_blank’">http://wiki.openstreetmap.org/wiki/Map_Features</a>
  </li>
  <li>Infos zu einzelnen Einträgen, die sich nicht strukturiert abbilden
    lassen, werden dem Eintrag als rdfs:comment zugeordnet.</li>
</ul>

