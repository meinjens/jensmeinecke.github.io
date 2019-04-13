---
layout: post
title: Erster Testlaufs des Antriebs
tags: [raspberrypi, pondpi]
comments: true
---

<p id="section-Erster+Test+des+Antriebs-Lösung">Wir haben uns für den zwei Motorenantrieb entschieden. Mit Hilfe der kostengünstigen L298N H-Brücke lässt sich der zudem sehr einfach umsetzen. Auch für die Größe und die Navigationseigenschaften schien uns das der geeignete Antrieb zu sein.</p>
<p>Dabei hat uns auch das tolle Projekt <a href="http://www.cardboard-car.com" target="_blank" rel="noopener">Cardboard Car</a> inspiriert. Dort finden sich sowohl Bauanleitungen mit Tipps und Tricks, die sich wunderbar auf unser Projekt übertragen lassen.</p>
<p><!--more--></p>
<h2 id="section-Erster+Test+des+Antriebs-Bauteile">Bauteile</h2>
<ul>
<li><a href="http://www.amazon.de/dp/B015SQ57VC" target="_blank" rel="noopener">L298N H-Brücke</a></li>
<li>2 x <a href="https://www.respotec.de/motore-und-pumpen/motore-gleichstrom/motor-116037044.php" target="_blank" rel="noopener">12V Gleichstrommotor von Bühler</a></li>
<li>12V Netzteil zum Testen der Motoren</li>
<li>5V Netzteil für den Raspberry Pi</li>
<li>Raspberry Pi 2 Model B</li>
<li>Kabel</li>
</ul>
<h2 id="section-Erster+Test+des+Antriebs-Software">Software</h2>
<p>Um die Motoren zu steuern, haben wir die Software vom <a href="http://www.cardboard-car.com/software" target="_blank" rel="noopener">Cardboard Car</a> verwendet. Auf der Seite finden sich Testprogramme für die L298N Bridge.</p>
<h2 id="section-Erster+Test+des+Antriebs-Verschaltungsplan">Schaltplan</h2>
<p>Auf dem Schaltplan symbolisiert das Akkupack unsere 12V Stromquelle.</p>
<p><a href="http://meinjens.de/wp-content/uploads/2016/04/Schaltung-Motorsteuerung_Steckplatine.png"><img class="alignnone wp-image-79 size-medium" src="http://meinjens.de/wp-content/uploads/2016/04/Schaltung-Motorsteuerung_Steckplatine-300x247.png" alt="Schaltung der Motorsteuerung" width="300" height="247" /></a></p>
<h2>Belegung der GPIOs</h2>
<p>Die Belegung der GPIOs haben wir im ersten Schritt übernommen. In der Software kann die Pinbelegung angepasst werden.</p>
<p>[table id=1 /]</p>
<h2>Probleme</h2>
<p id="section-Erster+Test+des+Antriebs-Fazit">Es gab erst Probleme mit der Leistung der Motoren. Es stellte sich aber recht schnell heraus, dass es an der Versorgungsspannung vom Netzteil lag. Wir hatten unterschiedliche Netzteile ausprobiert. Offensichtlich gab es da Unterschiede.</p>
<h2>Testlauf</h2>
<p>Beim ersten Testlauf haben wir zwei andere 12V Elektromotoren zum Testen gewählt. Das funktionierte genau so gut.</p>
<p>[video width="1280" height="720" mp4="http://meinjens.de/wp-content/uploads/2016/04/IMG_0935.mp4" preload="auto"][/video]</p>
<h2>Fazit</h2>
<p>Die Motoren lassen sich sehr gut und stabil steuern. Durch die Implementierung in Python können wir dies wunderbar in das Gesamtsystem integrieren.</p>
