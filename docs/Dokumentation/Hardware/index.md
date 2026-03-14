---
hide:
  - toc
---

# Überblick

Diese folgenden Seiten bieten einen Überblick über die Hardware, welche im Feuerwehrhaus betrieben wird.

## Geräteplan

```mermaid
graph TD

    subgraph buero[Büro]
        router[[Fritz!Box]]
        pwl-rt[[Fritz!Powerline Router]]
        rpidoc(RaspberryPi Docker)
        fe2pc(Alamos PC)
        phone[[AVM FRITZ!Fon]]
        relais([Relais Außenlicht])
        
        router---|LAN|pwl-rt
        router---|LAN|rpidoc
        router---|LAN|fe2pc
        router---|DECT|phone
    end
    
    subgraph schulungsraum[Schulungsraum]
        bueropc(Büro PC)
        copier([Multifunktionsgerät])
        beamer([Beamer])
        wlanrep[[Fritz!WLAN Repeater]]
        router---|LAN|wlanrep
        
        bueropc---|USB|copier
        bueropc---|HDMI|beamer
    end
    
    subgraph werkstatt[Werkstatt]
        rpidrucker(RaspberryPi Drucker)
        werkstatttablet(Werkstatt Tablet)
        werkstattmonitor([Werkstatt Monitor])
        labelprinter([Etikettendrucker])

        rpidrucker---|USB|labelprinter
        werkstatttablet---|USB-C|werkstattmonitor
    end
    
    subgraph fzh1[Fahrzeughalle 1]
        pwl-fzh1[["Fritz!Powerline WLAN FZH&nbsp;1"]]
        pwl-mon[[Fritz!Powerline Monitor]]
        printer([Laserdrucker])
        alarmmonitor([Alarmmonitor])
        actor([Aktor])
        motion([Bewegungsmelder])
        plug([Schalter])
        rpimon(RaspberryPi Monitor)
        tabletmzf(Tablet MZF)
        defi(Defibrillator)

        pwl-fzh1---|LAN|printer
        
        pwl-mon---|LAN|alarmmonitor
        pwl-mon---|LAN|rpimon
        
        plug-.->actor--Power-->alarmmonitor
        rpimon---|HDMI|alarmmonitor
        actor-.-motion

    end
    
    subgraph fzh2[Fahrzeughalle 2]
        pwl-fzh2[["Fritz!Powerline WLAN FZH&nbsp;2"]]
        lardis-hlf(Lardis HLF)
    end
    
    pwl-rt-.-|Powerline|pwl-mon
    pwl-rt-.-|Powerline|pwl-fzh1
    pwl-rt-.-|Powerline|pwl-fzh2
    
```

*Hinweis: WLAN Verbindungen sind zur besseren Lesbarkeit nicht eingezeichnet.*