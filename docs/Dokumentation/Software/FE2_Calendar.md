# FE2_Calendar

## Links

* :fontawesome-brands-github: [Repository](https://github.com/FFW-Baudenbach/FE2_Calendar)
* :fontawesome-brands-docker: [Container](https://hub.docker.com/r/odin568/fe2_calendar)
* :fontawesome-brands-raspberry-pi: [Hosting](../Hardware/RaspberryPi.md#docker)
* :fontawesome-solid-calendar-days: [Google Kalender](../Dienste/Google.md#kalender)

## Hintergrund

> Hinweis: Seit 2024 nutzen wir [FireManager](../Dienste/FireManager.md#kalender) für Termine.  
> Dadurch entfällt das Zerlegen eines Google Kalenders. Jedoch verwenden wir weiterhin dieses Tool um die 
> Alarme zu Alamos FE2 zu setzen.

Alamos bietet eine Kalenderintegration in den aPager Pro an.

Wir nutzen aktuell einen Google-Kalender für alle Termine. Einige KameradInnen haben diesen direkt abonniert. Daher wollen wir diesen gerne behalten.

Wenn man diesen Kalender als externen Kalender in FE2 einfügen würde, hätte das mehrere Nachteile:

* Unübersichtlich
* Keine oder alle Benachrichtigungen

Insbesondere der letzte Punkt ist problematisch: Vermutlich schaut niemand einfach so in den FE2 Kalender. Eingestellte Benachrichtigungen in Google 
werden zwar verwendet (wenn es funktioniert), jedoch kann dann nicht gesteuert werden, wer welche Benachrichtigungen erhält. Das ist suboptimal.

## Lösung

Obiges Repository baut einen Docker Container, der als "Filter-Proxy" fungiert und über eine Route in [FE2_ReverseProxy](FE2_ReverseProxy.md)
nach außen den Dienst bereitstellt.

In der Konfiguration ist nun als Quelle unser bekannter Google Kalender eingetragen. Das Tool schneidet nun einzelne 
logische Kalender anhand des Termintitels heraus, bspw. Übungen für den 1. Zug.

Diese Teilkalender sind dann in FE2 eingetragen und den entsprechenden Alarmgruppen zugewiesen.

Neben dem Filtern kann das Tool auch Benachrichtigungen hinzufügen und löschen. Dadurch ist es möglich Kalender so zu schneiden, dass
jeder alle Termine hat, jedoch nur bei bestimmten eine Erinnerung über den aPager bekommt.