---
layout: post
title: Erster Testlauf des Antriebs
tags: [raspberrypi, pondpi]
---
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

|Belegung|GPIO|Pin|Pin|GPIO|Belegung|
|--- |--- |--- |--- |--- |--- |
||+ 3,3 V|1|2|+ 5 V|Anschluss an 5V auf der L298N-H Brücke|
||(SDA1) GPIO 2|3|4|+ 5 V||
||(SCL1) GPIO 3|5|6|GND|Anschluss an GND auf der L298N-H Brücke|
|EN A: PWM für Motor 1|(GPIO_GCLK) GPIO 4|7|8|GPIO 14 (TXD0)||
||GND|9|10|GPIO 15 (RXD0)||
|EN B: PWM für Motor 2|(GPIO_GEN0) GPIO 17|11|12|GPIO 18 (GPIO_GEN1)||
|IN 1: Richtung für Motor 1|(GPIO_GEN2) GPIO 27|13|14|GND||
|IN 2: Richtung für Motor 1|(GPIO_GEN3) GPIO 22|15|16|GPIO 23 (GPIO_GEN4)||
||+ 3,3 V|17|18|GPIO 24 (GPIO_GEN5)|IN 3: Richtung für Motor 2|
||(SPI_MOSI) GPIO 10|19|20|GND||
||(SPI_MISO) GPIO 9|21|22|GPIO 25 (GPIO_GEN6)|IN 4: Richtung für Motor 2|
||(SPI_SLCK) GPIO 11|23|24|GPIO 8 (SPI_CE0_N)||
||GND|25|26|GPIO 7 (SPI_CE1_N)||
||(nur für I2C) ID_SD|27|28|ID_SC (nur für I2C)||
||GPIO 5|29|30|GND||
||GPIO 6|31|32|GPIO 12||
||GPIO 13|33|34|GND||
||GPIO 19|35|36|GPIO 16||
||GPIO 26|37|38|GPIO 20||
||GND|39|40|GPIO 21||

## Probleme

Es gab erst Probleme mit der Leistung der Motoren. Es stellte sich aber recht schnell heraus, dass es an der Versorgungsspannung vom Netzteil lag. Wir hatten unterschiedliche Netzteile ausprobiert. Offensichtlich gab es da Unterschiede.

## Testlauf

Beim ersten Testlauf haben wir zwei andere 12V Elektromotoren zum Testen gewählt. Das funktionierte genau so gut.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qDS_RjNYh58" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Fazit

Die Motoren lassen sich sehr gut und stabil steuern. Durch die Implementierung in Python können wir dies wunderbar in das Gesamtsystem integrieren.