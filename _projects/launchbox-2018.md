---
title: "Launch Box"
subtitle: "Website Launch mal anders"
category: "Show"
layout: "project"
project_name: "Launch Box - Website Launch mal anders"
project_type: "experiment"
project_sector: "tourism"
project_location: "Frankfurt"
project_start_date: 2016-12-01
project_end_date: 2017-04-01
---

Mein alter Chef hatte immer die Idee: "Ich will zum Launch der Website nur einen Knopf!" Da ich gerne mit dem Raspberry Pi bastle, brachte mich das zu der folgenden Idee: "Was wäre, wenn der Kunde zum Launch der Website eine Art Kontrollpult halt, mit dem er selbst die Seite live stellen kann?!"

Die Gelben Bengel haben in der kurzen Zeit eine herausragende Leistung hingelegt. Für mich war es dann selbstverständlich, dass wir diese Leistung noch mal mit einer verrückten Aktion krönen mussten.

### Herausforderung

In relativ kurzer Zeit musste ein Kontrollpult gebaut werden. Meine Kenntnisse in der Elektrotechnik sind nur rudimentär. Also durften die Schaltungen nicht sonderlich kompliziert sein. Gleichzeitig musste eine visuelle Bestätigung in Form einer kleinen Web App gebaut werden.

Ich entschied mich für ein Kontrollpult aus OSB Platten (9mm). Das Pult bekam einen schwarzen Anstrich und gelbschwarze Warnstreifen. Im Pult eingelassen waren 4 Schalter mit je 4 Dioden. Ein Killswitch und ein Notausschalter sollten das ganze ein wenig aufpeppen. Die Idee war, dass man durch eine Schalterkombination in zwei Stufen den Launch auslösen kann. So konnten beide Geschäftsführer von ADAC das neue ADACreisen.de Portal launchen. Eine kleine Webapp visualisierte die Schalterstellungen und löste über einen Webhook den entscheidenen Jenkins Job aus, der tatsächlich das Go-Live realisierte.

### Aufgaben

- Fertigen der Launch Box aus OSB Platten
- Bau der Schaltungen in der Launch Box zum Auslesen der Schalter
- Bau der Schaltungen in der Launch Box zum Ansteuern der LEDs
- Python basierter Webserver zum Auslesen der Schalter und Ansteuern der LEDs
- Web App zur Visualisierung mit Websockets


### Erfahrungen

Besonders spannend war der Mix aus den verschiedenen Tätigkeiten aus dem Handwerk, der Elektronik und Entwicklung. Das kleine Projekt hat sehr viel Spaß gemacht, obwohl es komplett in der Freizeit neben der anstregenden Projektentwicklung entstanden ist. Der Fortschritt war jeden Abend sichtbar. Und das am Ende alles reibungslos funktioniert hat, war ein sehr schönes Gefühl.

[![](/assets/launchbox/launchbox-small.jpg)](/assets/launchbox/launchbox.jpg)