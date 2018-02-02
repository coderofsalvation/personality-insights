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

# Panoramica per gli sviluppatori
{: #overviewDevelopers}

Puoi utilizzare il servizio {{site.data.keyword.personalityinsightsshort}} tramite un'API REST (Representational State Transfer) HTTP. Sono inoltre disponibili diversi SDK (Software Development Kit) per semplificare lo sviluppo delle applicazioni in vari linguaggi e ambienti.
{: shortdesc}

## Programmazione con il servizio
{: #programming}

Per produrre un profilo di personalità, invii il testo al metodo `POST /v3/profile` HTTP del servizio. Puoi inviare contenuti in testo semplice, HTML o JSON. Il servizio può restituire la sua analisi in formato JSON o CSV

Per ogni caratteristica della personalità, il servizio riporta un *percentile*, che è un punteggio normalizzato che descrive la misura in cui la scrittura dell'autore presenta una caratteristica all'interno di una popolazione campione. Se richiesto, il servizio restituisce anche un *punteggio non elaborato*, che è un valore assoluto che non è stato normalizzato per una popolazione campione. Se l'input ha un indicatore di data e ora, il servizio fornisce un riepilogo delle abitudini di scrittura dell'autore rispetto al giorno della settimana e all'ora del giorno. E se richiesto, il servizio restituisce anche un punteggio di probabilità per ciascuna delle sue preferenze di consumo disponibili.

Per ulteriori informazioni sull'utilizzo del servizio, vedi

-   [Richiesta di un profilo](/docs/services/personality-insights/input.html)
-   [Descrizione di un profilo JSON](/docs/services/personality-insights/output.html)
-   [Descrizione di un profilo CSV](/docs/services/personality-insights/output-csv.html)

### Visualizzazione di un profilo
{: #visualize}

Il servizio fornisce una raccolta di file JavaScript che consentono la visualizzazione grafica di un profilo. Gli script facilitano l'uso del servizio con le reti di distribuzione di cache e contenuto. Utilizzano JavaScript, jQuery, HTML e SVG con la libreria Data-Driven Documents (`D3.js`) per rappresentare i risultati. Per informazioni su questi file sul lato client, vedi le applicazioni di esempio citate in [Utilizzo di SDK (Software Development Kit)](#sdks); per ulteriori informazioni su `D3.js`, vedi [d3js.org ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://d3js.org/){: new_window}.

### Supporto CORS
{: #CORS}

Il servizio supporta CORS (Cross-Origin Resource Sharing) per consentire ai client basati su browser di effettuare richieste asincrone direttamente al servizio dagli script di front-end. CORS consente ai client di richiedere risorse da un dominio esterno al dominio da cui è originata la richiesta e consente alle applicazioni Web di aggirare la politica di sicurezza della stessa origine, che altrimenti impedisce tali richieste. Per ulteriori informazioni, vedi [enable-cors.org ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://enable-cors.org/){: new_window}.

## Utilizzo di SDK (Software Development Kit)
{: #sdks}

Il servizio {{site.data.keyword.personalityinsightsshort}} supporta diversi SDK per lo sviluppo di applicazioni semplificate. Gli SDK sono disponibili per molti linguaggi di programmazione e piattaforme popolari, tra cui Node.js, Java, Python e Apple&reg; iOS. Per un elenco completo di SDK e informazioni sul loro utilizzo, vedi [SDK {{site.data.keyword.watson}}](/docs/services/watson/getting-started-sdks.html). Tutti gli SDK sono disponibili nello [spazio dei nomi watson-developer-cloud![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/watson-developer-cloud){: new_window} su GitHub.

Il servizio mette inoltre a disposizione le seguenti applicazioni di esempio per aiutarti a iniziare:

-   Puoi accedere a un'applicazione che utilizza l'SDK Node.js nel [repository personality-insights-nodejs ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window}.
-   Puoi accedere a un'applicazione che utilizza l'SDK Java nel [repository personality-insights-java ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/watson-developer-cloud/personality-insights-java){: new_window}.

Per lo sviluppo di applicazioni per dispositivi mobili, vedi [{{site.data.keyword.watson}} Developer Cloud Swift SDK ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://github.com/watson-developer-cloud/swift-sdk){: new_window}. Tutti gli SDK supportano l'autenticazione mediante le credenziali del servizio o un token di autenticazione.

## Ulteriori informazioni sullo sviluppo di applicazioni
{: #learn}

Il servizio {{site.data.keyword.personalityinsightsshort}} supporta due tipici modelli di programmazione: *Interazione diretta*, in cui il client comunica direttamente con il servizio, e *inoltro tramite un proxy*, in cui il client e il servizio scambiano tutti i dati (richieste e risultati) tramite un'applicazione proxy che risiede in {{site.data.keyword.Bluemix_short}}.

Per ulteriori informazioni sull'utilizzo dei servizi {{site.data.keyword.watson}} Developer Cloud e {{site.data.keyword.Bluemix_notm}}, vedi quanto segue:

-   Per un'introduzione all'utilizzo dei servizi {{site.data.keyword.watson}} e {{site.data.keyword.Bluemix_notm}}, vedi [Introduzione a {{site.data.keyword.watson}} e {{site.data.keyword.Bluemix_notm}}](/docs/services/watson/index.html).
-   Per un'introduzione indipendente dal linguaggio allo sviluppo di applicazioni dei servizi {{site.data.keyword.watson}} in {{site.data.keyword.Bluemix_notm}}, vedi [Approcci di sviluppo in {{site.data.keyword.Bluemix_notm}}](/docs/services/watson/getting-started-bluemix.html).
-   Per informazioni sui due modelli di programmazione disponibili per lo sviluppo di applicazioni {{site.data.keyword.watson}}, vedi [Modelli di programmazione per i servizi {{site.data.keyword.watson}}](/docs/services/watson/getting-started-develop.html):
    -   Con l'inoltro tramite un proxy, il client si affida a un server proxy che risiede in  {{site.data.keyword.Bluemix_notm}} per comunicare con il servizio e quindi passa tutte le richieste attraverso l'applicazione proxy. L'inoltro delle richieste tramite un proxy utilizza solo le credenziali del servizio per eseguire l'autenticazione; vedi [Credenziali del servizio per i servizi {{site.data.keyword.watson}}](/docs/services/watson/getting-started-credentials.html).
    -   Con l'interazione diretta, il client utilizza l'applicazione proxy in {{site.data.keyword.Bluemix_notm}} solo per ottenere un token di autenticazione per il servizio, dopodiché comunica direttamente con il servizio. L'interazione diretta utilizza le credenziali del servizio solo per ottenere un token; vedi [Token per l'autenticazione](/docs/services/watson/getting-started-tokens.html).
-   Per informazioni sul controllo della registrazione di richieste predefinita eseguita per tutti i servizi {{site.data.keyword.watson}}, vedi [Controllo della registrazione di richieste per i servizi {{site.data.keyword.watson}}](/docs/services/watson/getting-started-logging.html).
