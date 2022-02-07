---
layout: default
title: Post_338
---


[Parent](Page_0)

# Event-Vorlage

<h2 style="text-align: left;">Vorlage für Events</h2>
Events werden im LD.Events-Projekt als RDF-Daten verwaltet. Ein verbreitetes Format dafür ist das Turtle-Format, das in den folgenden Beispielen verwendet wird. - todo: genauer erklären -

Events können noch genauer beschrieben werden (etwa Zugehörigkeit zu einer Reihe). Details dazu sind in <a title="Ontology" href="http://www.leipzig-data.de/ontology/">LEO - die Leipzig Ontology</a> zu finden.
<pre>&lt;http://leipzig-data.de/Data/Event/Event-ID&gt; a ld:Event ;
rdfs:label "Titel" ;
ld:hasURL &lt;http://EineURL&gt; ;
ld:description "Text ohne Zeilenumbruch, ggf. mit XHTML-Auszeichungen" ;
ical:dtstart "Datum im xsd:date oder xsd:datetime Format" ;
ical:location "Ort oder Orts-URI" ;
ical:organizer "Organisator oder Org.-URI" ;
ical:dtend "ggf. Ende, Format wie ical:dtstart" ;
ld:hasAddressAddendum "Adresszusatz (bei Orts-URI, die nicht genau auflöst)" ;
ical:summary "Kurzbeschreibung" .</pre>
<h2 style="text-align: left;"></h2>
<h2 style="text-align: left;">Ein Beispiel</h2>
<pre>&lt;http://leipzig-data.de/Data/Event/ASG.2013-04-23&gt; a ld:Event ;
rdfs:label "Alfred Nobel – die Verantwortung des Wissenschaftlers" ;
ld:hasTag ldtag:ASG ;
ld:hasURL &lt;http://www.leipzig-netz.de/index.php5/MINT.Schuelerakademie.2013-04-23&gt; ;
ld:description "Die Leipziger Schülerakademie lädt interessierte Schülerinnen und Schüler der Oberstufe ein ..." ;
ical:dtstart "2013-04-23T16:00:00+01:00" ;
ical:location ldo:HfTL ;
ical:organizer ldo:ASG ;
ical:dtend "2013-04-23T17:30:00+01:00" ;
ld:hasAddressAddendum "HfTL, Raum B-1.50" ;
ical:summary "Alfred Nobel – die Verantwortung des Wissenschaftlers. Mit Dr. Roland Boran." .</pre>

