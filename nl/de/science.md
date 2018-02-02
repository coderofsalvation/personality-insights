---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-12"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# Wissenschaftliche Grundlagen des Service
{: #science}

Eine breit akzeptierte Theorie in der Psychologie, im Marketing und anderen Feldern besagt, dass die natürliche Sprache Persönlichkeit, Denkweise, soziale Verbindungen und emotionale Zustände widerspiegelt. Die Häufigkeit, mit der wir bestimmte Kategorien von Wörtern verwenden, kann Aufschluss über diese Merkmale geben. Verschiedene Forscher haben herausgefunden, dass sich aus Varianten der Wörterverwendung in geschriebenen Texten wie Blogs, Essays und Tweets Aspekte der Persönlichkeit vorhersagen lassen ([Fast &amp; Funder, 2008](/docs/services/personality-insights/references.html#fast2008); [Gill et al., 2009](/docs/services/personality-insights/references.html#gill2009); [Golbeck et al., 2011](/docs/services/personality-insights/references.html#golbeck2011); [Hirsh &amp; Peterson, 2009](/docs/services/personality-insights/references.html#hirsh2009); und [Yarkoni, 2010](/docs/services/personality-insights/references.html#yarkoni2010)).
{: shortdesc}

{{site.data.keyword.IBM_notm}} hat eine Reihe von Studien durchgeführt, um zu untersuchen, ob sich aus den Persönlichkeitsmerkmalen, die aus Social Media-Daten abgeleitet werden, das Verhalten und die Präferenzen von Menschen vorhersagen lässt. {{site.data.keyword.IBM_notm}} hat herausgefunden, dass Menschen mit bestimmten Persönlichkeitsmerkmalen in höheren Anzahlen bei Informationssammel- und Informationsverteilaktivitäten antworteten und Tweets weitergaben. Zum Beispiel antworten Menschen mit hohen Bewertungen bei der Abenteuerlust mit höherer Wahrscheinlichkeit, während Menschen mit hohen Bewertungen in Vorsicht dies mit geringerer Wahrscheinlichkeit tun ([Mahmud et al., 2013](/docs/services/personality-insights/references.html#mahmud2013)). Ganz ähnlich sind Menschen mit hohen Bewertungen in Bescheidenheit, Offenheit und Freundlichkeit eher geneigt, Informationen weiterzugeben ([Lee et al., 2014](/docs/services/personality-insights/references.html#lee2014)).

{{site.data.keyword.IBM_notm}} hat außerdem festgestellt, dass Menschen mit hohen Bewertungen in Offenheit und niedrigen Bewertungen in emotionaler Bandbreite (Neurotizismus), wie sich dies aus ihrer Sprache in Social Media erschließen ließ, positiver reagierten (z. B. durch Klicken auf einen Werbelink oder durch Folgen eines Berichts). Diese Ergebnisse haben sich bei Ground-Truth-Prüfungen durch Befragungen bestätigt. Zum Beispiel führte die Ausrichtung auf die höchsten 10 Prozent bei hoher Offenheit und geringer emotionaler Bandbreite zu Erhöhungen der Klickrate von 6,8 Prozent auf 11,3 Prozent und der Folgerate von 4,7 Prozent auf 8,8 Prozent.

Mehrere kürzlich durchgeführte Studien ergaben ähnliche Ergebnisse für Merkmale, die aus Social Media-Daten berechnet worden waren. So hat eine kürzliche Studie mit Daten von Einzelhandelsgeschäften gezeigt, dass Menschen, die hohe Bewertungen in Ordnungsliebe, Selbstdisziplin und Vorsicht sowie niedrige Bewertungen in Impulsivität aufwiesen, mit 40 Prozent höherer Wahrscheinlichkeit als die Grundgesamtheit auf Coupons reagieren. Eine zweite Studie hat festgestellt, dass Menschen mit bestimmten Werten eine bestimmte Art von Lektüre bevorzugten ([Hsieh et al. 2014](/docs/services/personality-insights/references.html#hsieh2014)). Zum Beispiel zeigten Personen mit einem höheren Selbsttranszendenzwert Interesse an der Lektüre von Artikeln zu Umweltthemen und Personen mit einem höheren Selbstverbesserungswert Interesse an der Lektüre von Artikeln zu arbeitsbezogenen Themen. Eine dritte Studie mit mehr als 600 Twitter-Nutzern hat ergeben, dass sich anhand der Persönlichkeitsmerkmale einer Person deren Markenpräferenz mit einer Genauigkeit von 65 Prozent vorhersagen lässt.

In den folgenden Abschnitten wird auf diese allgemeinen Erkenntnisse näher eingegangen, um die Forschung und die Entwicklung, die dem {{site.data.keyword.personalityinsightsshort}}-Service zugrunde liegen, zu beschreiben. Weitere Informationen zu Studien, die den Service auf greifbare Szenarios anwenden, finden Sie unter [Service in Aktion](/docs/services/personality-insights/applied.html).

## Erläuterungen zu Persönlichkeitsmodellen
{: #researchModels}

Für den {{site.data.keyword.personalityinsightsshort}}-Service wurden von {{site.data.keyword.IBM_notm}} Modelle entwickelt, um Bewertungen für Big Five-Dimensionen und -Facetten, Bedürfnisse und Werte aus Textinformationen zu erschließen. Die Modelle, die vom Service angegeben werden, basieren auf Forschungen in den Feldern Psychologie, Psycholinguistik und Marketing:

-   [Big Five:](/docs/services/personality-insights/models.html) Ist die Bezeichnung für eines der am besten erforschten Persönlichkeitsmodelle, das von Psychologen entwickelt wurde ([Costa &amp; McCrae, 1992](/docs/services/personality-insights/references.html#costa1992) und [Norman, 1963](/docs/services/personality-insights/references.html#norman1963)). Es ist das Persönlichkeitsmodell, das am häufigsten zur Beschreibung verwendet wird, wie eine Person allgemein mit der Welt interagiert. Der Service berechnet die fünf Dimensionen und dreißig Facetten des Modells. Die Dimensionen werden häufig mit dem Merkbegriff *OCEAN* verbunden, wobei *O* für Offenheit (Openness), *C* für Gewissenhaftigkeit (Conscientiousness), *E* für Extraversion, *A* für Verträglichkeit (Agreeableness) und *N* für Neurotizismus stehen. (Da der Begriff Neurotizismus eine bestimmte klinische Bedeutung haben kann, gibt der Service die entsprechenden Erkenntnisse unter der etwas allgemeineren Bezeichnung der *emotionalen Bandbreite* zurück.)
-   [Bedürfnisse (Needs):](/docs/services/personality-insights/needs.html) Stellen einen wichtigen Aspekt des menschlichen Verhaltens dar. Die Forschungsliteratur legt nahe, dass verschiedene Typen menschlicher Bedürfnisse universell sind und das Verbraucherverhalten direkt beeinflussen ([Kotler &amp; Armstrong, 2013](/docs/services/personality-insights/references.html#kotler2013) und [Ford, 2005](/docs/services/personality-insights/references.html#ford2005)). Die zwölf Kategorien von Bedürfnissen, die von dem Service zurückgemeldet werden, werden in der Marketingliteratur als Begehren oder Verlangen (engl. desires) beschrieben, das eine Person befriedigen möchte, wenn er ein Produkt oder einen Service in Betracht zieht.
-   [Werte (Values):](/docs/services/personality-insights/values.html) Geben Aufschluss darüber, was einer Einzelperson am wichtigsten ist. Sie sind "erstrebenswerte, situationsübergreifende Ziele unterschiedlicher Wichtigkeit, die als leitende Prinzipien für das Leben von Menschen bestimmend sind" ([Schwartz, 2006](/docs/services/personality-insights/references.html#schwartz2006)). Schwartz fasst fünf Wesenszüge zusammen, die allen Werten gemein sind: (1) Werte sind Überzeugungen; (2) Werte sind ein Motivationskonstrukt; (3) Werte transzendieren bestimmte Aktionen und Situationen; (4) Werte leiten die Auswahl oder Bewertung von Aktionen, Handlungsmaßstäben, Menschen und Ereignissen; und (5) Werte variieren nach relativer Wichtigkeit und können einer entsprechenden Rangfolge zugeordnet werden. Der Service berechnet die fünf grundlegenden menschlichen Werte, die von Schwartz vorgeschlagen und in über zwanzig Ländern validiert wurden ([Schwartz, 1992](/docs/services/personality-insights/references.html#schwartz1992)).

## Ableitung von Persönlichkeitsmerkmalen
{: #researchInfer}

Der {{site.data.keyword.personalityinsightsshort}}-Service leitet Persönlichkeitsmerkmale aus Textinformationen auf Basis einer Methode mit offenem Vokabular ab. Diese Methode entspricht dem neuesten Trend der Forschung zum Thema Persönlichkeitserschließung  ([Arnoux et al., 2017](/docs/services/personality-insights/references.html#arnoux2017), [Schwartz et al., 2013](/docs/services/personality-insights/references.html#schwartz2013) und [Plank &amp; Hovy, 2015](/docs/services/personality-insights/references.html#plank2015)).

Der Service zerlegt den Eingabetext zunächst in logische Einheiten (so genannte Tokens), um eine Darstellung in einem *n*-dimensionalen Raum zu entwickeln. Der Service arbeitet mit einem quelloffenen Worteinbettungsverfahren mit dem Namen [GloVe ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://nlp.stanford.edu/projects/glove/){: new_window}, um eine Vektordarstellung für die Wörter im Eingabetext zu erzeugen ([Pennington et al., 2014](/docs/services/personality-insights/references.html#pennington2014)). Anschließend füttert er diese Darstellung in einen KI-Algorithmus, der ein Persönlichkeitsprofil mit Merkmalen für Big Five-Dimensionen, Bedürfnisse und Werte abzuleiten. Zum Trainieren des Algorithmus verwendet der Service Ergebnisse (Scores) von Umfragen, die unter Tausenden von Benutzern durchgeführt wurden, sowie Daten aus deren Twitter-Feeds.

{{site.data.keyword.IBM_notm}} hat die Modelle für alle unterstützten Sprachen in identischer Weise entwickelt. Die Modelle wurde unabhängig von demografischen Benutzerdaten wie Alter, Geschlecht oder Kultur entwickelt. In Zukunft wird {{site.data.keyword.IBM_notm}} möglicherweise spezielle Modelle für unterschiedliche demografische Kategorien entwickeln.

Frühere Versionen des Service verwendeten das psycholinguistische Wörterbuch von Linguistic Inquiry and Word Count (LIWC) mit seinem Modell für maschinelles Lernen (künstliche Intelligenz). Allerdings liefert die soeben beschriebene, auf einem offenen Vokabular basierende Methode eine bessere Leistung als das LIWC-basierte Modell. Weitere Informationen zur Genauigkeit des Service für die einzelnen Sprachen in Bezug auf den durchschnittlichen mittleren absoluten Fehler (Mean Absolute Error - MAE) und die Korrelation finden Sie unter [Genauigkeit des Service](#researchPrecise). Eine Anleitung zur Bereitstellung eines Eingabetexts, um die genauesten Ergebnisse zu erzielen, finden Sie unter [Ausreichende Eingabe bereitstellen](/docs/services/personality-insights/input.html#sufficient).

## Genauigkeit des Service
{: #researchPrecise}

{{site.data.keyword.IBM_notm}} hat eine Validierungsstudie durchgeführt, um die Genauigkeit des Verfahrens des Service zur Ableitung eines Persönlichkeitsprofils zu untersuchen. {{site.data.keyword.IBM_notm}} hat Umfrageantworten und Twitter-Feeds von 1500 bis 2000 Teilnehmern für alle Merkmale und Sprachen gesammelt. Zur Definition einer *Ground Truth* haben die Teilnehmer vier Gruppen von psychometrischen Standardtests absolviert:

-   50 Elemente zu Big Five-Merkmalen, abgeleitet aus dem International Personality Item Pool (IPIP)
-   120 Elemente zu Facetten, abgeleitet aus dem IPIP Neuroticism, Extraversion &amp; Openness (IPIP-NEO)
-   52 Elemente zu Grundbedürfnissen, entwickelt von {{site.data.keyword.IBM_notm}}
-   26 Elemente zu Grundwerten, entwickelt von Schwartz

{{site.data.keyword.IBM_notm}} hat anschließend die Bewertungen, die durch Modelle abgeleitet wurden, mit den umfragebasierten Bewertungen für die Twitter-Nutzer verglichen. Auf der Basis dieser Ergebnisse hat {{site.data.keyword.IBM_notm}} den [durchschnittlichen mittleren absoluten Fehler](#preciseMAE) und die [durchschnittliche Korrelation](#preciseCorrelation) zwischen den abgeleiteten Bewertungen und den tatsächlichen Bewertungen für die verschiedenen Kategorien der Persönlichkeitsmerkmale festgestellt. Im Abschnitt [Durchschnittlicher mittlerer absoluter Fehler und durchschnittliche Korrelation nach Sprache](#precisePerLanguage) finden Sie die statistischen Werte für jede unterstützte Sprache.

### Durchschnittlicher mittlerer absoluter Fehler
{: #preciseMAE}

Der *mittlere absolute Fehler (Mean Absolute Error - MAE)* ist eine Metrik, die zur Bemessung der Differenz zwischen tatsächlichen und vorhergesagten Werten verwendet wird. Für den {{site.data.keyword.personalityinsightsshort}}-Service ist der tatsächliche Wert (d. h. die Ground Truth) die Persönlichkeitsbewertung, die durch die Durchführung einer Umfrage zur Persönlichkeit ermittelt wurde. Der vorhergesagte Wert ist die Bewertung, die durch die Modelle des Service generiert wird.

Der MAE wurde von {{site.data.keyword.IBM_notm}} in der Weise berechnet, dass der Durchschnitt des absoluten Werte der Differenz zwischen der tatsächlichen und der vorhergesagten Bewertung genommen wurde. {{site.data.keyword.IBM_notm}} hat den absoluten Wert verwendet, weil eine Vorhersage eines höheren oder niedrigeren Werts als des tatsächlichen Werts irrelevant ist. Solange eine Differenz besteht, wird das Modell durch die Größenordnung des Fehlers beeinträchtigt. Je niedriger der MAE ist, desto besser ist die Leistung des Modells. {{site.data.keyword.IBM_notm}} verwendet eine Skala von 0 bis 1 für den MAE, wobei 0 keinen Fehler bedeutet (der vorhergesagte Wert ist exakt der gleiche wie der tatsächliche Wert) und 1 den maximalen Fehler bedeutet.

### Durchschnittliche Korrelation
{: #preciseCorrelation}

Die *durchschnittliche Korrelation* ist ein statistischer Begriff, der ein Maß für die gegenseitige Abhängigkeit zweier Variablen angibt. Mit dieser Metrik hat {{site.data.keyword.IBM_notm}} die Korrelation zwischen abgeleiteten und tatsächlichen Bewertungen für die verschiedenen Kategorien von Persönlichkeitsmerkmalen gemessen. Wenn die vorhergesagte Bewertung sich nahe an den tatsächlichen Ergebnissen bewegt, die der Korrelationswert hoch, andernfalls ist er niedrig.

{{site.data.keyword.IBM_notm}} misst die Korrelation auf einer Skala von -1 bis 1: Dabei gibt 1 eine perfekte direkte (zunehmende) lineare Beziehung und -1 eine perfekte inverse (abnehmende) lineare Beziehung an. In allen anderen Fällen liegt der Wert zwischen diesen Extremen. Wenn die Variablen unabhängig sind (d. h. wenn sie überhaupt keine Beziehung haben), ist der Korrelationswert 0.

{{site.data.keyword.IBM_notm}} sucht nach Werten möglichst nahe an 1, um beste Vorhersagen zu ermitteln. Allerdings sind Persönlichkeiten auf reiner Textbasis nur schwer vorherzusagen und es werden nur selten Korrelationswerte über 0,4 für diese Typen psychologischer Modelle beobachtet. In der Forschungsliteratur für dieses Gebiet werden Korrelationswerte über 0,2 als akzeptabel betrachtet.

### Durchschnittlicher mittlerer absoluter Fehler (MAE) und durchschnittliche Korrelation
{: #precisePerLanguage}

In der folgenden Tabelle werden die Ergebnisse für den durchschnittlichen mittleren absoluten Fehler (MAE) und die durchschnittliche Korrelation für den {{site.data.keyword.personalityinsightsshort}}-Service aufgeführt. Die Ergebnisse platzieren den Service an vorderster Front der Persönlichkeitserschließung aus Textdaten, wie durch [Schwartz et al. (2013)](/docs/services/personality-insights/references.html#schwartz2013) und [Plank and Hovy (2015)](/docs/services/personality-insights/references.html#plank2015) angegeben.

<table>
  <caption>Tabelle 1. Durchschnittlicher mittlerer absoluter Fehler (MAE) und durchschnittliche Korrelation nach Sprache</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      Sprache
    </th>
    <th style="text-align:center; vertical-align:bottom">
      Big Five-Dimensionen
    </th>
    <th style="text-align:center; vertical-align:bottom">
      Big Five-Facetten
    </th>
    <th style="text-align:center; vertical-align:bottom">
      Bedürfnisse
    </th>
    <th style="text-align:center; vertical-align:bottom">
      Werte
    </th>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Englisch**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Durchschnittlicher MAE
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Durchschnittliche Korrelation
    </td>
    <td style="text-align:center">
      0,33
    </td>
    <td style="text-align:center">
      0,28
    </td>
    <td style="text-align:center">
      0,22
    </td>
    <td style="text-align:center">
      0,24
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Spanisch**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Durchschnittlicher MAE
    </td>
    <td style="text-align:center">
      0,10
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Durchschnittliche Korrelation
    </td>
    <td style="text-align:center">
      0,35
    </td>
    <td style="text-align:center">
      0,21
    </td>
    <td style="text-align:center">
      0,24
    </td>
    <td style="text-align:center">
      0,19
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Japanisch**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Durchschnittlicher MAE
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Durchschnittliche Korrelation
    </td>
    <td style="text-align:center">
      0,27
    </td>
    <td style="text-align:center">
      0,22
    </td>
    <td style="text-align:center">
      0,25
    </td>
    <td style="text-align:center">
      0,19
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Arabisch**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Durchschnittlicher MAE
    </td>
    <td style="text-align:center">
      0,09
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,10
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Durchschnittliche Korrelation
    </td>
    <td style="text-align:center">
      0,17
    </td>
    <td style="text-align:center">
      0,14
    </td>
    <td style="text-align:center">
      0,13
    </td>
    <td style="text-align:center">
      0,14
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Koreanisch**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Durchschnittlicher MAE
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Durchschnittliche Korrelation
    </td>
    <td style="text-align:center">
      0,21
    </td>
    <td style="text-align:center">
      0,21
    </td>
    <td style="text-align:center">
      0,13
    </td>
    <td style="text-align:center">
      0,12
    </td>
  </tr>
</table>

Zur Berechnung der Perzentilbewertungen hat {{site.data.keyword.IBM_notm}} einen sehr umfangreichen Datenbestand an Twitter-Nutzern (1 Million für Englisch, 200.000 für Koreanisch, 100.000 für Arabisch und Japanisch sowie 80.000 für Spanisch) erfasst und die Persönlichkeitsportraits der Nutzer berechnet. Anschließend hat {{site.data.keyword.IBM_notm}} die unaufbereiteten ('raw') Bewertungen jedes berechneten Profils mit der Verteilung von Profilen aus diesen Datensätzen verglichen, um die Perzentile zu bestimmen.

> **Anmerkung:** Für arabische und koreanische Eingaben ist der Service nicht in der Lage, aussagefähige Perzentile und unaufbereitete Bewertungen für einige Persönlichkeitsmerkmale zu generieren. Weitere Informationen finden Sie unter [Einschränkungen für arabische und koreanische Eingaben](/docs/services/personality-insights/numeric.html#limitations).

## Verbraucherpräferenzen verstehen
{: #researchPrefs}

Die Beziehung zwischen Persönlichkeit und Einkaufsverhalten wurde für eine Auswahl an Produkten und Services durch Studien untersucht:

-   [Chen (2007)](/docs/services/personality-insights/references.html#chen2007) hat beim Testen der Präferenzen in Bezug auf Bio-Nahrungsmittel gezeigt, dass die Persönlichkeitsmerkmale einer Person eine wichtige Rolle bei der Herausbildung persönlicher Kriterien zur Nahrungsmittelwahl spielen.
-   [Schlegelmilch et al. (1996)](/docs/services/personality-insights/references.html#schlegelmilch1996) haben die Beziehung zwischen Persönlichkeitsvariablen und umweltbewusstem Einkaufsverhalten untersucht. Die Autoren haben gezeigt, dass das allgemeine Umweltbewusstsein von Verbrauchern eine positive Auswirkung auf umweltschonende Kaufentscheidungen hat.
-   [Hymbaugh und Garrett (2007)](/docs/services/personality-insights/references.html#hymbaugh1974) haben die Beziehung zwischen Persönlichkeit und Fallschirmspringen untersucht und herausgefunden, dass Menschen mit hoher Bewertung in Abenteuerlust und Erlebnishunger allgemein das Fallschirmspringen betreiben. (Weitere Informationen finden Sie unter [Risikoprofile](/docs/services/personality-insights/applied.html#otherRisk).)

Die Anwendung dieser bekannten Beziehungen zwischen Verbraucherverhaltensweisen und Persönlichkeit ist eine Herausforderung: Die meisten dieser Arbeiten haben Persönlichkeitsdaten verwendet, die aus Umfragen abgeleitet wurden, und ihre Modelle sind nicht öffentlich verfügbar. {{site.data.keyword.IBM_notm}} hat sich daher entschlossen, diese Modelle für Verbraucherpräferenzen direkt zu erlernen. Beim Trainieren der Modelle hat {{site.data.keyword.IBM_notm}} Persönlichkeitsbewertungen, die aus dem {{site.data.keyword.personalityinsightsshort}}-Service zurückgegeben wurden, als Merkmale verwendet. Wenn Sie also diese Modelle anwenden, um die Persönlichkeitsmerkmale eines Benutzers mit dem Service zu berechnen, sind die Vorhersagen wahrscheinlich genauer.

## Ableitung von Verbraucherpräferenzen
{: #researchInferPrefs}

Der {{site.data.keyword.personalityinsightsshort}}-Service leitet Verbraucherpräferenzen auf Basis der Ergebnisse seines Persönlichkeitsprofils für den Autor des Eingabetexts ab. Anhand der vorhandenen Literatur hat {{site.data.keyword.IBM_notm}} 104 Verbraucherpräferenzen ermittelt, für eine Korrelation mit Persönlichkeit nachgewiesen wurde. Dazu gehören Präferenzen in Bezug auf Einkauf, Filme, Musik und andere Kategorien. {{site.data.keyword.IBM_notm}} hat anschließend eine psychometrische Befragung erstellt, um die Neigung einer Person zu jedem einzelnen Verbraucherverhalten zu bewerten.

{{site.data.keyword.IBM_notm}} hat Antworten auf die Befragung von ca. 600 Personen erhalten, für die auch Twitter-Daten (mehr als 200 selbstverfasste Tweets für jeden Nutzer) verfügbar waren. {{site.data.keyword.IBM_notm}} hat die Tweets an den Service übergeben, um ein Persönlichkeitsprofil für jede Person zu erfassen. Anschließend wurde eine Klassifikation für jede Verbraucherpräferenz erstellt, deren Eingabemerkmal die Persönlichkeitsinformationen waren.

Für den Einschluss in den Service hat {{site.data.keyword.IBM_notm}} nur die Verbraucherpräferenzen ausgewählt, für die die persönlichkeitsbasierte Klassifikation mindestens um neun Prozent besser war als eine zufällige Klassifikation. Von den ursprünglich 104 Präferenzen haben 42 dieses Kriterium erfüllt und werden von dem Service als Verbraucherpräferenzen berücksichtigt.

<!--
COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016

## How media influence inferred characteristics

{{site.data.keyword.IBM_notm}} conducted a validation study to understand the effect of media on inferred characteristics. To determine the accuracy of the service's approach to estimating characteristics, {{site.data.keyword.IBM_notm}} compared scores that were derived by its models with survey-based scores for Twitter users (for instance, approximately 500 users for English and more than 600 for Spanish).

To establish ground truth, participants took three sets of standard psychometric tests: 50-item Big Five (derived from the International Personality Item Pool, or IPIP), 52-item fundamental Needs (developed by {{site.data.keyword.IBM_notm}}), and 26-item basic Values (developed by Schwartz). {{site.data.keyword.IBM_notm}} conducted the study in two phases:

-   For the first study, conducted in 2013, {{site.data.keyword.IBM_notm}} recruited 256 Twitter users ([Gou et al., 2014](/docs/services/personality-insights/references.html#gou2014)). Although the models were learned from different sources, {{site.data.keyword.IBM_notm}} found that for more than 80 percent of the Twitter users, scores for characteristics that were inferred for all three models correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80). Specifically, scores that were derived by the service correlated with survey-based scores as follows:
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

Bei der Entwicklung des {{site.data.keyword.personalityinsightsshort}}-Service hat {{site.data.keyword.IBM_notm}} auf Umfragen zur Persönlichkeit zurückgegriffen, um Ground-Truth-Daten für die Persönlichkeitsableitung zu ermitteln. Ground Truth bezeichnet die faktischen Daten, die durch direkte Beobachtung und nicht durch Schlussfolgerung gewonnen werden. Eine typische Bewertung der Genauigkeit jedes Modells für maschinelles Lernen besteht darin, die von dem Modell erschlossenen Werte mit Ground-Truth-Daten zu vergleichen. In den vorherigen Abschnitten wird beschrieben, wie {{site.data.keyword.IBM_notm}} Umfragen zur Überprüfung der Genauigkeit des Service verwendet hat.

Die folgenden Hinweise erläutern die Verwendung von Umfragen zur Persönlichkeit und die umfragebasierte Einschätzung der Persönlichkeit:

-   Umfragen zur Persönlichkeit sind lang und zeitaufwendig. Die Ergebnisse werden daher durch die Anzahl der Twitter-Nutzer eingeschränkt, die zur Teilnahme an der Studie von {{site.data.keyword.IBM_notm}} bereit und verfügbar sind. {{site.data.keyword.IBM_notm}} plant die Durchführung von Validierungsstudien mit mehr Nutzern sowie mit Nutzern anderer Online-Medien wie E-Mail, Blogs und Foren.
-   Die umfragebasierte Einschätzung der Persönlichkeit beruht auf Eigenberichten, die möglicherweise nicht immer eine getreue Wiedergabe der eigenen Persönlichkeit darstellen: Einige Nutzer können in solchen Umfragen möglicherweise unscharfe Antworten geben. Zur Verringerung der Unschärfen hat {{site.data.keyword.IBM_notm}} Umfrageantworten gefiltert, indem Fragen zur Überprüfung der Aufmerksamkeit eingefügt wurden und Umfragen verworfen wurden, die zu schnell ausgefüllt wurden.
-   Obwohl die Korrelation zwischen abgeleiteten und umfragebasierten Bewertungen positiv und signifikant ist, implizieren die Ergebnisse, dass abgeleitete Bewertungen möglicherweise nicht immer mit umfragebasierten Ergebnissen korrelieren. Forscher außerhalb von {{site.data.keyword.IBM_notm}} haben ebenfalls Experimente durchgeführt, um zu vergleichen, wie gut abgeleitete Bewertungen mit den aus Umfragen gewonnenen Bewertungen übereinstimmten, und keine Bewertung ergab eine vollständig konsistente Übereinstimmung:
    -   [Golbeck et al. (2011)](/docs/services/personality-insights/references.html#golbeck2011) berichten von einer Fehlerrate von 10 bis 18 Prozent beim Vergleich von abgeleiteten Bewertungen mit umfragebasierten Bewertungen.
    -   [Sumner et al. (2012)](/docs/services/personality-insights/references.html#sumner2012) berichten von einer ungefähr 65-prozentigen Genauigkeit für die Persönlichkeitsvorhersage.
    -   [Mairesse und Walker (2006)](/docs/services/personality-insights/references.html#mairesse2006) haben eine 60- bis 70-prozentige Genauigkeit für die Vorhersage von Big Five-Persönlichkeitsmerkmalen festgestellt.

In der Forschungsliteratur besteht im Allgemeinen Einigkeit darüber, dass Bewertungen von Eigenangaben aus Umfragen zur Persönlichkeit nicht immer vollständig mit Bewertungen übereinstimmen, die aus Text abgeleitet werden. Wichtiger ist jedoch, dass {{site.data.keyword.IBM_notm}} festgestellt hat, dass die Merkmale, die aus Text abgeleitet werden, zuverlässige Vorhersagen zu einer Reihe von realen Verhaltensweisen erlauben.
