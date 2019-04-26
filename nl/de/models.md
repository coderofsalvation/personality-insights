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

# Persönlichkeitsmodelle
{: #models}

Der {{site.data.keyword.personalityinsightsshort}}-Service basiert auf der Psychologie der Sprache in Kombination mit Datenanalysealgorithmen. Der Service analysiert den Inhalt, den Sie senden, und gibt ein Persönlichkeitsprofil für den Autor der Eingabe zurück. Der Service leitet Persönlichkeitsmerkmale auf der Basis von drei Modellen ab:
{: shortdesc}

-   Die *Big Five* der Persönlichkeitsmerkmale stellen das am häufigsten verwendete Modell zur allgemeinen Beschreibung der Interaktion einer Person mit ihrer Umgebung dar. Das Modell umfasst fünf primäre Dimensionen:
    -   [*Verträglichkeit*](/docs/services/personality-insights?topic=personality-insights-agreeableness) ist die Tendenz einer Person, Mitgefühl und Kooperationsbereitschaft gegenüber anderen zu zeigen.
    -   [*Gewissenhaftigkeit*](/docs/services/personality-insights?topic=personality-insights-conscientiousness) ist die Tendenz einer Person, organisiert und umsichtig zu agieren.
    -   [*Extraversion*](/docs/services/personality-insights?topic=personality-insights-extraversion) (Extrovertiertheit) ist die Tendenz einer Person zur Geselligkeit.
    -   [*Emotionales Spektrum*](/docs/services/personality-insights?topic=personality-insights-emotionalRange), auch als *Neurotizismus* oder *natürliche Reaktionen* bezeichnet, gibt an, wie sensibel eine Person auf ihre Umgebung reagiert.
    -   [*Offenheit*](/docs/services/personality-insights?topic=personality-insights-openness) gibt an, wie offen eine Person gegenüber unterschiedlichen Aktivitäten ist.

    Jede dieser übergeordneten Dimensionen weist 6 Facetten auf, die eine Person der Dimension entsprechend genauer charakterisieren.
-   [Bedürfnisse](/docs/services/personality-insights?topic=personality-insights-needs) beschreiben, auf welche Aspekte eines Produkts eine Person anspricht. Das Modell umfasst zwölf charakteristische Bedürfnisse.
-   [Werte](/docs/services/personality-insights?topic=personality-insights-values) beschreiben die Motivationsfaktoren, die die Entscheidungsfindung einer Person beeinflussen. Das Modell umfasst fünf Werte.

Weitere Informationen dazu, wie die Modelle entwickelt wurden und wie sie von dem Service verwendet werden, finden Sie unter [Wissenschaftliche Grundlagen des Service](/docs/services/personality-insights?topic=personality-insights-science).

## Beschreibungen der Big Five-Persönlichkeitsmerkmale
{: #bigFive}

Jede Big Five-Dimension wird durch drei Tabellen beschrieben:

-   In der Tabelle *Facetten* werden die Facetten der Dimension vorgestellt und Personen beschrieben, die für jede Facette eine hohe Bewertung erhalten.
-   Die Tabelle *Bereich der Merkmale* enthält allgemeine Beschreibungen, die für Personen gelten können, deren Werte mehr oder weniger jede Facette der Dimension belegen, sowie Begriffe, die diese Personen beschreiben könnten. Eine benutzerfreundliche einseitige Tabelle, in der die Tabellen *Bereich der Merkmale* für die Facetten aller fünf Dimensionen zusammengefasst werden, finden Sie im Dokument <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Facet-Characteristics.pdf" download="Personality-Insights-Facet-Characteristics.pdf">Personality-Insights-Facet-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="Symbol für externen Link" title="Symbol für externen Link"></a>.
-   Die Tabelle *Primäre und sekundäre Dimensionen* enthält Informationen, die die Dimension mit anderen Dimensionen in Beziehung setzen und dabei Kombinationen von Persönlichkeitsmerkmalen beschreiben. Die Tabelle liefert interessante Einblicke in die gegenseitigen Beziehungen von primären und sekundären Merkmalen zur Darstellung der Persönlichkeitszusammensetzung einer Person. Eine benutzerfreundliche einseitige Tabelle, in der die Tabellen *Primäre und sekundäre Dimensionen* für alle fünf Dimensionen zusammengefasst werden, finden Sie im Dokument <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Dimension-Characteristics.pdf" download="Personality-Insights-Dimension-Characteristics.pdf">Personality-Insights-Dimension-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="Symbol für externen Link" title="Symbol für externen Link"></a>.
