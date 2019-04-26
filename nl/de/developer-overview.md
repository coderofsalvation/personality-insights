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

# Übersicht für Entwickler
{: #overviewDevelopers}

Sie können den {{site.data.keyword.personalityinsightsshort}}-Service über eine HTTP-REST-API (Representational State Transfer-API) verwenden. Darüber hinaus sind mehrere Software Development Kits (SDKs) verfügbar, um die Anwendungsentwicklung in verschiedenen Sprachen zu vereinfachen.
{: shortdesc}

## Programmierung mit dem Service
{: #programming}

Zur Generierung eines Persönlichkeitsprofils senden Sie Text an die HTTP-Methode `POST /v3/profile` des Service. Sie können einfachen Text, Text im HTML-Format oder JSON-Inhalt übergeben. Der Service kann die Analyse im JSON- oder CSV-Format zurückgeben.

Für jedes Persönlichkeitsmerkmal meldet der Service ein *Perzentil*. Dies ist eine normalisierte Bewertung, die beschreibt, in welchem Maß der Text des Autors ein Merkmal in einer Beispielpopulation aufweist. Bei entsprechender Anforderung gibt der Service auch eine *unaufbereitete Bewertung* zurück, das heißt, einen absoluten Wert, der nicht in Bezug auf eine Beispielpopulation normalisiert ist. Wenn die Eingabe eine Zeitmarke aufweist, stellt der Service eine Zusammenfassung der Schreibgewohnheiten des Autors nach Wochentag und Tageszeit bereit. Bei entsprechender Anforderung gibt der Service außerdem eine Wahrscheinlichkeitsbewertung für jede der verfügbaren Verbraucherpräferenzen zurück.

Weitere Informationen zur Verwendung des Service finden Sie unter:

-   [Profil anfordern](/docs/services/personality-insights?topic=personality-insights-input)
-   [JSON-Profil verstehen](/docs/services/personality-insights?topic=personality-insights-output)
-   [CSV-Profil verstehen](/docs/services/personality-insights?topic=personality-insights-outputCSV)

### Profil visualisieren
{: #visualize}

Der Service stellt eine Gruppe von JavaScript-Dateien bereit, die die grafische Visualisierung eines Profils ermöglichen. Die Scripts ermöglichen die Verwendung des Service mit Caching und Netzen zur Verteilung von Inhalten. Sie nutzen JavaScript, jQuery, HTML und SVG mit der 3D-Bibliothek (`D3.js` - Data-Driven Documents), um die Ergebnisse darzustellen. Weitere Informationen zu `D3.js` finden Sie in [d3js.org ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://d3js.org/){: new_window}.

### CORS-Unterstützung
{: #CORS}

Der Service unterstützt Cross-Origin Resource Sharing (CORS). CORS ermöglicht browserbasierten Clients das Senden asynchroner Anforderungen aus Front-End-Scripts direkt an den Service. CORS umgeht die Sicherheitsrichtlinie zur Durchsetzung derselben Herkunft (Same-Origin-Policy), die derartige Anforderungen ansonsten verhindert.

Mithilfe von CORS können Webseiten Ressourcen aus einer fremden Domäne anfordern, die außerhalb der Domäne liegt, aus der die Anforderung stammt. Weitere Informationen finden Sie unter [enable-cors.org ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://enable-cors.org/){: new_window}.

## Software Development Kits verwenden
{: #sdks}

Zur Vereinfachung der Anwendungsentwicklung stehen SDKs für den {{site.data.keyword.personalityinsightsshort}}-Service zur Verfügung. {{site.data.keyword.ibmwatson}}-SDKs sind für viele gängige Programmiersprachen und Plattformen verfügbar.

-   Eine vollständige Liste der SDKs und Links zu den SDKs auf GitHub finden Sie in [SDKs verwenden](/docs/services/watson?topic=watson-using-sdks).
-   Detaillierte Informationen zu allen Methoden der Node-, Java-, Python-, Ruby- und Go-SDKs für den {{site.data.keyword.personalityinsightsshort}}-Service enthält die [API-Referenz ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/apidocs/personality-insights){: new_window}.

## Weitere Informationen zur Anwendungsentwicklung
{: #learn-overview}

Weitere Informationen zur Arbeit mit {{site.data.keyword.watson}}-Services und {{site.data.keyword.cloud}} enthalten die folgenden Abschnitte:

-   Eine Einführung in die Arbeit mit {{site.data.keyword.watson}}-Services und {{site.data.keyword.cloud_notm}} finden Sie unter [Einführung in {{site.data.keyword.watson}} und {{site.data.keyword.cloud_notm}}](/docs/services/watson?topic=watson-about).
-   Alle neuen Serviceinstanzen verwenden {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) für die Authentifizierung. Ältere Serviceinstanzen können `{username}` und `{password}` aus ihren vorhandenen Cloud Foundry-Serviceberechtigungsnachweisen weiterhin für die Authentifizierung verwenden. Weitere Informationen zur Authentifizierung beim Service enthalten die Angaben zur [Serviceaktualisierung vom 30. Oktober](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018) in den Releaseinformationen.
-   Die Protokollierung von Anforderungen ist für den {{site.data.keyword.personalityinsightsshort}}-Service inaktiviert. Der Service protokolliert oder speichert keine Daten aus Anfragen und Antworten, und zwar unabhängig davon, ob der Anforderungsheader `X-Watson-Learning-Opt-Out` festgelegt ist.
