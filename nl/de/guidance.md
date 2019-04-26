---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-07"

subcollection: personality-insights

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:deprecated: .deprecated}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# Verwendungshinweise
{: #guidance}

Benutzer nutzen den {{site.data.keyword.personalityinsightsshort}}-Service für eine wachsende Zahl von Anwendungsfällen. Sie setzen den Service ein, um Kunden über Selbstbedienungsterminals (Kiosks) im Geschäft personalisierte Produktempfehlungen zu präsentieren. Sie erkunden und analysieren Unterschiede in der Persönlichkeit von US-Präsidenten, wie sie aus ihrer jeweiligen Ansprache zur Lage der Nation ('State of the Union Address') abgeleitet wurden. Und sie integrieren den Service mit einem anderen Produkt im {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}}-Portfolio, nämlich {{site.data.keyword.watson}} Explorer, um zu veranschaulichen, wie ein Anlageberater auf der Grundlage der Persönlichkeitsportraits von Investoren geeignete Optionen anbieten kann. (Weitere Informationen finden Sie unter [Anwendungsfälle](/docs/services/personality-insights?topic=personality-insights-usecases).)
{: shortdesc}

Während der gesamten Entwicklung dieser und anderer zukünftiger Anwendungsfälle hat {{site.data.keyword.IBM_notm}} Gespräche mit Banken, Dienstleistern im Gesundheitswesen, Unternehmen für Kundenerfahrungsmanagement und Bundesbehörden geführt. Bei diesen Gesprächen werden häufig Fragen zu nützlichen Verwendungsszenarios aufgeworfen.

