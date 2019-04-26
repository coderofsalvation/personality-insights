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

# Numerische Ergebnisse interpretieren
{: #numeric}

Der {{site.data.keyword.personalityinsightsshort}}-Service gibt numerische Ergebnisse für jedes der Persönlichkeits- und Verhaltensmerkmale und für jede Nutzungspräferenz zurück. Die Werte unterscheiden sich in den Informationen, die sie bereitstellen.
{: shortdesc}

Für die Eingabe in arabischer und koreanischer Sprache ist der Service für eine Reihe von Persönlichkeitsmerkmalen nicht in der Lage, aussagekräftige Perzentile und unaufbereitete Bewertungen zu liefern. Weitere Informationen finden Sie unter [Einschränkungen für arabische und koreanische Eingaben](#limitations).
{: note}

## Perzentile für Persönlichkeitsmerkmale
{: #percentiles}

Für jede Anforderung gibt der Service immer ein normalisiertes Bewertungsergebnis als `Perzentil` für die Persönlichkeitsmerkmale im Hinblick auf Big Five-Aspekte, Werte und Bedürfnisse zurück. Normalisierte Bewertungen stellen eine Perzentilrangordnung für jedes Merkmal auf der Basis von Eigenschaften dar, die der Service aus dem Eingabetext ableitet. Der Service berechnet normalisierte Bewertungen, indem er die unaufbereiteten Bewertung für den Text des Autors mit Ergebnissen aus der Beispielpopulation vergleicht. Der Service gibt jedes Perzentil als Double-Wert im Bereich von 0 bis 1 zurück.

Der Perzentilwert `0.64980796071382` für das Persönlichkeitsmerkmal `big5_extraversion` gibt zum Beispiel an, dass die Bewertung des Autors für dieses Merkmal im 65. Perzentil liegt. Der Autor des Texts zeigt die Tendenz in einem Ausmaß, das größer als 64 Prozent und weniger als 34 Prozent der Beispielpopulation ist. Die Genauigkeit des Perzentils hängt von der Anzahl der Wörter ab, die als Eingabe mit der Anforderung übermittelt wurden. Weitere Informationen finden Sie unter [Ausreichende Eingabe bereitstellen](/docs/services/personality-insights?topic=personality-insights-input#sufficient).

Es besteht keine mathematische Beziehung zwischen den Perzentilen, die für Big Five-Dimensionen und -Facetten zurückgegeben werden. Der Service berechnet das normalisierte Perzentil für jede Dimension und Facette unabhängig auf der Basis von Korrelationen zwischen den Bewertungen von Umfrageteilnehmern für diese Dimension bzw. Facette und den Wörtern, die diese Teilnehmer verwenden. Das bedeutet, dass zwar einerseits Facetten differenziertere Beschreibungen von Dimensionen liefern, jedoch das Hinzufügen der Bewertungen für die sechs Facetten einer Dimension nicht unbedingt den Perzentilwert für diese Dimension liefert. Das Gleiche gilt für unaufbereitete Bewertungen.
{: note}

## Unaufbereitete Bewertungen für Persönlichkeitsmerkmale
{: #rawScores-numeric}

Wenn Sie für den Abfrageparameter `raw_scores` der Anforderung den Wert `true` angeben, gibt der Service eine unaufbereitete Bewertung im Feld `raw_score` für jedes Persönlichkeitsmerkmal zurück. Unaufbereitete Bewertungen Rohwerte stellen die Bewertung für ein Merkmal dar, die ausschließlich auf dem Text des Autors und dem Modell für dieses Merkmal basiert. Bei der Generierung von unaufbereiteten Werten vergleicht der Service die Ergebnisse nicht mit einer Beispielpopulation. Unaufbereitete Bewertungen können als die Bewertungen interpretiert werden, die der Autor erhielte, wenn er sich einem Persönlichkeitstest unterzöge.

Der Service gibt jede unaufbereitete Bewertung als Double-Wert im Bereich von 0 bis 1 zurück. Eine höhere Bewertung weist im Allgemeinen auf eine höhere Wahrscheinlichkeit hist, dass der Autor dieses Merkmal aufweist. Unaufbereitete Bewertungen müssen jedoch im Zusammenhang betrachtet werden: Der Wertebereich kann in der Praxis wesentlich kleiner als von 0 bis 1 sein, sodass eine einzelne Bewertung im Kontext der gesamten Bewertungen und ihres Bereichs betrachtet werden muss. Allgemein gilt jedoch, dass eine unaufbereitete Bewertung, zum Beispiel der Wert `0.56817738781166` für das Persönlichkeitsmerkmal `big5_extraversion` angibt, dass der Autor wahrscheinlich diese Bewertung in einem Persönlichkeitstest erreicht hätte. Vergleichen Sie diese unaufbereitete Bewertung mit dem normalisierten Perzentil, das für denselben Autor und dasselbe Merkmal im vorherigen Abschnitt zurückgegeben wird.

Der Service macht unaufbereitete Bewertungen für Benutzer verfügbar, die eine angepasste Normalisierung für ein bestimmtes Szenario anwenden wollen oder die keinen Vergleich mit einer Beispielpopulation benötigen. Benutzer, die wissen möchten, wie die Merkmale des Autors im Vergleich mit einer großen Beispielpopulation aussehen, können die normalisierten Bewertungen verwenden. Benutzer, die eigene normalisierte Perzentilbewertungen aus den Rohdaten ableiten möchten, können die unaufbereiteten Bewertungen mit einer anderen Beispielpopulation vergleichen und eine andere Normalisierungsmethode anwenden.

Zur Normalisierung einer unaufbereiteten Bewertung für ein bestimmtes Merkmal vergleichen Sie die unaufbereitete Bewertung mit einer Beispielpopulation, für die die mittlere Abweichung und die Standardabweichung für das Merkmal bekannt sind. {{site.data.keyword.IBM_notm}} hat zum Beispiel Studien zur Erfassung von Daten aus sehr großen Beispielpopulationen von Twitter-Nutzern durchgeführt. {{site.data.keyword.IBM_notm}} hat die Bewertungen der Nutzer für jedes Persönlichkeitsmerkmal berechnet und anschließend die mittlere und die Standardabweichung für jedes Merkmal ermittelt. Zur Berechnung der Perzentilbewertung für eine unaufbereitete Bewertung, die der Service aus seiner Analyse von Eingabetext ableitet, verwendet der Service die mittlere und die Standardabweichung, der er aus der Twitter-Beispielpopulation für dieses Merkmal abgeleitet hat.

## Prozentsätze für Verhaltensmerkmale
{: #percentages}

Wenn Sie JSON-Daten übergeben, deren Inhaltselemente Zeitmarken haben, gibt der Service einen Prozentsatz (`percentage`) für jedes Verhaltensmerkmal zurück. Verhaltensmerkmale geben die zeitliche Verteilung der Eingabe an. Der Prozentsatz gibt an, wie viele der Inhaltselemente an jedem Wochentag und zu jeder Tageszeit aufgetreten sind. Beispiel: Der Prozentsatz `0.4561049445005` für das Verhaltensmerkmal `behavior_0000` bedeutet, dass annähernd 46 Prozent der Inhaltselemente in der Zeit zwischen Mitternacht und 01:00 Uhr morgens erstellt wurden.

## Bewertungen für Verbraucherpräferenzen
{: #scores}

Wenn Sie für den Abfrageparameter `consumption_preferences` der Anforderung den Wert `true` angeben, gibt der Service Verbraucherpräferenzen zurück, die eine Bewertung (`score`) für jede Präferenz enthalten. Der Service leitet die Bewertung aus den Persönlichkeitsmerkmalen ab, die aus dem Eingabetext erschlossen werden. Die Bewertung ist ein Double-Wert, der die Wahrscheinlichkeit angibt, mit der der Autor des Texts das Element bevorzugt. Der Wert ist ein Indikator für Präferenz und kein normalisierter Prozentsatz.

Bei manchen Präferenzen erfolgt die Bewertung anhand eines der folgenden drei Werte:

-   `0.0`: Es ist sehr unwahrscheinlich, dass der Autor das Element bevorzugt. Für manche Präferenzen können Sie den Wert so interpretieren, dass der Autor nur wenig Interesse hat.
-   `0.5`: Der Autor steht dem Element neutral gegenüber. Für manche Präferenzen kann der Wert bedeuten, dass der Autor einen mittleren Grad an Interesse zeigt.
-   `1.0`: Es ist sehr wahrscheinlich, dass der Autor das Element bevorzugt. Für manche Präferenzen gibt der Wert starkes Interesse an.

Für andere Präferenzen stellt die Bewertung einen Binärwert dar. Es ist unwahrscheinlich (`0.0`) oder wahrscheinlich (`1.0`), dass der Autor des Eingabetexts ein Interesse an dem Element hat, oder der Autor hat einen niedrigen bzw. hohen Grad an Interesse. In einigen Fällen kann die Bewertung eine einfache Antwort Ja oder Nein darstellen (z. B. ob der Autor wahrscheinlich Erfahrung als Ehrenamtler im Sozialbereich hat).

Eine vollständige Liste aller Präferenzen nach Kategorie und Bereich ihrer Ergebnisse finden Sie unter [Verbraucherpräferenzen](/docs/services/personality-insights?topic=personality-insights-preferences).

## Einschränkungen für arabische und koreanische Eingaben
{: #limitations}

Für arabische und koreanische Eingaben können die Modelle des Service keine aussagefähigen Ergebnisse für einen Teil der Persönlichkeitsmerkmale generieren. Für die folgenden Merkmale sind die normalisierten Perzentilbewertungen immer `0.5` und die unaufbereiteten Bewertungen sind immer der Mittelwert der ursprünglichen Verteilung. Das Feld `significant` für jedes dieser Merkmale hat immer den Wert `false`. Verlassen Sie sich *nicht* auf die Ergebnisse für diese Merkmale als Teil des Persönlichkeitsprofils des Autors.

<table>
  <caption>Tabelle 1. Merkmale, deren Ergebnisse nicht signifikant sind</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      Merkmale
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      Arabische Ergebnisse, die<br/>nicht aussagekräftig sind
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      Koreanische Ergebnisse, die<br/>nicht aussagekräftig sind
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Big Five-Dimensionen
    </td>
    <td style="text-align:left; vertical-align:top">
      Emotionales Spektrum
    </td>
    <td style="text-align:left; vertical-align:top">
      Keins
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Big Five-Facetten
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; line-height:110%; padding:0px">
          *Verträglichkeit*: Altruismus, Kooperation, Bescheidenheit und Vertrauen
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Gewissenhaftigkeit*: Leistungsstreben und Pflichtbewusstsein
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Extraversion*: Heiterkeit und Freundlichkeit (Aufgeschlossen)
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Emotionales Spektrum*: Reizbarkeit (Temperamentvoll), Häufig besorgt, Impulsivität,
          und Unsicherheit
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Offenheit*: Abenteuerlust, Offenheit für Handlungen und Offenheit für Ideen
        </li>
      </ul>
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; padding:0px">
          *Extraversion*: Abenteuerlustig
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Bedürfnisse
    </td>
    <td style="text-align:left; vertical-align:top">
      Idealismus, Freiheit, Liebe, Sachlichkeit und Struktur
    </td>
    <td style="text-align:left; vertical-align:top">
      Freiheit und Stabilität
    </td>
  </tr>
  </tr>
    <td style="text-align:left; vertical-align:top">
      Werte
    </td>
    <td style="text-align:left; vertical-align:top">
      Selbstverbesserung
    </td>
    <td style="text-align:left; vertical-align:top">
      Konservatismus
    </td>
  </tr>
</table>
