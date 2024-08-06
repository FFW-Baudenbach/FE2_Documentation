# FE2_Monitoring

## Links

* :fontawesome-brands-github: [Repository](https://github.com/FFW-Baudenbach/FE2_Monitoring)
* :fontawesome-brands-docker: [Container](https://hub.docker.com/r/odin568/fe2_monitoring)
* :fontawesome-brands-raspberry-pi: [Hosting](../Hardware/RaspberryPi.md#docker)

## Hintergrund

Je mehr die Infrastruktur (Hardware und Software) wächst, desto schwieriger wird es, den Überblick zu behalten und das
ganze zu monitoren, idealerweise automatisiert.

Standardlösungen sind vom Setup nicht trivial und für den use-case entweder overkill oder zu simpel.

## Lösung

!!! Hinweis warning
    Diese Lösung ist (entgegen den Ansprüchen) nicht generalisiert. IP-Adressen, etc. sind alle fest verdrahtet.

Obiges Repository baut einen Docker Container, der diese Tätigkeiten übernimmt. Die Komponente bietet zwei Modi:

* Internes Monitoring (läuft im Feuerwehrhaus)
* Externes Monitoring (läuft außerhalb)

Der externe Modus stellt sicher, dass bei Internetausfall eine Benachrichtigung kommt. Er prüft daher lediglich, ob 
das interne Monitoring noch läuft über eine Route in [FE2_ReverseProxy](FE2_ReverseProxy.md).

Das interne Monitoring prüft nun regelmäßig alle Komponenten, Geräte, ... ab und schlägt über [Pushover](../Dienste/Pushover.md) Alarm.

Zu definierter Zeit wird auch der aktuelle Status versendet, damit man sieht, dass noch alles läuft.

Auch wird die Information auf der Ruheperspektive auf dem Monitor dargestellt.