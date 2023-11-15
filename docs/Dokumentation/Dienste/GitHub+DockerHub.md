# GitHub / DockerHub

## Hintergrund

Manche Anwendungsfälle lassen sich leichter in einer Hochsprache programmieren, als direkt in FE2 o.ä.

Für einige Projekte wird daher folgender tech stack genommen:

* Java mit [SpringBoot](https://spring.io/projects/spring-boot)
* [Gradle Build Tool](https://gradle.org/)
* [Docker](https://www.docker.com/)

Als Entwicklungsumgebung kommt [IntelliJ IDEA](https://www.jetbrains.com/de-de/idea/) zum Einsatz.

Des Weiteren sind Kenntnisse in folgenden Technologien hilfreich:

* Git
* Docker Compose
* SSH
* Markdown

## GitHub

Für die Sourcecodeverwaltung wird GitHub verwendet. Dies ist einerseits kostenlos, andererseits ist und soll sämtliche
Software open-source sein.

In GitHub wurde eine eigene Organisation erstellt: [FFW-Baudenbach](https://github.com/FFW-Baudenbach)

Darin befindet sich sämtlicher Source code für unsere eigene [Software](../Software/index.md).

## DockerHub

Viele Projekte bauen einen Docker Container. Diese werden mittels `GitHub workflows` nach [DockerHub](https://hub.docker.com/u/odin568) gepusht.