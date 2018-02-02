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

# Produktinformation
{: #about}

> **Serviceaktualisierung:** *Der {{site.data.keyword.personalityinsightsshort}}-Service wurde am 13. Oktober 2017 aktualisiert. Jedes Objekt `Trait` eines Persönlichkeitsprofils enthält jetzt ein Feld `significant`, das angibt, ob ein Persönlichkeitsmerkmal für die Eingabesprache aussagefähig ist. Das Feld gibt die Merkmale an, für die die Modelle des Service nicht in der Lage sind, aussagefähige Ergebnisse für arabische und koreanische Eingaben zu generieren. Die Schnittstellenversion für das Release ist `2017-10-13`. Weitere Informationen zu diesem und allen anderen Aktualisierungen an dem Service finden Sie in den [Releaseinformationen](/docs/services/personality-insights/release-notes.html).*

Der {{site.data.keyword.personalityinsightsfull}}-Service stellt eine Anwendungsprogrammierschnittstelle (API) zur Ableitung von Erkenntnissen aus Social Media-Daten, Unternehmensdaten oder anderen digitalen Kommunikationsdaten bereit. Der Service verwendet eine linguistische Analyse, um die intrinsischen Persönlichkeitsmerkmale von Personen aus der digitalen Kommunikation, wie E-Mails, Textnachrichten, Tweets und Beiträgen in Foren abzuleiten.
{: shortdesc}

Der Service leitet aus potenziell unscharfen Social Media-Beiträgen Portraits von Personen ab, die deren Persönlichkeitsmerkmale widerspiegeln. Der Service kann darüber hinaus die Verbraucherpräferenzen von Personen bestimmen, die die Wahrscheinlichkeit angeben, mit der diese Personen verschiedene Produkte, Services und Aktivitäten bevorzugen.

## Persönlichkeitsmerkmale
{: #models}

Der {{site.data.keyword.personalityinsightsshort}}-Service leitet Persönlichkeitsmerkmale nach drei primären Modellen ab:

-   Die **Big Five** der Persönlichkeitsmerkmale stellen das am häufigsten verwendete Modell zur allgemeinen Beschreibung der Interaktion einer Person mit ihrer Umgebung dar. Das Modell beinhaltet fünf primäre Dimensionen: *Verträglichkeit*, *Gewissenhaftigkeit*, *Extraversion*, *emotionale Bandbreite* und *Offenheit*. Jede Dimensionen hat 6 Facetten, die eine Person der Dimension entsprechend genauer charakterisieren.
-   **Bedürfnisse** beschreiben, auf welche Aspekte eines Produkts eine Person reagiert. Das Modell umfasst 12 typische Bedürfnisse: *Abenteuerlust*, *Harmonie*, *Neugier*, *Idealismus*, *Nähe*, *Selbstentfaltung*, *Freiheit*, *Liebe*, *Sachlichkeit*, *Stabilität*, *Herausforderung* und *Struktur*.
-   **Werte** beschreiben die Motivationsfaktoren, die die Entscheidungsfindung einer Person beeinflussen. Das Modell umfasst 5 Werte: *Selbsttranszendenz / Hilfsbereitschaft*, *Konservatismus / Traditionsbewusstsein*, *Hedonismus / Lebensfreude*, *Selbstverbesserung / Ehrgeiz* und *Offenheit für Veränderung / Abenteuerlust*.

Weitere Informationen finden Sie unter [Persönlichkeitsmodelle](/docs/services/personality-insights/models.html).

## Verbraucherpräferenzen
{: #preferences}

Auf der Basis der Persönlichkeitsmerkmale, die aus dem Eingabetext abgeleitet werden, kann der Service auch eine Angabe zu den Verbraucherpräferenzen des Autors zurückgeben. Verbraucherpräferenzen geben Aufschluss über die Wahrscheinlichkeit, mit der der Autor verschiedene Produkte, Services und Aktivitäten verfolgt. Der Service gruppiert die einzelnen Präferenzen in acht Kategorien: *Einkauf*, *Musik*,  *Filme*, *Lektüre und Bildung*, *Gesundheit und Aktivität*, *Ehrenamt*, *Umweltbewusstsein* und *Unternehmergeist*. Jede Kategorie enthält zwischen einer und einem Dutzenden einzelner Präferenzen.

Weitere Informationen finden Sie unter [Verbraucherpräferenzen](/docs/services/personality-insights/preferences.html).

## Vorteile des Service
{: #benefits}

Als Basisservice der {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}}-Plattform kann der {{site.data.keyword.personalityinsightsshort}}-Service Erkenntnisse bereitstellen, die Unternehmen vorteilhaft nutzen können.

-   Sie können ihre Kunden besser verstehen, indem sie die Präferenzen ihrer Kunden erforschen, sodass sie die Kundenzufriedenheit erhöhen und die Kundenbeziehungen stärken können.
-   Sie können Kundengewinnung, Kundenbindung und Kundenprojekte verbessern.
-   Sie können personalisierte Projekte und Interaktionen anleiten, um ihre Produkte, Services, Kampagnen sowie ihre Kommunikation auf einzelne Kunden zuzuschneiden.

Weitere Informationen dazu, wie Sie von dem Service profitieren können, finden Sie unter [Anwendungsfälle](/docs/services/personality-insights/usecases.html).

## Sprachunterstützung
{: #languages}

Der Service unterstützt die folgenden Sprachen. Sie können eine beliebige Kombination von unterstützten Sprachen für die Anforderung und die Antwort verwenden, jedoch muss der gesamte Eingabetext in derselben Sprache vorliegen. Weitere Informationen finden Sie unter [Anforderungs- und Antwortsprache angeben](/docs/services/personality-insights/input.html#languages).

<table style="width:75%">
  <caption>Tabelle 1. Unterstützte Sprachen</caption>
  <tr>
    <th style="width:50%; text-align:center">
      Anforderungssprachen
    </th>
    <th style="width:50%; text-align:center">
      Antwortsprachen
    </th>
  </tr>
  <tr>
    <td style="text-align:center; vertical-align:top">
      Arabisch<br/>
      Englisch<br/>
      Japanisch<br/>
      Koreanisch<br/>
      Spanisch
    </td>
    <td style="text-align:center; vertical-align:top">
      Arabisch<br/>
      Englisch<br/>
      Japanisch<br/>
      Koreanisch<br/>
      Spanisch<br/>
      Portugiesisch (Brasilien)<br/>
      Französisch<br/>
      Deutsch<br/>
      Italienisch<br/>
      Vereinfachtes Chinesisch<br/>
      Traditionelles Chinesisch
    </td>
  </tr>
</table>

## Weitere Informationen zum Service
{: #learn}

-   In einer [Schnelldemo ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://personality-insights-demo.ng.bluemix.net/){: new_window} des {{site.data.keyword.personalityinsightsshort}}-Service können Sie Eingabetext analysieren, um ein Persönlichkeitsportrait zu entwickeln, das Verbraucherpräferenzen für den Autor einschließt.
-   Anwendungen in {{site.data.keyword.watson}} Developer Cloud [Starter Kits ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://www.ibm.com/watson/developercloud/starter-kits.html){: new_window} demonstrieren den Service.
-   Die Abschnitte [Service in Aktion](/docs/services/personality-insights/applied.html) und [Wissenschaftliche Grundlagen des Service](/docs/services/personality-insights/science.html) enthalten Informationen zu der Forschung, die dem Service zugrunde liegt.
-   In [{{site.data.keyword.personalityinsightsshort}}-Service im {{site.data.keyword.Bluemix_short}}-Katalog ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://console.ng.bluemix.net/catalog/services/personality-insights/){: new_window} werden die für den Service verfügbaren Preistarife beschrieben.
