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

# Wissenschaftliche Grundlagen des Service
{: #science}

Eine breit akzeptierte Theorie in der Psychologie, im Marketing und anderen Feldern besagt, dass die natürliche Sprache Persönlichkeit, Denkweise, soziale Verbindungen und emotionale Zustände widerspiegelt. Die Häufigkeit, mit der Menschen bestimmte Kategorien von Wörtern verwenden, kann Aufschluss über diese Merkmale geben. Verschiedene Forscher haben herausgefunden, dass sich aus Unterschieden in der Wortverwendung bei geschriebenen Texten wie Blogs, Essays und Tweets Aspekte der Persönlichkeit vorhersagen lassen ([Fast und Funder, 2008](/docs/services/personality-insights?topic=personality-insights-references#fast2008), [Gill und andere, 2009](/docs/services/personality-insights?topic=personality-insights-references#gill2009), [Golbeck und andere, 2011](/docs/services/personality-insights?topic=personality-insights-references#golbeck2011), [Hirsh und Peterson, 2009](/docs/services/personality-insights?topic=personality-insights-references#hirsh2009), und [Yarkoni, 2010](/docs/services/personality-insights?topic=personality-insights-references#yarkoni2010)).
{: shortdesc}

{{site.data.keyword.IBM_notm}} hat eine Gruppe von Studien durchgeführt, um zu untersuchen, ob sich anhand der Persönlichkeitsmerkmale, die aus Social-Media-Daten abgeleitet werden, Vorhersagen zum Verhalten von Menschen und zu ihren Präferenzen machen lassen. {{site.data.keyword.IBM_notm}} fand heraus, dass Menschen mit bestimmten Persönlichkeitsmerkmalen in höherer Zahl bei Aktivitäten der Informationserfassung und -streuung reagierten und Retweets absetzten. Menschen, die hohe Werte für die Facette 'Abenteuerlust' aufweisen, reagieren zum Beispiel mit höherer Wahrscheinlichkeit als Menschen mit hohen Werten bei 'Vorsicht' ([Mahmud und andere, 2013](/docs/services/personality-insights?topic=personality-insights-references#mahmud2013)). Ebenso geben Menschen, die hohe Werte für 'Bescheidenheit', 'Offenheit' und 'Freundlichkeit' aufweisen, mit höherer Wahrscheinlichkeit Informationen weiter ([Lee und andere, 2014](/docs/services/personality-insights?topic=personality-insights-references#lee2014)).

Des weiteren stellte {{site.data.keyword.IBM_notm}} fest, dass Menschen mit hohen Bewertungen bei Offenheit und niedrigen Bewertungen bei emotionaler Bandbreite (Neurotizismus), wie aus ihrem Sprachgebrauch in Social Media abgeleitet, positiver reagierten, z. B. durch Klicken auf einen Werbelink oder durch Folgen eines Kontos. Diese Ergebnisse werden durch eine umfragebasierte Ground-Truth-Prüfung untermauert. Bei der Ausrichtung auf die 10 Prozent der Nutzer mit der höchsten Bewertung für Offenheit und den niedrigsten Werten für das emotionale Spektrum erhöhte sich zum Beispiel die Klickrate von 6,8 auf 11,3 Prozent und der Prozentsatz der Follower stieg von 4,7 auf 8,8 Prozent.


Mehrere kürzlich durchgeführte Studien ergaben ähnliche Ergebnisse für Merkmale, die aus Social Media-Daten berechnet worden waren. Eine vor kurzem durchgeführte Studie mit Daten von Einzelhandelsgeschäften ergab, dass Menschen, die bei Ordnungsliebe, Selbstdisziplin und Besonnenheit hoch punkten, bei Impulsivität jedoch niedrige Werte aufweisen, mit einer 40 Prozent höheren Wahrscheinlichkeit auf Coupons reagieren als die randomisierte Bevölkerung. Eine zweite Studie belegte, dass Menschen mit bestimmten Werten eine bestimmte Art von Lektüre bevorzugten ([Hsieh und andere, 2014](/docs/services/personality-insights?topic=personality-insights-references#hsieh2014)). Zum Beispiel zeigten Personen mit einem höheren Selbsttranszendenzwert Interesse an der Lektüre von Artikeln zu Umweltthemen und Personen mit einem höheren Selbstverbesserungswert Interesse an der Lektüre von Artikeln zu arbeitsbezogenen Themen. Eine dritte Studie mit mehr als 600 Twitter-Nutzern hat ergeben, dass sich anhand der Persönlichkeitsmerkmale einer Person deren Markenpräferenz mit einer Genauigkeit von 65 Prozent vorhersagen lässt.

In den folgenden Abschnitten wird auf diese allgemeinen Erkenntnisse näher eingegangen, um die Forschung und die Entwicklung, die dem {{site.data.keyword.personalityinsightsshort}}-Service zugrunde liegen, zu beschreiben. Weitere Informationen zu Studien, die den Service auf greifbare Szenarios anwenden, finden Sie unter [Service in Aktion](/docs/services/personality-insights?topic=personality-insights-applied).

## Erläuterungen zu Persönlichkeitsmodellen
{: #researchModels}

Für den {{site.data.keyword.personalityinsightsshort}}-Service wurden von {{site.data.keyword.IBM_notm}} Modelle entwickelt, um Bewertungen für Big Five-Dimensionen und -Facetten, Bedürfnisse und Werte aus Textinformationen zu erschließen. Die Modelle, die vom Service angegeben werden, basieren auf Forschungen in den Feldern Psychologie, Psycholinguistik und Marketing:

-   [Big Five:](/docs/services/personality-insights?topic=personality-insights-models) Bezeichnung für eines der am besten erforschten Persönlichkeitsmodelle, das von Psychologen entwickelt wurde ([Costa unnd McCrae, 1992](/docs/services/personality-insights?topic=personality-insights-references#costa1992), und [Norman, 1963](/docs/services/personality-insights?topic=personality-insights-references#norman1963)). Es ist das Persönlichkeitsmodell, das am häufigsten zur Beschreibung verwendet wird, wie eine Person allgemein mit der Welt interagiert. Der Service berechnet die fünf Dimensionen und dreißig Facetten des Modells. Die Dimensionen werden häufig mit dem Merkbegriff *OCEAN* verbunden, wobei *O* für Offenheit (Openness), *C* für Gewissenhaftigkeit (Conscientiousness), *E* für Extraversion, *A* für Verträglichkeit (Agreeableness) und *N* für Neurotizismus stehen. (Da der Begriff Neurotizismus eine bestimmte klinische Bedeutung haben kann, gibt der Service die entsprechenden Erkenntnisse unter der etwas allgemeineren Bezeichnung der *emotionalen Bandbreite* zurück.)
-   [Bedürfnisse (Needs):](/docs/services/personality-insights?topic=personality-insights-needs) Stellen einen wichtigen Aspekt des menschlichen Verhaltens dar. Die Forschungsliteratur legt nahe, dass mehrere Typen menschlicher Bedürfnisse universell sind und unmittelbaren Einfluss auf das Verbraucherverhalten ausüben ([Kotler und Armstrong, 2013](/docs/services/personality-insights?topic=personality-insights-references#kotler2013), und [Ford, 2005](/docs/services/personality-insights?topic=personality-insights-references#ford2005)). Die zwölf Kategorien von Bedürfnissen, die der Service dokumentiert, werden in der Marketingliteratur als Begehren oder Verlangen (engl. desires) beschrieben, das eine Person zu befriedigen hofft, wenn sie ein Produkt oder einen Service in Betracht zieht.
-   [Werte (Values):](/docs/services/personality-insights?topic=personality-insights-values) Geben Aufschluss darüber, was einer Einzelperson am wichtigsten ist. Sie sind "erstrebenswerte, situationsübergreifende Ziele unterschiedlicher Wichtigkeit, die als leitende Prinzipien für das Leben von Menschen bestimmend sind" ([Schwartz, 2006](/docs/services/personality-insights?topic=personality-insights-references#schwartz2006)). Schwartz Schwartz fasst fünf Merkmale zusammen, die allen Werten gemein sind:

    1.  Werte sind Überzeugungen.
    1.  Werte sind ein motivierendes Konstrukt.
    1.  Werte überschreiten die Grenzen bestimmter Handlungen und Situationen.
    1.  Werte leiten die Auswahl oder Bewertung von Aktionen, Richtlinien, Personen und Ereignissen.
    1.  Werte variieren nach relativer Bedeutung und können nach Stellenwert angeordnet werden.

    Der Service berechnet die fünf grundlegenden menschlichen Werte, die von Schwartz vorgeschlagen und in über zwanzig Ländern validiert wurden ([Schwartz, 1992](/docs/services/personality-insights?topic=personality-insights-references#schwartz1992)).

## Ableitung von Persönlichkeitsmerkmalen
{: #researchInfer}

Der {{site.data.keyword.personalityinsightsshort}}-Service leitet Persönlichkeitsmerkmale aus Textinformationen auf Basis einer Methode mit offenem Vokabular ab. Diese Methode spiegelt den neuesten Trend bei der Forschung zum Thema der Persönlichkeitserschließung wider ([Arnoux und andere, 2017](/docs/services/personality-insights?topic=personality-insights-references#arnoux2017), [Schwartz und andere, 2013](/docs/services/personality-insights?topic=personality-insights-references#schwartz2013), und [Plank und Hovy, 2015](/docs/services/personality-insights?topic=personality-insights-references#plank2015)).

Der Service zerlegt den Eingabetext zunächst in logische Einheiten (so genannte Tokens), um eine Darstellung in einem *n*-dimensionalen Raum zu entwickeln. Der Service verwendet [GloVe ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://nlp.stanford.edu/projects/glove/){: new_window}, ein quelloffenes Worteinbettungsverfahren, um eine Vektordarstellung für die Wörter im Eingabetext zu erhalten ([Pennington und andere, 2014](/docs/services/personality-insights?topic=personality-insights-references#pennington2014)). Anschließend speist er diese Darstellung in einen KI-Algorithmus ein, der ein Persönlichkeitsprofil mit Merkmalen für Big Five-Dimensionen, Bedürfnissen und Werten ableitet. Zum Trainieren des Algorithmus verwendet der Service Bewertungen (Scores) von Umfragen, die unter Tausenden von Benutzern durchgeführt wurden, sowie Daten aus deren Twitter-Feeds.

{{site.data.keyword.IBM_notm}} hat die Modelle für alle unterstützten Sprachen in identischer Weise entwickelt. Die Modelle wurde unabhängig von demografischen Benutzerdaten wie Alter, Geschlecht oder Kultur entwickelt. In Zukunft wird {{site.data.keyword.IBM_notm}} möglicherweise spezielle Modelle für unterschiedliche demografische Kategorien entwickeln.

Frühere Versionen des Service verwendeten das psycholinguistische Wörterbuch von Linguistic Inquiry and Word Count (LIWC) mit seinem Modell für maschinelles Lernen (künstliche Intelligenz). Allerdings liefert die auf einem offenen Vokabular basierende Methode eine bessere Leistung als das LIWC-basierte Modell. Weitere Informationen zur Genauigkeit des Service für die einzelnen Sprachen in Bezug auf den durchschnittlichen mittleren absoluten Fehler (Mean Absolute Error - MAE) und die Korrelation finden Sie unter [Genauigkeit des Service](#researchPrecise). Eine Anleitung zur Bereitstellung eines Eingabetexts, um die genauesten Ergebnisse zu erzielen, finden Sie unter [Ausreichende Eingabe bereitstellen](/docs/services/personality-insights?topic=personality-insights-input#sufficient).

## Genauigkeit des Service
{: #researchPrecise}

{{site.data.keyword.IBM_notm}} hat eine Validierungsstudie durchgeführt, um die Genauigkeit des Verfahrens des Service zur Ableitung eines Persönlichkeitsprofils zu untersuchen. {{site.data.keyword.IBM_notm}} hat Umfrageantworten und Twitter-Feeds von 1500 bis 2000 Teilnehmern für alle Merkmale und Sprachen gesammelt. Zur Definition einer *Ground Truth* haben die Teilnehmer vier Gruppen von psychometrischen Standardtests absolviert:

-   Ein aus dem International Personality Item Pool (IPIP) abgeleiteter Big Five-Test mit 50 Items
-   Ein Facettentest mit 120 Items, abgeleitet aus dem IPIP-NEO 'Neurotizismus, Extraversion und Offenheit'
-   Ein von {{site.data.keyword.IBM_notm}} entwickelter Test Grundbedürfnissen mit 52 Items
-   Ein von Schwartz entwickelter Test zu Grundwerten mit 26 Items

{{site.data.keyword.IBM_notm}} hat anschließend die Bewertungen, die durch Modelle abgeleitet wurden, mit den umfragebasierten Bewertungen für die Twitter-Nutzer verglichen. Auf der Basis dieser Ergebnisse hat {{site.data.keyword.IBM_notm}} den [durchschnittlichen mittleren absoluten Fehler](#preciseMAE) und die [durchschnittliche Korrelation](#preciseCorrelation) zwischen den abgeleiteten Bewertungen und den tatsächlichen Bewertungen für die verschiedenen Kategorien der Persönlichkeitsmerkmale festgestellt. Der Abschnitt [Durchschnittlicher mittlerer absoluter Fehler (MAE) und durchschnittliche Korrelation](#precisePerLanguage) enthält die statistischen Werte für jede unterstützte Sprache.

### Durchschnittlicher mittlerer absoluter Fehler
{: #preciseMAE}

Der *mittlere absolute Fehler (Mean Absolute Error - MAE)* ist eine Metrik, die zur Bemessung der Differenz zwischen tatsächlichen und vorhergesagten Werten verwendet wird. Für den {{site.data.keyword.personalityinsightsshort}}-Service ist der tatsächliche Wert (d. h. die Ground Truth) die Persönlichkeitsbewertung, die durch die Durchführung einer Umfrage zur Persönlichkeit ermittelt wurde. Der vorhergesagte Wert ist die Bewertung, die durch die Modelle des Service generiert wird.

Der MAE wurde von {{site.data.keyword.IBM_notm}} in der Weise berechnet, dass der Durchschnitt des absoluten Werte der Differenz zwischen der tatsächlichen und der vorhergesagten Bewertung genommen wurde. {{site.data.keyword.IBM_notm}} hat den absoluten Wert verwendet, da eine Vorhersage eines höheren oder eines niedrigeren Werts als des Ist-Werts irrelevant ist. Solange eine Differenz besteht, wird das Modell durch die Größenordnung des Fehlers beeinträchtigt. Je niedriger der MAE ist, desto besser ist die Leistung des Modells. {{site.data.keyword.IBM_notm}} verwendet eine Skala von 0 bis 1 für den MAE, wobei 0 keinen Fehler bedeutet (der vorhergesagte Wert ist exakt der gleiche wie der tatsächliche Wert) und 1 den maximalen Fehler bedeutet.

### Durchschnittliche Korrelation
{: #preciseCorrelation}

Die *durchschnittliche Korrelation* ist ein statistischer Begriff, der ein Maß für die gegenseitige Abhängigkeit zweier Variablen angibt. Mit dieser Metrik hat {{site.data.keyword.IBM_notm}} die Korrelation zwischen abgeleiteten und tatsächlichen Bewertungen für die verschiedenen Kategorien von Persönlichkeitsmerkmalen gemessen. Wenn die vorhergesagte Bewertung sich nahe an den tatsächlichen Ergebnissen bewegt, die der Korrelationswert hoch, andernfalls ist er niedrig.

{{site.data.keyword.IBM_notm}} misst die Korrelation auf einer Skala von -1 bis 1:

-   1 gibt eine perfekte direkte (zunehmende) lineare Beziehung an.
-   -1 zeigt eine perfekte inverse (abnehmende) lineare Beziehung an.

In allen anderen Fällen liegt der Wert zwischen diesen Extremen. Wenn die Variablen unabhängig sind (d. h. wenn sie überhaupt keine Beziehung haben), ist der Korrelationswert 0.

{{site.data.keyword.IBM_notm}} sucht nach Werten möglichst nahe an 1, um beste Vorhersagen zu ermitteln. Persönlichkeiten sind jedoch, wenn als Grundlage ausschließlich Text verwendet wird, nur schwer vorherzusagen und nur selten kommen bei diesen Typen psychologischer Modelle Korrelationswerte vor, die über 0,4 liegen. In der Forschungsliteratur für dieses Gebiet gelten Korrelationswerte größer als 0,2 als akzeptabel.

### Durchschnittlicher mittlerer absoluter Fehler (MAE) und durchschnittliche Korrelation
{: #precisePerLanguage}

In der folgenden Tabelle werden die Ergebnisse für den durchschnittlichen mittleren absoluten Fehler (MAE) und die durchschnittliche Korrelation für den {{site.data.keyword.personalityinsightsshort}}-Service aufgeführt. Die Ergebnisse stellen den Service an die Spitze der Persönlichkeitserschließung aus Textdaten, wie durch [Schwartz und andere (2013)](/docs/services/personality-insights?topic=personality-insights-references#schwartz2013) und [Plank und Hovy (2015)](/docs/services/personality-insights?topic=personality-insights-references#plank2015) angegeben.

<table summary="Für jede Zeile, die eine Sprache in der ersten Spalte angibt, wird in den folgenden zwei Zeilen der durchschnittliche MAE und die durchschnittliche Korrelation für die Big Five-Dimensionen, die Big Five-Facetten, die Bedürfnisse und die Werte genannt.">
  <caption>Tabelle 1. Durchschnittlicher mittlerer absoluter Fehler (MAE) und durchschnittliche Korrelation nach Sprache</caption>
  <tr>
    <th id="language" style="text-align:left; vertical-align:bottom">
      Sprache
    </th>
    <th id="dimensions" style="text-align:center; vertical-align:bottom">
      Big Five-Dimensionen
    </th>
    <th id="facets" style="text-align:center; vertical-align:bottom">
      Big Five-Facetten
    </th>
    <th id="needs" style="text-align:center; vertical-align:bottom">
      Bedürfnisse
    </th>
    <th id="values" style="text-align:center; vertical-align:bottom">
      Werte
    </th>
  </tr>
  <tr>
    <th id="arabic" headers="language" colspan="5" style="text-align:left">
      **Arabisch**
    </th>
  </tr>
  <tr>
    <td headers="language arabic" style="text-align:left">
      Durchschnittlicher MAE
    </td>
    <td headers="dimensions arabic" style="text-align:center">
      0,09
    </td>
    <td headers="facets arabic" style="text-align:center">
      0,12
    </td>
    <td headers="needs arabic" style="text-align:center">
      0,11
    </td>
    <td headers="values arabic" style="text-align:center">
      0,10
    </td>
  </tr>
  <tr>
    <td headers="language arabic" style="text-align:left">
      Durchschnittliche Korrelation
    </td>
    <td headers="dimensions arabic" style="text-align:center">
      0,17
    </td>
    <td headers="facets arabic" style="text-align:center">
      0,14
    </td>
    <td headers="needs arabic" style="text-align:center">
      0,13
    </td>
    <td headers="values arabic" style="text-align:center">
      0,14
    </td>
  </tr>
  <tr>
    <th id="english" headers="language" colspan="5" style="text-align:left">
      **Englisch**
    </th>
  </tr>
  <tr>
    <td headers="language english" style="text-align:left">
      Durchschnittlicher MAE
    </td>
    <td headers="dimensions english" style="text-align:center">
      0,12
    </td>
    <td headers="facets english" style="text-align:center">
      0,12
    </td>
    <td headers="needs english" style="text-align:center">
      0,11
    </td>
    <td headers="values english" style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td headers="language english" style="text-align:left">
      Durchschnittliche Korrelation
    </td>
    <td headers="dimensions english" style="text-align:center">
      0,33
    </td>
    <td headers="facets english" style="text-align:center">
      0,28
    </td>
    <td headers="needs english" style="text-align:center">
      0,22
    </td>
    <td headers="values english" style="text-align:center">
      0,24
    </td>
  </tr>
  <tr>
    <th id="japanese" headers="language" colspan="5" style="text-align:left">
      **Japanisch**
    </th>
  </tr>
  <tr>
    <td headers="language japanese" style="text-align:left">
      Durchschnittlicher MAE
    </td>
    <td headers="dimensions japanese" style="text-align:center">
      0,11
    </td>
    <td headers="facets japanese" style="text-align:center">
      0,12
    </td>
    <td headers="needs japanese" style="text-align:center">
      0,11
    </td>
    <td headers="values japanese" style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td headers="language japanese" style="text-align:left">
      Durchschnittliche Korrelation
    </td>
    <td headers="dimensions japanese" style="text-align:center">
      0,27
    </td>
    <td headers="facets japanese" style="text-align:center">
      0,22
    </td>
    <td headers="needs japanese" style="text-align:center">
      0,25
    </td>
    <td headers="values japanese" style="text-align:center">
      0,19
    </td>
  </tr>
  <tr>
    <th id="korean" headers="language" colspan="5" style="text-align:left">
      **Koreanisch**
    </th>
  </tr>
  <tr>
    <td headers="language korean" style="text-align:left">
      Durchschnittlicher MAE
    </td>
    <td headers="dimensions korean" style="text-align:center">
      0,11
    </td>
    <td headers="facets korean" style="text-align:center">
      0,12
    </td>
    <td headers="needs korean" style="text-align:center">
      0,11
    </td>
    <td headers="values korean" style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td headers="language korean" style="text-align:left">
      Durchschnittliche Korrelation
    </td>
    <td headers="dimensions korean" style="text-align:center">
      0,21
    </td>
    <td headers="facets korean" style="text-align:center">
      0,21
    </td>
    <td headers="needs korean" style="text-align:center">
      0,13
    </td>
    <td headers="values korean" style="text-align:center">
      0,12
    </td>
  </tr>
  <tr>
    <th id="spanish" headers="language" colspan="5" style="text-align:left">
      **Spanisch**
    </th>
  </tr>
  <tr>
    <td headers="language spanish" style="text-align:left">
      Durchschnittlicher MAE
    </td>
    <td headers="dimensions spanish" style="text-align:center">
      0,10
    </td>
    <td headers="facets spanish" style="text-align:center">
      0,12
    </td>
    <td headers="needs spanish" style="text-align:center">
      0,12
    </td>
    <td headers="values spanish" style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td headers="language spanish" style="text-align:left">
      Durchschnittliche Korrelation
    </td>
    <td headers="dimensions spanish" style="text-align:center">
      0,35
    </td>
    <td headers="facets spanish" style="text-align:center">
      0,21
    </td>
    <td headers="needs spanish" style="text-align:center">
      0,24
    </td>
    <td headers="values spanish" style="text-align:center">
      0,19
    </td>
  </tr>
</table>

Zur Berechnung der Perzentilwerte hat {{site.data.keyword.IBM_notm}} einen sehr großen Datenbestand an Twitter-Nutzern erfasst und die Persönlichkeitsporträts dieser Nutzer berechnet:

-   Eine Million Benutzer für Englisch
-   Zweihunderttausend Benutzer für Koreanisch
-   Einhunderttausend Benutzer jeweils für Arabisch und für Japanisch
-   Achtzigtausend Benutzer für Spanisch

Anschließend hat {{site.data.keyword.IBM_notm}} die unaufbereiteten ('raw') Bewertungen eines jeden berechneten Profils mit der Verteilung von Profilen aus den Datensätzen verglichen, um die Perzentile zu bestimmen.

Für die Eingabe in arabischer und koreanischer Sprache ist der Service für manche Persönlichkeitsmerkmale nicht in der Lage, aussagekräftige Perzentile und unaufbereitete Bewertungen zu liefern. Weitere Informationen finden Sie unter [Einschränkungen für arabische und koreanische Eingaben](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).
{: note}

## Verbraucherpräferenzen verstehen
{: #researchPrefs}

Die Beziehung zwischen Persönlichkeit und Einkaufsverhalten wurde für diverse Produkte und Services in untersucht:

-   [Chen (2007)](/docs/services/personality-insights?topic=personality-insights-references#chen2007) hat beim Testen von Präferenzen in Bezug auf Bio-Nahrungsmittel aufgezeigt, dass die Persönlichkeitsmerkmale einer Person eine wichtige Rolle bei der Herausbildung persönlicher Kriterien zur Auswahl von Nahrungsmitteln spielen.
-   [Schlegelmilch und andere (1996)](/docs/services/personality-insights?topic=personality-insights-references#schlegelmilch1996) haben die Beziehung zwischen Persönlichkeitsvariablen und umweltbewusstem Einkaufsverhalten untersucht. Die Autoren haben gezeigt, dass das allgemeine Umweltbewusstsein von Verbrauchern eine positive Auswirkung auf umweltschonende Kaufentscheidungen hat.
-   [Hymbaugh und Garrett (2007)](/docs/services/personality-insights?topic=personality-insights-references#hymbaugh1974) haben die Beziehung zwischen Persönlichkeit und Fallschirmspringen untersucht und herausgefunden, dass Menschen mit hoher Bewertung in Abenteuerlust und Erlebnishunger allgemein das Fallschirmspringen betreiben. (Weitere Informationen finden Sie unter [Risikoprofile](/docs/services/personality-insights?topic=personality-insights-applied#otherRisk).)

Die Anwendung dieser bekannten Beziehungen zwischen Verbraucherverhaltensweisen und Persönlichkeit ist eine Herausforderung. Bei den meisten dieser Arbeiten wurden Persönlichkeitsdaten verwendet, die aus Umfragen abgeleitet wurden, und ihre Modelle sind nicht öffentlich verfügbar. Daher hat sich {{site.data.keyword.IBM_notm}} entschlossen, diese Modelle für Verbraucherpräferenzen direkt zu erlernen. Beim Trainieren der Modelle hat {{site.data.keyword.IBM_notm}} Persönlichkeitsbewertungen, die vom {{site.data.keyword.personalityinsightsshort}}-Service zurückgegeben wurden, als Merkmale verwendet. Wenn Sie also diese Modelle anwenden, um die Persönlichkeitsmerkmale eines Benutzers mit dem Service zu berechnen, sind die Vorhersagen wahrscheinlich genauer.

## Ableitung von Verbraucherpräferenzen
{: #researchInferPrefs}

Der {{site.data.keyword.personalityinsightsshort}}-Service leitet Verbraucherpräferenzen auf Basis der Ergebnisse seines Persönlichkeitsprofils für den Autor des Eingabetexts ab. Anhand der vorhandenen Literatur hat {{site.data.keyword.IBM_notm}} 104 Verbraucherpräferenzen ermittelt, für eine Korrelation mit Persönlichkeit nachgewiesen wurde. Dazu gehören Präferenzen im Zusammenhang mit 'Kaufverhalten', 'Filme', 'Musik' sowie anderen Kategorien. {{site.data.keyword.IBM_notm}} hat anschließend eine psychometrische Befragung erstellt, um die Neigung einer Person zu jedem einzelnen Verbraucherverhalten zu bewerten.

{{site.data.keyword.IBM_notm}} hat Antworten auf die Befragung von ca. 600 Personen erhalten, für die auch Twitter-Daten (mehr als 200 selbstverfasste Tweets für jeden Nutzer) verfügbar waren. {{site.data.keyword.IBM_notm}} hat die Tweets an den Service übergeben, um ein Persönlichkeitsprofil für jede Person zu erfassen. Anschließend wurde eine Klassifikation für jede Verbraucherpräferenz erstellt, deren Eingabemerkmal die Persönlichkeitsinformationen waren.

Für den Einschluss in den Service hat {{site.data.keyword.IBM_notm}} nur die Verbraucherpräferenzen ausgewählt, für die die persönlichkeitsbasierte Klassifikation mindestens um neun Prozent besser war als eine zufällige Klassifikation. Von den ursprünglich 104 Präferenzen haben 42 dieses Kriterium erfüllt und werden von dem Service als Verbraucherpräferenzen berücksichtigt.

<!--
COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016

## How media influence inferred characteristics

{{site.data.keyword.IBM_notm}} conducted a validation study to understand the effect of media on inferred characteristics. To determine the accuracy of the service's approach to estimating characteristics, {{site.data.keyword.IBM_notm}} compared scores that were derived by its models with survey-based scores for Twitter users (for instance, approximately 500 users for English and more than 600 for Spanish).

To establish ground truth, participants took three sets of standard psychometric tests: 50-item Big Five (derived from the International Personality Item Pool, or IPIP), 52-item fundamental Needs (developed by {{site.data.keyword.IBM_notm}}), and 26-item basic Values (developed by Schwartz). {{site.data.keyword.IBM_notm}} conducted the study in two phases:

-   For the first study, conducted in 2013, {{site.data.keyword.IBM_notm}} recruited 256 Twitter users ([Gou and others, 2014](/docs/services/personality-insights?topic=personality-insights-references#gou2014)). Although the models were learned from different sources, {{site.data.keyword.IBM_notm}} found that for more than 80 percent of the Twitter users, scores for characteristics that were inferred for all three models correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80). Specifically, scores that were derived by the service correlated with survey-based scores as follows:
    -   For 80.8 percent of participants' Big Five scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.75)
    -   For 86.6 percent of participants' Needs scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80)
    -   For 98.21 percent of participants' Values scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.55)
-   For the second study, conducted in 2015, {{site.data.keyword.IBM_notm}} recruited another set of 237 Twitter users. The study found that for Big Five and Values, scores for inferred characteristics correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.07 and 0.21) for every Twitter user. For needs, such significant correlation was observed for 90 percent of the users (p value &lt; 0.05 and correlation coefficient between 0.01 and 0.20).

In both studies, participants also rated on a five-point scale how well each derived characteristic matched their perceptions of themselves. Their ratings suggest that the inferred characteristics largely matched their self-perceptions. Specifically, means of all ratings were above 3 ("somewhat") out of 5 ("perfect").

-   For the 256 Twitter users of the first study, means were 3.4 (with a standard deviation of 1.14) for Big Five, 3.39 (with a standard deviation of 1.34) for Needs, and 3.13 (with a standard deviation of 1.17) for Values.
-   For the 237 Twitter users of the second study, means were 3.31 (with a standard deviation of 1.18) for Big Five, 3.37 (with a standard deviation of 1.22) for Needs, and 3.36 (with a standard deviation of 1.18) for Values.

COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016
-->

## Hinweise zu Persönlichkeitsumfragen
{: #researchSurveys}

Bei der Entwicklung des {{site.data.keyword.personalityinsightsshort}}-Service hat {{site.data.keyword.IBM_notm}} auf Umfragen zur Persönlichkeit zurückgegriffen, um Ground-Truth-Daten für die Persönlichkeitserschließung zu bestimmen. Ground Truth bezeichnet die faktischen Daten, die durch direkte Beobachtung und nicht durch Schlussfolgerung gewonnen werden. Eine typische Maßnahme zur Beurteilung der Genauigkeit bei jedem beliebigen Modell für maschinelles Lernen besteht darin, die von dem Modell erschlossenen Werte mit Ground-Truth-Daten zu vergleichen. In den vorherigen Abschnitten wird beschrieben, wie {{site.data.keyword.IBM_notm}} Umfragen zur Validierung der Genauigkeit des Service verwendet hat.

Die folgenden Hinweise erläutern die Verwendung von Umfragen zur Persönlichkeit und die umfragebasierte Einschätzung der Persönlichkeit:

-   Umfragen zur Persönlichkeit sind lang und zeitaufwendig. Die Umfrageergebnisse sind durch die Anzahl der Twitter-Nutzer begrenzt, die zur Teilnahme an der Studie von {{site.data.keyword.IBM_notm}} bereit und verfügbar waren. {{site.data.keyword.IBM_notm}} plant die Durchführung von Validierungsstudien mit mehr Nutzern sowie mit Nutzern anderer Online-Medien wie E-Mail, Blogs und Foren.
-   Die umfragebasierte Einschätzung der Persönlichkeit beruht auf Eigenberichten, die möglicherweise nicht immer eine getreue Wiedergabe der eigenen Persönlichkeit darstellen: Einige Nutzer können in solchen Umfragen möglicherweise unscharfe Antworten geben. Zur Verringerung der Unschärfen hat {{site.data.keyword.IBM_notm}} Umfrageantworten gefiltert, indem Fragen zur Überprüfung der Aufmerksamkeit eingefügt wurden und Umfragen verworfen wurden, die zu schnell ausgefüllt wurden.
-   Obwohl die Korrelation zwischen abgeleiteten und umfragebasierten Bewertungen positiv und signifikant ist, implizieren die Ergebnisse, dass abgeleitete Bewertungen möglicherweise nicht immer mit umfragebasierten Ergebnissen korrelieren. Forscher außerhalb von {{site.data.keyword.IBM_notm}} haben ebenfalls Experimente durchgeführt, um zu vergleichen, wie gut erschlossene Bewertungen mit den aus Umfragen gewonnenen Bewertungen übereinstimmten, und keiner konnte eine vollständig konsistente Übereinstimmung melden:
    -   [Golbeck und andere (2011)](/docs/services/personality-insights?topic=personality-insights-references#golbeck2011) berichteten von einer Fehlerrate von 10 bis 18 Prozent für den Abgleich von erschlossenen Bewertungen mit umfragebasierten Bewertungen.
    -   [Sumner und andere (2012)](/docs/services/personality-insights?topic=personality-insights-references#sumner2012) berichteten von einer ungefähr 65-prozentigen Genauigkeit für die Persönlichkeitsvorhersage.
    -   [Mairesse und Walker (2006)](/docs/services/personality-insights?topic=personality-insights-references#mairesse2006) haben eine 60- bis 70-prozentige Genauigkeit für die Vorhersage von Big Five-Persönlichkeitsmerkmalen festgestellt.

In der Forschungsliteratur besteht im Allgemeinen Einigkeit darüber, dass Bewertungen von Eigenangaben aus Umfragen zur Persönlichkeit nicht immer vollständig mit Bewertungen übereinstimmen, die aus Text abgeleitet werden. Wichtiger ist jedoch, dass {{site.data.keyword.IBM_notm}} herausgefunden hat, dass die Merkmale, die aus Text erschlossen werden, oft zuverlässige Vorhersagen zu einer Reihe von realen Verhaltensweisen erlauben.
