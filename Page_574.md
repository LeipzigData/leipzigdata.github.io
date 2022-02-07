---
layout: default
title: Post_574
---


[Parent](Page_0)

# Wordpress Management

<h2>Wordpress-Management</h2>
Im Rahmen von Leipzig Data nutzen wir Wordpress als Präsentations-Engine und entwickeln dafür eine Reihe von Anbindungen unserer Werkzeuge und Konzepte an Wordpress. Auf dieser Seite ist der grundlegende Aufbau einer dabei unterstützten Wordpress-Instanz beschrieben.
<h3>Installation und Konfiguration</h3>
Wir haben gute Erfahrungen damit gemacht, Wordpress direkt aus dem offiziellen SVN-Repo heraus zu installieren. Eine <a href="http://codex.wordpress.org/Installing_WordPress">genauere Beschreibung</a> findet sich auf den Wordpress-Seiten. Wir gehen weiter davon aus, dass das System mit Permalinks konfiguriert ist, um mit sprechenden Link-Namen statt Post-Nummern zu arbeiten.

Wesentliche Elemente der Anpassung von Wordpress an lokale Gegebenheiten sind über das gewählte und modifizierte <strong>Thema</strong> (dort insbesondere über die Datei functions.php) sowie über installierte <strong>Plugins</strong> möglich.

Die weitere Beschreibung geht vom grundsätzlichen Design eines Themas der von Wordpress mitgelieferten Twenty-Reihe aus (Kopfbereich, Menüleiste, Textbereich und ggf. Sidebar, Fußbereich), in der Menüs und Widgets direkt durch den Administrator ohne weitere Modifikationen auf php-Ebene konfiguriert werden können.
<h3>FAQ und Tipps</h3>
<ul>
	<li><a href="http://codex.wordpress.org/Debugging_in_WordPress">Debug</a>-Modus: kann in der Datei wp-config.php eingeschaltet werden. Nach WP_DEBUG suchen.</li>
	<li>Zahl der <a href="http://codex.wordpress.org/Revisions">Revisionen</a> beschränken: etwa <tt>define('WP_POST_REVISIONS',30)</tt></li>
</ul>
<h3>Grundsätzlicher Seitenaufbau</h3>
Seiten werden über die entsprechenden Seitentemplates aufgebaut. Die typische Struktur eines Seitentemplates kann am Aufbau von page.php studiert werden: Die Einzelteile der Seite werden über verschiedene php-Dateien erzeugt und hier zusammengebaut
<ul>
	<li>get_header() - ruft header.php auf:
<ul>
	<li>HTTP-Header (mit Meta-Informationen wie Titel und Stylesheets)</li>
	<li>Seiten-Header (Beginn der div-id <em>page</em>, diese schließt in footer.php<em>)</em>
<ul>
	<li>div-id <em>header-bar</em></li>
	<li>div-id <em>header-img</em></li>
	<li>div-id <em>header-menu: </em>Hier sind die Menüs einzubinden, die über den Admin-Account weiter konfiguriert werden können. Diese müssen in functions.php in der <tt>function register_my_menus()</tt> registriert werden.</li>
</ul>
</li>
</ul>
</li>
	<li>Aufbau des Textbereichs</li>
	<li>optional get_sidebar() - Aufbau des Sidebar (für einspaltiges Layout auskommentieren)</li>
	<li>get_footer() - ruft footer.php auf:
<ul>
	<li>div-id <em>footer</em> mit standardmäßigen Links auf drei Seiten</li>
	<li>div-id <em>page</em> wird geschlossen</li>
	<li>Aufruf der <a href="http://codex.wordpress.org/Function_Reference/wp_footer">Funktion <tt>wp_footer()</tt></a></li>
</ul>
</li>
</ul>
<h3>Layout-Steuerung über CSS</h3>
Die aktiven Stylesheets (default: style.css) werden in der Datei header.php im Titel-Bereich eingebunden.

