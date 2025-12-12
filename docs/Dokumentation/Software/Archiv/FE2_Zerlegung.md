# FE2_Zerlegung

## Links

* :fontawesome-brands-github: [Repository FE2_Zerlegung_ILSAnsbach](https://github.com/FFW-Baudenbach/FE2_Zerlegung_ILSAnsbach)
* :fontawesome-brands-github: [Repository FE2_Zerlegung_v2](ttps://github.com/FFW-Baudenbach/FE2_Zerlegung_v2)
* :fontawesome-solid-computer: [FE2](../FE2.md)

## Hintergrund

> Mit Ende des Alarmfaxes in 2026 benötigen wir diese Zerlegung nicht mehr.

Zu Beginn des Setups der Handyalarmierung (2019) gab es lediglich die Möglichkeit das Leitstellenfax auszuwerten.

Mittlerweile gibt es glücklicherweise eine direkte Schnittstelle zur Leitstelle, daher wird diese Lösung nur noch als Fallback für die Alarmierung genutzt.

Dennoch ist es hilfreich, komplexe Parameter (bspw. für HTML-Mails) in Code zusammenzusetzen anstatt mit FE2 Bordmitteln.


## FE2_Zerlegung_ILSAnsbach

!!! Hinweis info
    Diese Lösung wird noch für die Alarmdepesche und die Einsatzmail verwendet.  
    Offen ist noch die Migration auf die neue v2 Schnittstelle von Alamos und das Auswerten der Parameter über die ILS Verbindung und nicht mehr aus dem Fax.


Aus dem Textinput des Faxes werden zunächst alle Informationen extrahiert und als Parameter für die weitere Verwendung zurückgegeben.

Zusätzlich werden auch spezielle Parameter gesetzt, sodass Formatierungslogik für aPager Pro Text und HTML-Mailtext entfällt und nur an einer zentralen Stelle gemacht wird.
Dies ist deutlich einfacher als im Alarmablauf händisch zusammenzubasteln.

## FE2_Zerlegung_v2

!!! Hinweis info
    Diese Lösung ist noch nicht implementiert :(

Eine Nachfolgelösung soll sich aus den Informationen aus der Leitstelle speisen und daher die Faxzerlegung obsolet machen.
