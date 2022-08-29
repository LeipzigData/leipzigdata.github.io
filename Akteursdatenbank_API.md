---
layout: default
title: Akteursdatenbank_API
---

# Leipziger Akteursdatenbank - die API

## Allgemeines

Die Anbieter nutzen eine
[webbasierte Erfassungsschnittstelle](https://daten.nachhaltiges-sachsen.de/),
um die entsprechenden Informationen bereitzustellen.  Die Plattform stellt
eine REST-Schnittstelle zur Verfügung, über welche Informationen strukturiert
im JSON-Format ausgelesen werden können.

Auf einzelne Datensätze einer Klasse kann teilweise über deren Klassennamen
und die _id_ zugegriffen werden.

Achtung - die intern vergebenen IDs der Art #(nr) und die _id_ in der REST-API
stimmen nicht überein.

## Schnittstelle

- <https://daten.nachhaltiges-sachsen.de/api/v1/activities.json>
  - Returns an array of all _activity_ objects. They are the core concept of
    this application.
  - Beispielhafter Zugriff auf eine Instanz:
    <https://daten.nachhaltiges-sachsen.de/api/v1/activities/12993.json>

- <https://daten.nachhaltiges-sachsen.de/api/v1/categories.json>
  - Returns an array of all _category_ objects.
  - Activities may belong to one or more categories and subcategories. 

- <https://daten.nachhaltiges-sachsen.de/api/v1/goals.json>
  - Returns an array of all _goal_ objects.
  - Each activity can have one or more goals, think of them as „tags“.
  - The count for each goal_cloud object (?) shows how many activities from
    each category use each goal. Use this to build a tag cloud.

- <https://daten.nachhaltiges-sachsen.de/api/v1/locations.json>
  - Returns an array of all _location_ objects. Locations can be referenced by
    users and activities.
  - Beispielhafter Zugriff auf eine Instanz:
    <https://daten.nachhaltiges-sachsen.de/api/v1/locations/15.json>

- <https://daten.nachhaltiges-sachsen.de/api/v1/regions.json>
  - Returns an array of all _region_ objects.

- <https://daten.nachhaltiges-sachsen.de/api/v1/products.json>
  - Returns an array of all _product_ objects. They are specific to the
    activity type _Filiale_.

- <https://daten.nachhaltiges-sachsen.de/api/v1/trade_categories.json>
  - Returns an array of all <em>trade_category</em> objects. They are specific
    to the activity type _Filiale_.

- <https://daten.nachhaltiges-sachsen.de/api/v1/trade_types.json>
  - Returns an array of all <em>trade_type</em> objects. They are specific to
    the activity type _Filiale_.

- <https://daten.nachhaltiges-sachsen.de/api/v1/users.json>
  - Returns an array of all _user_ objects. 
  - Beispielhafter Zugriff auf eine Instanz:
    <https://daten.nachhaltiges-sachsen.de/api/v1/users/106.json>

## Datenmodell - Übersicht

Im Modell wurden zunächst die zwei Klassen _Akteure_ (<tt>users</tt>) und
_Aktivitäten_ (<tt>activities</tt>) unterschieden, welche über die REST-API
ausgelesen werden können. Eine dritte Klasse _Orte_ (<tt>locations</tt>) wurde
2020 eingeführt. Weitere kleinere Strukturen existieren als Werte einer
morphologischen Tabelle (categories, goals, regions, products, ...), deren
Bedeutung noch genauer beschrieben werden muss.

Im Modell sind weitere Datenstrukturen implizit als Konzepte vorhanden.  Das
ist zum einen eine genauere Aufteilung eines _Akteurs_ in
- die Beschreibung des Akteurs,
- die Adresse,
- der Ansprechpartner und
- die Accountdaten des Ansprechpartners,

die alle in einer gemeinsamen Datenbanktabelle <tt>users</tt> zusammengefasst
sind.

_Aktivitäten_ sind in verschiedene Aktivitätstypen unterteilt, welche durch
den Wert eines speziellen Attributs <tt>type</tt> unterschieden werden.  Neben
generischen Attributen haben die einzelnen Aktivitätstypen weitere spezielle
Attribute, was man in einer zweistufigen (erweiterbaren) Vererbungshierarchie
oder als abstrakten Datentyp (im Sinne etwa von Java Interfaces) als Mengen
von Signaturen beschreiben kann.  Im Weiteren wird die letztere
Darstellungsform verwendet.

Die Klasse __Akteure__ umfasst ein Sublimat aus Informationen zum Akteur
selbst, zu dessen Adresse sowie zu Personen, die für den Akteur als
Ansprechpartner tätig sind.  Es lässt sich nicht unterscheiden, ob zum
Beispiel eine Telefonnummer oder eine Adresse zum Vereinsbüro gehört oder zum
Ansprechpartner.  An anderer Stelle wird aber sehr wohl der Datentyp _Kontakt_
(„Kontakt zur Abholung“ einer Ressource, „Ansprechpartner“ eines
Bildungsangebots) als Teilinterface mit [Name, Email-Adresse, Telefon]
verwendet.

Die Klasse __Aktivitäten__ zerfällt in die Unterklassen <tt>Event</tt>,
<tt>Action</tt>, <tt>Project</tt>, <tt>Service</tt> und <tt>Store</tt>, die
über das Feld <tt>type</tt> unterschieden werden. Später wurden die „Klassen“
<tt>Ressource</tt>, <tt>Bildungsangebot</tt> und <tt>Beratungsangebot</tt> als
Unterklassen von <tt>Service</tt> eingeführt, wobei hier die zusätzliche
Unterscheidung über das Feld <tt>service_type</tt> ausgeführt wird.

In der aktuellen Version werden für einen „einfachen Akteur“ Erfassungsmasken
für die Datensatztypen _Project_, _Event_, _Action_ sowie die drei
Servicetypen _Ressourcen_, _Bildungsangebot_ und _Beratungsangebot_ angeboten.

Zur Unterscheidung der Instanzen werden ID's als numerische Primärschlüssel
der Datenbank verwendet. 

## Beschreibung einzelner Klassen

### Akteure.

In der Collection <tt>users</tt> (Akteure) sind Informationen über Akteure
zusammengefasst, wobei nicht zwischen den juristischen Personen und den für
diese agierenden Personen unterschieden wird.

Prädikate in users.json:
- Akteur
  - id - Integer, URI des user-Objekts
  - name - String, Name der Organisation
  - description - Text
  - organization_type - String (Art der Organisation)
    - Auswahl: corporation (117), freelancer (26), club (134), collective (8),
      other (58), initiative (48), educational (29), foundation (4), null (7)
    - In Klammern Zahl der Instanzen, Stand vom 29.08.2022
  - organization_url - URL, Homepage
  - organization_logo_url - URL, Logo
  - organization_logo_url_base - URL, Logo
- ?? - Checkbox, Handels- oder Gastronomieeinrichtung (nicht mit
  ausgeliefert)
- ?? - Checkbox, veröffentlicht (nicht mit ausgeliefert)
- ?? - Checkbox, aktiv (nicht mit ausgeliefert)
- Adresse (des Akteurs oder des Ansprechpartners?)
  - nur full_address, district (nie initialisiert), latlng, keine location_id
- ?? - Checkbox, Anschrift öffentlich sichtbar (nicht mit ausgeliefert)
- Ansprechpartner
  - first_name - String
  - last_name - String
  - organization_position - String
- Account- und Erreichbarkeitsdaten
  - email - String
  - phone_primary - String
  - phone_secondary - String
  - Passwort (nicht mit ausgeliefert)
- region - Array, region-Objekt (id, name)

### Aktivitäten.

<tt>activities</tt> ist ein Obertyp zu verschiedenen Arten von Aktivitäten
(Aktionen, Events, Projekte, Services, Stores, \ldots), die mit dem Prädikat
<tt>hastype</tt> näher spezifiziert werden.  In der Collection
<tt>activities</tt> sind Informationen über die verschiedenen Typen von
Aktivitäten zusammengefasst, wobei nicht alle Prädikate bei allen Untertypen
verwendet werden. 

Generische Prädikate:
  - id - Integer, URI des Objekts
  - type - String (Typ der Aktivität)
    - Auswahl: Project (84), Service (95), Event (2280), Store (290)
    - In Klammern Zahl der Instanzen, Stand vom 29.08.2022
  - service_type - String (Typ der Aktivität)
    - Auswahl: Projekt, Bildungsangebot, Veranstaltung, Filiale,
      Beratungsangebot
    - 29.08.2022: Doppelt die durch _type_ gegebene Auswahl.
  - user_id - String (Id des beteiligten Akteurs), Auswahl
  - name - String (Titel, Name) 
  - description - Text (Beschreibung) 
  - Adresse (an der die Aktivität stattfindet) - Ortsauswahl, s.u.
  - is_fallback_address - Boolean (Bedeutung unklar)
  - info_url - URL
  - video_url - URL
  - image_url - URL
  - published - Boolean, ist der Eintrag publiziert?
    - Nur publizierte Instanzen werden gelistet  
  - categories - Array, weitere Kategorien (siehe Kategorienkonzept, zu
    ergänzen)  
  - first_root_category - String, Hauptkategorie
  - root_categories - Array, Bedeutung zu klären
  - goals - Array, Bedeutung zu klären
  - region - Array, region-Objekt

Adresse besteht dabei aus:
  - location_id -  Integer, URI des location-Objekts
  - full_address - String, volle Adresse
  - is_fallback_address - Boolean, Bedeutung unklar
  - street_name, home_number, zip, city - die entsprechenden Adress-Elemente
    - Bezug zu den gleichnamigen Adress-Elementen in der location_id ist zu
      klären.
  - latlng - Array (lat,lng)
  - district - Bedeutung unklar, es gibt auch noch _region_.

Weitere Prädikate:
  - start_at - Datum/Zeit
  - end_at - Datum/Zeit
  - duration
  - costs
  - requirements
  - speaker
  - curriculum
  - property_list
  - target_group - (Zielgruppe) String, Freitextfeld
  - costs - (Kosten) String, Freitextfeld
  - requirements - (Bedingungen) String, Freitext-Area
  - speaker - (Referenten) String, Freitextfeld
  - Checkboxen free, child_friendly, accessible, climate_protection
  - goals - (Ziele) Array, Mehrfachauswahl, wird aktuell nicht mit
    ausgeliefert.
  - target_group_selection 
  - target_group - String, Zielgruppe
  - education_type
  - products, trade_categories, trade_types - Arrays, nur für type _Store_ 

Das Folgende ist noch zu überarbeiten:

Weitere Prädikate für Events:
  - start_at - String (mit Auswahl Datum/Zeit hinterlegt)
  - end_at - String (mit Auswahl Datum/Zeit hinterlegt)
  - target_group - (Zielgruppe) String, Freitextfeld
  - costs - (Kosten) String, Freitextfeld
  - requirements - (Bedingungen) String, Freitext-Area
  - speaker - (Referenten) String, Freitextfeld
  - Checkboxen, kostenfrei, kinderfreundlich, barrierefrei (nicht
    mit ausgeliefert) 
  - goals - (Ziele) Array, Mehrfachauswahl, wird aktuell nicht mit
    ausgeliefert.

Weitere Prädikate für Projects:
  - short_description - (Kurzbeschreibung) String, Freitext-Area
  - goals - (Ziele) Array, Mehrfachauswahl
  - property_list - Array, Liste mit speziellen Merkmalen, als
    Freitext-Area, die zeilenweise ausgelesen wird. 

Weitere Prädikate für Services:
  - target_group - String, Zielgruppenbeschreibung
  - costs - String, Kosten
  - requirements - String, Bedingungen
  - short_description - String, Kurzbeschreibung
  - goals - Array
  - service_type - String, Angebotsart (Workshop, Exkursion, Vortrag,
    GTA, Unterrichtseinheit, Beratungsangebot)
  - target_group_selection - String, Auswahl (Kindergarten,
    Grundschule, Sekundarstufe, Erwachsenenbildung)
  - duration - String

Neu gibt es Beratungsangebote und Bidungsangebote, jeweils ohne Feld
„Angebotsart“ 

Weitere Prädikate für Store:
  - short_description - String
  - property_list - Array
  - products - Array
  - trade_categories - Array
  - trade_types - Array

### Orte

2021 wurde eine weitere Klasse __Orte__ ergänzt, die eine akteursübergreifende
Verwaltung von Adressdaten umsetzt. Eine _Adresse_ ist dabei eine implizite
Datenstruktur, die über die API als Menge von Attributen
  - id - Integer, URI des location-Objekts
  - name - String, Bezeichnung
  - zip - PLZ
  - city - Stadt
  - street - Straße mit Hausnummer
  - street_name - Straße
  - house_number - Hausnummer (z.B. auch 16-18)

In der bisherigen Modellierung wurden Adressen grundsätzlich als
Datenaggregate verwaltet, nicht als Datenobjekte.  Wenn zu einer Aktivität
keine Adresse angegeben ist, wird die Adresse aus den Profildaten des Akteurs
übernommen.  Spätere Änderungen dieser Profildaten haben aber aktuell keine
Auswirkung auf diesen Klon.

Es ist eine akteursübergreifende Datenbank zu Orten im Aufbau, aus der häufig
verwendete Adressdaten übernommen werden können.  Auch dies geschieht durch
einfache Übernahme der entsprechenden Attributwerte. Geplant ist, Änderungen
in dieser Datenbasis in die entsprechenden Adressfelder von Aktivitäten (und
auch Akteuren?) zu propagieren, wozu ein System von Backlinks aufgebaut werden
müsste. Unklar bleibt, wie mit zwischenzeitlichen Änderungen umgegangen wird,
die vom Besitzer der Aktivität an den früher übernommenen Adressdaten
vorgenommen worden sind.


### Weitere Teile der Modellierung.

Diese sind noch wenig ausgearbeitet und enthalten oft nur wenige Instanzen pro
Klasse. 
- <tt>categories</tt> repräsentiert eine baumartige Struktur verschiedener
  Tags, die einzelnen Aktivitäten zugewiesen sind. 
- <tt>goals</tt> repräsentiert eine geordnete Liste verschiedener Tags, die
  einzelnen Aktivitäten zugewiesen sind. Das ist als Tagwolke modelliert, kann
  aber - mit Blick auf die Datenqualität - nur von einem Administrator
  erweitert werden. Ist aktuell nicht mit im Editinterface.
- <tt>products</tt> repräsentiert eine Liste verschiedener Produktkategorien,
  die einzelnen Stores zugewiesen werden können.
- <tt>trade_types</tt> und <tt>trade_categories</tt> repräsentieren zwei
  geordnete Listen verschiedener Tags, die einzelnen Store-Objekten zugewiesen
  werden können.
