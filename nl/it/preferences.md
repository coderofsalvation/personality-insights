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

# Preferenze di consumo
{: #preferences}

Il servizio {{site.data.keyword.personalityinsightsshort}} deduce le caratteristiche della personalità di un autore per tre modelli: Big Five, Esigenze e Valori. Sulla base dei risultati ottenuti per questi modelli, il servizio può anche produrre preferenze di consumo per l'autore del testo di input. Per ottenere le preferenze di consumo, imposta il parametro di query `consumption_preferences` su `true` per una richiesta.
{: shortdesc}

Il servizio raggruppa le oltre 40 preferenze di consumo in otto categorie di alto livello. Le preferenze indicano la probabilità dell'autore a preferire prodotti, servizi e attività differenti. Ad esempio, il servizio può identificare

-   Le inclinazioni dell'autore per abbigliamento (comodità in opposizione a moda) e automobili (costo in opposizione a sicurezza).
-   Le inclinazioni dell'autore verso diversi generi di musica, film e lettura. 
-   L'atteggiamento dell'autore nei confronti dell'ambiente e del volontariato. 

Le aziende utilizzano i modelli di personalità del servizio per comprendere meglio i propri clienti e per progettare e sviluppare campagne, prodotti e servizi più personalizzati e mirati. Le preferenze di consumo rendono ancora più semplice agire in base ai risultati del servizio. Le aziende possono facilmente ottenere e rispondere a un elenco di preferenze associate alle caratteristiche dominanti di un individuo. Per ulteriori informazioni sulle possibili applicazioni delle preferenze di consumo, vedi [Casi di utilizzo](/docs/services/personality-insights?topic=personality-insights-usecases) e [Il servizio in azione](/docs/services/personality-insights?topic=personality-insights-applied).

Le seguenti sezioni elencano e descrivono le preferenze di consumo che possono essere restituite dal servizio. Per informazioni sull'interpretazione delle preferenze numeriche, vedi [Punteggi per le preferenze di consumo](/docs/services/personality-insights?topic=personality-insights-numeric#scores). Per informazioni su come {{site.data.keyword.IBM_notm}} ha sviluppato le preferenze, vedi [La scienza alla base del servizio](/docs/services/personality-insights?topic=personality-insights-science).

## Preferenze di acquisto
{: #shopping}

Le preferenze di acquisto indicano l'interesse dell'autore per diversi tipi di acquisti, la misura in cui le abitudini di acquisto dell'autore sono influenzate da diverse fonti esterne e le abitudini di spesa dell'autore. L'ID categoria e il nome sono `consumption_preferences_shopping` e `Purchasing Preferences`. La categoria include 12 preferenze.

<table>
  <caption>Tabella 1. Preferenze di acquisto</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID preferenza di consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Punteggi
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_ownership_cost</code>
    </td>
    <td style="text-align:left">
      Probabilità di essere sensibili ai costi di proprietà al momento di acquistare automobili
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_safety</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire la sicurezza al momento di acquistare automobili
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_quality</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire la qualità al momento di acquistare vestiti
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_style</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire lo stile al momento di acquistare vestiti
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_comfort</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire la comodità al momento di acquistare vestiti
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_brand_name</code>
    </td>
    <td style="text-align:left">
      Probabilità di lasciarsi influenzare dal nome del marchio al momento di acquistare prodotti
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_utility</code>
    </td>
    <td style="text-align:left">
      Probabilità di lasciarsi influenzare dall'utilità del prodotto al momento di acquistare
      prodotti
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_online_ads</code>
    </td>
    <td style="text-align:left">
      Probabilità di lasciarsi influenzare dagli annunci online al momento di acquistare prodotti
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_social_media</code>
    </td>
    <td style="text-align:left">
      Probabilità di lasciarsi influenzare dai social media al momento di acquistare
      prodotti
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_family_members</code>
    </td>
    <td style="text-align:left">
      Probabilità di lasciarsi influenzare dalla famiglia al momento di acquistare prodotti
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_spur_of_moment</code>
    </td>
    <td style="text-align:left">
      Probabilità di lanciarsi in acquisti impulsivi
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_credit_card_payment</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire l'utilizzo di carte di credito per gli acquisti
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
</table>

## Preferenze di film
{: #movie}

Le preferenze di film indicano l'interesse dell'autore per diversi tipi di film. L'ID categoria e il nome sono `consumption_preferences_movie` e `Movie Preferences`. La categoria include 10 preferenze.

<table>
  <caption>Tabella 2. Preferenze di film</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID preferenza di consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Punteggi
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_romance</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire i film romantici
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_adventure</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire i film di avventura
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_horror</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire i film horror
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_musical</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire i film musicali
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_historical</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire i film storici
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_science_fiction</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire i film di fantascienza
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_war</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire i film di guerra
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_drama</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire i film drammatici
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_action</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire i film di azione
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_documentary</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire i documentari
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
</table>

## Preferenze musicali
{: #music}

Le preferenze musicali indicano l'interesse dell'autore per diversi tipi di musica e se l'autore si diletta a suonare. L'ID categoria e il nome sono `consumption_preferences_music` e `Music Preferences`. La categoria include nove preferenze.

<table>
  <caption>Tabella 3. Preferenze musicali</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID preferenza di consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Punteggi
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rap</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire la musica rap
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_country</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire la musica country
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_r_b</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire la musica R&amp;B
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_hip_hop</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire la musica hip hop
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_live_event</code>
    </td>
    <td style="text-align:left">
      Probabilità di partecipare a eventi musicali dal vivo
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_playing</code>
    </td>
    <td style="text-align:left">
      Probabilità di avere esperienza con la musica
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_latin</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire la musica latina
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rock</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire la musica rock
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_classical</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire la musica classica
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
</table>

## Preferenze di lettura e apprendimento
{: #reading}

Le preferenze di lettura e apprendimento indicano la probabilità dell'autore di dilettarsi a leggere, la motivazione dell'autore per la lettura e i tipi di contenuti che l'autore ama leggere. L'ID categoria e il nome sono `consumption_preferences_reading` e `Reading Preferences`. La categoria include cinque preferenze.

<table>
  <caption>Tabella 4. Preferenze di lettura e apprendimento</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID preferenza di consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Punteggi
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_read_frequency</code>
    </td>
    <td style="text-align:left">
      Probabilità di leggere spesso
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_entertainment_magazines</code>
    </td>
    <td style="text-align:left">
      Probabilità di leggere riviste di intrattenimento
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_non_fiction</code>
    </td>
    <td style="text-align:left">
      Probabilità di leggere libri di saggistica
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_financial_investing</code>
    </td>
    <td style="text-align:left">
      Probabilità di leggere libri di investimenti finanziari
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_autobiographies</code>
    </td>
    <td style="text-align:left">
      Probabilità di leggere libri autobiografici
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
</table>

## Preferenze di salute e attività
{: #health}

Le preferenze di salute e attività indicano l'interesse dell'autore per i cibi sani e l'attività fisica. L'ID categoria e il nome sono `consumption_preferences_health_and_activity` e `Health & Activity Preferences`. La categoria include tre preferenze.

<table>
  <caption>Tabella 5. Preferenze di salute e attività</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID preferenza di consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Punteggi
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_eat_out</code>
    </td>
    <td style="text-align:left">
      Probabilità di mangiare fuori spesso
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_gym_membership</code>
    </td>
    <td style="text-align:left">
      Probabilità di avere un abbonamento a una palestra
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_outdoor</code>
    </td>
    <td style="text-align:left">
      Probabilità di preferire attività all'aperto
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
</table>

## Preferenze di imprenditorialità
{: #entrepreneur}

Le preferenze di imprenditorialità indicano l'interesse dell'autore ad avviare un'impresa. L'ID categoria e il nome sono `consumption_preferences_entrepreneurship` e `Entrepreneurship Preferences`. La categoria include una preferenza.

<table>
  <caption>Tabella 6. Preferenze di imprenditorialità</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID preferenza di consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Punteggi
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_start_business</code>
    </td>
    <td style="text-align:left">
      Probabilità di prendere in considerazione l'avvio di un'impresa nei prossimi anni
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
</table>

## Preferenze di interesse ambientale
{: #environment}

Le preferenze di interesse ambientale indicano l'interesse dell'autore per l'ambiente. L'ID categoria e il nome sono `consumption_preferences_environmental_concern` e `Environmental Concern Preferences`. La categoria include una preferenza.

<table>
  <caption>Tabella 7. Preferenze di interesse ambientale</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID preferenza di consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Punteggi
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_concerned_environment</code>
    </td>
    <td style="text-align:left">
      Probabilità di preoccuparsi per l'ambiente
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>0.5</code> (neutrale)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
</table>

## Preferenze di volontariato
{: #volunteer}

Le preferenze di volontariato indicano l'interesse dell'autore per il  volontariato per cause sociali. L'ID categoria e il nome sono `consumption_preferences_volunteering` e `Volunteering Preferences`. La categoria include una preferenza.

<table>
  <caption>Tabella 8. Preferenze di volontariato</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID preferenza di consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Punteggi
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_volunteer</code>
    </td>
    <td style="text-align:left">
      Probabilità di offrirsi volontario per cause sociali
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improbabilità)<br/>
      <code>1.0</code> (probabilità)
    </td>
  </tr>
</table>
