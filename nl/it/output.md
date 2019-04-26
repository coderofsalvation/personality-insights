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

# Descrizione di un profilo JSON
{: #output}

Quando utilizzi il metodo `POST /v3/profile` per analizzare il contenuto, il servizio restituisce i risultati della sua analisi come oggetto `Profile` o se specifichi `application/json` con l'intestazione `Accept` di una richiesta. L'ambito dell'output JSON dipende dai parametri che specifichi con la richiesta. Dipende anche dal fatto che il testo di input rappresenti dati con data e ora, ad esempio il testo associato a un feed Twitter.
{: shortdesc}

Le seguenti sezioni descrivono i contenuti di una risposta in formato JSON. Tutto l'output di esempio è prodotto dal file JSON campione <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Icona link esterno" title="Icona link esterno"></a> utilizzato nell'[Esercitazione introduttiva](/docs/services/personality-insights?topic=personality-insights-gettingStarted). Per informazioni sull'output CSV, vedi [Descrizione di un profilo CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV).

## Oggetto Profile
{: #outputJSON}

L'oggetto `Profile` è l'oggetto JSON di livello superiore restituito dal servizio. L'oggetto include i seguenti campi:

-   `word_count` (numero intero) fornisce il numero di parole del contenuto di input utilizzate per generare il profilo. Questa figura può essere inferiore al numero di parole nell'input se la richiesta ha inoltrato una grande quantità di contenuto. Se il numero di parole non riesce a soddisfare una soglia minima, l'output include anche un campo `word_count_message` che fornisce ulteriori indicazioni. 
-   `processed language` (stringa) descrive il modello di lingua utilizzato dal servizio per elaborare l'input: `ar` (Arabo), `en` (Inglese), `es` (Spagnolo), `ja` (Giapponese) o `ko` (Coreano).
-   `personality` è un array ricorsivo di oggetti `Trait` che descrive le dimensioni e gli oggetti Big Five dedotti dal testo di input. 
-   `needs` è un array di oggetti `Trait` che descrive le Esigenze dedotte dal testo di input. 
-   `values` è un array di oggetti `Trait` che descrive i Valori dedotti dal testo di input. 
-   `behavior` è un array di oggetti `Behavior` che descrive la distribuzione dei contenuti nei giorni della settimana e nelle ore del giorno. Il servizio restituisce il campo solo per l'input JSON che ha un indicatore di data e ora.
-   `consumption_preferences` è un array di oggetti `ConsumptionPreferencesCategory` che fornisce risultati per ogni categoria delle preferenze di consumo. Gli elementi dell'array forniscono informazioni per le singole preferenze della categoria. Il servizio restituisce il campo solo se il parametro di query `consumption_preferences` della richiesta è impostato su `true`.
-   `warnings` è un array di oggetti `Warning` che fornisce i messaggi relativi al testo di input. L'array è vuoto se l'input non genera avvertenze.

### Risposta di esempio
{: #JSONExample}

Il seguente output di esempio mostra la struttura di alto livello di un oggetto `Profile`. L'output include sempre i campi `personality`, `needs` e `values`. Se l'input è un JSON con data e ora, la risposta include il campo `behavior`. E se la richiesta richiede anche preferenze di consumo, la risposta include il campo `consumption_preferences`. In questo esempio, l'input non genera avvertenze.

```javascript
{
  "word_count": 15223,
  "processed_language": "en",
  "personality": [
     . . .
  ],
  "needs": [
     . . .
  ],
  "values": [
     . . .
  ],
  "behavior": [
     . . .
  ],
  "consumption_preferences": [
     . . .
   ],
  "warnings": []
}
```
{: codeblock}

## Output delle caratteristiche della personalità
{: #traitJSON}

L'oggetto `Profile` include sempre i campi `personality`, `needs` e `values` per tutti i tipi di input. Ognuno di questi campi contiene un array di oggetti `Trait` che descrive le caratteristiche della personalità per gli attributi di quel tipo di caratteristica. Per le caratteristiche di Esigenze e Valori, l'array ha un unico livello che descrive le caratteristiche. Per le caratteristiche Big Five, un array di livello superiore descrive le dimensioni e gli array di secondo livello descrivono gli aspetti di ciascuna dimensione.

-   `trait_id` (stringa) è l'ID univoco della caratteristica a cui si riferiscono i risultati:
    -   `big5_{characteristic}` per le dimensioni della personalità Big Five
    -   `facet_{characteristic}` per gli aspetti della personalità Big Five
    -   `need_{characteristic}` per le Esigenze
    -   `value_{characteristic}` per i Valori
-   `name` (stringa) è il nome visibile all'utente della caratteristica.
-   `category` (stringa) è la categoria della caratteristica:
    -   `personality` per le caratteristiche della personalità Big Five
    -   `needs` per le Esigenze
    -   `values` per i Valori
-   `percentile` (doppio) è il punteggio percentile normalizzato per la caratteristica. Per ulteriori informazioni, vedi [Percentili per le caratteristiche della personalità](/docs/services/personality-insights?topic=personality-insights-numeric#percentiles).
-   `raw_score` (doppio) è il punteggio non elaborato per la caratteristica. Il campo viene restituito solo se richiedi i punteggi non elaborati impostando il parametro di query `raw_scores` su `true`. Per ulteriori informazioni, vedi [Punteggi non elaborati per le caratteristiche della personalità](/docs/services/personality-insights?topic=personality-insights-numeric#rawScores-numeric).
-   `significant` (booleano) indica se la caratteristica è significativa per la lingua di input. Il campo è sempre `true` per tutte le caratteristiche dell'input in inglese, spagnolo e giapponese. Il campo è `false` per il sottoinsieme di caratteristiche dell'input in arabo e coreano per cui i modelli del servizio non sono in grado di generare risultati significativi. Per ulteriori informazioni, vedi [Limitazioni per l'input in arabo e coreano](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).
-   `children` è un array di oggetti `Trait` che fornisce risultati più dettagliati per gli aspetti di ogni dimensione Big Five dedotta dal testo di input. L'array viene restituito solo per le dimensioni Big Five.

### Risposta di esempio
{: #traitExample}

Il seguente output di esempio mostra frammenti dell'output per le caratteristiche di Big Five, Esigenze e Valori. Come descritto, solo le caratteristiche Big Five hanno un array di `children` per i loro rispettivi aspetti.

```javascript
{
  . . .
  "personality": [
    {
      "trait_id": "big5_openness",
      "name": "Openness",
      "category": "personality",
      "percentile": 0.8011555009553,
      "raw_score": 0.77565404255038,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_adventurousness",
          "name": "Adventurousness",
          "category": "personality",
          "percentile": 0.89755869047319,
          "raw_score": 0.54990704031219,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_conscientiousness",
      "name": "Conscientiousness",
      "category": "personality",
      "percentile": 0.81001753184176,
      "raw_score": 0.66899984888815,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_achievement_striving",
          "name": "Achievement striving",
          "category": "personality",
          "percentile": 0.84613299226628,
          "raw_score": 0.74240118454888,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_extraversion",
      "name": "Extraversion",
      "category": "personality",
      "percentile": 0.64980796071382,
      "raw_score": 0.56817738781166,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_activity_level",
          "name": "Activity level",
          "category": "personality",
          "percentile": 0.88220584913965,
          "raw_score": 0.60106995926143,
          "significant": true
        },
      ]
    },
    {
      "trait_id": "big5_agreeableness",
      "name": "Agreeableness",
      "category": "personality",
      "percentile": 0.94786124793821,
      "raw_score": 0.80677815631809,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_altruism",
          "name": "Altruism",
          "category": "personality",
          "percentile": 0.99241983824205,
          "raw_score": 0.79028406290747,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_neuroticism",
      "name": "Emotional range",
      "category": "personality",
      "percentile": 0.5008224041628,
      "raw_score": 0.46748200007024,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_anger",
          "name": "Fiery",
          "category": "personality",
          "percentile": 0.17640022058508,
          "raw_score": 0.48490315691802,
          "significant": true
        },
        . . .
      ]
    }
  ],
  "needs": [
    {
      "trait_id": "need_challenge",
      "name": "Challenge",
      "category": "needs",
      "percentile": 0.67362332054511,
      "raw_score": 0.75196348037675,
      "significant": true
    },
    . . .
  ],
  "values": [
    {
      "trait_id": "value_conservation",
      "name": "Conservation",
      "category": "values",
      "percentile": 0.89268222856139,
      "raw_score": 0.72135308187423,
      "significant": true
    },
    . . .
  ],
  . . .
}
```
{: codeblock}

## Output comportamentale
{: #behaviorJSON}

Se l'input per il servizio è un JSON con indicatori di data e ora per i singoli elementi di contenuto, l'oggetto `Profile` include un campo `behavior`. Il campo include un oggetto `Behavior` per ogni giorno della settimana e ora del giorno.

-   `trait_id` (stringa) è l'ID univoco della caratteristica a cui si riferiscono i risultati:
    -   `behavior_{day}` per i giorni della settimana (ad esempio, `behavior_sunday`).
    -   `behavior_{hour}` per le ore del giorno (ad esempio, `behavior_0000`).
-   `name` (stringa) è il nome visibile all'utente della caratteristica.
-   `category` (stringa) è la categoria della caratteristica, che è sempre `behavior`.
-   `percentage` (doppio) è la percentuale di elementi di contenuto che si sono verificati durante quel giorno della settimana o quell'ora del giorno. Per ulteriori informazioni, vedi [Percentuali per le caratteristiche comportamentali](/docs/services/personality-insights?topic=personality-insights-numeric#percentages).

### Risposta di esempio
{: #behaviorExample}

Il seguente output mostra frammenti dell'output comportamentale per le caratteristiche temporali.

```javascript
{
  . . .
  "behavior": [
    {
      "trait_id": "behavior_sunday",
      "name": "Sunday",
      "category": "behavior",
      "percentage": 0.21392532795156
    },
    {
      "trait_id": "behavior_monday",
      "name": "Monday",
      "category": "behavior",
      "percentage": 0.42583249243189
    },
    . . .
    {
      "trait_id": "behavior_saturday",
      "name": "Saturday",
      "category": "behavior",
      "percentage": 0.077699293642785
    },
    {
      "trait_id": "behavior_0000",
      "name": "0:00 am",
      "category": "behavior",
      "percentage": 0.4561049445005
    },
    {
      "trait_id": "behavior_0100",
      "name": "1:00 am",
      "category": "behavior",
      "percentage": 0.12209889001009
    },
    . . .
    {
      "trait_id": "behavior_2300",
      "name": "11:00 pm",
      "category": "behavior",
      "percentage": 0.12310797174571
    }
  ],
  . . .
}
```
{: codeblock}

## Output delle preferenze di consumo
{: #preferenceJSON}

Se il parametro di query `consumption_preferences` è impostato su `true`, l'oggetto `Profile` include un campo `consumption_preferences`. Il campo include un oggetto `ConsumptionPreferencesCategory` per ogni categoria di preferenze.

-   `consumption_preference_category_id` (stringa) è l'ID univoco della categoria delle preferenze di consumo a cui si riferiscono i risultati in formato `consumption_preferences_{category}`.
-   `name` (stringa) è il nome visibile all'utente della categoria delle preferenze di consumo.
-   `consumption_preferences` è un array di oggetti `ConsumptionPreferences` che fornisce i risultati per le singole preferenze della categoria.

Ogni singola preferenza per una categoria è descritta tramite un oggetto `ConsumptionPreferences`. Alcune categorie hanno solo un'unica preferenza; altre categorie ne hanno molte di più. 

-   `consumption_preference_id` (stringa) è l'ID univoco della preferenza di consumo a cui si riferiscono i risultati in formato `consumption_preferences_{preference}`.
-   `name` (stringa) è il nome visibile all'utente della preferenza di consumo.
-   `score` (doppio) è un punteggio che indica la probabilità dell'autore di preferire l'elemento. Per ulteriori informazioni, vedi [Punteggi per le preferenze di consumo](/docs/services/personality-insights?topic=personality-insights-numeric#scores).

### Risposta di esempio
{: #preferenceExample}

Il seguente output mostra frammenti dell'output per le preferenze di consumo.

```javascript
{
  . . .
  "consumption_preferences": [
    {
      "consumption_preference_category_id": "consumption_preferences_shopping",
      "name": "Purchasing Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_automobile_ownership_cost",
          "name": "Likely to be sensitive to ownership cost when buying automobiles",
          "score": 0
        },
        . . .
      ]
    },
    {
      "consumption_preference_category_id": "consumption_preferences_health_and_activity",
      "name": "Health & Activity Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_eat_out",
          "name": "Likely to eat out frequently",
          "score": 1
        },
        . . .
      ]
    },
    . . .
    {
      "consumption_preference_category_id": "consumption_preferences_volunteering",
      "name": "Volunteering Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_volunteer",
          "name": "Likely to volunteer for social causes",
          "score": 0
        }
      ]
    }
  ],
  . . .
}
```
{: codeblock}
