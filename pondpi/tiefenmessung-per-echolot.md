---
layout: page
title: Pond Pi - Tiefenmessung per Echolot
---
### Anforderungen

*   Anbindung an den Raspberry Pi
*   Kostengünstiger Sensor
*   Tiefenmessungen von wenigen Zentimeter bis zu Tiefen von 10m
*   Geringer Stromverbrauch
*   Frequenzbereich 200kHz um die Tiere nicht zu stören

### Mögliche Sensoren

**Signalgeber**

Im Marinebereich gibt es verschiedene Arten von Gebern, die für die Signalumwandlung zuständig sind. Diese sind jedoch auch relativ teuer. Wenn man günstig an einen gebrauchten Sensor kommt, dann wäre das vielleicht eine Alternative. Eine passendes Schaltbild dazu haben wir jedoch noch nicht gefunden.

**Fishfinder**

Günstige Fishfinder für etwa 30 EUR bieten die Sensoren, die wir für unser Projekt benötigen. Leider haben wir die Sensoren einzelnd nicht finden können. So war auch diese Variante nicht passend.

**Ultraschallsensoren für den Unterwassergebrauch**

Sensoren für Echolote oder Sonar haben wir nur vereinzelnd gefunden. Diese waren dann auch nicht gerade günstig. Das vielversprechenste Produkt, das sich auch im deutschsprachigen Raum bestellen ließ ist der [200LM450](http://www.sander-electronic.de/ultraschall-unter-wasser.html).

**Wasserdichte Ultraschallsensoren**

Eine Variante ist der Einsatz von [wasserdichten bzw. wetterfesten Ultraschallsensoren](http://www.maxbotix.com/Ultrasonic_Sensors/MB7072.htm). Diese werden mit Hilfe von transparentem Silikon wasserdicht gemacht und sind somit verwendbar. Bei der Berechnung der Distanz muss dazu berücksichtigt werden dass sich der Schall Unterwasser viermal so schnell ausbreitet wie in der Luft. Ein entsprechendes [Projekt](https://coconutpi.wordpress.com/), das genau dieses Prinzip verwendet, gibt es auch bereits.