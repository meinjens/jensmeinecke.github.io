Wir haben uns für den zwei Motorenantrieb entschieden. Mit Hilfe der kostengünstigen L298N H-Brücke lässt sich der zudem sehr einfach umsetzen. Auch für die Größe und die Navigationseigenschaften schien uns das der geeignete Antrieb zu sein.

Dabei hat uns auch das tolle Projekt [Cardboard Car](http://www.cardboard-car.com) inspiriert. Dort finden sich sowohl Bauanleitungen mit Tipps und Tricks, die sich wunderbar auf unser Projekt übertragen lassen.

## Bauteile

*   [L298N H-Brücke](http://www.amazon.de/dp/B015SQ57VC)
*   2 x [12V Gleichstrommotor von Bühler](https://www.respotec.de/motore-und-pumpen/motore-gleichstrom/motor-116037044.php)
*   12V Netzteil zum Testen der Motoren
*   5V Netzteil für den Raspberry Pi
*   Raspberry Pi 2 Model B
*   Kabel

## Software

Um die Motoren zu steuern, haben wir die Software vom [Cardboard Car](http://www.cardboard-car.com/software) verwendet. Auf der Seite finden sich Testprogramme für die L298N Bridge.

## Schaltplan

Auf dem Schaltplan symbolisiert das Akkupack unsere 12V Stromquelle.

[![Schaltung der Motorsteuerung](http://meinjens.de/wp-content/uploads/2016/04/Schaltung-Motorsteuerung_Steckplatine-300x247.png)](http://meinjens.de/wp-content/uploads/2016/04/Schaltung-Motorsteuerung_Steckplatine.png)

## Belegung der GPIOs

Die Belegung der GPIOs haben wir im ersten Schritt übernommen. In der Software kann die Pinbelegung angepasst werden.

<table id="tablepress-1" class="tablepress tablepress-id-1 gpio">
<caption style="caption-side:bottom;text-align:left;border:none;background:none;margin:0;padding:0;"><a href="http://meinjens.de/wp-admin/admin.php?page=tablepress&amp;action=edit&amp;table_id=1">Bearbeiten</a></caption>
<thead>
<tr class="row-1">
	<th class="column-1">Belegung</th><th class="column-2">GPIO</th><th class="column-3">Pin</th><th class="column-4">Pin</th><th class="column-5">GPIO</th><th class="column-6">Belegung</th>
</tr>
</thead>
<tbody>
<tr class="row-2">
	<td class="column-1"></td><td class="column-2">+ 3,3 V</td><td class="column-3">1</td><td class="column-4">2</td><td class="column-5">+ 5 V</td><td class="column-6">Anschluss an 5V auf der L298N-H Brücke</td>
</tr>
<tr class="row-3">
	<td class="column-1"></td><td class="column-2">(SDA1) GPIO 2</td><td class="column-3">3</td><td class="column-4">4</td><td class="column-5">+ 5 V</td><td class="column-6"></td>
</tr>
<tr class="row-4">
	<td class="column-1"></td><td class="column-2"> (SCL1) GPIO 3</td><td class="column-3">5</td><td class="column-4">6</td><td class="column-5">GND</td><td class="column-6">Anschluss an GND auf der L298N-H Brücke</td>
</tr>
<tr class="row-5">
	<td class="column-1">EN A<br>
<br>
PWM für Motor 1</td><td class="column-2">(GPIO_GCLK) GPIO 4</td><td class="column-3">7</td><td class="column-4">8</td><td class="column-5">GPIO 14 (TXD0)</td><td class="column-6"></td>
</tr>
<tr class="row-6">
	<td class="column-1"></td><td class="column-2">GND</td><td class="column-3">9</td><td class="column-4">10</td><td class="column-5">GPIO 15 (RXD0)</td><td class="column-6"></td>
</tr>
<tr class="row-7">
	<td class="column-1">EN B<br>
<br>
PWM für Motor 2</td><td class="column-2"> (GPIO_GEN0) GPIO 17</td><td class="column-3">11</td><td class="column-4">12</td><td class="column-5">GPIO 18 (GPIO_GEN1)</td><td class="column-6"></td>
</tr>
<tr class="row-8">
	<td class="column-1">IN 1<br>
Richtung für Motor 1</td><td class="column-2"> (GPIO_GEN2) GPIO 27</td><td class="column-3">13</td><td class="column-4">14</td><td class="column-5">GND</td><td class="column-6"></td>
</tr>
<tr class="row-9">
	<td class="column-1">IN 2<br>
<br>
Richtung für Motor 1</td><td class="column-2"> (GPIO_GEN3) GPIO 22</td><td class="column-3">15</td><td class="column-4">16</td><td class="column-5">GPIO 23 (GPIO_GEN4)</td><td class="column-6"></td>
</tr>
<tr class="row-10">
	<td class="column-1"></td><td class="column-2">+ 3,3 V</td><td class="column-3">17</td><td class="column-4">18</td><td class="column-5">GPIO 24 (GPIO_GEN5)</td><td class="column-6">IN 3<br>
<br>
Richtung für Motor 2</td>
</tr>
<tr class="row-11">
	<td class="column-1"></td><td class="column-2">(SPI_MOSI) GPIO 10</td><td class="column-3">19</td><td class="column-4">20</td><td class="column-5">GND</td><td class="column-6"></td>
</tr>
<tr class="row-12">
	<td class="column-1"></td><td class="column-2">(SPI_MISO) GPIO 9</td><td class="column-3">21</td><td class="column-4">22</td><td class="column-5">GPIO 25 (GPIO_GEN6)</td><td class="column-6">IN 4<br>
Richtung für Motor 2</td>
</tr>
<tr class="row-13">
	<td class="column-1"></td><td class="column-2">(SPI_SLCK) GPIO 11</td><td class="column-3">23</td><td class="column-4">24</td><td class="column-5">GPIO 8 (SPI_CE0_N)</td><td class="column-6"></td>
</tr>
<tr class="row-14">
	<td class="column-1"></td><td class="column-2">GND</td><td class="column-3">25</td><td class="column-4">26</td><td class="column-5">GPIO 7 (SPI_CE1_N)</td><td class="column-6"></td>
</tr>
<tr class="row-15">
	<td class="column-1">&nbsp;</td><td class="column-2">(nur für I2C) ID_SD</td><td class="column-3">27</td><td class="column-4">28</td><td class="column-5">ID_SC (nur für I2C)</td><td class="column-6">&nbsp;</td>
</tr>
<tr class="row-16">
	<td class="column-1">&nbsp;</td><td class="column-2">GPIO 5</td><td class="column-3">29</td><td class="column-4">30</td><td class="column-5">GND</td><td class="column-6">&nbsp;</td>
</tr>
<tr class="row-17">
	<td class="column-1">&nbsp;</td><td class="column-2">GPIO 6</td><td class="column-3">31</td><td class="column-4">32</td><td class="column-5">GPIO 12</td><td class="column-6">&nbsp;</td>
</tr>
<tr class="row-18">
	<td class="column-1">&nbsp;</td><td class="column-2">GPIO 13</td><td class="column-3">33</td><td class="column-4">34</td><td class="column-5">GND</td><td class="column-6">&nbsp;</td>
</tr>
<tr class="row-19">
	<td class="column-1">&nbsp;</td><td class="column-2">GPIO 19</td><td class="column-3">35</td><td class="column-4">36</td><td class="column-5">GPIO 16</td><td class="column-6">&nbsp;</td>
</tr>
<tr class="row-20">
	<td class="column-1">&nbsp;</td><td class="column-2">GPIO 26</td><td class="column-3">37</td><td class="column-4">38</td><td class="column-5">GPIO 20</td><td class="column-6">&nbsp;</td>
</tr>
<tr class="row-21">
	<td class="column-1">&nbsp;</td><td class="column-2">GND</td><td class="column-3">39</td><td class="column-4">40</td><td class="column-5">GPIO 21</td><td class="column-6">&nbsp;</td>
</tr>
</tbody>
</table>

## Probleme

Es gab erst Probleme mit der Leistung der Motoren. Es stellte sich aber recht schnell heraus, dass es an der Versorgungsspannung vom Netzteil lag. Wir hatten unterschiedliche Netzteile ausprobiert. Offensichtlich gab es da Unterschiede.

## Testlauf

Beim ersten Testlauf haben wir zwei andere 12V Elektromotoren zum Testen gewählt. Das funktionierte genau so gut.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qDS_RjNYh58" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Fazit

Die Motoren lassen sich sehr gut und stabil steuern. Durch die Implementierung in Python können wir dies wunderbar in das Gesamtsystem integrieren.