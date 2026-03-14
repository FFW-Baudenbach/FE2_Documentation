# RaspberryPi

Es werden mehrere RaspberryPi betrieben.

Auf diesen läuft als Basisbetriebssystem immer [DietPi](https://dietpi.com/).

## Docker

Modell: RaspberryPi 3b
Anschaffung: 2021  
Dieser RaspberryPI wird als Docker-Host genutzt und hostet daher eine Vielzahl an Applikationen, siehe [Software](../Software/index.md).

## Monitor

Modell: RaspberryPi 4 (8 GB)  
Anschaffung: 2022  
Angeschlossen an unseren [Monitor](../Hardware/Visualisierung.md#alarmmonitor) für die Darstellung von AMWeb via Chromium Kiosk Mode.

## Etikettendrucker

Modell: RaspberryPi 3b  
Anschaffung: 2026  
Angeschlossen an unseren [Etikettendrucker](Drucker.md#etikettendrucker) als TCP-Gateway für den USB-Drucker mittels `socat`.

Hinweis: Filesystem ist Read-Only um mit "Strom aus" sicher umgehen zu können. 

Folgender Dienst ist installiert:

```
[Unit]
Description=ZD220 USB to TCP 9100
After=network.target

[Service]
ExecStartPre=/bin/sh -c 'until [ -e /dev/usb/lp0 ]; do sleep 2; done'
ExecStart=/usr/bin/socat TCP-LISTEN:9100,reuseaddr,fork FILE:/dev/usb/lp0
Restart=always
RestartSec=2

[Install]
WantedBy=multi-user.target
```

Damit kann mit Tablet & co auf den Drucker zugegriffen werden.