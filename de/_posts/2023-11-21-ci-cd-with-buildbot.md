---
layout: post-de
title: "Buildbot als quelloffene CI/CD Alternative"
description: "Buildbot ist ein leistungsstarkes, quelloffene CI/CD-System, das durch eine flexible Konfiguration besticht, die nahezu gänzlich aus Python-Code besteht."
author: "Fabian Stadler"
categories: tech
tags: [tools]
image: assets/img/screw.jpg
image_description: "Schrauben, Unterlegschreiben und Muttern auf einem braunen, marmorierten Tisch."
image_title: "Bildquelle: <a href='https://pixabay.com/de/photos/schraube-gewinde-technik-1924174/'>PIRO4D auf Pixabay</a>"
permalink: de/2023/11/ci-ci-with-buildbot.html
lang: de
---

CI/CD-Software ist mittlerweile zu einem Standard für Entwicklungsabteilungen verschiedenster Branchen geworden. Und so gibt es mittlerweile Services von verschiedensten Anbietern, die alle mehr oder weniger ihre Daseinsberechtigung haben. Beispiele sind Microsoft mit Azure Devops Pipelines, Gitlab mit Gitlab CI, Atlassian mit Atlassian Bamboo oder Github mit Github Actions.

Aber nicht immer möchte man auf eine kommerzielle Plattform setzen, bei der man sich unter anderem von weiteren Technologien des gleichen Anbieters abhängig macht. Daher möchte ich im Folgenden auf eine quelloffene Alternative namens [Buildbot](https://www.buildbot.net/) eingehen, mit der ich in den letzten Monaten arbeiten durfte und die den meisten nicht bekannt sein dürfte.

## Master-Server als zentrale Schnittstelle

![](/assets/img/buildbot_architecture.png)
_Buildbot verwendet ein Master-Worker-Pattern als Architektur, Bildquelle: [Buildbot](http://docs.buildbot.net/current/manual/introduction.html)_

Buildbot ist im Kern den oben genannten großen CI/CD-Systemen recht ähnlich. Allerdings ist es genau auf seinen Anwendungsfall fokussiert, bietet also kein Code-Management, kein Artefakt-Repository und auch kein Sprint-Dashboard.

Die Hauptanwendung, auch Buildmaster genannt, stellt sicher, dass das Continuous Integration Management wie definiert abläuft. Sie wird über die sogenannte master.cfg, eine Konfigurationsdatei, die aus Python-Code besteht, gesteuert und steht als Schnittstelle für alle weiteren Komponenten zur Verfügung.

So unterstützt Buildbot unter anderem Codeverwaltungssysteme wie Git und Subversion, die auch automatisch abgefragt und auf Änderungen überprüft werden können. Darüber hinaus ist auch die Anbindung von Artefakt-Repositories für gebauten Code möglich. Nicht zuletzt steht den Anwendern eine übersichtliche Webanwendung zur Verfügung, in der sie manuell Einblick in die laufenden CI/CD-Pipelines nehmen können.

![](/assets/img/buildbot_example_web.png)
_Eine übersichtliche Weboberfläche vereinfacht die Übersicht, Bildquelle: [Limepepper](https://limepepper.co.uk/techtiles/buildbot.html)_

## Anbindung unterschiedlicher Umgebungen

Um jedoch Tests und Buildjobs in Form von Pipelines auf den benötigten Umgebungen ausführen zu können, benötigt Buildbot neben dem Master-Server sogenannte Worker, die in der master.cfg mit Authentifizierungsmethode konfiguriert werden müssen.

Worker können auf Systemen, auf denen Python installiert ist, einfach als Python-Package installiert und dann als Service ausgeführt werden. So spart man sich eine aufwändige Installation und kann relativ schnell, auch in einer virtuellen Maschine oder einem Container, einen Worker aufsetzen.

Dieser steht dann für beliebige Jobs bereit, die der Master-Server eben diesem Worker zuweist. Ob zufällig per Round-Robin-Distribution oder als dedizierter Worker für bestimmte Jobs, die nur unter einem bestimmten Betriebssystem laufen sollen, kann in der Konfiguration flexibel angepasst werden.

## Buildbot kommt ohne Editor

Letzteres geschieht, indem man dem Builder, dem Bindeglied zwischen dem Scheduler und dem fertigen Job, vorgibt, welche Worker er verwenden darf. Auch die Art und Weise, also wie oft und wann bestimmte Jobs laufen sollen, lässt sich über den verwendeten Scheduler einstellen, der verwaltet, unter welchen Umständen oder ob ein Job periodisch ausgeführt werden soll.

![](/assets/img/buildbot_config_architecture.png)
_Der Buildmaster steuert mehrere Einzelkomponenten, Bildquelle: [Buildbot](http://docs.buildbot.net/current/manual/introduction.html)_

Leider bietet Buildbot für solche Zwecke keinen grafischen Editor, mit dem man die Konfiguration auch ohne Programmierkenntnisse bearbeiten könnte. Andere Systeme sind hier weiter und bieten sogar vorgefertigte Templates an. Es sind sogar nur wenige Parameter für die Konfiguration in der Oberfläche verfügbar, so dass man nicht umhin kommt, die Konfigurationsdatei anzupassen und das System neu zu laden. Immerhin bietet buildbot mit `bbc`, buildbot check, ein Werkzeug, um die Konfiguration vor dem Neuladen auf syntaktische Korrektheit zu überprüfen.

## Konfiguration als Python-Code

Da es sich um Python-Code handelt, kann dies unter Umständen eine Hürde darstellen, da die Einstiegshürde für Entwickler höher ist als bei einfacheren Definitionen wie YAML. Python-Entwickler haben es hier sicherlich etwas einfacher.

Allerdings bietet dieser Umstand auch mehr Flexibilität. Denn durch die Verwendung von Code können Logiken implementiert werden, die in YAML nicht oder nur umständlich realisierbar sind. Alternativ kann ein Großteil der Build- oder Testlogik auch über Skripte in Bash, Powershell oder Make abgebildet werden. In Buildbot können dann sehr einfache Pipelines erstellt werden, die projektunabhängig und wiederverwendbar sind.

## Metadaten können selbst verwaltet werden

Die Datenhaltung von Buildbot erfolgt nach wie vor über eine Datenbank, die aus mehreren Optionen ausgewählt werden kann. Dank der Verwendung von [SQLAlchemy](https://www.sqlalchemy.org/) funktionieren MySQL und PostgreSQL genauso gut wie SQLite3. Buildbot nutzt diese Datenbank dann unter anderem, um Jobs, Historie, Quellcode-Änderungen und bestimmte Einstellungen zu speichern. So bleiben die Daten auch bei kurzfristigen Ausfällen oder Neustarts erhalten.

Dies ermöglicht es u.a. auch, selbst für Backups und Skalierung zu sorgen. Es ist auch möglich, Buildbot in eine bestehende Datenbank des eigenen Unternehmens zu integrieren. Metadaten, die kommerzielle Anbieter oft nicht exportieren können, hat man somit immer in der eigenen Hand.

## Quelloffen und kostenlos

Der größte Vorteil ist meiner Meinung nach, dass es sich bei Buildbot um quelloffene Software handelt. Das bedeutet, dass man in erster Linie nicht von den Entscheidungen des Herstellers abhängig ist und selbst bestimmt, was man bekommt.

Setzt man auf kommerzielle Lösungen (mit Ausnahme von Gitlab, wo große Teile ebenfalls quelloffen sind), muss man immer darauf vertrauen, dass der Anbieter nicht kurzfristig ein Update herausbringt, das Wartungsaufwand verursacht oder bestimmte Funktionen unbrauchbar macht. Ganz zu schweigen von den hohen Kosten, die man ohne Abonnement spart.

Natürlich kann dies auch ein Nachteil sein, da man im Falle von Bugs keine Garantie seitens der Projektbetreuer hat. Für Support und Updates ist man auf eine Gruppe von Freiwilligen angewiesen und muss das System selbst warten. Allerdings wird das Projekt seit mehreren Jahren kontinuierlich gepflegt und weiterentwickelt. Und da es auch von großen Projekten wie Chromium genutzt wird, dürfte sich daran so schnell auch nichts ändern.

## Konstante Kosten vs. hohe Kosten bei Bedarf

![](/assets/img/man-362150_640.jpg)
_Wie ein altes Auto lässt sich Buildbot auch selbst reparieren, Bildquelle: [RyanMcGuire](https://pixabay.com/de/photos/mann-wagen-reparatur-autoreparatur-362150/)_

Gleichzeitig kann es aber auch ein Vorteil sein, auf Buildbot zu setzen, da der Code jederzeit angepasst werden kann, auch wenn der Entwickler einen bestimmten Bugfix oder eine Funktionalität noch nicht eingebaut hat.

Vorausgesetzt man hat entsprechende Mitarbeiter, die sich mit Python und Twisted etwas auskennen. Dies sollte aber in größeren Entwicklungsabteilungen vorausgesetzt werden können. Zu bedenken ist, dass Buildbot unter der GPLv2 lizenziert ist, Änderungen also auch wieder veröffentlicht werden müssen.

Trotzdem kann die eigene Fehlerbehebung auch hohe Kosten verursachen, so dass es günstiger und besser planbar sein kann, auf ein monatliches fixes Abonnement zu setzen, in dem die Fehlerbehebung enthalten ist. Gerade wenn man nicht über viel Fachpersonal verfügt, können kritische Bugs sonst zum Flaschenhals werden.

## Buildbot ist nachhaltig

Dennoch ist auch bei kommerziellen Systemen nicht immer gewährleistet, dass Probleme schnell oder überhaupt behoben werden. Bis ein größeres Update kommt, vergehen manchmal Wochen, wenn nicht Monate.

Ist man wirklich auf einen schnellen Fix angewiesen, kann man im Falle von Buildbot auch auf externes Personal zurückgreifen. So kann man Buildbot und auch ältere Versionen davon noch einige Jahre gut nutzen, während man bei kommerziellen Lösungen erfahrungsgemäß migrieren muss, da sie meist an unterliegende Infrastruktur gekoppelt sind.

## Enterprise Workloads sind kein Problem

![](/assets/img/buildbot_multimaster.png)
_Im Multimaster-Setup lässt sich Buildbot beliebig skalieren, Bildquelle: [Buildbot](http://docs.buildbot.net/current/manual/configuration/multimaster.html)_

Auch hunderte von Pipelines sind für Buildbot in einem Setup mit einem einzigen Master kein Problem. Bei sehr vielen Benutzern und vielen Änderungen kann es aber zumindest im Webinterface langsam werden.

Um dem entgegenzuwirken, kann Buildbot auch in einem Multi-Master Setup betrieben werden. Dann existieren mehrere Master-Server nebeneinander, die über eine Middleware wie z.B. Crossbar kommunizieren und über Loadbalancer wie z.B. HaProxy die Last der Worker verteilen. Selbst die Datenbank kann bei steigender Last durch Replikation skaliert oder durch einen fähigen Administrator entsprechend gesichert werden, da sie selbst verwaltet wird.

Diese Master können auch unterschiedliche Konfigurationen verwenden, so dass einer nur für das Webinterface verwendet wird, während die anderen die eigentlichen Aufgaben übernehmen. Leider ist diese Form des Setups offiziell noch experimentell, im Selbsttest aber durchaus produktiv einsetzbar.

## Fazit: Mit Buildbot bleibt man unabhängig

Es steht außer Frage, dass Buildbot im Vergleich zu kommerziellen und gemanagten Lösungen durchaus mehr Administrationsaufwand und Komplexität mit sich bringt. SaaS-Cloud-Lösungen können daher auch Vorteile bei der Skalierung bieten, da sie als On-Demand-Infrastruktur arbeiten und oft alles aus einer Hand kommen. Zudem ist die monatliche oder jährliche Kostenstruktur lukrativ, da man schnell ein fertiges System und Support von einem großen Anbieter erhält.

Mit fähigem Personal bietet Buildbot aber im Grunde ähnliche, wenn nicht sogar mehr Funktionalität, die unendlich flexibel erweitert werden kann. Und das ohne Vorabkosten, da die Einarbeitung auch bei anderen Systemen notwendig ist. Ob auf der eigenen Infrastruktur oder in der Cloud, auf physischen oder virtuellen Maschinen oder in einem Kubernetes Cluster, Buildbot ist skalierbar und für Enterprise Workloads einsetzbar. Hinzu kommt der Vorteil, dass man die volle Kontrolle über den Code behält und Zugriff auf alle Metadaten hat, was bei kommerziellen Systemen in der Regel nicht der Fall ist.

Wer also mit einem nachhaltig nutzbaren und offenen System arbeiten möchte, trifft mit Buildbot sicherlich nicht die schlechteste Wahl. In der immer größer werdenden Landschaft der CI/CD-Tools sticht Buildbot somit durch seine hohe Flexibilität und das Recht auf Reparatur hervor.

_Weitere Informationen zu Buildbot finden sich in der [offiziellen Dokumentation](http://docs.buildbot.net/current/tutorial/index.html)._
