# HomeAssistant

## Links

* :fontawesome-brands-github: [Repository](https://github.com/home-assistant)
* :fontawesome-brands-raspberry-pi: [Hosting](../Hardware/Endgeräte.md#alamos-pc) (VM in VirtualBox)

## Hintergrund

Seit 2026 wird für sämtliche Steuerungsaufgaben HomeAssistant verwendet, um von Eigenlösungen loszukommen.

Neben SmartHome Integrationen (Shelly, Fritz, ...) sind über HACS auch FusionSolar und PVOutput Integrationen aktiv um Daten der Photovoltaikanlage auswertbar zu machen.

HomeAssistant bietet WebHooks an, welche von [FE2](../Software/FE2.md) im Alarmablauf angetriggert werden. Somit ist eine klare Trennung zwischen Alarm- und SmartHome Features gegeben.