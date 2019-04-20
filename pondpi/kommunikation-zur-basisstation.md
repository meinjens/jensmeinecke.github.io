---
layout: page
title: Kommunikation zur Basisstation
permalink: /pondpi/kommunikation-zur-basisstation
---

## Anforderungen

* Manuelle Steuerung im Notfall
* Bestimmung von Routen
* Konfiguration
* Übertragung von Daten / Bilder / Videos (vielleicht in Echtzeit)

## Lösungsmöglichkeiten

### WLAN Verbindung

Als einfaches Mittel der Kommunikation erschien uns eine WLAN Verbindung. Die Reichweite könnte dabei problematisch sein. Im ersten Schritt wird uns das genügen. Somit können wir mit der Anwendung zur Steuerung per Websocket kommunizieren und Daten übertragen / empfangen.

### Funkverbindung mit 2,4 GHz

Eine Alternative bietet die Übertragung mit Hilfe von 2,4GHz Funkmodulen wie in diesem Artikel zur [Funkkommunikation zwischen Raspberry Pi und Arduino](https://tutorials-raspberrypi.de/funkkommunikation-zwischen-raspberry-pis-und-arduinos-2-4-ghz/) beschrieben.
