# FE2_Kartengenerierung

## Links

* :fontawesome-brands-github: [Repository](https://github.com/FFW-Baudenbach/FE2_Kartengenerierung)
* :fontawesome-brands-docker: [Container](https://hub.docker.com/r/odin568/fe2_kartengenerierung)
* :fontawesome-brands-raspberry-pi: [Hosting](../Hardware/RaspberryPi.md#Docker)
* :material-google-cloud: [Google Cloud](../Dienste/Google.md#cloud)

## Hintergrund

Neben der Handyalarmierung werden auch eine Alarmdepesche gedruckt und eine Mail an Führungskräfte versendet.

Hier sollen Lagekarten mit Hydranten, sowie eine Anfahrtskarte mit abgedruckt/versendet werden.

## Lösung

Obiges Repository baut einen Docker Container, der diese Tätigkeiten übernimmt, jedoch nur im internen Netz erreichbar ist.

Es werden Google Maps Karten erzeugt. Technisch wird hierfür die [Google Static Maps API](https://developers.google.com/maps/documentation/maps-static/start?hl=de), sowie die
[Directions API](https://developers.google.com/maps/documentation/directions/start?hl=de) verwendet.

Im Alarmablauf von FE2 sind die Koordinaten bekannt. Mit diesen werden nun REST-Endpunkte (HTTP) aufgerufen.
Diese liefern einerseits die Karte zurück, speichern sie jedoch auch lokal ab. 

Auf den Ordner der generierten Karten kann nun über eine [FE2_ReverseProxy](FE2_ReverseProxy.md) Route zugegriffen werden. Dies 
wird in der Mail verwendet, welche die Karten als `<img src="..."/>` enthält.

Für die Alarmdepesche wird die reguläre Funktion von FE2 verwendet. In der Vorlage wurde ebenfalls ein "Internetbild" 
eingebaut, welche beim Generieren dynamisch die Karte ebenfalls abfragt.

Somit werden Karten mehrmals abgefragt, das ist aber kein Problem, da das Tool in sich Anfragen gegen [GCP](../Dienste/Google.md#cloud) cached.
