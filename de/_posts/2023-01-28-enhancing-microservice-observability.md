---
layout: post-de
title: "Beobachtbarkeit von Microservices mit Datadog"
description: "Dieser Artikel befasst sich mit dem Thema der Beobachtbarkeit bei der Bereitstellung von Microservices in Kubernetes am Beispiel des SaaS Datadog."
author: "Fabian Stadler"
categories: tech
tags: [microservices,tools]
image: assets/img/cateyes.png
image_description: "Ein Bild einer Katze mit blauen Augen als Metapher für Beobachtbarkeit."
permalink: de/2023/01/enhancing-microservice-observability.html
lang: de
---

In der heutigen schnelllebigen und sich ständig verändernden Softwareentwicklungslandschaft ist die Bereitstellung von Microservices in Kubernetes zu einer beliebten und effektiven Methode für die Erstellung und Verwaltung großer, komplexer Systeme geworden. Mit der zunehmenden Anzahl von Microservices in einem System steigt jedoch auch die Komplexität der Überwachung und des Verständnisses des Verhaltens und der Leistung dieser Services in der Produktion.

An dieser Stelle kommt die Beobachtbarkeit ins Spiel. In diesem Artikel gehen wir der Frage nach, warum die Beobachtbarkeit beim Deployment von Microservices in Kubernetes entscheidend ist und was Sie wissen müssen, um Ihre Microservices in einer Kubernetes-Umgebung effektiv zu überwachen und Fehler zu beheben. Dazu nehmen wir die Monitoring-SaaS Datadog als Beispiel.




## Was ist Datadog?

Datadog ist eine Cloud-basierte Überwachungs- und Analyseplattform, die detaillierte Einblicke in die Leistung und den Zustand von IT-Infrastruktur, Anwendungen und Protokolldaten bietet. Sie ermöglicht das Sammeln, Analysieren und Visualisieren von Metriken und Traces aus verschiedenen Quellen, wie Servern, Containern und Cloud-Diensten.

Die Plattform umfasst eine Vielzahl von Funktionen wie Echtzeitüberwachung, Warnmeldungen, Anomalieerkennung und Dashboards, die Unternehmen dabei helfen, Probleme mit ihren Systemen zu identifizieren und zu beheben sowie Leistung und Verfügbarkeit zu optimieren. Darüber hinaus bietet Datadog eine leistungsstarke Abfragesprache, mit der Sie benutzerdefinierte Metriken und Warnmeldungen erstellen können. Die Lösung unterstützt Multi-Cloud-, Hybrid- und On-Premises-Umgebungen.


## Verbessern Sie die Beobachtbarkeit von Microservices mit Datadog

Datadog kann dazu beitragen, die Beobachtbarkeit von Microservices zu verbessern, indem es einen umfassenden Überblick über die Leistung und den Zustand der Microservices und der ihnen zugrunde liegenden Infrastruktur bietet. Mit Funktionen wie Metriksammlung, Tracing, Log-Aggregation, Dashboards und Alerts sowie Kubernetes-Integration bietet Datadog die nötige Transparenz, um Probleme mit Microservices zu überwachen und zu beheben.

Durch das Sammeln und Aggregieren von Metriken, Traces und Protokollen von Microservices und deren Abhängigkeiten, wie Datenbanken und Message Queues, kann Datadog in Echtzeit Einblicke in die Leistung und Ressourcennutzung Ihrer Microservices geben, so dass Sie Probleme schnell erkennen und beheben können.

Darüber hinaus kann Datadog mit der Kubernetes-Integration Kubernetes-spezifische Metriken sammeln, wie z. B. die Ressourcennutzung und die Leistung der Nodes und Pods, was dabei hilft, Probleme mit den Microservices und der Kubernetes-Infrastruktur, auf der sie laufen, zu identifizieren.

![Query Traces & Logs in Datadog](/assets/img/datadog-logexplorer.png "Query Traces & Logs in Datadog"){:style="float: center"}
*Abfrage von Traces und Protokollen mit dem Log Explorer, Copyright: Datadog*

## Vorteile der Verwendung von Datadog gegenüber anderen Protokolldiensten

