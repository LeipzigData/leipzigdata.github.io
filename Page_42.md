---
layout: default
title: Post_42
---


[Parent](Page_0)

# Glossar

<h1>Grundlegende Begriffe des Semantic Web</h1>
<h2>Ressource</h2>
Der Begriff "Ressource" im Kontext des Semantic Web weicht etwas ab von der üblichen Verwendungsweise. Eine Ressource steht hier nicht so sehr für ein nutzbares Gut oder einen Rohstoff, sondern allgemeiner für alle möglichen materiellen und immateriellen Dinge und Ereignisse, wie z.B. Gebäude, Plätze und Personen, aber auch Vereine, Firmen und Austellungen. Ganz allgemein gesagt, ist eine Ressource alles, was ein Subjekt in einem Satz sein kann.
<h2>URI</h2>
Die Abkürzung URI steht für "universal resource identifier", d.h. für einen einheitlichen Bezeichner von Ressourcen. Gemeint ist damit, dass man Ressourcen (bzw. "Dinge") immer mit dem gleichen Bezeichner anspricht und das kein Bezeichner doppelt belegt ist. Dies ist wichtig für die automatische Verarbeitung durch Computer und hat also eher technischen Hintergrund.
<h2>RDF</h2>
RDF steht für "Resource Description Framework", was nicht vielmehr bedeutet, als das RDF einige Grundlagen definiert, in welcher Art über "Ressourcen" (oder einfach "Dinge") gesprochen wird bzw. wie wir Tatsachen aufschreiben.
Die Grammatik, die durch RDF vorgegeben wird, folgt einer sehr simplen Struktur. Die Idee ist es, Informationen in in Form von Sätzen aus Subjekt, Prädikate und Objekt zu beschreiben. So zerlegen wir den Satz "Das Gewandhaus befindet sich auf dem Augustusplatz" in das Subjekt "Gewandhaus", das (etwas verallgemeinerte) Prädikat "befindet sich auf" und das Objekt "Augustusplatz". Da also immer drei Komponenten enthalten sind, nennt man solche Sätze auch kurz "Tripel".
Wenn solche Tripel elektronisch gespeichert werden, sollen dabei Subjekt, Prädikat und Objekt durch URIs bezeichnet werden. Das bedeutet im Wesentlichen eigentlich nur, dass die benutzte (formale) Sprache sehr viel ausdrucksärmer ist, als eine natürliche Sprache, die praktisch Synonyme und verschiedene Wortstellung zulässt, obwohl eigentlich immer die gleiche Tatsache gemeint ist.

RDF Daten können als Dateien in verschiedenen Formaten (RDF/XML, Turtle, n-triples, rdf-json u.ä.) wie in unserem Verzeichnis <a href="http://leipzig-data.de/RDFData/">http://leipzig-data.de/RDFData/</a> weitergegeben werden oder/und in einen RDF Triple Store hochgeladen werden.
<h2>RDF Triple Store</h2>
Ein RDF Triple Store präsentiert die verschiedenen RDF-Graphen einer Datensammlung. Wir verwenden einen RDF Store auf <a href="https://virtuoso.openlinksw.com/">Virtuoso-Basis</a>, der mit einer <a href="http://aksw.org/Projects/OntoWiki.html">Ontowiki-Instanz</a> gekoppelt war. Diese wurde im August 2017 wegen ständiger Sicherheitsprobleme abgeschaltet.
<h2>SPARQL</h2>
Hat man eine größere Mengen von Tripeln gesammelt, so stellen diese Tripel ein Auschnitt des Wissens über die Welt dar, bzw. in unserem Fall einen Ausschnitt des Wissens über Leipzig. Da niemand alle diese Tripel durchschauen möchte um relevante Informationen zu finden, liegt es nahe, Frage zu formulieren, wie z.B. "Wo befindet sich das Gewandhaus?", "Welche Kneipen befinden sich in der Karl-Liebknecht-Straße?" oder auch "Welche Ausstellungen werden im Bildermuseum gezeigt?"
SPARQL ist ein Sprachstandard, mit dem man genau solche (und noch komplizierte) Fragen formulieren kann. Da SPARQL wie RDF eine formale Sprache ist, kann ein Computer solche Fragen sehr gut verarbeiten und die Antworten auf diese Fragen finden.
<h2>SPARQL Endpunkt</h2>
Anfragen an einen RDF-Triple Store können über einen SPARQL Endpunkt gestellt werden. Wir betreiben den SPARQL Endpunkt <a href="http://leipzig-data.de:8890/sparql">http://leipzig-data.de:8890/sparql</a>.

