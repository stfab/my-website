---
layout: post-de
title: "Low-code vs. High-code Datenpipelines"
description: "Unternehmen stehen oft vor dem Dilemma, wie sie Datenpipelines schnell implementieren können. In diesem Beitrag erkläre ich, warum High-Code oft die bessere Wahl ist."
author: "Fabian Stadler"
categories: tech
tags: [data-engineering,architecture]
image: assets/img/investment-5241253_1280.jpg
image_description: "Ein Cartoonbild einer kleinen Pflanze, die aus der Erde wächst, als Metapher für Investitionen in technologische Architektur."
permalink: de/2023/04/low-code-vs-high-code.html
lang: de
---


In den hybriden Szenarien, die ich kürzlich in meinem [Beitrag über das Data Lakehouse](/de/2023/04/data-lakehouse-as-single-source-of-truth.html) erwähnt habe und die immer noch die Branche dominieren, werden Spark-Maschinen oft an vielen Stellen eingesetzt, um Datentransformationen durchzuführen. In diesem Zusammenhang ist Spark als Open-Source-System mit hocheffizienter verteilter Datenverarbeitung fast zum Standard geworden.


Allerdings ist Spark allein auch für erfahrene Entwickler zunächst eine zu überwindende Hürde. Hinzu kommen zeitaufwändige Optimierungsarbeiten, wenn man beispielsweise mit komplexen Python-Workflows arbeitet. Der Entwickler muss an vielen Stellen selbst aktiv werden, um das Bestmögliche herauszuholen und Kosten zu sparen. Dies bringt ein Dilemma mit sich, das in der Vergangenheit mit verschiedenen Ansätzen zu lösen versucht wurde.


Eine zentrale Frage, die sich Unternehmen oft stellen, ist, wie sie mit einfachen Mitteln schnell redundante Prozesse umsetzen können. Sie wollen sich nicht zu sehr in die Abhängigkeit von teuren Spezialisten begeben. Ziel ist es also, schnell zur Lösung zu kommen und sie auch für Nicht-Spezialisten einigermaßen einfach bedienbar zu machen. Geringe Personal- und Entwicklungskosten gegenüber höheren Betriebskosten.


