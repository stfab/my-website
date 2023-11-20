---
layout: post-de
title: "Ich habe GitHub Copilot getestet und das ist passiert"
description: "Sie fragen sich, ob GitHub Copilot das Richtige für Sie ist? In diesem Artikel teile ich meine Gedanken und Erfahrungen, nachdem ich das Tool 30 Tage lang verwendet habe."
author: "Fabian Stadler"
categories: [tech,journal]
tags: [tools]
image: assets/img/github-copilot.jpeg
image_description: "An image of the GitHub Copilot logo."
permalink: de/2023/01/i-tested-github-copilot.html
lang: de
---

Ende 2021 hörte ich zum ersten Mal von Microsofts neuem KI-Codierungstool, GitHub Copilot. Es war die erste große Nachricht für mich nach der [umstrittenen Übernahme von GitHub durch Microsoft](https://news.microsoft.com/2018/06/04/microsoft-to-acquire-github-for-7-5-billion/) und der bekannten Massenflucht zu anderen Plattformen wie GitLab.


Damals war die KI als Technologie bereits im Aufwind und löste einen vergleichsweise kleinen Hype aus. [AlphaGo](https://www.deepmind.com/research/highlighted-research/alphago) von Google DeepMind hatte zwischen 2015 und 2017 für Schlagzeilen gesorgt, weil es mehrere Profi-Go-Spieler besiegt hatte. Ein Bot von [OpenAI zeigte 2017 einen Sieg beim Dota-2-Turnier The International 2017](https://qz.com/1052409/openai-just-beat-a-professional-dota-2-player-at-the-international-2017). Später kündigte Google sein KI-gestütztes Tool Google Lens an, das Millionen von Menschen auf ihren Smartphones nutzen.


Dennoch war dieser Hype weit von dem entfernt, was wir heute haben, da die meisten dieser Entwicklungen nur Demonstrationen waren, aber keine bahnbrechenden Verbesserungen für das tägliche Leben der Menschen brachten. Dies änderte sich 2020, als OpenAI seinen Generative Pre-trained Transformer 3 (GPT-3) veröffentlichte und eine breite Palette von Fähigkeiten vorstellte. Dazu gehörten die Generierung verschiedener Texte, Codegenerierung, Frage-und-Antwort-Szenarien und vieles mehr.


Von da an war es nur noch eine Frage der Zeit, bis die Menschen einen Weg fanden, KI für ein breites Spektrum von Anwendungsfällen zu nutzen. Ein wichtiger Impuls kam von OpenAI, das eine Beta-Version mit kostenlosem Guthaben zur Verfügung stellte, die es fast jedem ermöglichte, seine API für die oben genannten Aufgaben auszuprobieren. Wie viele andere Menschen bin auch ich zum ersten Mal durch Memes und lustige Textgenerierungsversuche anderer Leute mit GPT-3 in Berührung gekommen.


Als Ingenieur war die Codegenerierung für mich der interessanteste Anwendungsfall, da ich viele Aufgaben kannte, die einfach und repetitiv zu codieren waren, aber dennoch einige Minuten oder eine schnelle Suche auf Stack Overflow kosteten. Wenn wir ein Tool hätten, das nur diese Aufgaben überflüssig machen würde, könnte es jede Woche Minuten, wenn nicht sogar Stunden einsparen und die Personalkosten um mehrere hundert Dollar pro Person und Monat senken.


Das einzige Problem, das ich hatte, war, dass meine ersten Versuche mit der OpenAI-Beta nicht zufriedenstellend waren. Die Benutzeroberfläche lieferte interessante und oft gute Ergebnisse für kleine Eingabeaufforderungen, aber es war schwierig, hervorragende Ergebnisse für große Zusammenhänge zu erzielen. Oft wollen wir Hilfsmethoden innerhalb bereits existierender Klassen generieren und Variablennamen und Konventionen beibehalten. Das bedeutete, dass man bei einem unbefriedigenden Ergebnis die gesamte Eingabeaufforderung wiederherstellen und erneut ändern musste. Bald war ich der Meinung, dass KI in diesem Zustand nur bei der Generierung einfacher Dinge hilfreich ist.


## GitHub Copilot - ein Game Changer?


GitHub Copilot wurde erstmals im Juni 2021 angekündigt und als technische Vorschau veröffentlicht, wobei der Zugang zunächst auf eine kleine Gruppe von Entwicklern beschränkt war. Ab März 2022 wurde GitHub Copilot für Microsofts IDE Visual Studio verfügbar. Später im Juni beendete GitHub die technische Vorschau und stellte Copilot als abonnementbasierten Dienst für einzelne Entwickler zur Verfügung. Das Tool befindet sich nach wie vor in der Entwicklung und wird seither regelmäßig aktualisiert und verbessert.


Von da an stieg GitHub Copilot schnell zum Diskussionsthema Nr. 1 auf und erregte die Aufmerksamkeit fast aller Entwickler. Die Erwartungen waren hoch. Man fragte sich, ob es die Branche verändern würde, aber viele machten sich auch Sorgen über Entlassungen durch Automatisierung. Es war so allgegenwärtig, dass es lästig war. Und da meine Erfahrungen mit GPT-3 unbefriedigend waren, habe ich mich nicht wirklich bemüht, es auszuprobieren, als ich von vielen Problemen hörte. 


Eines der größeren Probleme war das Urheberrecht. Da ich mich mit der Open-Source-Gemeinschaft verbunden fühlte und um die Probleme wusste, die KI mit unseren derzeitigen Urheberrechtsgesetzen verursacht, fand ich es sehr kontrovers. Vor allem DALL-E, ein weiteres KI-Modell von OpenAI, das auf der Grundlage von gescrapten Bildern Bilder mit Textaufforderungen generiert, war parallel dazu sehr in Verruf geraten, weil sich viele Künstler machtlos und beraubt fühlten. 


## ChatGPT und der zweite KI-Hype


Nun, da die Diskussionen über GitHub Copilot abflauten, bahnte sich ein anderes KI-Modell seinen Weg zur Popularität. Und dieses Mal war der KI-Hype echt. Mit ChatGPT veröffentlichte OpenAI Ende 2022 eine verbesserte Version ihrer bisherigen Modelle als kostenlose Forschungsversion. Nun konnte jeder einfach und ohne Einschränkungen auf KI zugreifen. Die Anwendungsfälle waren unbegrenzt. Selbst für OpenAI kam der Hype so unerwartet, dass die kostenlose Benutzeroberfläche bis heute stark belastet ist und sie einen kostenpflichtigen Dienst mit stabilerem Zugang eröffnen konnten.


Während Medienunternehmen schnell auf diesen Hype-Zug aufsprangen, wurde ChatGPT zu einem der großen Nachrichtenthemen. Dies bedeutete auch, dass viele Unternehmen darüber nachdachten, wie sie KI nicht nur als Analysedienst, sondern auch zur Verbesserung ihrer eigenen Entwicklung nutzen können. Microsoft hat eine große Investition in seine Partnerschaft mit OpenAI getätigt und damit große Erwartungen an viele zukünftige KI-gestützte Dienste geweckt, auf die Unternehmen Zugriff haben.


Das führt mich zum eigentlichen Thema dieses Artikels, nämlich meinen eigenen Erfahrungen mit GitHub Copilot. Um mehr über die Fähigkeiten von GitHub Copilot herauszufinden, hatte ich im letzten Monat die Gelegenheit, die Testversion auszuprobieren. So habe ich den KI-Assistenten in verschiedenen Szenarien getestet und viel darüber nachgedacht.


## Die Grundlagen von GitHub Copilot


Zunächst einmal: Wie funktioniert GitHub Copilot eigentlich? Die Einrichtung ist im Prinzip sehr einfach. Alles, was Sie brauchen, ist ein GitHub-Konto. Wenn Sie bereits ein bestehendes Konto haben oder ein neues erstellt haben, können Sie nun auf die Seite [GitHub Copilot](https://github.com/features/copilot) gehen und sich für die kostenlose Testversion anmelden, indem Sie auf "Start my free trial" klicken.


![Eine kostenlose Testversion von GitHub Copilot starten](/assets/img/github-copilot-homepage.png){:style="float: center"}


Sie werden durch ein Verfahren geführt, bei dem Sie einige persönliche Daten eingeben müssen. Dazu gehören Ihre Adresse und eine Kreditkarte oder ein PayPal-Konto, um Missbrauch vorzubeugen und künftige Zahlungen einzuziehen, falls Sie den Dienst über einen längeren Zeitraum nutzen möchten. Ansonsten endet die Testphase nach 60 Tagen und ist kostenlos.


Wenn Sie das getan haben, ist alles andere sehr einfach. Sowohl für Visual Studio Code als auch für Visual Studio gibt es Plugins, die einfach über den Marketplace installiert werden können. Für Visual Studio müssen Sie ein Upgrade auf eine neuere Version durchführen, wenn Sie es noch nicht installiert haben. Natürlich gibt es ähnliche Plugins auch für andere IDEs, aber ich habe sie bisher nur für diese beiden IDEs ausprobiert.


### Code-Vorschläge


Kommen wir nun zur Verwendung von GitHub Copilot selbst. GitHub Copilot ist automatisch aktiviert, nachdem Sie die Plugins installiert haben. Aber wie arbeitet man mit ihm? Das ist eigentlich ganz einfach: Am besten legen Sie ein neues lokales Repository für die ersten Tests an und erstellen eine neue Hauptklasse oder Funktion in einem Unterverzeichnis. Alternativ können Sie auch ein bestehendes Repository oder sogar eine lose Skriptdatei verwenden.


Sobald Sie programmieren, werden automatisch Vorschläge für weiteren Code generiert und angezeigt. Dies funktioniert analog zu bestehenden Code-Vervollständigungsfunktionen.


![Schreiben einer Hello World-Funktion mit GitHub Copilot](/assets/img/github-copilot-hello-world-test.png){:style="float: center"}


Normalerweise braucht es ein paar Buchstaben, um einen sinnvollen Vorschlag anzuzeigen. GitHub Copilot lässt sich von dem leiten, was es einliest, im obigen Beispiel der Funktionsname, der schon deutlich darauf hindeutet, dass jetzt "Hello World" ausgegeben werden soll.


Für die Entwicklung mit dem Tool bedeutet dies, dass Sie bei Funktionsnamen immer so spezifisch sein sollten wie der Code, den Sie haben wollen. GitHub Copilot ist nicht der heilige Gral, der schon anhand des Klassennamens weiß, wie der komplette Code aussehen soll. Sie müssen das Tool auch ein wenig anleiten.


Sie wollen aber nicht immer einen 120-Zeichen-Funktionsnamen erstellen, damit das Tool weiß, was es tun soll. Deshalb können Sie sich mit Kommentaren helfen. Entweder Sie geben im Docstring genau an, was die Funktion tun soll.


![Hello World From With Loop Docstring](/assets/img/github-copilot-hello-world-hundred.png){:style="float: center"}


Oder Sie können Copilot zeilenweise verwenden und immer zuerst einen Kommentar schreiben und dann einen Vorschlag für die nächsten Zeilen erhalten.


![Hello World With Loop From Comment](/assets/img/github-copilot-hello-world-hundred2.png){:style="float: center"}


Einige werden sich nun fragen, ob GitHub Copilot auch kontextabhängig verwendet werden kann, und die Antwort auf diese Frage ist ein klares Ja. Copilot kann auch innerhalb bestehender Klassen originelle Vorschläge machen.


Einerseits kann er neue Funktionen erwarten und somit proaktiv beitragen.


![Context Suggestions With Copilot](/assets/img/github-copilot-hello-world2.png){:style="float: center"}


Wie zuvor können Sie auch mit der Definition einer Funktion beginnen und Copilot diese vervollständigen lassen.


![Hello World From Context](/assets/img/github-copilot-hello-world3.png){:style="float: center"}


Auch hier gilt: Geben Sie so viele Informationen wie möglich an, wenn die Funktion angemessen komplex sein soll.


### KI-unterstützte Dokumentation


Eine weitere Funktion, die die Arbeit mit Copilot vereinfacht, ist die Dokumentation von bestehendem Code. Das bedeutet, dass Sie eine Funktion schreiben oder bereits eine haben und dann GitHub den Docstring für Copilot schreiben lassen. Das spart sehr oft eine Menge Zeit, die die meisten Leute sparen, indem sie nicht dokumentieren. Mit Copilot ist das eine Sache von Sekunden.


![Copilot zur Erstellung von Docstrings](/assets/img/github-copilot-hello-world4.png){:style="float: center"}


Wenn Sie eine bestimmte Syntax für den Docstring erzwingen wollen, können Sie dies tun, indem Sie GitHub Copilot eine Anleitung geben.


![Copilot verwendet, um Parameter zu dokumentieren](/assets/img/github-copilot-hello-world5.png){:style="float: center"}


Im obigen Beispiel können Sie sehen, dass Sie durch die Angabe des Abschnitts für die Argumente und das Einfügen eines Tabs die entsprechende Variable mit einem Kommentar erhalten. Leider ist Copilot noch nicht so gut, um den kompletten Docstring mit allen Parametern zu erstellen. Man muss also ein wenig nachhelfen.


Wie gut die Dokumentation am Ende sein wird, ist natürlich Geschmackssache. Aber Copilot ist ein hervorragender Assistent, der vieles schneller macht und es ist besser, schwach zu dokumentieren als gar nicht.


### Generierte Unit-Tests


Abschließend möchte ich noch auf einen für mich sehr lohnenswerten Anwendungsfall hinweisen. GitHub Copilot eignet sich nämlich nicht nur für den eigentlichen Code oder die Dokumentation, sondern auch für Tests. Wie bei der Dokumentation sind Unit-Tests bei Entwicklern oft unbeliebt, weil sie Zeit kosten und bei größeren Änderungen ohnehin neu geschrieben werden müssen. Wenn man nicht mit TDD arbeitet, testet man selten Erwartungen, sondern Dinge, von denen man bereits weiß, dass sie funktionieren. Ob das Sinn macht, muss jeder für sich selbst wissen. Zumindest für Regressionstests macht es ein bisschen Sinn.


Wenn wir jetzt also einen Test erstellen und zum Beispiel pytest in Python importieren, können wir zunächst eine Funktion definieren, die "Hello World" zurückgibt. Sobald ich eine neue Funktion implementieren will, bekomme ich automatisch einen Test generiert. 


![Unit Tests mit GitHub Copilot](/assets/img/github-copilot-hello-world6.png){:style="float: center"}


Dies funktioniert natürlich nicht nur bei der direkten Implementierung von Funktionen, sondern auch bei importierten Modulen. Noch komplexere Tests sind möglich, wenn man sie richtig spezialisiert. Oft muss man aber eigene Fixtures schreiben. Aber dann kann Copilot mit den Informationen aus dem Fixture und ein wenig Anleitung einen guten Unit-Test schreiben.


## Die Sichtweise des Reviewers


Nachdem ich nun die grundlegende Funktionalität von GitHub Copilot erklärt habe, die ich sehr interessant finde, ein Kommentar von mir zu seiner allgemeinen Verwendung. Wie wir bereits gesehen haben, ist GitHub Copilot sehr leistungsfähig und hebt die bisherigen Code-Vervollständigungsfunktionen auf eine ganz neue Ebene, indem es die Generierung von komplexem Code im Kontext ermöglicht.


Aber was bedeutet das für den Entwickler und seine Arbeit mit solchen Tools? Nun, nachdem ich viel darüber nachgedacht habe, bin ich zu dem Schluss gekommen, dass der Entwickler zunehmend die Rolle eines Überprüfers einnimmt. Damit meine ich, dass wir als Entwickler weniger über einfache Implementierungen nachdenken und uns stattdessen zuerst um eine akkurate Dokumentation und konzeptionelle Gestaltung kümmern müssen. Dann lassen wir den Code auf der Grundlage dieses Konzepts schreiben und prüfen nur noch, ob das Ergebnis gut ist oder ob es überarbeitet werden muss.


Dieser Ansatz ist vergleichbar mit einem Architekten oder leitenden Entwickler, der ein Programm mit Hilfe von UML und in Textform entwirft. Die Entwickler kümmern sich dann um den Code und legen ihn zur Überprüfung vor. Dort wird geprüft, ob die Qualität stimmt, ob Dinge angepasst oder sogar optimiert werden müssen und so weiter. Was wir am Ende veröffentlichen und verwenden, entscheidet in der Regel der Verantwortliche.


Für uns, die wir Dienste wie Copilot nutzen, bedeutet dies, dass wir eindeutig für das verantwortlich sind, was wir veröffentlichen. Wie viele bereits wissen, kann Copilot auch fehlerhaften oder sogar unsicheren Code erzeugen. Oft erhält man auch nicht das gewünschte Ergebnis. Es ist also Sache des Entwicklers, den Code gründlich zu prüfen, zu testen und gegebenenfalls manuell zu optimieren. Auch ein Tool wie GitHub Copilot kann einen erfahrenen Entwickler nicht ersetzen. Aber es kann unterstützen.


Wir müssen uns im Voraus darüber im Klaren sein, was wir als exzellentes Ergebnis akzeptieren, und während der Entwicklung entscheidende Änderungen vornehmen, um unser gewünschtes Ergebnis zu erreichen. Umso wichtiger ist es, eine gute Grundlage zu schaffen und diese konsequent durchzusetzen. Ohne diese Grundlage kann uns auch GitHub Copilot keinen vorbildlichen Dienst oder ein vorbildliches Programm erstellen.


Im schlimmsten Fall kann dies dazu führen, dass unerfahrene Entwickler KI-Tools wie GitHub Copilot nutzen, um schlechte und unsichere Lösungen zu erstellen, die ihren Weg in die Produktionssysteme finden. Nach wie vor ist es Aufgabe des Prüfers, diese Schwachstellen zu analysieren und zu finden. Es wäre töricht, einfach darauf zu vertrauen, dass Menschen, die mit GitHub Copilot entwickeln, guten Code erstellen.


An der aktuellen Rollenverteilung wird sich also so schnell nichts ändern. Aber vielleicht kann die Effizienzsteigerung schon den einen oder anderen Arbeitsplatz retten. Vielleicht bleibt durch die Kosteneinsparungen mehr Geld für mehr Entwickler übrig. Letztendlich könnte dies sogar zu mehr Stellen führen. Aus meiner Sicht kann ich das aber im Moment nicht sagen.


Ich kann nur sagen, dass es einige Aufgaben wie Dokumentation, Unit-Tests und sich wiederholenden Code, den man oft schreibt, wie rekursive Funktionen, viel schneller erledigt. Das spart mir selbst bei der Entwicklung viel Zeit und möglicherweise auch den Kunden viel Zeit.


GitHub Copilot gibt es derzeit in [zwei Versionen](https://github.com/features/copilot#pricing) für einzelne Entwickler für 10 Dollar pro Monat und für Unternehmen für 19 Dollar pro Monat und Lizenz. Nehmen wir an, ein Entwickler kostet ein Unternehmen rund 100 Dollar pro Stunde, dann muss das Tool nur ein Fünftel einer einzigen Stunde Zeit im Monat einsparen, um sich zu amortisieren. Schon die Dokumentation einiger weniger Funktionen kann diese Zeitersparnis bringen. Wie ich bereits geschrieben habe, gehe ich davon aus, dass sich damit mehrere hundert Dollar pro Monat und Person einsparen lassen. Copilot wird aber sicher nicht der einzige Dienst bleiben, der solche Funktionen anbietet. Sonst könnte Microsoft viel mehr verlangen.


## Kontroversen und Befürchtungen


Nachdem ich nun alle meine Gedanken zusammengetragen habe, möchte ich noch einen weiteren Punkt ansprechen. Und zwar, dass meine obigen Erfahrungen lediglich eine unvoreingenommene Sichtweise darstellen, ohne zu kritisieren, was der Entwickler mit GitHub Copilot noch an Rechten verschenkt oder wie Copilot rechtlich einzuordnen ist. Auch bin ich noch nicht auf die geschäftlichen Risiken eingegangen, die von Diensten wie GitHub Copilot ausgehen.


Erstens gibt es, wie ich eingangs erwähnt habe, die Urheberrechtskontroverse. Gemeint ist damit, dass [GitHub Copilot auf öffentliche Repositories geschult wurde](https://www.theverge.com/2022/11/8/23446821/microsoft-openai-github-copilot-class-action-lawsuit-ai-copyright-violation-training-data). Dazu gehören auch solche, die mit vererbbaren Lizenzen ausgestattet sind, die es Nutzern erlauben, Code in ihrem eigenen Repository zu verlinken oder zu verwenden, sofern dieselbe Lizenz verwendet wird. Dies ist sehr häufig der Fall, insbesondere bei Open-Source-Software, da die Leute selten wollen, dass freier Code kommerziell wird.


Aus diesem Grund gibt es einen Rechtsstreit, der wahrscheinlich wenig Chancen hat. GitHub verweist auf seine eigenen Nutzungsbedingungen, die einen Hinweis darauf enthalten, dass GitHub die gehosteten Daten zur Verbesserung seiner eigenen Dienste nutzen darf. Wie das rechtlich korrekt aussieht, kann ich allerdings nicht beantworten, da ich kein Jurist bin.


Tatsache ist jedoch, dass wie bei DALL-E, das es Nutzern ermöglicht, ohne Wiederverwendungsrechte mit viel Aufwand und wenig Gegenleistung sehr ähnliche Dinge wie die von Künstlern veröffentlichten zu erzeugen, GitHub Copilot sehr ähnlichen Code erzeugen kann, an dem jemand anderes ein Urheberrecht besitzt. In seltenen Fällen [kann er sogar bloße Kopien erstellen](https://twitter.com/DocSparse/status/1581461734665367554?s=20). Auch wenn GitHub dies einschränkt.


Damit befinden sich die Nutzer von Copilot in einer [rechtlichen Grauzone](https://www.creativereview.co.uk/artificial-intelligence-copyright/), die in den kommenden Jahren sicherlich noch zu diskutieren sein wird. Die Quintessenz ist, dass der Nutzer sicherstellen muss, dass er keinen Code verwendet, der dem Urheberrecht unterliegt. In der Realität ist dies jedoch fast unmöglich. Genauso wie es fast unmöglich ist, zu widerlegen, dass man den Code selbst entwickelt hat. Vor allem bei einfachen Funktionen, die jeder schon einmal geschrieben hat. Der Nutzer von Copilot trägt also dazu bei, dass man sich zunächst mit dieser Grauzone abfindet, die vor allem für Künstler den finanziellen Ruin bedeuten kann.


Genauso undurchsichtig ist, was es bedeutet, wenn Copilot zum Urheber wird. In vielen Ländern ist es [nicht vorgesehen, dass ein Programm oder eine Maschine etwas mit Urheberrecht produziert](https://www.theverge.com/2023/1/26/23570967/chatgpt-author-scientific-papers-springer-nature-ban). Dieser Umstand wird bereits bei KI-generierten Büchern mit ChatGPT diskutiert und ist rechtlich nicht geklärt.


Letztlich ist für mich als Nutzer nicht ganz klar, welche Daten in welcher Form an GitHub Copilot gesendet werden. Natürlich wird Datensicherheit behauptet und wahrscheinlich wird das auch korrekt gemacht. Aber es gibt [andere Metriken](https://docs.github.com/en/site-policy/privacy-policies/github-copilot-for-business-privacy-statement), die in die Hände des Produktanbieters fallen, nicht nur Copilot. Daher sollte das Produkt, wie andere KI-Tools auch, mit Vorsicht genossen werden. 


Vor allem, wenn Sie in einem Bereich tätig sind, in dem Sicherheit an erster Stelle steht. Daher ist es wahrscheinlich rechtlich nicht möglich, Copilot ohne Zustimmung für Kunden oder Projekte zu verwenden, bei denen man einer gewissen Geheimhaltung unterliegt. Unterm Strich senden Sie immer noch Code, der Eigentum eines Kunden ist, an eine dritte Partei. Das ist wie eine Auslagerung der Entwicklung. Aber auch hier kann ich keine rechtlich fundierte Bewertung abgeben, so dass dies nur meine Meinung widerspiegelt.


## GitHub Copilot macht lästige Aufgaben überflüssig


Abschließend kann ich sagen, dass es mir trotz aller Bedenken und Risiken Spaß gemacht hat, GitHub Copilot zu testen, und ich werde es weiter verfolgen. Vielleicht schreibe ich noch einige Artikel über ähnliche Lösungen. Dennoch kann ich mir noch keine allgemeine Meinung darüber bilden, ob die Verwendung von GitHub Copilot kommerziell sinnvoll ist und wie man es rechtlich nutzen kann. Ich denke, diese Diskussion wird in den nächsten Jahren viele Bereiche betreffen und wird auch weiterhin eine schwer zu lösende Grauzone sein.


Dennoch muss ich zugeben, dass Tools wie Copilot viele Dinge vereinfachen und definitiv Zeit sparen. Insbesondere für die Dokumentation, das Testen und viele sich wiederholende Aufgaben, die sonst viel Zeit in Anspruch nehmen, ist es eine optimale Lösung, die sicherlich noch besser werden wird.


Letztendlich akzeptieren wir, dass sich solche Lösungen durchsetzen werden. Denn wenn man nicht auf den Zug aufspringt, wird man wahrscheinlich überholt werden. KI-Dienste erinnern mich an Erfindungen wie Drucker und Roboter, die zwar Arbeitsplätze gekostet haben, es den Menschen aber ermöglichten, sich mit wichtigeren Dingen zu beschäftigen. Es bleibt also abzuwarten, inwieweit Tools wie GitHub Copilot zu einem Wandel in der Entwicklung führen werden. Es ist jedoch absehbar, dass sie wesentlich zur weiteren Entwicklung im IT-Sektor beitragen werden. Zumindest was die Produktivität angeht.