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

# Panoramica per gli sviluppatori
{: #overviewDevelopers}

Puoi utilizzare il servizio {{site.data.keyword.personalityinsightsshort}} tramite un'API REST (Representational State Transfer) HTTP. Sono inoltre disponibili diversi SDK (Software Development Kit) per semplificare lo sviluppo delle applicazioni in vari linguaggi.
{: shortdesc}

## Programmazione con il servizio
{: #programming}

Per produrre un profilo di personalità, invii il testo al metodo `POST /v3/profile` HTTP del servizio. Puoi inviare contenuti in testo semplice, HTML o JSON. Il servizio può restituire la sua analisi in formato JSON o CSV

Per ogni caratteristica della personalità, il servizio riporta un *percentile*. Il percentile è un punteggio normalizzato che descrive la misura in cui la scrittura dell'autore presenta una caratteristica all'interno di una popolazione campione. Se richiesto, il servizio restituisce anche un *punteggio non elaborato*, che è un valore assoluto che non è stato normalizzato per una popolazione campione. Se l'input ha un indicatore di data e ora, il servizio fornisce un riepilogo delle abitudini di scrittura dell'autore in base al giorno della settimana e all'ora del giorno. E se richiesto, il servizio restituisce anche un punteggio di probabilità per ciascuna delle sue preferenze di consumo disponibili.

Per ulteriori informazioni sull'utilizzo del servizio, vedi

-   [Richiesta di un profilo](/docs/services/personality-insights?topic=personality-insights-input)
-   [Descrizione di un profilo JSON](/docs/services/personality-insights?topic=personality-insights-output)
-   [Descrizione di un profilo CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV)

### Visualizzazione di un profilo
{: #visualize}

Il servizio fornisce una raccolta di file JavaScript che consentono la visualizzazione grafica di un profilo. Gli script facilitano l'uso del servizio con le reti di distribuzione di cache e contenuto. Utilizzano JavaScript, jQuery, HTML e SVG con la libreria Data-Driven Documents (`D3.js`) per rappresentare i risultati. Per ulteriori informazioni su `D3.js`, vedi [d3js.org ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://d3js.org/){: new_window}.

### Supporto CORS
{: #CORS}

Il servizio supporta CORS (Cross-Origin Resource Sharing). CORS consente ai client basati su browser di effettuare richieste asincrone direttamente al servizio dagli script di front-end. CORS aggira la politica di sicurezza della stessa origine, che altrimenti impedisce tali richieste. 

Utilizzando CORS, le pagine web possono richiedere risorse da un dominio esterno al dominio da cui è originata la richiesta. Per ulteriori informazioni, vedi [enable-cors.org ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://enable-cors.org/){: new_window}.

## Utilizzo di SDK (Software Development Kit)
{: #sdks}

Per semplificare lo sviluppo dell'applicazione, sono disponibili gli SDK per il servizio {{site.data.keyword.personalityinsightsshort}}. Gli SDK {{site.data.keyword.ibmwatson}} sono disponibili per molti linguaggi di programmazione e piattaforme popolari.

-   Per un elenco completo degli SDK e dei link agli SDK su GitHub, vedi [Utilizzo degli SDK](/docs/services/watson?topic=watson-using-sdks).
-   Per informazioni dettagliate su tutti i metodi degli SDK Node, Java, Python, Ruby e Go per il servizio {{site.data.keyword.personalityinsightsshort}}, vedi il [Riferimento API ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}/apidocs/personality-insights){: new_window}.

## Ulteriori informazioni sullo sviluppo di applicazioni
{: #learn-overview}

Per ulteriori informazioni sull'utilizzo dei servizi {{site.data.keyword.watson}} e {{site.data.keyword.cloud}}, vedi le seguenti sezioni:

-   Per un'introduzione all'utilizzo dei servizi {{site.data.keyword.watson}} e {{site.data.keyword.cloud_notm}}, vedi [Introduzione a {{site.data.keyword.watson}} e {{site.data.keyword.cloud_notm}}](/docs/services/watson?topic=watson-about).
-   Tutte le nuove istanze del servizio utilizzano {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) per l'autenticazione. Le istanze del servizio più vecchie potrebbero continuare a utilizzare `{username}` e `{password}` delle loro credenziali esistenti del servizio Cloud Foundry per eseguire l'autenticazione. Per ulteriori informazioni sull'autenticazione al servizio, vedi l'[aggiornamento del servizio del 30 ottobre 2018](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018) nelle note sulla release.
-   La registrazione delle richieste è disabilitata per il servizio {{site.data.keyword.personalityinsightsshort}}. Il servizio non registra o conserva i dati delle richieste e delle risposte, indipendentemente dal fatto che sia impostata l'intestazione della richiesta `X-Watson-Learning-Opt-Out`. 
