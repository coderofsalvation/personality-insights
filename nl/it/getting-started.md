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

# Esercitazione introduttiva
{: #gettingStarted}

Il servizio {{site.data.keyword.personalityinsightsfull}} ricava informazioni approfondite sulle caratteristiche della personalità da social media, dati aziendali o altre comunicazioni digitali. Questa esercitazione può aiutarti a iniziare a utilizzare subito il servizio {{site.data.keyword.personalityinsightsshort}}. Gli esempi ti mostrano come richiamare il metodo `POST /v3/profile` del servizio con diversi tipi di input e come richiedere diversi tipi e formati di output.
{: shortdesc}

## Prima di iniziare
{: #before-you-begin}

- Crea un'istanza del servizio.
    - {: download} Se vedi questa opzione, hai creato la tua istanza del servizio. Ora ottieni le tue credenziali.
    - Crea un progetto da un servizio:
        1.  Vai alla pagina [Servizi ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://console.{DomainName}/developer/watson/services){: new_window} di {{site.data.keyword.watson}} Developer Console.
        1.  Seleziona {{site.data.keyword.personalityinsightsshort}}, fai clic su **Aggiungi servizi** e registrati per un account {{site.data.keyword.Bluemix_notm}} gratuito o effettua l'accesso.
        1.  Immetti `personality-tutorial` come nome del progetto e fai clic su **Crea progetto**.
- Copia le credenziali per l'autenticazione alla tua istanza del servizio:
    - {: download} Dal dashboard del servizio (che stai utilizzando):
        1.  Fai clic sulla scheda **Credenziali del servizio**.
        1.  Sotto **Azioni**, fai clic su **Visualizza credenziali**.
        1.  Copia i valori `username`, `password` e `url`.
        {: download}
    - Dal tuo progetto **personality-tutorial** in Developer Console, copia i valori `username`,  `password` e `url` per `"personality_insights"` dalla sezione **Credenziali**.
- Assicurati di avere il cURL:
    - Gli esempi utilizzano il cURL per richiamare i metodi dell'interfaccia HTTP. Installa la versione per il tuo sistema operativo da [curl.haxx.se ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://curl.haxx.se/){: new_window}. Installa la versione che supporta il protocollo SSL (Secure Sockets Layer). Assicurati di includere il file binario installato nella tua variabile di ambiente `PATH`.

<!-- Remove this text after dedicated instances have the Developer Console: begin -->

Se utilizzi {{site.data.keyword.Bluemix_dedicated_notm}}, dovrai creare un'istanza del servizio dalla pagina [{{site.data.keyword.personalityinsightsshort}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://console.{DomainName}/catalog/services/personality-insights/){: new_window} nel catalogo. Per i dettagli su come creare le tue credenziali del servizio, vedi [Credenziali del servizio per i servizi Watson ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](/docs/services/watson/getting-started-credentials.html#getting-credentials-manually){: new_window}.

<!-- Remove this text after dedicated instances have the Developer Console: end -->

## Passo 1: invia l'input di testo semplice e ricevi l'output JSON di base
{: #example1}

Il primo esempio passa il file di testo semplice `profile.txt` al metodo `POST /v3/profile`  e richiede implicitamente la risposta JSON predefinita.

1.  Scarica il file di esempio <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="Icona link esterno" title="Icona link esterno" class="style-scope doc-content"></a>.
1.  Immetti il seguente comando per inviare il file al metodo `/v3/profile` e richiedere la risposta JSON predefinita. Il parametro `charset` incluso nell'intestazione `Content-Type` specifica la codifica dei caratteri del testo di input.
    -   Sostituisci `{username}` e `{password}` con le tue credenziali del servizio ottenute nel passo precedente.
    -   Modifica `{path_to_file}` per specificare la posizione del file `profile.txt`.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --data-binary "@{path_to_file}profile.txt" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
    ```
    {: pre}

Il servizio restituisce un oggetto JSON `Profile` che include i metadati di base come il numero di parole nell'input, il modello di lingua con cui è stato elaborato l'input e tutte le avvertenze associate all'input. Per ulteriori informazioni, vedi [Oggetto Profile](/docs/services/personality-insights/output.html#outputJSON).

Il profilo include informazioni sulle caratteristiche di personalità Big Five, Esigenze e Valori per l'autore come dedotte dal testo di input. Il servizio riporta un `percentile`, o punteggio normalizzato, per ciascuna caratteristica. Il servizio calcola il percentile confrontando i risultati dell'autore con i risultati di una popolazione campione. Per ulteriori informazioni, vedi [Output delle caratteristiche della personalità](/docs/services/personality-insights/output.html#traitJSON).

## Passo 2: invia l'input JSON e ricevi l'output JSON dettagliato
{: #example2}

Il secondo esempio passa il file JSON `profile.json` al metodo `/v3/profile`, accettando di nuovo la risposta JSON predefinita. L'esempio richiede le preferenze di consumo e i punteggi non elaborati per un'analisi più dettagliata dell'input.

1.  Scarica il file di esempio <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Icona link esterno" title="Icona link esterno" class="style-scope doc-content"></a>, che contiene una raccolta di messaggi di Twitter.
1.  Immetti il seguente comando per inviare il file al metodo `/v3/profile`. L'esempio specifica `application/json` per l'intestazione `Content-Type`; il parametro `charset` non è necessario per l'input JSON. L'esempio imposta i parametri di query `consumption_preferences` e `raw_scores` su `true`.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --data-binary "@{path_to_file}profile.json" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"
    ```
    {: pre}

Il servizio riporta un profilo JSON che include i metadati e le caratteristiche restituiti con l'esempio precedente. Per ogni caratteristica, il servizio include anche un `raw_score`, che rappresenta il punteggio dell'autore per la caratteristica basato esclusivamente sul testo di input, senza confrontare i risultati con una popolazione campione.

Poiché il contenuto di input include indicatori di data e ora, il servizio riporta anche le caratteristiche comportamentali. Queste sono caratteristiche temporali che indicano la `percentuale` degli elementi di contenuto creati ogni giorno della settimana e ora del giorno. Per ulteriori informazioni, vedi [Output comportamentale](/docs/services/personality-insights/output.html#behaviorJSON).

Il servizio riporta anche i punteggi per la raccolta delle preferenze di consumo. I punteggi indicano la probabilità dell'autore di preferire prodotti, servizi e attività differenti in base alle caratteristiche dedotte. Per ulteriori informazioni, vedi [Output delle preferenze di consumo](/docs/services/personality-insights/output.html#preferenceJSON).

## Passo 3: invia l'input JSON e ricevi l'output CSV dettagliato
{: #example3}

Il terzo esempio è simile al secondo: passa lo stesso contenuto JSON e richiede gli stessi risultati. Ma questo esempio specifica `text/csv` per l'intestazione `Accept` per richiedere la risposta in formato CSV (comma-separated value). Utilizza l'opzione `--output` del comando cURL per indirizzare i risultati in un file denominato `profile.csv`. L'esempio imposta il parametro di query `csv_headers` su `true` per richiedere che con l'output vengano restituite le intestazioni di colonna.

1.  Immetti il seguente comando per inviare il file JSON al metodo `/v3/profile`.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary "@{path_to_file}profile.json" \
    --output profile.csv \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"
    ```
    {: pre}

Per una descrizione dettagliata della risposta e delle intestazioni CSV, vedi [Descrizione di un profilo CSV](/docs/services/personality-insights/output-csv.html).

## Passi successivi

-   Ulteriori informazioni sulla [Richiesta di un profilo](/docs/services/personality-insights/input.html) e sulla [Descrizione di un profilo JSON](/docs/services/personality-insights/output.html) e [Descrizione di un profilo CSV](/docs/services/personality-insights/output-csv.html).
-   Informazioni sui [Modelli di personalità](/docs/services/personality-insights/models.html) Big Five, Esigenze e Valori.
-   Ulteriori informazioni sull'API nel [Riferimento API ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}
-   Interagisci con l'API in [Explorer API ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v3){: new_window}.
-   Esplora l'[applicazione di esempio Node.js ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} per ulteriori informazioni sullo sviluppo dell'applicazione con il servizio.
