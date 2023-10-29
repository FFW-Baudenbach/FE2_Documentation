# FE2_ReverseProxy

## Links

* :fontawesome-brands-github: [Repository](https://github.com/FFW-Baudenbach/FE2_ReverseProxy)
* :fontawesome-brands-docker: [Container](https://hub.docker.com/r/odin568/fe2_reverseproxy) (private)
* :fontawesome-brands-raspberry-pi: [Hosting](../Hardware/RaspberryPi.md#Docker)

## Hintergrund

Einige Funktionen in FE2 erfordern, dass die Weboberfläche über das Internet erreichbar ist. Dies ist natürlich immer etwas riskant.

Gründe sind unter anderem:

* Nutzung der App `Mobiler Alarm`
* Synchronisieren `aMobile Pro` von außerhalb
* FE2 Selbstregistrierung von KameradInnen
* FE2 Eingangsschnittstelle zusätzlich auch über HTTP

FE2 selbst bietet nur HTTP an. Dies sollte nie direkt nach außen gegeben werden. Auch sollte man keine Portfreigaben
direkt auf Windows-Systeme machen.

Alamos schlägt hier bspw. einen IIS o.ä. vor. Sicherer ist hier eine `Reverse Proxy` Lösung auf einem eigenen Gerät,
welche ein Zertifikat benutzt und wo auch die Verbindung von außen terminiert.

## Lösung

Obiges Repository baut einen Docker Container, der diese Tätigkeiten übernimmt und auch selbstständig das Zertifikat von
`Let's encrypt` erneuert. 

Neben der reinen Proxy-Funktionalität für FE2 werden noch weitere use-cases abgedeckt:

* SSL Terminierung, sowie generelle Sicherheitseinstellungen
* Reverse Proxy für [FE2](FE2.md)
* Bereitstellung von statischen Icons und generierter Karten (über volume mount) von [FE2_Kartengenerierung](FE2_Kartengenerierung.md)
* Route auf Dashboard von [FE2_Monitoring](FE2_Monitoring.md)
* Reverse Proxy für [FE2_Calendar](FE2_Calendar.md)
* Eine Route (Weiterleitung) für [FE2_Documentation](FE2_Documentation.md)