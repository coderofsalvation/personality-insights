---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-27"

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

# Produktinformation
{: #about}

> **Serviceaktualisierung:** *Der {{site.data.keyword.personalityinsightsshort}}-Service wurde am 18. November 2018 aktualisiert. Der Service ist nun am {{site.data.keyword.cloud}}-Standort London verfügbar. Weitere Informationen finden Sie in den Releaseinformationen im Abschnitt [Serviceaktualisierung vom 18. November 2018](/docs/services/personality-insights?topic=personality-insights-release-notes#November2018b).*

Der {{site.data.keyword.personalityinsightsfull}}-Service stellt eine Anwendungsprogrammierschnittstelle (API) zur Verfügung, um Erkenntnisse aus Social Media, Unternehmensdaten und anderen digitalen Kommunikationsquellen ableiten zu können. Der Service verwendet eine linguistische Analyse, um die intrinsischen Persönlichkeitsmerkmale von Personen aus der digitalen Kommunikation, wie E-Mails, Textnachrichten, Tweets und Beiträgen in Foren abzuleiten.
{: shortdesc}

Der Service leitet aus potenziell unscharfen Social Media-Beiträgen Portraits von Personen ab, die deren Persönlichkeitsmerkmale widerspiegeln. Der Service kann darüber hinaus die Verbraucherpräferenzen von Personen bestimmen, die die Wahrscheinlichkeit angeben, mit der diese Personen verschiedene Produkte, Services und Aktivitäten bevorzugen.

## Persönlichkeitsmerkmale
{: #models-index}

Der {{site.data.keyword.personalityinsightsshort}}-Service leitet Persönlichkeitsmerkmale nach drei primären Modellen ab:

-   Die **Big Five** der Persönlichkeitsmerkmale stellen das am häufigsten verwendete Modell zur allgemeinen Beschreibung der Interaktion einer Person mit ihrer Umgebung dar. Das Modell beinhaltet fünf primäre Dimensionen: *Verträglichkeit*, *Gewissenhaftigkeit*, *Extraversion*, *emotionales Spektrum* und *Offenheit*. Jede Dimension hat sechs Facetten, die ein Individuum entsprechend der Dimension näher charakterisieren.
-   **Bedürfnisse** beschreiben, auf welche Aspekte eines Produkts eine Person wahrscheinlich anspricht. Das Modell umfasst 12 typische Bedürfnisse: *Abenteuerlust*, *Harmonie*, *Neugier*, *Idealismus*, *Nähe*, *Selbstentfaltung*, *Freiheit*, *Liebe*, *Sachlichkeit*, *Stabilität*, *Herausforderung* und *Struktur*.
-   **Werte** beschreiben die Motivationsfaktoren, die die Entscheidungsfindung einer Person beeinflussen. Das Modell umfasst 5 Werte: *Selbsttranszendenz / Hilfsbereitschaft*, *Konservatismus / Traditionsbewusstsein*, *Hedonismus / Lebensfreude*, *Selbstverbesserung / Ehrgeiz* und *Offenheit für Veränderung / Abenteuerlust*.

Weitere Informationen finden Sie unter [Persönlichkeitsmodelle](/docs/services/personality-insights?topic=personality-insights-models).

## Verbraucherpräferenzen
{: #preferences-index}

Auf der Basis der Persönlichkeitsmerkmale, die sich aus dem Eingabetext ableiten lassen, kann der Service auch einen Hinweis auf die Verbraucherpräferenzen des Autors liefern. Verbraucherpräferenzen geben Aufschluss über die Wahrscheinlichkeit, mit der der Autor verschiedene Produkte, Services und Aktivitäten verfolgt. Der Service gruppiert die einzelnen Präferenzen in acht Kategorien: *Einkauf*, *Musik*, *Filme*, *Lektüre und Lernen*, *Gesundheit und Aktivität*, *Ehrenamtliche Mitarbeit*, *Umweltbewusstsein* und *Unternehmergeist*. Jede Kategorie enthält zwischen einer Präferenz und einem Dutzend einzelner Präferenzen.

Weitere Informationen finden Sie unter [Verbraucherpräferenzen](/docs/services/personality-insights?topic=personality-insights-preferences).

## Vorteile des Service
{: #benefits}

Als Basisservice der {{site.data.keyword.ibmwatson}}-Plattform kann der {{site.data.keyword.personalityinsightsshort}}-Service Erkenntnisse bereitstellen, die Unternehmen vorteilhaft nutzen können.

-   Sie können ihre Kunden besser verstehen, indem sie die Präferenzen ihrer Kunden erforschen, sodass sie die Kundenzufriedenheit erhöhen und die Kundenbeziehungen stärken können.
-   Sie können Kundengewinnung, Kundenbindung und Kundenprojekte verbessern.
-   Sie können personalisierte Projekte und Interaktionen anleiten, um ihre Produkte, Services, Kampagnen sowie ihre Kommunikation auf einzelne Kunden zuzuschneiden.

Weitere Informationen dazu, wie Sie von dem Service profitieren können, finden Sie unter [Anwendungsfälle](/docs/services/personality-insights?topic=personality-insights-usecases).

## Sprachunterstützung
{: #languages-index}

Der Service unterstützt die folgenden Sprachen. Sie können eine beliebige Kombination von unterstützten Sprachen für die Anforderung und die Antwort verwenden, jedoch muss der gesamte Eingabetext in derselben Sprache vorliegen. Weitere Informationen finden Sie unter [Anforderungs- und Antwortsprache angeben](/docs/services/personality-insights?topic=personality-insights-input#languages-input).

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

## HIPAA
{: hipaa}

Die Unterstützung des US-amerikanischen Health Insurance Portability and Accountability Act (HIPAA) gilt nicht für den {{site.data.keyword.personalityinsightsshort}}-Service. Der Service ist statusunabhängig. Er speichert keine Benutzerdaten in {{site.data.keyword.cloud_notm}}. 

## Weitere Informationen zum Service
{: #learn-index}

-   Im Rahmen einer [Schnelldemo ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://personality-insights-demo.ng.bluemix.net/){: new_window} des {{site.data.keyword.personalityinsightsshort}}-Service wird Eingabetext analysiert, um ein Persönlichkeitsportrait zu entwickeln, das Verbraucherpräferenzen für den Autor einschließt.
-   Anwendungen in {{site.data.keyword.watson}} [Starter-Kits ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://www.ibm.com/watson/developercloud/starter-kits.html){: new_window} veranschaulichen die Funktion des Service.
-   Die Abschnitte [Service in Aktion](/docs/services/personality-insights?topic=personality-insights-applied) und [Wissenschaftliche Grundlagen des Service](/docs/services/personality-insights?topic=personality-insights-science) enthalten Informationen zu der Forschung, die dem Service zugrunde liegt.
-   In {{site.data.keyword.personalityinsightsshort}}-Service im [{{site.data.keyword.cloud_notm}}-Katalog ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/catalog/services/personality-insights/){: new_window} werden die für den Service verfügbaren Preistarife beschrieben.
