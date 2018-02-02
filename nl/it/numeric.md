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

# Interpretazione dei risultati numerici
{: #numeric}

Il servizio {{site.data.keyword.personalityinsightsshort}} restituisce risultati numerici per ciascuna delle caratteristiche di personalità e comportamentali e per ogni preferenza di consumo. I valori differiscono nelle informazioni fornite.
{: shortdesc}

> **Nota:** per l'input in arabo e coreano, il servizio non è in grado di produrre percentili e punteggi non elaborati significativi per alcune delle caratteristiche della personalità. Per ulteriori informazioni, vedi [Limitazioni per l'input in arabo e coreano](#limitations).

## Percentili per le caratteristiche della personalità
{: #percentiles}

Per ogni richiesta, il servizio riporta sempre un punteggio normalizzato come `percentile` per ogni caratteristica della personalità Big Five, Valori ed Esigenze. I punteggi normalizzati rappresentano una classificazione percentile per ogni caratteristica in base alle qualità dedotte dal testo di input. Il servizio calcola i punteggi normalizzati confrontando il punteggio non elaborato per il testo dell'autore con i risultati di una popolazione campione. Il servizio riporta ogni percentile come un doppio nell'intervallo da 0 a 1.

Ad esempio, un percentile di `0.64980796071382` per la caratteristica della personalità `big5_extraversion` indica che l'autore del testo ottenuto un punteggio nel 65° percentile per quella caratteristica. La scrittura dell'autore mostra la tendenza a una misura superiore al 64 percento e inferiore al 34 percento della popolazione campione. La precisione del percentile dipende dal numero di parole che sono state inoltrate come input con la richiesta; per ulteriori informazioni, vedi [Immissione di input sufficiente](/docs/services/personality-insights/input.html#sufficient).

> **Nota:** non esiste alcuna relazione matematica tra i percentili riportati per le dimensioni e gli aspetti Big Five. Il servizio calcola il percentile normalizzato per ogni dimensione e aspetto in modo indipendente in base alle correlazioni tra i punteggi dei partecipanti all'indagine per tale dimensione o aspetto e le parole che utilizzano. Pertanto, anche se gli aspetti forniscono descrizioni più dettagliate delle dimensioni, l'aggiunta dei punteggi per i sei aspetti di una dimensione non produce necessariamente il percentile per quella dimensione. Lo stesso vale per i punteggi non elaborati.

## Punteggi non elaborati per le caratteristiche della personalità
{: #rawScores}

Se specifichi `true` per il parametro di query `raw_scores` della richiesta, il servizio riporta un `raw_score` per ogni caratteristica della personalità. I punteggi non elaborati rappresentano il punteggio per la specifica caratteristica basato esclusivamente sul testo dell'autore e sul modello di quella caratteristica, senza confrontare i risultati con una popolazione campione. I punteggi non elaborati possono essere interpretati come i punteggi che l'autore potrebbe ricevere effettuando un test della personalità.

Il servizio riporta ogni punteggio non elaborato come un doppio nell'intervallo da 0 a 1. Un punteggio più alto indica generalmente una maggiore probabilità che l'autore abbia quella caratteristica. Tuttavia, i punteggi non elaborati devono essere considerati nell'insieme: l'intervallo di valori in pratica potrebbe essere molto più piccolo di da 0 a 1, quindi un singolo punteggio deve essere considerato nel contesto dei punteggi complessivi e del loro intervallo. Ma in generale, un punteggio non elaborato, come ad esempio `0.56817738781166` per la caratteristica della personalità `big5_extraversion` indica che l'autore avrebbe probabilmente raggiunto questo punteggio con un test della personalità. Confronta questo punteggio non elaborato con il percentile normalizzato riportato per lo stesso autore e la stessa caratteristica nella sezione precedente.

Il servizio rende disponibili i punteggi non elaborati per gli utenti che desiderano applicare una normalizzazione personalizzata per uno scenario specifico o che non richiedono un confronto con una popolazione campione. Gli utenti che vogliono sapere come vengono confrontate le caratteristiche dell'autore con una vasta popolazione campione possono utilizzare i punteggi normalizzati. Gli utenti che vogliono ricavare i propri punteggi percentili normalizzati dai dati non elaborati possono confrontare i punteggi non elaborati con una popolazione campione diversa e applicare un diverso approccio alla normalizzazione.

Per normalizzare un punteggio non elaborato in un percentile per una caratteristica specifica, confronta il punteggio non elaborato con una popolazione campione per la quale sono noti la media e la deviazione standard per la caratteristica. Ad esempio, {{site.data.keyword.IBM_notm}} ha condotto studi per raccogliere dati da una vasta popolazione di utenti di Twitter. {{site.data.keyword.IBM_notm}} ha calcolato i punteggi degli utenti per ciascuna delle caratteristiche della personalità e ha quindi stabilito la media e la deviazione standard per ogni caratteristica. Per calcolare il punteggio percentile per un punteggio non elaborato dedotto dalla sua analisi del testo di input, il servizio utilizza la media e la deviazione standard derivate dalla popolazione di Twitter campione per quella caratteristica.

## Percentuali per le caratteristiche comportamentali
{: #percentages}

Se inoltri dei dati JSON i cui elementi di contenuto includono indicatori di data e ora, il servizio riporta una `percentuale` per ogni caratteristica comportamentale. Le caratteristiche comportamentali identificano la distribuzione temporale dell'input. La percentuale indica quanti oggetti di contenuto si sono verificati durante ogni giorno della settimana e ora del giorno. Ad esempio, una percentuale di `0.4561049445005` per la caratteristica comportamentale `behavior_0000` significa che circa il 46 percento degli elementi di contenuto è stato creato tra le ore di mezzanotte e 1:00 a.m.

## Punteggi per le preferenze di consumo
{: #scores}

Se specifichi `true` per il parametro di query `consumption_preferences` della richiesta, il servizio riporta le preferenze di consumo che includono un `punteggio` per ogni preferenza. Il servizio ricava il punteggio dalle caratteristiche della personalità che deduce dal testo di input. Il punteggio è un doppio che indica quanto è probabile che l'autore del testo preferisca l'oggetto. Si tratta di un'indicazione di preferenza, non una percentuale normalizzata.

Per alcune preferenze, il punteggio è uno dei seguenti tre valori:

-   `0.0`: è molto improbabile che l'autore preferisca l'oggetto. Per alcune preferenze, puoi interpretare il valore nel senso che l'autore ha un livello di interesse molto basso. 
-   `0.5`: l'autore è neutrale rispetto all'oggetto. Per alcune preferenze, il valore può significare che l'autore ha un livello medio di interesse.
-   `1.0`: è molto probabile che l'autore preferisca l'oggetto. Per alcune preferenze, il valore indica un alto livello di interesse.

Per altre preferenze, il punteggio rappresenta un valore binario. È improbabile (`0.0`) o probabile (`1.0`) che l'autore del testo di input abbia un interesse per l'oggetto o l'autore ha un livello di interesse basso o alto. In alcuni casi, il punteggio può rappresentare una semplice risposta sì o no (ad esempio, la probabilità che l'autore abbia esperienza di volontariato per cause sociali).

Per un elenco completo di tutte le preferenze per categoria e l'intervallo dei loro risultati, vedi [Preferenze di consumo](/docs/services/personality-insights/preferences.html).

## Limitazioni per l'input in arabo e coreano
{: #limitations}

Per l'input in arabo e coreano, i modelli del servizio non sono in grado di produrre risultati significativi per un sottoinsieme di caratteristiche della personalità. Per le seguenti caratteristiche, i punteggi percentili normalizzati sono sempre `0.5` e i punteggi non elaborati sono sempre la media della distribuzione originale. Il campo `significant` per ognuna di queste caratteristiche è sempre `false`. *Non* fare affidamento sui risultati per queste caratteristiche come parte del profilo della personalità dell'autore.

<table>
  <caption>Tabella 1. Caratteristiche i cui risultati non sono significativi</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      Caratteristiche
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      Risultati in arabo che<br/>non sono significativi
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      Risultati in coreano che <br/>non sono significativi
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Dimensioni Big Five
    </td>
    <td style="text-align:left; vertical-align:top">
      Stabilità emotiva
    </td>
    <td style="text-align:left; vertical-align:top">
      Nessuno
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Aspetti Big Five
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; line-height:110%; padding:0px">
          *Gradevolezza*: altruismo, cooperazione, modestia e fiducia
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Coscienziosità*: perseguimento di obiettivi e doverosità
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Estroversione*: allegria e cordialità (socievole)
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Stabilità emotiva*: rabbia (impetuoso), incline alla preoccupazione, smoderatezza
          e imbarazzo
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Apertura mentale*: spirito di avventura, immaginazione e intelletto
        </li>
      </ul>
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; padding:0px">
          *Estroversione*: desiderio di stimoli
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Esigenze
    </td>
    <td style="text-align:left; vertical-align:top">
      Ideale, libertà, amore, praticità e struttura
    </td>
    <td style="text-align:left; vertical-align:top">
      Libertà e stabilità
    </td>
  </tr>
  </tr>
    <td style="text-align:left; vertical-align:top">
      Valori
    </td>
    <td style="text-align:left; vertical-align:top">
      Auto-miglioramento
    </td>
    <td style="text-align:left; vertical-align:top">
      Conservazione
    </td>
  </tr>
</table>
