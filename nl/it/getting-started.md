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

# Esercitazione introduttiva
{: #gettingStarted}

Il servizio {{site.data.keyword.personalityinsightsfull}} ricava informazioni approfondite sulle caratteristiche della personalità da social media, dati aziendali o altre comunicazioni digitali. Questa esercitazione può aiutarti a iniziare a utilizzare subito il servizio {{site.data.keyword.personalityinsightsshort}}. Gli esempi ti mostrano come richiamare il metodo `POST /v3/profile` del servizio con diversi tipi di input e come richiedere diversi tipi e formati di output.
{: shortdesc}

L'esercitazione utilizza le chiavi API {{site.data.keyword.cloud}} Identity and Access Management (IAM) per l'autenticazione. Le istanze del servizio più vecchie potrebbero continuare a utilizzare `{username}` e `{password}` delle loro credenziali esistenti del servizio Cloud Foundry per eseguire l'autenticazione. Esegui l'autenticazione utilizzando l'approccio corretto per la tua istanza del servizio. Per ulteriori informazioni sull'utilizzo dell'autenticazione IAM del servizio, vedi l'[aggiornamento del servizio del 30 ottobre 2018](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018) nelle note sulla release.
{: important}

## Prima di iniziare
{: #before-you-begin}

-   {: hide-dashboard} Crea un'istanza del servizio.
    1.  {: hide-dashboard} Vai alla pagina [{{site.data.keyword.personalityinsightsshort}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}/catalog/services/personality-insights){: new_window} nel catalogo {{site.data.keyword.cloud_notm}}.
    1.  {: hide-dashboard} Registrati per un account {{site.data.keyword.cloud_notm}} gratuito o esegui l'accesso. 
    1.  {: hide-dashboard} Fai clic su **Crea**.
-   Copia le credenziali per l'autenticazione alla tua istanza del servizio:
    1.  {: hide-dashboard} Dal [dashboard {{site.data.keyword.cloud_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}/dashboard/apps){: new_window}, fai clic sulla tua istanza del servizio {{site.data.keyword.personalityinsightsshort}} per andare alla pagina del dashboard del servizio {{site.data.keyword.personalityinsightsshort}}. 
    1.  Nella pagina **Gestisci**, fai clic su **Mostra** per visualizzare le tue credenziali. 
    1.  Copia i valori `Chiave API` e `URL`.
-   Assicurati di avere il comando `curl`.
    -   Gli esempi utilizzano il comando `curl` per richiamare i metodi dell'interfaccia HTTP. Installa la versione per il tuo sistema operativo da [curl.haxx.se ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://curl.haxx.se/){: new_window}. Installa la versione che supporta il protocollo SSL (Secure Sockets Layer). Assicurati di includere il file binario installato nella tua variabile di ambiente `PATH`.

Quando immetti un comando, sostituisci `{apikey}` e `{url}` con la tua chiave API e il tuo URL reali. Ometti le parentesi graffe, che indicano un valore variabile, dal comando. Un valore reale somiglia al seguente esempio:
{: hide-dashboard}

```bash
curl -X POST -u "apikey:L_HALhLVIksh1b73l97LSs6R_3gLo4xkujAaxm7i-b9x"
. . .
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{:pre}
{: hide-dashboard}

## Passo 1: invia l'input di testo semplice e ricevi l'output JSON di base
{: #example1}

Il primo esempio passa il file di testo semplice `profile.txt` al metodo `POST /v3/profile` e richiede una risposta JSON.

1.  Scarica il file di esempio <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="Icona link esterno" title="Icona link esterno"></a>.
1.  Immetti il seguente comando per inviare il file al metodo `/v3/profile` e richiedere una risposta JSON.
    -   L'intestazione `Content-Type` specifica che l'input è in testo semplice, `text/plain`. Il parametro `charset` incluso nell'intestazione identifica la codifica dei caratteri del testo di input. 
    -   L'intestazione `Accept` specifica `application/json` per indicare che è stato richiesto l'output JSON.
    -   {: hide-dashboard} Sostituisci `{apikey}` e `{url}` con le tue informazioni. 
    -   Modifica `{path_to_file}` per specificare la posizione del file `profile.txt`.

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.txt \
    "{url}/v3/profile?version=2017-10-13"{: url}
    ```
    {: pre}

Il servizio restituisce un oggetto JSON `Profile` che include i metadati di base come il numero di parole nell'input, il modello di lingua con cui è stato elaborato l'input e tutte le avvertenze associate all'input. Per ulteriori informazioni, vedi [Oggetto Profile](/docs/services/personality-insights?topic=personality-insights-output#outputJSON).

Il profilo include informazioni sulle caratteristiche di personalità Big Five, Esigenze e Valori per l'autore come dedotte dal testo di input. Il servizio riporta un `percentile`, o punteggio normalizzato, per ciascuna caratteristica. Il servizio calcola il percentile confrontando i risultati dell'autore con i risultati di una popolazione campione. Per ulteriori informazioni, vedi [Output delle caratteristiche della personalità](/docs/services/personality-insights?topic=personality-insights-output#traitJSON).

## Passo 2: invia l'input JSON e ricevi l'output JSON dettagliato
{: #example2}

Il secondo esempio passa il file JSON `profile.json` al metodo `/v3/profile`, richiedendo di nuovo una risposta JSON. L'esempio richiede le preferenze di consumo e i punteggi non elaborati per un'analisi più dettagliata dell'input.

1.  Scarica il file di esempio <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Icona link esterno" title="Icona link esterno"></a>, che contiene una raccolta di messaggi di Twitter.
1.  Immetti il seguente comando per inviare il file al metodo `/v3/profile`. L'esempio specifica `application/json` per le intestazioni `Content-Type` e `Accept`; il parametro `charset` non è necessario per l'input JSON. L'esempio imposta i parametri di query `consumption_preferences` e `raw_scores` su `true`.

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.json \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"{: url}
    ```
    {: pre}

Il servizio riporta un profilo JSON che include i metadati e le caratteristiche restituiti con l'esempio precedente. Per ogni caratteristica, il servizio include anche un `raw_score`, che rappresenta il punteggio dell'autore per la caratteristica basato esclusivamente sul testo di input, senza confrontare i risultati con una popolazione campione.

Poiché il contenuto di input include indicatori di data e ora, il servizio riporta anche le caratteristiche comportamentali. Queste sono caratteristiche temporali che indicano la `percentuale` degli elementi di contenuto creati ogni giorno della settimana e ora del giorno. Per ulteriori informazioni, vedi [Output comportamentale](/docs/services/personality-insights?topic=personality-insights-output#behaviorJSON).

Il servizio riporta anche i punteggi per la raccolta delle preferenze di consumo. I punteggi indicano la probabilità dell'autore di preferire prodotti, servizi e attività differenti in base alle caratteristiche dedotte. Per ulteriori informazioni, vedi [Output delle preferenze di consumo](/docs/services/personality-insights?topic=personality-insights-output#preferenceJSON).

## Passo 3: invia l'input JSON e ricevi l'output CSV dettagliato
{: #example3}

Il terzo esempio è simile al secondo: passa lo stesso contenuto JSON e richiede gli stessi risultati. Ma questo esempio specifica `text/csv` per l'intestazione `Accept` per richiedere la risposta in formato CSV (comma-separated value). Utilizza l'opzione `--output` del comando `curl` per indirizzare i risultati in un file denominato `profile.csv`. L'esempio imposta il parametro di query `csv_headers` su `true` per richiedere che con l'output vengano restituite le intestazioni di colonna.

1.  Immetti il seguente comando per inviare il file JSON al metodo `/v3/profile`. L'intestazione `Content-Type` identifica il contenuto di input come `application/json` e l'intestazione `Accept` richiede l'output CSV, `text/csv`.

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary @{path_to_file}profile.json \
    --output profile.csv \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"{: url}
    ```
    {: pre}

Per una descrizione dettagliata della risposta e delle intestazioni CSV, vedi [Descrizione di un profilo CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV).

## Passi successivi
{: #gsns}

-   Ulteriori informazioni sulla [Richiesta di un profilo](/docs/services/personality-insights?topic=personality-insights-input) e sulla [Descrizione di un profilo JSON](/docs/services/personality-insights?topic=personality-insights-output) e [Descrizione di un profilo CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV).
-   Informazioni sui [Modelli di personalità](/docs/services/personality-insights?topic=personality-insights-models) Big Five, Esigenze e Valori.
-   Ulteriori informazioni sull'API nel [Riferimento API ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}/apidocs/personality-insights){: new_window}
-   Esplora l'[applicazione di esempio Node.js ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} per ulteriori informazioni sullo sviluppo dell'applicazione con il servizio.
