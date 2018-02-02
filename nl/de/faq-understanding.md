---

copyright:
  years: 2015, 2017
lastupdated: "2017-09-13"

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

# Profil interpretieren
{: #output}

1.  <span style="color:#003F69">Wie werden die Ergebnisse interpretiert, die vom Service zurückgegeben werden?</span>

    -   In [Numerische Ergebnisse interpretieren](/docs/services/personality-insights/numeric.html) wird beschrieben, wie die Perzentile zu interpretieren sind, die von dem Service zurückgegeben werden. Weiterhin enthält der Abschnitt Informationen zu den Verhaltensprozentsätzen sowie zu den optionalen unaufbereiteten Bewertungen und Verbraucherpräferenzen, die der Service zurückgeben kann.

1.  <span style="color:#003F69">Warum ergibt das Hinzufügen der Bewertungen für die Facetten einer Dimension nicht die Bewertung für diese Dimension?</span>

    -   In [Perzentile für Persönlichkeitsmerkmale](/docs/services/personality-insights/numeric.html#percentiles) wird diese Frage beantwortet. Kurz gesagt, berechnet der Service die normalisierten Perzentile für jede Dimension und Facette unabhängig. Es besteht keine mathematische Beziehung zwischen einer Dimension und ihren Facetten.

1.  <span style="color:#003F69">Wann ist die unaufbereitete Bewertung anstelle der Perzentilbewertung zu verwenden?</span>

    -   In [Unaufbereitete Bewertungen für Persönlichkeitsmerkmale](/docs/services/personality-insights/numeric.html#rawScores) wird diese Wahl näher erläutert. Kurz gesagt, können Sie eine unaufbereitete Bewertung verwenden, wenn Sie eine angepasste Normalisierung für ein bestimmtes Szenario entwickeln möchten oder wenn kein Vergleich mit einer Beispielpopulation erforderlich ist. Wenn Sie wissen müssen, wie sich die Ergebnisse eines Autors im Vergleich zu einer Beispielpopulation verhalten, verwenden Sie Perzentilbewertungen.

1.  <span style="color:#003F69">Wie lässt sich eine unaufbereitete Bewertung in eine Perzentilbewertung normalisieren?</span>

    -   Der Abschnitt [Unaufbereitete Bewertungen für Persönlichkeitsmerkmale](/docs/services/personality-insights/numeric.html#rawScores) enthält allgemeine Hinweise zur Normalisierung einer unaufbereiteten Bewertung und erläutert den Ansatz für die Normalisierung von {{site.data.keyword.IBM_notm}}.

1.  <span style="color:#003F69">Wie wird die {{site.data.keyword.personalityinsightsshort}}-Visualisierung interpretiert?</span>

    -   In [Numerische Ergebnisse interpretieren](/docs/services/personality-insights/numeric.html) wird beschrieben, wie die numerischen Ergebnisse zu interpretieren sind, die in der Visualisierung dargestellt werden.