Datadog bietet eine umfassende und flexible Überwachungslösung, die Unternehmen dabei helfen kann, ein tieferes Verständnis für ihre Systeme zu erlangen und die Gesamtverfügbarkeit und Leistung ihrer Microservices zu verbessern. Es bietet zum Beispiel:

  * Umfassende Überwachung: Datadog bietet eine umfassende Überwachungslösung, die die Sammlung von Metriken, die Nachverfolgung und die Aggregation von Protokollen umfasst, wodurch Sie einen vollständigen Überblick über die Leistung und den Zustand Ihrer Systeme erhalten und nicht nur über die Protokolle.
  * Überwachung in Echtzeit: Mit Datadog können Sie Ihre Systeme in Echtzeit überwachen, was Ihnen dabei helfen kann, Probleme zu erkennen und zu beheben, sobald sie auftreten, und nicht erst im Nachhinein.
  * Anomalie-Erkennung: Datadog verfügt über eine integrierte Funktion zur Erkennung von Anomalien, die automatisch abnormales Verhalten in Ihren Metriken identifizieren und Sie auf mögliche Probleme aufmerksam machen kann.
  * Anpassbare Dashboards: Datadog bietet eine Vielzahl von Visualisierungsoptionen, wie z. B. Dashboards, die an die spezifischen Anforderungen Ihres Unternehmens angepasst werden können.
  * Multi-Cloud- und Hybrid-Unterstützung: Datadog unterstützt Multi-Cloud- und Hybrid-Umgebungen und kann Ressourcen über verschiedene Cloud-Anbieter, On-Premises und Edge überwachen.
  * Integrationen: Datadog verfügt über eine große Anzahl von Integrationen mit anderen Tools und Diensten, wie AWS, GCP, Azure, Slack, PagerDuty, usw., die es Ihnen ermöglichen, Datadog einfach in Ihre bestehenden Arbeitsabläufe und Tools zu integrieren.

## Senden von Protokollen eines .NET-Dienstes an Datadog

Das Senden von Protokollen eines .NET-Dienstes an Datadog ist ein wesentlicher Schritt bei der Überwachung und Fehlerbehebung Ihrer Anwendung. Es gibt mehrere Möglichkeiten, dies zu erreichen, jede mit ihren eigenen Vor- und Nachteilen.

Die erste Option ist die Verwendung des Datadog-Agenten. Dabei handelt es sich um eine leichtgewichtige Software, die auf Ihren Servern installiert werden kann, um Protokolle zu sammeln und an die Datadog-Plattform weiterzuleiten. Sie können den Agent so konfigurieren, dass er Protokolle von Ihrem .NET-Dienst sammelt, indem Sie den Dateipfad der Protokolldateien in der Konfigurationsdatei des Agenten angeben.

Eine andere Möglichkeit ist die Verwendung der Datadog .NET Logs Library. Diese Bibliothek ermöglicht es Ihnen, Protokolle direkt von Ihrem .NET-Dienst an die Datadog-Plattform zu senden. Sie können die Bibliothek mit NuGet installieren und dann die bereitgestellten APIs verwenden, um Logs an Datadog zu senden.

Eine dritte Möglichkeit ist die Verwendung eines Log-Shippers, wie z.B. Filebeat. Bei diesem Ansatz müssen Sie Filebeat so konfigurieren, dass es die Protokolle von Ihrem .NET-Dienst sammelt und sie mit Hilfe des Datadog-Ausgabe-Plugins an die Datadog-Plattform weiterleitet.

Wenn Sie einen Cloud-Anbieter wie AWS, Azure oder GCP verwenden, können Sie deren Service nutzen, um Ihre Protokolle an Datadog weiterzuleiten.

Unabhängig von der gewählten Methode müssen Sie die Datadog-Plattform für den Empfang und die Verarbeitung der Protokolle konfigurieren. Dies kann durch das Erstellen einer Protokoll-Pipeline in der Datadog-Plattform und das Festlegen der Quelle und des Formats der Protokolle erfolgen.

Bevor die Protokolle an Datadog gesendet werden, muss sichergestellt werden, dass sie in einem strukturierten Format vorliegen und die notwendigen Informationen für die Fehlersuche und -diagnose enthalten.

## Exportieren von Traces und Logs eines .NET-Dienstes mit OpenTelemetry und Serilog

Mit OpenTelemetry und Serilog können Sie Telemetriedaten aus Ihrer .NET-Anwendung instrumentieren und an Datadog senden. Installieren Sie das OpenTelemetry-Paket und den Datadog-Exporter mit NuGet, indem Sie den folgenden Befehl ausführen:

```bash
dotnet add package OpenTelemetry
dotnet add package OpenTelemetry.Exporter.Datadog
```

Konfigurieren Sie in Ihrer Anwendung den OpenTelemetry-Exporter, um Telemetriedaten an Datadog zu senden. Sie müssen Ihren Datadog-API-Schlüssel angeben und einen Dienstnamen für Ihre Anwendung bereitstellen. Sie können dies in der Datei "Startup.cs" oder in jeder anderen Konfigurationsdatei Ihrer Anwendung tun.

```csharp
using OpenTelemetry;
using OpenTelemetry.Exporter.Datadog;
var exporter = new DatadogExporter(new DatadogExporterOptions()
{
    ApiKey = "IHR_API_KEY",
    ServiceName = "ihr-service-name"
});

TelemetryConfiguration configuration = TelemetryConfiguration.CreateDefault();
configuration.AddExporter(exporter);
```

Verwenden Sie die OpenTelemetry-APIs, um Ihren Code zu instrumentieren und Telemetriedaten an Datadog zu senden. Das OpenTelemetry-Paket bietet mehrere APIs zur Erstellung von Spans, Metriken und Traces, die zur Instrumentierung Ihres Codes verwendet werden können.

