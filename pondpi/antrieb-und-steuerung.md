---
layout: page
title: Antrieb und Steuerung
---

<!-- wp:heading -->
<h2 id="section-Antrieb+und+Steuerung-Anforderungen">Anforderungen</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><li>kräftiger und geräuscharmer Antrieb</li><li>stromsparender Antrieb mit max. 12V</li><li>präzise Navigation mit Halten einer Position</li><li>Schutz der Schraube vor Pflanzen oder Grundberührung</li><li>Kostengünstig</li></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="section-Antrieb+und+Steuerung-Art+des+Antriebs">Art des Antriebs</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3><strong>Schottelantriebe</strong></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Die beste Navigation hinsichtlich Kraft und Präzision ist wohl der Schottelantrieb. Damit lässt sich das&nbsp;Schiff in jede Richtung navigieren und damit auch die Position bei Wind und Wetter gut halten. Schottelantriebe gibt es z.B. von Graupner. Diese sind jedoch nicht ganz billig. Für unseren Fall würden wir auch mindestens zwei benötigen.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><strong>Schraubenantrieb mit Ruder</strong></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Beim Antrieb mit Schraube und Ruder würden wir ebenfalls zwei verbauen (in jeden Ausleger einen Motor und Ruder). Die Motoren würden gegenläufig laufen und die Ruder müssten synchronisiert werden, damit das Schiff geradeaus fährt.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><strong>Doppelschraube ohne Ruder</strong></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Eine elegante und einfache Variante ist die Verwendung der Motoren zur Steuerung des Schiffes. Die Motoren werden dabei individuell vorwärts und rückwärts gesteuert. So kann das Schiff ähnlich wie ein Panzer auf der Stelle wenden.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="section-Antrieb+und+Steuerung-Treiber+für+die+Motoren">Treiber für die Motoren</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Im Modellbau werden zur Steuerung der Drehzahl der Motoren sogenannte Fahrtenregler verwendet. Da der Raspberry Pi die Steuerung übernehmen soll bietet sich hier eine andere Möglichkeit. Das Projekt <a href="http://www.cardboard-car.com/top-story/raspberry-pi-motorsteuerung-mit-einem-motortreiber-l298n-h-bridge/7298">Cardboard Car zeigt hier die Anwendung einer L298N H-Brücke</a> zur Kontrolle der Motoren. Wir müssen ähnlich wie in dem Projekt zwei Motoren getrennt voneinander kontrollieren. Dies schien uns also als geeigneter Ansatz.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="section-Antrieb+und+Steuerung-Schutz+gegen+Fremdkörper">Schutz gegen Fremdkörper</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Damit die Schrauben gegen Fremdkörper geschützt werden, sparen wir die Ausleger am Ende des Rumpfes jeweils aus und montieren dort die Schrauben. Anschließend wird der Rumpf mit einem Metallgitter verlängert so dass die Schrauben vollständig hinter dem Metallgitter geschützt sind.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="section-Antrieb+und+Steuerung-Auswahl+der+Motoren">Auswahl der Motoren</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Bei der Auswahl der Motoren gab es ebenso eine große Vielfalt. Es musste auf jeden Fall ein Gleichstrommotor mit maximal 12 Volt sein.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="section-Antrieb+und+Steuerung-Entstörung+der+Elektromotoren">Entstörung der Elektromotoren</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Wir wissen noch nicht, ob das für uns relevant ist. Einige Modellbauer entstören ihre Motoren um so Störfrequenzen zu vermeinden. Diese <a href="http://www.bnhof.de/~ho1645/entstoer.htm">Anleitung</a>&nbsp;beschreibt sehr gut wie das funktioniert.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Entscheidung</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Wir haben uns letztendlich für die Doppelschraube ohne Ruder entschieden.&nbsp;Im Zusammenspiel mit dem Motortreiber ist das eine gute und günstige Kombination.</p>
<!-- /wp:paragraph -->