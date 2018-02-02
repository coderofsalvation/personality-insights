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

# Übersicht für Entwickler
{: #overviewDevelopers}

Sie können den {{site.data.keyword.personalityinsightsshort}}-Service über eine HTTP-REST-API (Representational State Transfer-API) verwenden. Darüber hinaus sind verschiedene Software Development Kits (SDKs) verfügbar, um die Anwendungsentwicklung in verschiedenen Sprachen und Umgebungen zu vereinfachen.
{: shortdesc}

## Programmierung mit dem Service
{: #programming}

Zur Generierung eines Persönlichkeitsprofils senden Sie Text an die HTTP-Methode `POST /v3/profile` des Service. Sie können einfachen Text, Text im HTML-Format oder JSON-Inhalt übergeben. Der Service kann die Analyse im JSON- oder CSV-Format zurückgeben.

Für jedes Persönlichkeitsmerkmal gibt der Service ein *Perzentil* zurück. Dies ist eine normalisierte Bewertung, die das Ausmaß beschreibt, in dem der Text des Autors ein Merkmal in einer Beispielpopulation aufweist. Bei entsprechender Anforderung gibt der Service auch eine *unaufbereitete Bewertung* zurück, das heißt, einen absoluten Wert, der nicht in Bezug auf eine Beispielpopulation normalisiert ist. Wenn die Eingabe eine Zeitmarke hat, stellt der Service eine Zusammenfassung der Schreibgewohnheiten des Autors in Bezug auf Wochentag und Tageszeit bereit. Bei entsprechender Anforderung gibt der Service außerdem eine Wahrscheinlichkeitsbewertung für jede der verfügbaren Verbraucherpräferenzen zurück.

Weitere Informationen zur Verwendung des Service finden Sie unter:

-   [Profil anfordern](/docs/services/personality-insights/input.html)
-   [JSON-Profil verstehen](/docs/services/personality-insights/output.html)
-   [CSV-Profil verstehen](/docs/services/personality-insights/output-csv.html)

### Profil visualisieren
{: #visualize}

Der Service stellt eine Gruppe von JavaScript-Dateien bereit, die die grafische Visualisierung eines Profils ermöglichen. Die Scripts ermöglichen die Verwendung des Service mit Caching und Netzen zur Verteilung von Inhalten. Sie nutzen JavaScript, jQuery, HTML und SVG mit der 3D-Bibliothek (`D3.js` - Data-Driven Documents), um die Ergebnisse darzustellen. Informationen zu diesen clientseitigen Dateien finden Sie in den Beispielanwendungen, die unter [Software Development Kits verwenden](#sdks) erwähnt werden. Weitere Informationen zu `D3.js` finden Sie unter [d3js.org ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://d3js.org/){: new_window}.

### CORS-Unterstützung
{: #CORS}

Der Service unterstützt Cross-Origin Resource Sharing (CORS), sodass browserbasierte Clients asynchrone Anforderungen aus Front-End-Scripts direkt an den Service senden können. Mithilfe von CORS können Clients Ressourcen aus einer Domäne anfordern, die außerhalb der Domäne liegt, aus der die Anforderung stammt, und Webanwendungen können von der Sicherheitsrichtlinie zur Durchsetzung derselben Herkunft (Same-Origin-Policy) abweichen, die ansonsten solche Anforderungen verhindert. Weitere Informationen finden Sie unter [enable-cors.org ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://enable-cors.org/){: new_window}.

## Software Development Kits verwenden
{: #sdks}

Der {{site.data.keyword.personalityinsightsshort}}-Service unterstützt eine Reihe von SDKs zur Vereinfachung der Anwendungsentwicklung. Die SDKs sind für viele gängige Programmiersprachen und Plattformen verfügbar, wie zum Beispiel Node.js, Java, Python und Apple&reg; iOS. Eine vollständige Liste der SDKs sowie Informationen zu ihrer Verwendung finden Sie unter [{{site.data.keyword.watson}}-SDKs](/docs/services/watson/getting-started-sdks.html). Alle SDKs sind über den [Namensbereich watson-developer-cloud ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/watson-developer-cloud){: new_window} auf GitHub verfügbar.

Der Service stellt darüber hinaus die folgenden Beispielanwendungen als Hilfe für den Einstieg zur Verfügung:

-   Sie können auf eine Anwendung, die das Node.js-SDK verwendet, über das [Repository personality-insights-nodejs ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} zugreifen.
-   Sie können auf eine Anwendung, die das Java-SDK verwendet, über das [Repository personality-insights-java ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/watson-developer-cloud/personality-insights-java){: new_window} zugreifen.

Informationen zur Entwicklung mobiler Anwendungen finden Sie unter [{{site.data.keyword.watson}} Developer Cloud Swift SDK ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/watson-developer-cloud/swift-sdk){: new_window}. Alle SDKs unterstützen eine Authentifizierung durch Ihre Serviceberechtigungsnachweise oder durch ein Authentifizierungstoken.

## Weitere Informationen zur Anwendungsentwicklung
{: #learn}

Der {{site.data.keyword.personalityinsightsshort}}-Service unterstützt zwei typische Programmiermodelle: Das Modell der *direkten Interaktion*, bei dem der Client direkt mit dem Service kommuniziert, und das Modell der *Weiterleitung über einen Proxy*, bei dem der Client und der Service alle Daten (Anforderungen und Ergebnisse) über eine Proxy-Anwendung austauschen, die sich in {{site.data.keyword.Bluemix_short}} befindet.

Weitere Informationen zur Arbeit mit {{site.data.keyword.watson}} Developer Cloud-Services und {{site.data.keyword.Bluemix_notm}} finden Sie in der folgenden Dokumentation:

-   Eine Einführung in die Arbeit mit {{site.data.keyword.watson}}-Services und {{site.data.keyword.Bluemix_notm}} finden Sie unter [Einführung in {{site.data.keyword.watson}} und {{site.data.keyword.Bluemix_notm}}](/docs/services/watson/index.html).
-   Eine sprachunabhängige Einführung in die Entwicklung von {{site.data.keyword.watson}}-Serviceanwendungen in {{site.data.keyword.Bluemix_notm}} finden Sie unter [{{site.data.keyword.Bluemix_notm}}-Entwicklungsansätze](/docs/services/watson/getting-started-bluemix.html).
-   Informationen zu den beiden Programmiermodellen, die für die Entwicklung von {{site.data.keyword.watson}}-Anwendungen verfügbar sind, finden Sie unter [Programmiermodelle für {{site.data.keyword.watson}}-Services](/docs/services/watson/getting-started-develop.html):
    -   Bei der Weiterleitung über einen Proxy bedient sich der Client eines Proxy-Servers, der sich in {{site.data.keyword.Bluemix_notm}} befindet, um mit dem Service zu kommunizieren. Er übergibt alle Anforderungen durch die Proxy-Anwendung. Bei der Weiterleitung durch einen Proxy werden zur Authentifizierung des Service nur die Serviceberechtigungsnachweise verwendet (siehe [Serviceberechtigungsnachweise für {{site.data.keyword.watson}}-Services](/docs/services/watson/getting-started-credentials.html)).
    -   Bei der direkten Interaktion verwendet der Client die Proxy-Anwendung in {{site.data.keyword.Bluemix_notm}} nur zum Abrufen des Authentifizierungstokens für den Service. Anschließend kommuniziert er direkt mit dem Service. Bei der direkten Interaktion werden die Serviceberechtigungsnachweise nur zum Abrufen eines Tokens verwendet (siehe [Tokens für die Authentifizierung](/docs/services/watson/getting-started-tokens.html)).
-   Informationen zur Steuerung der Standardanforderungsprotokollierung, die für alle {{site.data.keyword.watson}}-Services durchgeführt wird, finden Sie unter [Anforderungsprotokollierung für {{site.data.keyword.watson}}-Services steuern](/docs/services/watson/getting-started-logging.html).
