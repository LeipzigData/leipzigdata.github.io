---
layout: default
title: Behoerdenwegweiser
---

<h2>Der Behördenwegweiser der Stadt Leipzig</h2>

Der Behördenwegweiser der Stadt Leipzig wird über den <a
href="https://opendata.leipzig.de/virt-sparql">SPARQL Endpunkt</a> des Open
Data Portals der Stadt Leipzig angeboten. Die folgende Ontologie wurde 2018
aus einer Analyse der Daten auf dem RDF Store extrahiert. Die genaue
semantische Bedeutung der einzelnen Prädikate bleibt weiter zu erschließen.

Es scheint, dass die Daten seit 2012 nicht weiter aktualisiert wurden.

<h2>Relevante RDF-Graphen</h2>
<ul>
  <li><a href="http://leipzig-data.de/RDFData/Behoerdenwegweiser.ttl">http://leipzig-data.de/RDFData/Behoerdenwegweiser.ttl</a> (ein Dump aus dem Open Data Portal)</li>
</ul>
<h2>Verwendete <a href="http://lov.okfn.org">Namensräume</a></h2>
<ul>
  <li>bwd: &lt;https://opendata.leipzig.de/behoerdenwegweiser/data/&gt;</li>
  <li>bws: &lt;https://opendata.leipzig.de/behoerdenwegweiser/schema/&gt;</li>
  <li>foaf: &lt;http://xmlns.com/foaf/0.1/&gt;</li>
  <li>org: &lt;http://www.w3.org/ns/org#&gt;</li>
  <li>rdfs: &lt;http://www.w3.org/2000/01/rdf-schema#&gt;</li>
  <li>skos: &lt;http://www.w3.org/2004/02/skos/core#&gt;</li>
  <li>vcard2006: &lt;http://www.w3.org/2006/vcard/ns#&gt;</li>
</ul>
<h2>Klassen</h2>
<ul>
  <li><strong>bws:Entry</strong> - allgemeine Klasse, die Personen und
    Cross-Referenzen etc. enthält</li>
  <li><strong>org:OrganizationalUnit</strong></li>
  <li><strong>org:Site </strong>- physischer Ort mit Adresse und
    Erreichbarkeit durch ÖPNV</li>
</ul>
<h2>Beschreibung der Prädikate</h2>
<strong>bws:Entry</strong>
<ul>
  <li>foaf:firstName</li>
  <li>foaf:gender</li>
  <li>foaf:lastName</li>
  <li>foaf:title</li>
  <li>org:basedAt</li>
  <li>org:headOf</li>
  <li>org:memberOf</li>
  <li>rdfs:label</li>
  <li>sioc:id</li>
  <li>vcard2006:role</li>
</ul>
<strong>org:OrganizationalUnit</strong>
<ul>
  <li>bws:fax</li>
  <li>bws:amenityBabyChangeRoom</li>
  <li>bws:amenityKidsCorner</li>
  <li>bws:manager</li>
  <li>org:identifier</li>
  <li>org:subOrganizationOf</li>
  <li>rdfs:label</li>
  <li>skos:prefLabel</li>
  <li>vcard2006:email</li>
  <li>vcard2006:photo</li>
  <li>vcard2006:tel</li>
  <li>vcard2006:url</li>
</ul>
<strong>org:Site</strong>
<ul>
  <li>bws:pubTransportBus</li>
  <li>bws:pubTransportCityTrain</li>
  <li>bws:pubTransportTram</li>
  <li>rdfs:label</li>
  <li>vcard2006:locality</li>
  <li>vcard2006:postal-code</li>
  <li>vcard2006:street-address</li>
</ul>

