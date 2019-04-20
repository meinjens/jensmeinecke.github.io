---
layout: page
title: Antrieb und Ruder
permalink: /pondpi/antrieb-und-ruder
---

## Anforderungen

* kräftiger und geräuscharmer Antrieb
* stromsparender Antrieb mit max. 12V
* präzise Navigation mit Halten einer Position
* Schutz der Schraube vor Pflanzen oder Grundberührung
* Kostengünstig

## Art des Antriebs

### Schottelantriebe

Die beste Navigation hinsichtlich Kraft und Präzision ist wohl der Schottelantrieb. Damit lässt sich das Schiff in jede Richtung navigieren und damit auch die Position bei Wind und Wetter gut halten. Schottelantriebe gibt es z.B. von Graupner. Diese sind jedoch nicht ganz billig. Für unseren Fall würden wir auch mindestens zwei benötigen.

### Schraubenantrieb mit Ruder

Beim Antrieb mit Schraube und Ruder würden wir ebenfalls zwei verbauen (in jeden Ausleger einen Motor und Ruder). Die Motoren würden gegenläufig laufen und die Ruder müssten synchronisiert werden, damit das Schiff geradeaus fährt.

### Doppelschraube ohne Ruder

Eine elegante und einfache Variante ist die Verwendung der Motoren zur Steuerung des Schiffes. Die Motoren werden dabei individuell vorwärts und rückwärts gesteuert. So kann das Schiff ähnlich wie ein Panzer auf der Stelle wenden.

## Treiber für die Motoren

Im Modellbau werden zur Steuerung der Drehzahl der Motoren sogenannte Fahrtenregler verwendet. Da der Raspberry Pi die Steuerung übernehmen soll bietet sich hier eine andere Möglichkeit. Das Projekt [Cardboard Car zeigt hier die Anwendung einer L298N H-Brücke](http://www.cardboard-car.com/top-story/raspberry-pi-motorsteuerung-mit-einem-motortreiber-l298n-h-bridge/7298) zur Kontrolle der Motoren. Wir müssen ähnlich wie in dem Projekt zwei Motoren getrennt voneinander kontrollieren. Dies schien uns also als geeigneter Ansatz.

## Schutz gegen Fremdkörper

Damit die Schrauben gegen Fremdkörper geschützt werden, sparen wir die Ausleger am Ende des Rumpfes jeweils aus und montieren dort die Schrauben. Anschließend wird der Rumpf mit einem Metallgitter verlängert so dass die Schrauben vollständig hinter dem Metallgitter geschützt sind.

## Auswahl der Motoren

Bei der Auswahl der Motoren gab es ebenso eine große Vielfalt. Es musste auf jeden Fall ein Gleichstrommotor mit maximal 12 Volt sein.

## Entstörung der Elektromotoren

Wir wissen noch nicht, ob das für uns relevant ist. Einige Modellbauer entstören ihre Motoren um so Störfrequenzen zu vermeinden. Diese [Anleitung](http://www.bnhof.de/~ho1645/entstoer.htm) beschreibt sehr gut wie das funktioniert.

## Entscheidung

Wir haben uns letztendlich für die Doppelschraube ohne Ruder entschieden. Im Zusammenspiel mit dem Motortreiber ist das eine gute und günstige Kombination.