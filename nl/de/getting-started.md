---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-18"

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
{:download: .download}

# Lernprogramm zur Einführung
{: #gettingStarted}

Der {{site.data.keyword.personalityinsightsfull}}-Service leitet Erkenntnisse zu Persönlichkeitsmerkmalen aus Social Media, Unternehmensdaten oder anderer digitaler Kommunikation ab. Dieses Lernprogramm kann Sie beim schnellen Einstieg in die Arbeit mit dem {{site.data.keyword.personalityinsightsshort}} unterstützen. Die Beispiele zeigen, wie die Methode `POST /v3/profile` des Service mit verschiedenen Typen von Eingaben aufgerufen wird und wie verschiedene Typen von Ausgaben und Ausgabeformaten angefordert werden.
{: shortdesc}

## Vorbereitungen
{: #before-you-begin}

- Erstellen Sie eine Instanz des Service:
    - {: download} Wenn Sie dies sehen, haben Sie Ihre Serviceinstanz erstellt. Rufen Sie nun Ihre Berechtigungsnachweise ab.
    - Erstellen Sie ein Projekt aus einem Service:
        1.  Wechseln Sie zur {{site.data.keyword.watson}} Developer Console-Seite [Services ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://console.{DomainName}/developer/watson/services){: new_window}.
        1.  Wählen Sie {{site.data.keyword.personalityinsightsshort}} aus, klicken Sie auf **Add Services** (Services hinzufügen) und registrieren Sie sich entweder für ein kostenloses {{site.data.keyword.Bluemix_notm}}-Konto an oder melden Sie sich an.
        1.  Geben Sie `personality-tutorial` als Projektnamen ein und klicken Sie auf **Create Project** (Projekt erstellen).
- Kopieren Sie die Berechtigungsnachweise für die Authentifizierung Ihrer Serviceinstanz:
    - {: download} Im Service-Dashboard (in dem Sie sich befinden):
        1.  Klicken Sie auf die Registerkarte **Serviceberechtigungsnachweise**.
        1.  Klicken Sie auf **Berechtigungsnachweise anzeigen** unter **Aktionen**.
        1.  Kopieren Sie die Werte der Felder `Benutzername`, `Kennwort` und `URL`.
        {: download}
    - Kopieren Sie in Ihrem Projekt **personality-tutorial** in der Entwicklerkonsole (Developer Console) die Werte für Benutzername (`username`), Kennwort (`password`) und URL (`url`) für `"personality_insights"` aus dem Abschnitt für Berechtigungsnachweise (**Credentials**).
- Stellen Sie sicher, dass Sie über cURL verfügen:
    - In den Beispielen werden mithilfe von cURL Methoden der HTTP-Schnittstelle aufgerufen. Installieren Sie die Version für Ihr Betriebssystem von [curl.haxx.se ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://curl.haxx.se/){: new_window}. Installieren Sie die Version, die das SSL-Protokoll (Secure Sockets Layer) unterstützt. Stellen Sie sicher, dass Sie die installierte Binärdatei in Ihre Umgebungsvariable `PATH` einschließen.

<!-- Remove this text after dedicated instances have the Developer Console: begin -->

Wenn Sie {{site.data.keyword.Bluemix_dedicated_notm}} verwenden, erstellen Sie eine Serviceinstanz auf der Seite [{{site.data.keyword.personalityinsightsshort}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://console.{DomainName}/catalog/services/personality-insights/){: new_window} im Katalog (Catalog). Detaillierte Informationen zur Ermittlung Ihrer Serviceberechtigungsnachweise finden Sie unter [Serviceberechtigungsnachweise für Watson-Services ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](/docs/services/watson/getting-started-credentials.html#getting-credentials-manually){: new_window}.

<!-- Remove this text after dedicated instances have the Developer Console: end -->

## Schritt 1: Eingabe mit einfachem Text senden und JSON-Basisausgabe empfangen
{: #example1}

Im ersten Beispiel wird die Datei `profile.txt` mit einfachem Text an die Methode `POST /v3/profile` übergeben und implizit die JSON-Standardausgabe angefordert.

1.  Laden Sie die Beispieldatei <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="Symbol für externen Link" title="Symbol für externen Link" class="style-scope doc-content"></a> herunter.
1.  Führen Sie den folgenden Befehl aus, um die Datei an die Methode `/v3/profile` zu senden und die JSON-Standardantwort anzufordern. Der Parameter `charset` im Header `Content-Type` gibt die Zeichencodierung des Eingabetexts an.
    -   Ersetzen Sie `{username}` und `{password}` durch Ihre Berechtigungsnachweise für den Service aus dem vorherigen Schritt.
    -   Ändern Sie `{path_to_file}`, um die Position der Datei `profile.txt` anzugeben.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --data-binary "@{path_to_file}profile.txt" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
    ```
    {: pre}

Der Service gibt ein JSON-Objekt `Profile` zurück, das die grundlegenden Metadaten enthält, wie die Anzahl der Wörter in der Eingabe, das Sprachmodell, mit dem die Eingabe verarbeitet wurde, sowie Warnungen, die der Eingabe zugeordnet sind, sofern zutreffend. Weitere Informationen finden Sie unter [Objekt 'Profile'](/docs/services/personality-insights/output.html#outputJSON).

Das Profil enthält Informationen zu den Big Five-Persönlichkeitsmerkmalen, Bedürfnissen und Werten für den Autor, wie sie aus dem Eingabetext abgeleitet werden. Der Service gibt einen Perzentilwert (`percentile`) bzw. eine normalisierte Bewertung für jedes Merkmal zurück. Der Service berechnet das Perzentil, indem die Ergebnisse des Autors mit den Ergebnissen aus einer Beispielpopulation verglichen werden. Weitere Informationen finden Sie unter [Ausgabe von Persönlichkeitsmerkmalen](/docs/services/personality-insights/output.html#traitJSON).

## Schritt 2: JSON-Eingabe senden und detaillierte JSON-Ausgabe empfangen
{: #example2}

Im zweiten Beispiel wird die JSON-Datei `profile.json` an die Methode `/v3/profile` übergeben, wiederum unter Übernahme der JSON-Standardantwort. Das Beispiel fordert Verbraucherpräferenzen und unaufbereitete Bewertungen für eine detailliertere Analyse der Eingabe an.

1.  Laden Sie die Beispieldatei <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Symbol für externen Link" title="Symbol für externen Link" class="style-scope doc-content"></a> herunter, die eine Sammlung von Twitter-Nachrichten enthält.
1.  Führen Sie den folgenden Befehl aus, um die Datei an die Methode `/v3/profile` zu senden. Im Beispiel wird `application/json` für den Header `Content-Type` angegeben. Der Parameter `charset` ist für JSON-Eingaben nicht erforderlich. Im Beispiel werden die Abfrageparameter `consumption_preferences` und `raw_scores` auf den Wert `true` gesetzt.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --data-binary "@{path_to_file}profile.json" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"
    ```
    {: pre}

Der Service gibt ein JSON-Profil zurück, das die Metadaten und Merkmale enthält, die auch mit dem vorherigen Beispiel zurückgegeben werden. Für jedes Merkmal schließt der Service außerdem ein Feld `raw_score` ein, das die Bewertung des Autors für das Merkmal ausschließlich auf der Basis des Eingabetexts ohne Vergleich der Ergebnisse mit einer Beispielpopulation enthält.

Da der Eingabeinhalt Zeitmarken einschließt, gibt der Service darüber hinaus Verhaltensmerkmale zurück. Dabei handelt es sich um zeitbezogene Merkmale, die den Prozentsatz (`percentage`) der Inhaltselemente angeben, die an jedem Wochentag und zu jeder Tagesstunde erstellt wurden. Weitere Informationen finden Sie unter [Ausgaben von Verhaltensmerkmalen](/docs/services/personality-insights/output.html#behaviorJSON).

Der Service gibt zudem Bewertungen für die zugehörige Gruppe von Verbraucherpräferenzen zurück. Die Bewertungen geben die Wahrscheinlichkeit, mit der der Autor verschiedene Produkte, Services und Aktivitäten bevorzugt, auf der Basis der abgeleiteten Merkmale an. Weitere Informationen finden Sie unter [Ausgabe für Verbraucherpräferenzen](/docs/services/personality-insights/output.html#preferenceJSON).

## Schritt 3: JSON-Eingabe und detaillierte CSV-Ausgabe empfangen
{: #example3}

Das dritte Beispiel ist dem zweiten ähnlich: es werden derselbe JSON-Inhalt übergeben und dieselben Ergebnisse angefordert. Jedoch wird in diesem Beispiel der Wert `text/csv` für den Header `Accept` angegeben, um die Antwort in einem CSV-Format (d. h. in einer Datei mit durch Kommas getrennten Werten) anzufordern. Im Beispiel wird die Option `--output` des cURL-Befehls verwendet, um die Ergebnisse in eine Datei mit dem Namen `profile.csv` zu leiten. In dem Beispiel wird der Abfrageparameter `csv_headers` auf den Wert `true` gesetzt, um anzufordern, dass Spaltenüberschriften mit der Ausgabe zurückgegeben werden.

1.  Führen Sie den folgenden Befehl aus, um die JSON-Datei an die Methode `/v3/profile` zu senden.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary "@{path_to_file}profile.json" \
    --output profile.csv \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"
    ```
    {: pre}

Eine ausführliche Beschreibung der CSV-Antwort und der Spaltenüberschriften finden Sie unter [CSV-Profil verstehen](/docs/services/personality-insights/output-csv.html).

## Nächste Schritte

-   Lesen Sie die weiteren Informationen zur [Anforderung eines Profils](/docs/services/personality-insights/input.html) sowie zum [Lesen eines JSON-Profils](/docs/services/personality-insights/output.html) und zum [Lesen eines CSV-Profils](/docs/services/personality-insights/output-csv.html).
-   Lesen Sie die Informationen zu den [Persönlichkeitsmodellen](/docs/services/personality-insights/models.html) für die Kategorien Big Five, Bedürfnisse und Werte.
-   Lesen Sie die weiteren Informationen zur API in der [API-Referenz ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}
-   Interagieren Sie mit der API im [API-Explorer ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v3){: new_window}.
-   Erkunden Sie die [Node.js-Beispielanwendung ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window}, um sich weiter über die Anwendungsentwicklung mit dem Service zu informieren.
