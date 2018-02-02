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

# Informazioni
{: #about}

> **Aggiornamento del servizio:** *il servizio {{site.data.keyword.personalityinsightsshort}} è stato aggiornato il 13 ottobre 2017. Ogni oggetto `Trait` di un profilo di personalità include ora un campo `significant` per indicare se una caratteristica della personalità è significativa per la lingua di input. Il campo identifica quelle caratteristiche per le quali i modelli del servizio non sono in grado di generare risultati significativi per l'input in arabo e in coreano. La versione dell'interfaccia per la release è `2017-10-13`. Per ulteriori informazioni su questo e su tutti gli aggiornamenti del servizio, vedi le [Note sulla release](/docs/services/personality-insights/release-notes.html).*

Il servizio {{site.data.keyword.personalityinsightsfull}} fornisce un'API (Application Programming Interface) per ricavare informazioni approfondite da social media, dati aziendali o altre comunicazioni digitali. Il servizio utilizza l'analisi linguistica per dedurre le caratteristiche intrinseche della personalità degli individui dalle comunicazioni digitali come e-mail, messaggi di testo, tweet e post nei forum.
{: shortdesc}

Dai social media potenzialmente risonanti, il servizio deduce ritratti di individui che riflettono le loro caratteristiche della personalità. Può anche determinare le preferenze di consumo delle persone, che indicano la loro probabilità di preferire vari prodotti, servizi e attività. 

## Caratteristiche della personalità
{: #models}

Il servizio {{site.data.keyword.personalityinsightsshort}} deduce le caratteristiche della personalità sulla base di tre modelli primari:

-   Le caratteristiche della personalità **Big Five** rappresentano il modello
          più utilizzato per descrivere generalmente come una persona si
          relaziona con il mondo. Il modello include cinque dimensioni primarie: *Gradevolezza*, *Coscienziosità*, *Estroversione*, *Stabilità emotiva* e *Apertura mentale*. Ogni dimensione ha sei aspetti che caratterizzano ulteriormente un individuo a seconda della dimensione.
-   Le **Esigenze** descrivono quali aspetti di un prodotto
          verranno accolti da una persona. Il modello include dodici
          esigenze caratteristiche: *Eccitazione*, *Armonia*,
          *Curiosità*, *Ideale*, *Prossimità*,
          *Espressione personale*, *Libertà*, *Amore*,
          *Praticità*, *Stabilità*, *Sfida* e
          *Struttura*.
-   I **Valori** descrivono i fattori motivanti che influenzano il processo decisionale di una persona. Il modello include cinque valori: *Autotrascendenza / Aiutare gli altri*, *Conservazione / Tradizione*, *Edonismo / Ricerca dei piaceri della vita*, *Auto-miglioramento / Raggiungimento del successo* e *Apertura al cambiamento / Eccitazione*.

Per ulteriori informazioni, vedi [Modelli di personalità](/docs/services/personality-insights/models.html).

## Preferenze di consumo
{: #preferences}

Sulla base delle caratteristiche della personalità desunte dal testo di input, il servizio può anche restituire un'indicazione delle preferenze di consumo dell'autore. Le preferenze di consumo indicano la probabilità dell'autore di perseguire diversi prodotti, servizi e attività. Il servizio raggruppa le preferenze individuali in otto categorie: *Acquisti*, *Musica*, *Film*, *Lettura e apprendimento*, *Salute e attività*, *Volontariato*, *Interesse ambientale* e *Imprenditorialità*. Ogni categoria contiene da una a una dozzina di preferenze individuali.

Per ulteriori informazioni, vedi [Preferenze di consumo](/docs/services/personality-insights/preferences.html).

## Vantaggi del servizio
{: #benefits}

Come servizio principale della piattaforma {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}}, il servizio {{site.data.keyword.personalityinsightsshort}} può fornire informazioni approfondite utili per le aziende

-   Comprendere i propri clienti a un livello più profondo imparando a conoscere le loro preferenze, migliorandone la soddisfazione e rafforzando le relazioni con i clienti.
-   Migliorare l'acquisizione, la fidelizzazione e il coinvolgimento dei clienti.
-   Guidare iterazioni e coinvolgimenti altamente personalizzati per adattare al meglio prodotti, servizi, campagne e comunicazioni ai singoli clienti.

Per ulteriori informazioni su come beneficiare del servizio, vedi [Casi di utilizzo](/docs/services/personality-insights/usecases.html).

## Supporto delle lingue
{: #languages}

Il servizio supporta le seguenti lingue. Puoi utilizzare qualsiasi combinazione di lingue supportate per la richiesta e la risposta, ma tutto il testo inserito deve essere nella stessa lingua. Per ulteriori informazioni, vedi [Specifica delle lingue di richiesta e di risposta](/docs/services/personality-insights/input.html#languages).

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

## Ulteriori informazioni sul servizio
{: #learn}

-   Una [demo rapida ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://personality-insights-demo.ng.bluemix.net/){: new_window} del servizio {{site.data.keyword.personalityinsightsshort}} ti consente di analizzare il testo di input per sviluppare un ritratto di personalità che include le preferenze di consumo per l'autore.
-   Le applicazioni in {{site.data.keyword.watson}} Developer Cloud [Starter Kits ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://www.ibm.com/watson/developercloud/starter-kits.html){: new_window} illustrano il servizio.
-   [Il servizio in azione](/docs/services/personality-insights/applied.html) e [La scienza alla base del servizio](/docs/services/personality-insights/science.html) forniscono informazioni sulla ricerca che sta alla base del servizio.
-   Il servizio [{{site.data.keyword.personalityinsightsshort}} nel catalogo {{site.data.keyword.Bluemix_short}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://console.ng.bluemix.net/catalog/services/personality-insights/){: new_window} descrive i piani dei prezzi disponibili per il servizio. 
