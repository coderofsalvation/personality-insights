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

# Informazioni
{: #about}

> **Aggiornamento del servizio:** *il servizio {{site.data.keyword.personalityinsightsshort}} è stato aggiornato il 18 novembre 2018. Ora il servizio è disponibile nell'ubicazione di Londra {{site.data.keyword.cloud}}. Per ulteriori informazioni, vedi l'[aggiornamento del servizio del 18 novembre 2018](/docs/services/personality-insights?topic=personality-insights-release-notes#November2018b) nelle note sulla release.*

Il servizio {{site.data.keyword.personalityinsightsfull}} fornisce un'API (application programming interface) per ricavare informazioni approfondite da social media, dati aziendali o altre comunicazioni digitali. Il servizio utilizza l'analisi linguistica per dedurre le caratteristiche intrinseche della personalità degli individui dalle comunicazioni digitali come e-mail, messaggi di testo, tweet e post nei forum.
{: shortdesc}

Dai social media potenzialmente risonanti, il servizio deduce ritratti di individui che riflettono le loro caratteristiche della personalità. Può anche determinare le preferenze di consumo delle persone, che indicano la loro probabilità di preferire vari prodotti, servizi e attività.

## Caratteristiche della personalità
{: #models-index}

Il servizio {{site.data.keyword.personalityinsightsshort}} deduce le caratteristiche della personalità sulla base di tre modelli primari:

-   Le caratteristiche della personalità **Big Five** rappresentano il modello
          più utilizzato per descrivere generalmente come una persona si
          relaziona con il mondo. Il modello include cinque dimensioni primarie: *Gradevolezza*, *Coscienziosità*, *Estroversione*, *Stabilità emotiva* e *Apertura mentale*. Ogni dimensione ha sei aspetti che caratterizzano ulteriormente un individuo a seconda della dimensione.
-   Le **esigenze** descrivono quali aspetti di un prodotto vengono accolti da una persona. Il modello include dodici
          esigenze caratteristiche: *Eccitazione*, *Armonia*,
          *Curiosità*, *Ideale*, *Prossimità*,
          *Espressione personale*, *Libertà*, *Amore*,
          *Praticità*, *Stabilità*, *Sfida* e
          *Struttura*.
-   I **Valori** descrivono i fattori motivanti che influenzano il processo decisionale di una persona. Il modello include cinque valori: *Autotrascendenza / Aiutare gli altri*, *Conservazione / Tradizione*, *Edonismo / Ricerca dei piaceri della vita*, *Auto-miglioramento / Raggiungimento del successo* e *Apertura al cambiamento / Eccitazione*.

Per ulteriori informazioni, vedi [Modelli di personalità](/docs/services/personality-insights?topic=personality-insights-models).

## Preferenze di consumo
{: #preferences-index}

Sulla base delle caratteristiche della personalità desunte dal testo di input, il servizio può anche restituire un'indicazione delle preferenze di consumo dell'autore. Le preferenze di consumo indicano la probabilità dell'autore di perseguire diversi prodotti, servizi e attività. Il servizio raggruppa le preferenze individuali in otto categorie: *Acquisti*, *Musica*, *Film*, *Lettura e apprendimento*, *Salute e attività*, *Volontariato*, *Interesse ambientale* e *Imprenditorialità*. Ogni categoria contiene da una a una dozzina di preferenze individuali.

Per ulteriori informazioni, vedi [Preferenze di consumo](/docs/services/personality-insights?topic=personality-insights-preferences).

## Vantaggi del servizio
{: #benefits}

Come servizio principale della piattaforma {{site.data.keyword.ibmwatson}}, il servizio {{site.data.keyword.personalityinsightsshort}} può fornire informazioni approfondite utili per le aziende

-   Comprendere i propri clienti a un livello più profondo imparando a conoscere le loro preferenze, migliorandone la soddisfazione e rafforzando le relazioni con i clienti.
-   Migliorare l'acquisizione, la fidelizzazione e il coinvolgimento dei clienti.
-   Guidare iterazioni e coinvolgimenti altamente personalizzati per adattare al meglio prodotti, servizi, campagne e comunicazioni ai singoli clienti.

Per ulteriori informazioni su come beneficiare del servizio, vedi [Casi di utilizzo](/docs/services/personality-insights?topic=personality-insights-usecases).

## Supporto delle lingue
{: #languages-index}

Il servizio supporta le seguenti lingue. Puoi utilizzare qualsiasi combinazione di lingue supportate per la richiesta e la risposta, ma tutto il testo inserito deve essere nella stessa lingua. Per ulteriori informazioni, vedi [Specifica delle lingue di richiesta e di risposta](/docs/services/personality-insights?topic=personality-insights-input#languages-input).

<table style="width:75%">
  <caption>Tabella 1. Lingue supportate</caption>
  <tr>
    <th style="width:50%; text-align:center">
      Lingue di richiesta
    </th>
    <th style="width:50%; text-align:center">
      Lingue di risposta
    </th>
  </tr>
  <tr>
    <td style="text-align:center; vertical-align:top">
      Arabo<br/>
      Inglese<br/>
      Giapponese<br/>
      Coreano<br/>
      Spagnolo
    </td>
    <td style="text-align:center; vertical-align:top">
      Arabo<br/>
      Inglese<br/>
      Giapponese<br/>
      Coreano<br/>
      Spagnolo<br/>
      Portoghese brasiliano<br/>
      Francese<br/>
      Tedesco<br/>
      Italiano<br/>
      Cinese semplificato<br/>
      Cinese tradizionale
    </td>
  </tr>
</table>

## HIPAA
{: hipaa}

Il supporto HIPAA (Health Insurance Portability and Accountability Act) degli Stati Uniti non si applica al servizio {{site.data.keyword.personalityinsightsshort}}. Il servizio è senza stato. Non memorizza dati utente in {{site.data.keyword.cloud_notm}}. 

## Ulteriori informazioni sul servizio
{: #learn-index}

-   Una [demo rapida ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://personality-insights-demo.ng.bluemix.net/){: new_window} del servizio {{site.data.keyword.personalityinsightsshort}} analizza il testo di input per sviluppare un ritratto di personalità che include le preferenze di consumo per l'autore. 
-   Le applicazioni in {{site.data.keyword.watson}} [Starter Kits ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://www.ibm.com/watson/developercloud/starter-kits.html){: new_window} illustrano il servizio.
-   [Il servizio in azione](/docs/services/personality-insights?topic=personality-insights-applied) e [La scienza alla base del servizio](/docs/services/personality-insights?topic=personality-insights-science) forniscono informazioni sulla ricerca che sta alla base del servizio.
-   Il servizio {{site.data.keyword.personalityinsightsshort}} nel [catalogo {{site.data.keyword.cloud_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}/catalog/services/personality-insights/){: new_window} descrive i piani dei prezzi disponibili per il servizio. 