-   Welcher Typ von Text eignet sich am besten zur Erschließung der Persönlichkeit einer Person? Muss der Text seinem Wesen nach reflektierend sein? Wenn dem so ist, wie viel Reflexion ist erforderlich und wie lässt sie sich messen? Siehe [Welcher Typ von Text ist für die Persönlichkeitserschließung optimal?](#optimal)
-   Wie ist Text zu interpretieren, der von einer Person über eine andere Person geschrieben wurde? Lässt sich die Persönlichkeit eines Autors aus fiktiven Werken des Autors ableiten? Kann Text, der von mehreren Personen geschrieben wurde, kombiniert werden, um ein Persönlichkeitsportrait zu erhalten? Siehe [Ergebnisse aus verschiedenen Typen von Text interpretieren](#interpreting).
-   Lassen sich Persönlichkeitsportraits aus Text ableiten, der durch Transkriptions- oder Übersetzungsservices generiert wurde? Siehe [Persönlichkeit aus generiertem Text ableiten](#inferring).
-   Lassen sich Persönlichkeitsportraits für Anwendungen wie das Abgleichen von Personen, Überwachen und Vorhersagen mentaler Gesundheit und das Überwachen radikaler und verbrecherischer Elemente in Social Media nutzen? Siehe [Persönlichkeitsportraits für bestimmte Anwendungen verwenden](#applying).
-   Entwickelt sich die Persönlichkeit einer Person mit zunehmendem Alter? Siehe [Ändert sich die Persönlichkeit einer Person mit der Zeit?](#evolve)

## Welcher Typ von Text ist für die Persönlichkeitserschließung optimal?
{: #optimal}

Welcher Typ von Text eignet sich am besten zur Persönlichkeitserschließung? Muss der Text reflektierend, selbstreflektierend, formell oder informell sein? Wie werden die Wörter gemessen, die im alltäglichen Leben verwendet werden? Sind solche Wörter an sich reflektierend? Die Antworten auf diese Fragen helfen Ihnen bei der Auswahl der am besten geeigneten Eingabe, um den Service mit höchster Effektivität zu nutzen.

Die Arbeit von {{site.data.keyword.IBM_notm}} am {{site.data.keyword.personalityinsightsshort}}-Service basiert auf der grundlegenden Prämisse, dass die Wörter, die eine Person im täglichen Leben benutzt, Aufschluss über die Persönlichkeit der Person geben ([Pennebaker und andere, 2001](/docs/services/personality-insights?topic=personality-insights-references#pennebaker2001), und [Pennebaker und andere, 2007](/docs/services/personality-insights?topic=personality-insights-references#pennebaker2007)). Der Service kann Wörter analysieren, die von Einzelpersonen zu sich selbst oder zu einem beliebigen Thema geschrieben wurden. Damit der Service ein genaues Persönlichkeitsporträt generieren kann, müssen die Einzelpersonen die Wörter selbst auswählen und schreiben.

{{site.data.keyword.IBM_notm}} ist der Ansicht, dass der Text, der zur Erschließung der Persönlichkeit einer Person verwendet wird, im Idealfall reflektierend sein sollte. Reflektierendes Schreiben offenbart die persönlichen Erfahrungen und Reaktionen des Autors. Es verlangt vom Autor , sich ein bestimmtes Maß an Gedanken um die Auswahl der Wörter zu machen. Der Text kann zum Beispiel Meinungen, Einstellungen, Empfindungen und Beobachtungen des Autors über jemanden oder etwas beinhalten. Er kann auch die Vorlieben und die Abneigungen des Autors zum Ausdruck bringen. Er muss jedoch die Wortwahl des Verfassers widerspiegeln.

{{site.data.keyword.IBM_notm}} hat keine expliziten Verweise in der psycholinguistischen Literatur dazu gefunden, ob der Text, der zur Ableitung der Persönlichkeit herangezogen wird, Reflexion enthalten sollte. {{site.data.keyword.IBM_notm}} hat jedoch beobachtet, dass manche Studien Wörter aus Text verwenden, der in einem Laborumfeld erfasst wurde, in dem Personen dazu aufgefordert wurden, kurze Aufsätze zu bestimmten Themen zu verfassen. Dieser Typ von Text erfordert implizit einen gewissen Grad an Reflexion. Andere Studien verwendeten Text aus natürlichen Proben wie Blogs zu verschiedenen Themen, Tweets auf Twitter, E-Mails oder sogar aus der Kommunikation, die aus dem Spiel *World of Warcraft* extrahiert wurde. Alle Studien dieser Art gehen davon aus, dass die Wörter, die im täglichen Leben benutzt werden, Persönlichkeit offenbaren, da sie die Tendenz haben, die Gedanken des Verfassers widerzuspiegeln.

Andere Studien belegen, dass sich emotionale Texte, kontrolliert geschriebene Texte sowie Blogs und Sprachtranskripte gut zur Ableitung von Persönlichkeitsmerkmalen eignen. Wissenschaftliche Artikel sind im Gegensatz dazu eher weniger zur Erschließung von Persönlichkeitsmerkmalen geeignet. Darüber hinaus weist die Literatur darauf hin, dass die Erzielung genauer Persönlichkeitsmerkmale durch folgende Texteigenschaften noch erschwert wird:

-   Text mit fehlender Authentizität wie durch Sarkasmus, Ironie, intensive Bearbeitung oder mehrere Autoren
-   Text mit orthografischen Fehlern, Fachwörtern, alternativen Wortbedeutungen, Negation und Phrasen anstelle einzelner Wörter
-   Text mit ungeeigneten Vergleichsgruppen, wie professionell oder persönlich verfasste Texte oder technische oder emotionale Texte

## Ergebnisse aus verschiedenen Typen von Text interpretieren
{: #interpreting}

Der Typ des zu analysierenden Texts kann signifikante Auswirkungen auf die Qualität der Ergebnisse des {{site.data.keyword.personalityinsightsshort}}-Service haben. In den folgenden Abschnitten wird die Interpretation der Ergebnisse erörtert, die aus verschiedenen Quellen abgeleitet werden:

-   [Ergebnisse aus Text über andere interpretieren](#writingaboutothers)
-   [Ergebnisse aus fiktiven Werken interpretieren](#fictionalworks)
-   [Ergebnisse aus Text von mehreren Personen interpretieren](#multipleindividuals)

### Ergebnisse aus Text über andere interpretieren
{: #writingaboutothers}

Muss der Text für eine zuverlässige Erschließung der Persönlichkeit einer Person *von* der Person geschrieben sein oder kann er *über* die Person von einem anderen Verfasser geschrieben sein? Wenn eine Person über eine andere Person schreibt, wessen Persönlichkeit wird aus dem Text erschlossen?

{{site.data.keyword.IBM_notm}} geht intuitiv davon aus, dass ein Text immer die Persönlichkeit des Autors widerspiegelt, und zwar unabhängig vom Thema. Wenn Person A zum Beispiel einen Text über Person B schreibt, leitet eine Analyse des Texts die Persönlichkeit von Person A ab. Obwohl Person A über Person B schreibt, wählt tatsächlich Person A die Wörter aus, um ihre Eindrücke über Person B auszudrücken. {{site.data.keyword.IBM_notm}} hat dieses Szenario allerdings nicht explizit getestet.

### Ergebnisse aus fiktiven Werken interpretieren
{: #fictionalworks}

{{site.data.keyword.IBM_notm}} empfiehlt, keine Persönlichkeitsmerkmale eines Autors aus seinen fiktiven Werken abzuleiten. Beim Verfassen fiktiver Texte portraitieren Autoren jeden Charakter mit Bedacht unterschiedlich, sie bauen Dialoge auf, um die Persönlichkeiten ihrer Charaktere widerzuspiegeln und sie definieren in ihrer Vorstellung die Persönlichkeit eines jeden Charakter vorab.

Die Verwendung eines Texts, der dazu gedacht ist, die Persönlichkeit eines personifizierten fiktiven Charakters abzubilden, um die Persönlichkeit des Erfinders dieses Charakters zu erschließen, ist ein fragwürdiges Verfahren. Auch wenn jeder Autor einen einzigartigen Stil hat, sind die Charaktere immer noch bewusst und gezielt vorkonfiguriert. Die Persönlichkeit eines Autors kann jedoch aus nicht fiktiven Essays, Interviewmitschriften oder anderen Werken wie Einführungen, Prologen, Danksagungen oder Widmungen abgeleitet werden.

### Ergebnisse aus Text von mehreren Personen interpretieren
{: #multipleindividuals}

Ein gängiger Anwendungsfall des {{site.data.keyword.personalityinsightsshort}}-Service ist die Analyse der Follower einer Marke oder eines Unternehmens. Follower sind als Menschen definiert, die einem Unternehmen auf Twitter oder auf einer öffentlichen Facebook-Seite folgen. In diesem Szenario besteht das Ziel darin, die Gesamtpersönlichkeit der Follower eines Unternehmens zu ermitteln. Eine bevorzugte Methode besteht darin, genügend Text zu sammeln, der von den Mitgliedern einer Gruppe geschrieben wurde, um die Persönlichkeit eines jeden Mitglieds zu berechnen. Die Persönlichkeiten werden dann in unterschiedlichen Gruppen zusammengefasst. Diese Gruppen stellen die Charaktere (Personae) mit individuellen Persönlichkeitsmerkmalen dar, die dem Unternehmen folgen.

Wenn nicht ausreichend Text von den Mitgliedern einer Gruppe zur Verfügung steht, kann Text, der von vielen Mitgliedern geschrieben wurde, kombiniert und analysiert werden, um ein durchschnittliches oder zusammengesetztes (kombiniertes) Persönlichkeitsportrait für die Gruppe als solche zu erzeugen. Dieser Ansatz kann einen Hinweis auf die dominanten Eigenschaften der Gruppe geben, jedoch nimmt die Genauigkeit dieser Methode mit der Diversität der Mitgliedspopulation ab. Gehen Sie bei der Interpretation von Portraits, die aus der Aggregation von Text mehrerer Einzelpersonen abgeleitet wurden, mit Umsicht vor. Die Arbeit von {{site.data.keyword.IBM_notm}} auf diesem Gebiet befindet sich immer noch in der Anfangsphase. Weitere Erkenntnisse werden von {{site.data.keyword.IBM_notm}} berichtet, wenn überzeugende Ergebnisse vorliegen.

## Persönlichkeit aus generiertem Text ableiten
{: #inferring}

Die Analyse von Text, der durch Transkriptions- oder Übersetzungsservices generiert wurde, kann sich auf die Zuverlässigkeit der Ergebnisse des {{site.data.keyword.personalityinsightsshort}}-Service auswirken. In den folgenden Abschnitten werden die Auswirkungen der Ableitung von Persönlichkeitsmerkmalen aus generiertem Text erläutert:

-   [Persönlichkeit aus Sprachtranskripten ableiten](#transcription)
-   [Persönlichkeit aus übersetztem Text ableiten](#translation)

### Persönlichkeit aus Sprachtranskripten ableiten
{: #transcription}

Engines für die Verschriftung (Transkription) von Sprache wie der Service {{site.data.keyword.speechtotextshort}} von {{site.data.keyword.IBM_notm}} generieren schriftlich festgehaltenen Text aus gesprochener Sprache. Unterschiedliche Transkriptionsengines haben jeweils unterschiedliche Genauigkeitsbereiche. Kunden, die Sprache zu Text verschriften (transkribieren) und diesen als Eingabe für den {{site.data.keyword.personalityinsightsshort}}-Service verwenden wollen, müssen sich bewusst sein, dass die Ergebnisse je nach Leistungsfähigkeit der Engine sehr stark variieren können. {{site.data.keyword.IBM_notm}} rät Kunden und Business Partnern insbesondere, die Qualität der Transkription auf zwei Typen von Fehlern zu prüfen:

-   *Auslassung (Drop out):* Ein gesprochenes Wort wurde in der Transkription nicht erfasst (ausgelassen).
-   *Ersetzung (Substitution):* Ein gesprochenes Wort wurde falsch transkribiert.

Ersetzungen können ein ernsteres Problem darstellen, weil sie Wörter erzeugen können, die nicht gesprochen wurden, die jedoch Wörtern entsprechen, die zur Bestimmung der Persönlichkeit verwendet werden. Vor der Verwendung von transkribiertem (verschriftetem) Text sollten Sie den Text eines Testkorpus manuell korrigieren und die gefundenen Fehler zählen. Vergleichen Sie anschließend die Ergebnisse des automatisch generierten Texts mit der manuell korrigierten Version, um die Ergebnisvarianz durch Transkriptionsfehler zu ermitteln.

### Persönlichkeit aus übersetztem Text ableiten
{: #translation}

Sprachübersetzungsservices übersetzen Text, der in einer Sprache geschrieben ist, in eine andere Sprache. Ebenso wie bei der Verschriftung (Transkription) von Sprache stellt sich die Frage, ob übersetzter Text als Eingabe für den {{site.data.keyword.personalityinsightsshort}}-Service verwendet werden kann. {{site.data.keyword.IBM_notm}} empfiehlt nicht, Text, der aus Übersetzungsservices gewonnen wurde, als Eingabe für den {{site.data.keyword.personalityinsightsshort}}-Service zu verwenden. Abhängig vom Übersetzungsservice können die Ergebnisse sowohl der Übersetzung als auch der Persönlichkeitserschließung beträchtlich variieren. Wörter, ihre Bedeutungen und kulturelle Bezüge haben die Tendenz, in der Übersetzung verloren zu gehen, sodass die Ergebnisse ungültig sind.

{{site.data.keyword.IBM_notm}} empfiehlt, dass Sie als Eingabe nur Text verwenden, der in einer Sprache geschrieben ist, für die der {{site.data.keyword.personalityinsightsshort}}-Service eingerichtet ist. Sprachfähige Versionen des Service ... 

-   ... parsen den Eingabetext ist seiner Landessprache.
-   ... verwenden zum Identifizieren von Persönlichkeitsmerkmalen Wörterbücher in der Landessprache.
-   ... verwenden Modelle, die für die entsprechende Landessprache kalibriert sind, um statistische Ergebnisse liefern.

Wenn Sie den übersetzten Text analysieren müssen, empfiehlt {{site.data.keyword.IBM_notm}}, dass Sie zuerst Beispieltext manuell mit Hilfe eines Experten für menschliche Sprache übersetzen lassen. Anschließend können Sie die Ergebnisse vergleichen, die der {{site.data.keyword.personalityinsightsshort}}-Service aus dem manuell und dem automatisch übersetzten Text erhält, um die Varianz in den Ergebnissen zu ermitteln.

{{site.data.keyword.IBM_notm}} wird mit steigenden Geschäftsanforderungen weitere Sprachen hinzufügen. {{site.data.keyword.IBM_notm}} ist sich bewusst, dass der {{site.data.keyword.personalityinsightsshort}}-Service möglicherweise Ihre Landessprache für Ihre Zwecke nicht mit ausreichender Geschwindigkeit unterstützt. {{site.data.keyword.IBM_notm}} führt Tests durch, um Ergebnisse, die aus der Aktivierung der Landessprache gewonnen werden, mit Ergebnissen von Sprachübersetzungsservices zu vergleichen und wird über die Ergebnisse berichten, sobald sie verfügbar sind.

## Persönlichkeitsportraits für bestimmte Anwendungen verwenden
{: #applying}

Der {{site.data.keyword.personalityinsightsshort}}-Service kann auf unzählige Anwendungsfälle angewendet werden. In den folgenden Abschnitten wird die Nutzung von Persönlichkeitsportraits für einige bestimmte Zwecke beschrieben:

-   [Personen abgleichen](#matching)
-   [Mentale Gesundheit überwachen und vorhersagen](#mentalhealth)
-   [Radikale und bösartige Elemente über Social Media überwachen](#monitoring)

### Personen abgleichen
{: #matching}

Ein guter Abgleich zwischen Personen kann die Interaktion und die Ergebnisse von Beziehungen verbessern. Dieser Gedanke gilt auch für die Teambildung innerhalb eines Unternehmens und für die Interaktion mit Kunden aus ganz unterschiedlichen Branchen. In einer Studie zum Abgleich von Ärzten und Patienten haben Forscher herausgefunden, dass Patienten Ärzte bevorzugen, die ihnen ähnlich sind. Effektives Abgleichen von Ärzten und Patienten kann Vertrauen aufbauen und die Kommunikation fördern, was wiederum das Entgegenkommen verbessert und zu einer erfolgreicheren Behandlung führen kann ([Godager, 2012](/docs/services/personality-insights?topic=personality-insights-references#godager2012)).

Die Persönlichkeit beeinflusst außerdem die Interaktionspräferenzen zwischen Berufstätigen und Kunden. Zum Beispiel bevorzugen es Patienten mit einem hohen Grad an Gewissenhaftigkeit und Offenheit, an der Entscheidung des Behandlungsablaufs aktiv beteiligt zu werden. Patienten mit hohen Werten für Verträglichkeit oder Neurotizismus ziehen es vor, wenn Ärzte die Führung bei wichtigen gesundheitlichen Entscheidungen übernehmen ([Flynn und Smith, 2007](/docs/services/personality-insights?topic=personality-insights-references#flynn2007)).

### Mentale Gesundheit überwachen und vorhersagen
{: #mentalhealth}

{{site.data.keyword.IBM_notm}} ist überzeugt, dass medizinische Diagnosen am besten von ausgebildetem medizinischem Fachpersonal durchgeführt werden. Es kann jedoch möglich sein, einige Anzeichen für den mentalen Zustand einer Person aus dem Sprachgebrauch der Person zu erkennen. {{site.data.keyword.IBM_notm}} hat aber keine Ground Truth-Studien durchgeführt oder die Möglichkeit ausgelotet, eine wissenschaftliche Grundlage für eine solche Arbeit zu schaffen.

Kunden und Geschäftspartner, die daran interessiert sind, den {{site.data.keyword.personalityinsightsshort}}-Service zur Diagnose der psychischen Gesundheit zu nutzen, sind herzlich eingeladen, für solche Anwendungsfälle Ground Truth-Experimente zu konzipieren und durchzuführen. Aktive Forschung in diesem Bereich umfasst Arbeiten, die die Persönlichkeit mit den Gesundheitsergebnissen in Beziehung setzen ([Israel und andere, 2014](/docs/services/personality-insights?topic=personality-insights-references#israel2014)). Sie schließt auch Arbeiten ein, die darauf abzielen, postpartale Depressionen und andere Formen der Depression aus sozialen Medien vorherzusagen ([De Choudhury und andere, 2013a](/docs/services/personality-insights?topic=personality-insights-references#dechoudhury2013a), und [De Choudhury und andere, 2013b](/docs/services/personality-insights?topic=personality-insights-references#dechoudhury2013b)).

### Radikale und bösartige Elemente über Social Media überwachen
{: #monitoring}

Behörden in aller Welt suchen ständig nach Möglichkeiten, frühe Signale für die Radikalisierung von Einzelpersonen oder Gruppen über Social-Media-Kanäle zu erkennen. Die Ableitung der Persönlichkeit aus geschriebenen Texten von Personen ist eine traditionelle Anwendung des {{site.data.keyword.personalityinsightsshort}}-Service. Daher ist es keine Überraschung, dass die Verwendung des Service zur Erschließung radikaler und bösartiger Elemente über Social Media ein möglicher Anwendungsfall ist. Zuverlässige Schlüsse erfordern nicht nur Persönlichkeitsmerkmale, sondern auch eine ganze Reihe anderer Attribute wie Geschlecht, Alter und Geografie. {{site.data.keyword.IBM_notm}} verfügt über keine Studien, die diesen Anwendungsfall validieren oder ungültig machen. Kunden und Business Partner sind willkommen und eingeladen, Studien zur Erforschung dieses Anwendungsfalls auf der Basis ihrer jeweiligen Ziele und Anforderungen durchzuführen.

## Ändert sich die Persönlichkeit einer Person mit der Zeit?
{: #evolve}

Entwickelt sich die Persönlichkeit einer Person mit der Zeit? Falls dies so ist, wie oft sollte dann der {{site.data.keyword.personalityinsightsshort}}-Service verwendet werden, um die Persönlichkeit einer Person zu ermitteln? Verschiedene Studien belegen oder widerlegen die Theorie, dass sich die Persönlichkeit einer Person im Erwachsenenalter stabilisiert. In seiner bahnbrechenden Arbeit zur Messung der Stabilität der Persönlichkeit, die er 1890 unter dem Titel *The Principles of Psychology* veröffentlichte, merkte Harvard-Psychologe William James folgendes an: „Bei den meisten von uns hat sich bis zum 30. Lebensjahr der Charakter wie Gips gefestigt und wird nie wieder weich werden.“ Jüngere Studien geben jedoch an, dass sich die Persönlichkeit im Lauf der Zeit entwickelt:

-   [Helson und andere (2002)](/docs/services/personality-insights?topic=personality-insights-references#helson2002) berichten, dass „die Vorstellung, dass die Persönlichkeitsveränderung vor dem 30. Lebensjahr am stärksten ausgeprägt ist und dann stagniert, keine Unterstützung fand.“ Die Autoren haben eine Längsschnittstudie an zwei Kohorten über einen Zeitraum von 40 Jahren durchgeführt. Sie merken an, dass der Zeitraum des Lebens und das soziale Klima signifikante Faktoren für Persönlichkeitsveränderung im Erwachsenenalter sind. Sie kommentieren, dass „Bewertungen für Dominanz und Unabhängigkeit im mittleren Alter beider Kohorten Spitzenwerte erreichten und dass Bewertungen für Verantwortungsbewusstsein in den Spitzenjahren der Kultur des Individualismus am niedrigsten waren.“
-   [Scollon und Diener (2006)](/docs/services/personality-insights?topic=personality-insights-references#scollon2006) haben die individuellen Unterschiede der Veränderung in Bezug auf Extraversion, Neurotizismus sowie in Bezug auf Arbeits- und Beziehungszufriedenheit im Lauf der Zeit untersucht. Die Autoren merken an, dass die höhere Arbeits- und Beziehungszufriedenheit mit Abnahmen in Neurotizismus und Zunahmen in Extraversion im Lauf der Zeit verbunden waren.
-   [Roberts und Mroczek (2008)](/docs/services/personality-insights?topic=personality-insights-references#roberts2008) stellen fest, dass es Anzeichen für eine "Änderung mittleren Grades in Persönlichkeitseigenschaften sowie für individuelle Unterschiede in der Veränderung über die Lebensdauer" gibt. Die Autoren merken an, dass Menschen mit dem Alter höheres Selbstvertrauen, größere Warmherzigkeit und Selbstbeherrschung sowie höhere emotionale Stabilität zeigen. Diese Veränderungen überwiegen im jungen Erwachsenenalter (20 bis 40 Jahre). Darüber hinaus tritt eine Veränderung mittleren Grades in Persönlichkeitsmerkmalen im mittleren und hohen Alter auf. Dies zeigt, dass sich Persönlichkeitsmerkmale in jedem Alter verändern können.

Auf der Grundlage dieser Studien empfiehlt {{site.data.keyword.IBM_notm}}, dass Benutzer des {{site.data.keyword.personalityinsightsshort}}-Service immer mit den zuletzt verfügbaren Daten sowie mit möglichst vielen der verfügbaren Daten arbeiten. {{site.data.keyword.IBM_notm}} empfiehlt außerdem, dass Benutzer Persönlichkeitsportraits in regelmäßigen Intervallen aktualisieren, um die sich entwickelnden Persönlichkeiten von Personen zu erfassen. {{site.data.keyword.IBM_notm}} ist zwar der Ansicht, dass sich eine Persönlichkeit innerhalb bestimmter Grenzen entwickelt, hat jedoch keine Studien durchgeführt, um die obere und untere Grenze dieser Entwicklung zu erforschen.

Es könnte sich die Frage stellen, wie häufig die Persönlichkeitsportraits von Personen aktualisiert werden sollten. Die Empfehlung von {{site.data.keyword.IBM_notm}} lautet, nach der Verfügbarkeit von neuen Daten und neuem Text von einer Einzelperson Ausschau zu halten. Wenn eine Person eine nennenswerte Menge an neuem Text seit der Ermittlung des Persönlichkeitsportraits verfasst hat, kann es sich lohnen, das Portrait zu aktualisieren. Dieser Ansatz erfasst die Entwicklungsspezifik der Persönlichkeit, sofern man anerkennt, dass sich eine Persönlichkeit weiterentwickelt. Andererseits verleiht er dem {{site.data.keyword.personalityinsightsshort}}-Service auch den Vorteil, mit mehr Wörtern arbeiten zu können, was wiederum die Genauigkeit der Ergebnisse des Service steigern kann.
