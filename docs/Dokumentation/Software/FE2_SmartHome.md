# FE2_SmartHome

## Links

* :fontawesome-brands-github: [Repository](https://github.com/FFW-Baudenbach/FE2_SmartHome)
* :fontawesome-brands-docker: [Container](https://hub.docker.com/r/odin568/fe2_smarthome)
* :fontawesome-brands-raspberry-pi: [Hosting](../Hardware/RaspberryPi.md#docker)
* :fontawesome-solid-tv: [Monitor](../Hardware/Visualisierung.md
* #monitor)
* :fontawesome-solid-plug-circle-bolt: [SmartHome](../Hardware/Netzwerk.md#smarthome)
* :fontawesome-solid-calendar-days: [Google Kalender](../Dienste/Google.md#kalender)

## Hintergrund

Seit 2022 haben wir einen Monitor in der Fahrzeughalle. Auf diesem wird eine Standardansicht, sowie eine
Alarmansicht als Webseite mittels Alamos AMWeb dargestellt.

Dieser Monitor soll nun natürlich im Einsatzfall automatisch eingeschaltet und natürlich generell nach einer bestimmten
Zeit wieder ausgeschaltet werden.

Da wir relativ wenig Einsätze haben, soll der Monitor auch bei Übungen bzw. generell bei Veranstaltungen im 
Feuerwehrhaus angeschaltet werden.

## Lösung

Obiges Repository baut einen Docker Container, der diese Tätigkeiten übernimmt, jedoch nur im internen Netz erreichbar ist.

Intern kommuniziert das Tool mit unserem Router, welcher als SmartHome-Zentrale fungiert und schlussendlich einen Plug
am Monitor schaltet.

Das Tool bietet REST-Endpunkte (URL-Aufrufe) an, um u.a. den Monitor anzuschalten. Dies geschieht im Alarmablauf von FE2.

Nach einer konfigurierbaren Zeit (seit einschalten) und einer definierten Zeitspanne, in der keine Bewegung festgestellt wurde,
wird der Monitor wieder ausgeschaltet.

Das Ganze wird "smart", indem zusätzlich unser Google Kalender genutzt wird:

Solange ein Termin den Begriff "Übung" oder "Feuerwehrhaus" im Betreff oder Ort hat, wird der Monitor eingeschaltet und für 
die Dauer des Termins aktiv gelassen.