![Ein Cartoon-Bild eines Eisbergs, der zu 80% unter Wasser liegt und nur eine kleine Spitze sichtbar ist.](/assets/img/iceberg.jpg)_Anfangskosten entsprechen oft der Spitze eines Eisbergs, Bildquelle: [Pixabay](https://pixabay.com/de/illustrations/eisberg-wasser-blau-ozean-eis-1421411/)_


## Low-code - Der einfache Weg


Der häufigste Ansatz zur Erreichung dieses Ziels ist die Nutzung von Low-Code-Plattformen. Dabei handelt es sich um Plattformen, die einfache, häufig verwendete Funktionen in einer einfachen, schnell zu erlernenden Benutzeroberfläche anbieten. Diese werden unter der Haube als Konfigurationen in gängigen Formaten wie JSON, YAML oder XML persistiert und schließlich von einem Interpreter programmatisch ausgeführt.


Wie beim Programmieren werden z.B. Kopieroperationen, Schleifen und Auswertungsaktivitäten angeboten, die sich ein Benutzer über einen grafischen Editor als zusammenklickbare Bausteine zusammensetzen kann. Erweitert wird dieses Funktionspaket in der Regel durch Konnektoren, die APIs von bekannten Drittanbietern integrieren.


Der Vorteil ist, dass es auch für einen unerfahrenen Dateningenieur möglich wird, einfache Anwendungsfälle zu implementieren. Darüber hinaus werden die Datenpipelines weitgehend selbstdokumentierend und können vom Benutzer ohne Verwendung von Code viel schneller entworfen werden. In Verbindung mit verwalteten Ressourcen, die von vielen Cloud-Anbietern zur Verfügung gestellt werden, kann so von der Notwendigkeit einer eigenen Infrastruktur abstrahiert werden.


Ein Nachteil ist jedoch, dass unerfahrene Dateningenieure in der Regel weniger optimierte Lösungen mit Low-Code erstellen. Diese können zwar die Aufgabe erfüllen, verursachen aber über einen langen Zeitraum sehr hohe Betriebskosten. Weitere Probleme ergeben sich aus der Abhängigkeit von einem bestimmten Anbieter, es sei denn, es handelt sich um eine Open-Source-Plattform, die auf eigenen Ressourcen läuft. Dadurch wird auch die künftige Migration zu anderen Systemen kostspieliger.


Komplexe Anwendungsfälle sind auch nicht so einfach zu implementieren. Nach meiner Erfahrung können etwa 80 % der Anwendungsfälle mit Low-Code implementiert werden. Für die Umsetzung der verbleibenden komplexeren Anwendungsfälle werden jedoch etwa 80 % der gesamten Entwicklungszeit benötigt. Pareto-Verteilung.


Einige Low-Code-Plattformen bieten hierfür bestimmte Mischformen an, zum Beispiel Mapping Data Flows, die Sie von Azure Data Factory kennen. Dabei handelt es sich um komplexere Datenpipeline-Jobs, die auf der Grundlage von Apache Spark-Clustern, die von Microsoft bereitgestellt werden, erstellt und ausgeführt werden können. Damit sind auch größere Transformationen für echtes ETL möglich, allerdings nur bis zu einem gewissen Grad.


![Ein Bild, das die Schnittstelle von Azure Data Mapping Data Flows beim Erstellen einer neuen Quelle am Anfang einer Pipeline zeigt](/assets/img/mapping_data_flow.png)
_Erstellung von ETL-Pipelines in einem Browser mit Data Factory, Bildquelle: [Microsoft](https://learn.microsoft.com/de-de/azure/data-factory/concepts-data-flow-overview)_


Viele Unternehmen werden daher weiterhin auf andere Drittanbieter zurückgreifen müssen, die die externe Ausführung von komplexem Code ermöglichen. Am Beispiel von Azure Data Factory bieten zum Beispiel HDInsight oder Databricks diese Möglichkeit, aber auch Azure Functions kann für diesen Zweck genutzt werden. In Azure Synapse Analytics gibt es zumindest die Möglichkeit, Code auf On-Demand-Clustern mit sogenannten Notebooks auszuführen. Das Gleiche gilt für vergleichbare Lösungen in AWS oder Google Cloud.


Damit wird das Problem sichtbar: Um alle Anwendungsfälle abzubilden, kommt man um einen Mix aus verschiedenen Frameworks nicht herum. Und dieser Overhead führt dazu, dass sich die Teams in verschiedene Technologien einarbeiten müssen. Manchmal entstehen auch gewisse Hürden, weil unerfahrene Ingenieure nicht in der Lage sind, komplexe Anwendungsfälle zu implementieren oder gar zu pflegen. Erfahrene Ingenieure möchten einfache Anwendungsfälle aufwändig, aber optimiert implementieren.


## High-Code - Teuer, aber effizient


Es stellt sich also die Frage, warum nicht direkt zu High-Code übergehen? Darunter verstehe ich rohen, selbst verwalteten und ausgeführten Code. Zum Beispiel Python-Programme, die auf ihren eigenen virtuellen Maschinen (in der Cloud gehostet) oder auf einem Kubernetes-Cluster laufen.


Wie bereits erwähnt, müssten dafür 80 % der Anwendungsfälle als Code implementiert werden. Wenn es sich dabei um Aufgaben handelt, die nicht sehr häufig ausgeführt werden und bei denen keine großen Betriebskosten zu erwarten sind, könnten die Entwicklungskosten stark ansteigen. Wenn langlebige Pipelines erforderlich sind, können die Entwicklungskosten langfristig amortisiert werden.


Mit High-Code ist es auch möglich, sehr optimierte und vereinfachte Frameworks zu erstellen. Diese können auch von weniger erfahrenen Kräften genutzt werden, indem man sie einbindet. Beispiele für bestehende Open-Source-Lösungen sind [Bonobo](https://www.bonobo-project.org/) oder [petl](https://petl.readthedocs.io/en/stable/) für Python.


![Ein Code-Beispiel des Python-Frameworks bonobo, das zeigt, wie man CSV-Daten mit einem CSV-Reader extrahiert, aus Name und Domain ein E-Mail-Ratefeld hinzufügt und es mit einem CSV-Writer wieder schreibt](/assets/img/bonobo.png)
_Schreiben von Datenpipelines in High-Code mit Bonobo, Bildquelle: [Bonobo](https://www.bonobo-project.org/)_


Gute Entwicklerteams sind aber auch in der Lage, solche Frameworks für die jeweiligen Anforderungen zu entwickeln. Damit hätte man eine einheitliche Plattform, die sowohl einfache als auch komplexe Datenpipelines schnell herstellbar macht. Nur eben nicht mit einem hübschen grafischen Editor.


Allerdings macht es Sinn, in verschiedene Lösungen zu diversifizieren. Schließlich entwickelt sich High-Code nicht weiter. Und auch Programmiersprachen ändern und verbessern sich. Open-Source-Pakete können veraltet sein und Sicherheitslücken können auftreten. Erfahrene Ingenieure sind oft rar und die oben genannten Gründe machen ein Unternehmen abhängig von erfahrenem Personal.


Im Vergleich zu den vielen Vorteilen, die man mit gemischten Low-Code-Plattformen automatisch erhält, ist der anfängliche Aufwand also höher. Es ist wie beim Bau eines Hauses: Will ich ein gutes, langlebiges Fundament oder will ich mein Haus häufig an sich ändernde Anforderungen anpassen?


## Fazit


Letztlich ist es eine Frage, wie viel Sie in die Erstentwicklung investieren wollen. Wenn Sie schnell zu einer Lösung kommen wollen und nicht zu viel in die Erstentwicklung investieren wollen, dann ist Low-Code der richtige Weg. Sie sollten sich jedoch darüber im Klaren sein, dass Sie auf lange Sicht mehr investieren müssen.


Vor allem beim Aufbau kritischer Datenpipelines, die über einen langen Zeitraum laufen sollen, ist es ratsam, in High-Code zu investieren. Dadurch sparen Sie langfristig viel Geld und reduzieren den Bedarf an umfangreichen und wiederkehrenden Wartungsarbeiten. Allerdings kann es schwierig sein, erfahrene Ingenieure für die Implementierung der Lösung zu finden.


Die Wahl der richtigen Lösung ist nicht immer einfach. Aber wenn Sie die Anforderungen und Prioritäten Ihres Unternehmens analysieren, werden Sie die richtige Lösung für sich finden. Wenn Sie unsicher sind, können Sie immer mit Low-Code beginnen und dann bei Bedarf teilweise auf High-Code migrieren. Und nicht zuletzt können Sie auch eine Mischung aus beiden Ansätzen verwenden. In diesem [Beitrag](/2023/04/data-pipelines-as-code-with-delta-live-tables.html) stelle ich mit Delta Live Tables eine Hybridlösung vor, die das Beste aus beiden Welten vereint.