Sie können auch das Serilog-Paket verwenden, um strukturierte Daten zu protokollieren. Es kann in Ihre Anwendung integriert werden, indem Sie das Paket installieren und es so konfigurieren, dass es in die Konsole, eine Datei oder eine bestimmte Senke wie Datadog schreibt. Sie können das Serilog.Sinks.Datadog-Paket verwenden, um Protokolldaten an Datadog zu senden. In der Datadog-Plattform müssen Sie eine Protokollpipeline konfigurieren, um die von Serilog gesendeten Protokolle zu empfangen und zu verarbeiten.

Durch den gemeinsamen Einsatz von OpenTelemetry und Serilog erhalten Sie einen umfassenden Einblick in die Leistung und das Verhalten Ihrer Anwendung, einschließlich detaillierter Traces und Metriken sowie strukturierter Protokolldaten. Dies kann Ihnen helfen, folgende Probleme schnell zu identifizieren und zu beheben

## Erkennen von nicht optimiertem Code und Leistungsengpässen

Datadog bietet eine Reihe von Funktionen, die bei der Erkennung von nicht optimiertem Code und Leistungsengpässen in Ihren Anwendungen helfen können. Die Code-Profiling-Funktion in Datadog APM ermöglicht die Erstellung von Profilen für die Leistung Ihrer Anwendung, um festzustellen, welche Teile Ihres Codes die meiste Zeit für die Ausführung benötigen, und um nicht optimierte Bereiche zu identifizieren, die Engpässe verursachen können.

Die Verfolgung von Anfragen, während sie durch Ihre Anwendung fließen, mit Datadog APM kann auch helfen, Engpässe und Latenzprobleme in der Architektur Ihrer Anwendung zu identifizieren. Die Anomalie-Erkennung identifiziert automatisch abnormales Verhalten in den Metriken und warnt Sie vor möglichen Problemen.

Anpassbare Dashboards und Visualisierungsoptionen, wie sie Datadog anbietet, können Ihnen helfen, die Leistung Ihrer Anwendungen zu verstehen und Bereiche mit Optimierungsbedarf zu identifizieren.

## Erstellen Sie Berichte für Entwicklerteams und Stakeholder

![Create Dashboard Reports in Datadog](/assets/img/datadog-dashboard.png "Create Dashboard Reports in Datadog"){:style="float: center"}
*Erstellen von Dashboard-Berichten, Copyright: Datadog*

Schließlich bietet Datadog eine Vielzahl von Funktionen, die bei der Erstellung von Leistungs- und Sicherheitsberichten helfen. Mit benutzerdefinierten Dashboards können Sie Metriken, Traces und Protokolle visualisieren, um Leistungsberichte zu erstellen, die wichtige Informationen wie Antwortzeit, Fehlerrate und Durchsatz anzeigen. 

Die Funktion Berichte ermöglicht die einfache Erstellung und Planung von benutzerdefinierten Berichten in verschiedenen Formaten, einschließlich PDF, CSV und JSON. Diese Berichte können so angepasst werden, dass sie die für Ihr Unternehmen wichtigsten Daten enthalten und können Metriken, Traces und Protokolle enthalten. 

Darüber hinaus ermöglicht der Datadog Monitor-Dienst die Erstellung von Monitoren, die bei Erfüllung bestimmter Bedingungen Alarme auslösen. Diese Monitore können zur Erstellung von Sicherheitsberichten verwendet werden, die Informationen über sicherheitsrelevante Metriken liefern, wie z. B. die Anzahl der fehlgeschlagenen Anmeldeversuche oder blockierte IPs.

## Fazit

Datadog ist eine leistungsstarke Überwachungs- und Beobachtungsplattform, die eine breite Palette von Funktionen für die Überwachung und Fehlersuche bei Anwendungen, Netzwerken und Infrastrukturen bietet. Zu den Vorteilen von Datadog gehören die Fähigkeit, Metriken, Traces und Logs aus einer Vielzahl von Quellen zu sammeln und zu aggregieren, die Unterstützung für benutzerdefinierte Dashboards und Warnmeldungen sowie die Fähigkeit, Anomalien automatisch zu erkennen und zu melden. Darüber hinaus bietet Datadog eine Vielzahl von Integrationsmöglichkeiten mit anderen Tools, wie z. B. Cloud-Anbietern, Sicherheitstools und Datenbanken.

Datadog hat jedoch auch einige Nachteile, wie z. B. die hohen Kosten für einige Anwendungsfälle in großen Unternehmen und die relativ steile Lernkurve für neue Benutzer. Außerdem ist Datadog möglicherweise nicht die beste Lösung für Unternehmen mit strengen Sicherheits- und Regulierungsanforderungen. Wie immer hängt es von den Geschäftsanforderungen ab, ob die Arbeit mit einer SaaS-Lösung wie Datadog optimal ist.
