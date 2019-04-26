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
{:go: .ph data-hd-programlang='go'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}
{:download: .download}
{:apikey: data-credential-placeholder='apikey'}
{:url: data-credential-placeholder='url'}
{:hide-dashboard: .hide-dashboard}

# Lernprogramm zur Einführung
{: #gettingStarted}

Der {{site.data.keyword.personalityinsightsfull}}-Service leitet Erkenntnisse zu Persönlichkeitsmerkmalen aus Social Media, Unternehmensdaten oder anderer digitaler Kommunikation ab. Dieses Lernprogramm kann Sie beim schnellen Einstieg in die Arbeit mit dem {{site.data.keyword.personalityinsightsshort}} unterstützen. Die Beispiele zeigen, wie die Methode `POST /v3/profile` des Service mit verschiedenen Typen von Eingaben aufgerufen wird und wie verschiedene Typen von Ausgaben und Ausgabeformaten angefordert werden.
{: shortdesc}

Dieses Lernprogramm verwendet API-Schlüssel von {{site.data.keyword.cloud}} Identity and Access Management (IAM) für die Authentifizierung. Ältere Serviceinstanzen können `{username}` und `{password}` aus ihren vorhandenen Cloud Foundry-Serviceberechtigungsnachweisen weiterhin für die Authentifizierung verwenden. Führen Sie die Authentifizierung mit dem Ansatz durch, der für Ihre Serviceinstanz geeignet ist. Weitere Informationen zur Verwendung der IAM-Authentifizierung durch den Service enthalten die Angaben zur [Serviceaktualisierung vom 30. Oktober 2018](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018) in den Releaseinformationen.
{: important}

## Vorbereitungen
{: #before-you-begin}

-   {: hide-dashboard} Erstellen Sie eine Instanz des Service:
    1.  {: hide-dashboard} Rufen Sie die Seite für [{{site.data.keyword.personalityinsightsshort}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/catalog/services/personality-insights){: new_window} im {{site.data.keyword.cloud_notm}}-Katalog auf.
    1.  {: hide-dashboard} Registrieren Sie sich für ein kostenloses {{site.data.keyword.cloud_notm}}-Konto oder melden Sie sich an.
    1.  {: hide-dashboard} Klicken Sie auf **Erstellen**.
-   Kopieren Sie die Berechtigungsnachweise für die Authentifizierung Ihrer Serviceinstanz:
    1.  {: hide-dashboard} Klicken Sie im [{{site.data.keyword.cloud_notm}}-Dashboard ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/dashboard/apps){: new_window} auf Ihre {{site.data.keyword.personalityinsightsshort}}-Serviceinstanz, um zur Dashboardseite für den {{site.data.keyword.personalityinsightsshort}}-Service zu gelangen.
    1.  Klicken Sie auf der Seite **Verwalten** auf **Anzeigen**, um Ihre Berechtigungsnachweise anzuzeigen.
    1.  Kopieren Sie die Werte für `API-Schlüssel` und `URL`.
-   Stellen Sie sicher, dass Sie den Befehl `curl` verwenden können.
    -   Die Beispiele verwenden den Befehl `curl`, um Methoden der HTTP-Schnittstelle aufzurufen. Installieren Sie die Version für Ihr Betriebssystem von [curl.haxx.se ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://curl.haxx.se/){: new_window}. Installieren Sie die Version, die das SSL-Protokoll (Secure Sockets Layer) unterstützt. Stellen Sie sicher, dass Sie die installierte Binärdatei in Ihre Umgebungsvariable `PATH` einschließen.

Achten Sie bei der Eingabe eines Befehls darauf, `{apikey}` und `{url}` jeweils durch Ihren tatsächlichen API-Schlüssel und die tatsächliche URL zu ersetzen. Lassen Sie die Klammern, die einen Variablenwert angeben, aus dem Befehl weg. Ein tatsächlicher Wert ähnelt dem folgenden Beispiel:
{: hide-dashboard}

```bash
curl -X POST -u "apikey:L_HALhLVIksh1b73l97LSs6R_3gLo4xkujAaxm7i-b9x"
. . .
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{:pre}
{: hide-dashboard}

## Schritt 1: Eingabe mit einfachem Text senden und JSON-Basisausgabe empfangen
{: #example1}

Das erste Beispiel übergibt die unverschlüsselte Textdatei `profile.txt` an die Methode `POST /v3/profile` und fordert eine JSON-Antwort an.

1.  Laden Sie die Beispieldatei <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="Symbol für externen Link" title="Symbol für externen Link"></a> herunter.
1.  Setzen Sie den folgenden Befehl ab, um die Datei an die Methode `/v3/profile` zu senden und eine JSON-Antwort anzufordern.
    -   Der Header `Content-Type` gibt mit `text/plain` an, dass es sich bei der Eingabe um unverschlüsselten Text handelt. Der im Header enthaltene Parameter `charset` kennzeichnet die Zeichenkodierung des Eingabetextes.
    -   Der Header `Accept` gibt durch `application/json` an, dass eine JSON-Ausgabe angefordert wird.
    -   {: hide-dashboard} Ersetzen Sie `{apikey}` und `{url}` jeweils durch die für Sie zutreffenden Angaben.
    -   Ändern Sie `{path_to_file}`, um die Position der Datei `profile.txt` anzugeben.

    ```bash
    curl -X POST -u "apikey:{apikey}"
{: apikey} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.txt \
    "{url}/v3/profile?version=2017-10-13"
{: url}
    ```
    {: pre}

Der Service gibt ein JSON-Objekt `Profile` zurück, das die grundlegenden Metadaten enthält, wie die Anzahl der Wörter in der Eingabe, das Sprachmodell, mit dem die Eingabe verarbeitet wurde, sowie Warnungen, die der Eingabe zugeordnet sind, sofern zutreffend. Weitere Informationen finden Sie unter [Objekt 'Profile'](/docs/services/personality-insights?topic=personality-insights-output#outputJSON).

Das Profil enthält Informationen zu den Big Five-Persönlichkeitsmerkmalen, Bedürfnissen und Werten für den Autor, wie sie aus dem Eingabetext abgeleitet werden. Der Service gibt einen Perzentilwert (`percentile`) bzw. eine normalisierte Bewertung für jedes Merkmal zurück. Der Service berechnet das Perzentil, indem die Ergebnisse des Autors mit den Ergebnissen aus einer Beispielpopulation verglichen werden. Weitere Informationen finden Sie unter [Ausgabe von Persönlichkeitsmerkmalen](/docs/services/personality-insights?topic=personality-insights-output#traitJSON).

## Schritt 2: JSON-Eingabe senden und detaillierte JSON-Ausgabe empfangen
{: #example2}

Das zweite Beispiel übergibt die JSON-Datei `profile.json` an die Methode `/v3/profile` und fordert abermals eine JSON-Antwort an. Das Beispiel fordert Verbraucherpräferenzen und unaufbereitete Bewertungen für eine detailliertere Analyse der Eingabe an.

1.  Laden Sie die Beispieldatei <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Symbol für externen Link" title="Symbol für externen Link"></a> herunter, die eine Sammlung von Twitter-Nachrichten enthält.
1.  Führen Sie den folgenden Befehl aus, um die Datei an die Methode `/v3/profile` zu senden. Im Beispiel wird `application/json` für die Header `Content-Type` und `Accept` angegeben. Der Parameter `charset` wird für die JSON-Eingabe nicht benötigt. Im Beispiel werden die Abfrageparameter `consumption_preferences` und `raw_scores` auf den Wert `true` gesetzt.

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.json \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"{: url}
    ```
    {: pre}

Der Service gibt ein JSON-Profil zurück, das die Metadaten und Merkmale enthält, die auch mit dem vorherigen Beispiel zurückgegeben werden. Für jedes Merkmal schließt der Service außerdem ein Feld `raw_score` ein, das die Bewertung des Autors für das Merkmal ausschließlich auf der Basis des Eingabetexts ohne Vergleich der Ergebnisse mit einer Beispielpopulation enthält.

Da der Eingabeinhalt Zeitmarken einschließt, gibt der Service darüber hinaus Verhaltensmerkmale zurück. Dabei handelt es sich um zeitbezogene Merkmale, die den Prozentsatz (`percentage`) der Inhaltselemente angeben, die an jedem Wochentag und zu jeder Tagesstunde erstellt wurden. Weitere Informationen finden Sie unter [Ausgaben von Verhaltensmerkmalen](/docs/services/personality-insights?topic=personality-insights-output#behaviorJSON).

Der Service gibt zudem Bewertungen für die zugehörige Gruppe von Verbraucherpräferenzen zurück. Die Bewertungen geben die Wahrscheinlichkeit, mit der der Autor verschiedene Produkte, Services und Aktivitäten bevorzugt, auf der Basis der abgeleiteten Merkmale an. Weitere Informationen finden Sie unter [Ausgabe für Verbraucherpräferenzen](/docs/services/personality-insights?topic=personality-insights-output#preferenceJSON).

## Schritt 3: JSON-Eingabe und detaillierte CSV-Ausgabe empfangen
{: #example3}

Das dritte Beispiel ist dem zweiten ähnlich: es werden derselbe JSON-Inhalt übergeben und dieselben Ergebnisse angefordert. Jedoch wird in diesem Beispiel der Wert `text/csv` für den Header `Accept` angegeben, um die Antwort in einem CSV-Format (d. h. in einer Datei mit durch Kommas getrennten Werten) anzufordern. Im Beispiel wird die Option `--output` des `curl`-Befehls verwendet, um die Ergebnisse in eine Datei namens `profile.csv` zu leiten. In dem Beispiel wird der Abfrageparameter `csv_headers` auf den Wert `true` gesetzt, um anzufordern, dass Spaltenüberschriften mit der Ausgabe zurückgegeben werden.

1.  Führen Sie den folgenden Befehl aus, um die JSON-Datei an die Methode `/v3/profile` zu senden. Der Header `Content-Type` bezeichnet den Eingabeinhalt als `application/json` und der Header `Accept` fordert mit `text/csv` die CSV-Ausgabe an.

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary @{path_to_file}profile.json \
    --output profile.csv \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"{: url}
    ```
    {: pre}

Eine ausführliche Beschreibung der CSV-Antwort und der Spaltenüberschriften finden Sie unter [CSV-Profil verstehen](/docs/services/personality-insights?topic=personality-insights-outputCSV).

## Nächste Schritte
{: #gsns}

-   Lesen Sie die weiteren Informationen zur [Anforderung eines Profils](/docs/services/personality-insights?topic=personality-insights-input) sowie zum [Lesen eines JSON-Profils](/docs/services/personality-insights?topic=personality-insights-output) und zum [Lesen eines CSV-Profils](/docs/services/personality-insights?topic=personality-insights-outputCSV).
-   Lesen Sie die Informationen zu den [Persönlichkeitsmodellen](/docs/services/personality-insights?topic=personality-insights-models) für die Kategorien Big Five, Bedürfnisse und Werte.
-   Lesen Sie die weiteren Informationen zur API in der [API-Referenz ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/apidocs/personality-insights){: new_window}
-   Erkunden Sie die [Node.js-Beispielanwendung ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window}, um sich weiter über die Anwendungsentwicklung mit dem Service zu informieren.
