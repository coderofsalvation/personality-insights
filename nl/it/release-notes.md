---

copyright:
  years: 2015, 2017
lastupdated: "2017-11-28"

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

# Note sulla release
{: #release-notes}

Le seguenti sezioni documentano le nuove funzioni e modifiche che sono state incluse per ogni release del servizio {{site.data.keyword.personalityinsightsshort}}. Salvo diversa indicazione, tutte le modifiche sono compatibili con le versioni precedenti e sono automaticamente e trasparentemente disponibili per tutte le applicazioni nuove ed esistenti.
{: shortdesc}

> **Nota:** le note sulla release documentano la *versione del servizio* e la *versione dell'interfaccia* per tutti gli aggiornamenti recenti. Specifica la *versione dell'interfaccia* con il parametro di query `version` per utilizzare le nuove funzioni e funzionalità rese disponibili con l'aggiornamento. Il servizio restituisce entrambe le versioni con l'intestazione di risposta `X-Service-Api-Version`.

## 13 ottobre 2017
{: #October2017}

**Versione del servizio:** `3.4.0`<br/> **Versione dell'interfaccia:** `2017-10-13`

-   L'oggetto `Trait` di un profilo di personalità include ora un campo `significant` aggiuntivo. Un oggetto `Trait` separato riporta i risultati di ogni dimensione e aspetto Big Five, Necessità e Valore. Il campo `significant` di ogni istanza dell'oggetto identifica se i risultati per quella caratteristica sono significativi per la lingua di input (`Content-Language`) della richiesta:

    -   Per inglese, spagnolo e giapponese, il campo è sempre `true` per tutte le caratteristiche della personalità.
    -   Per arabo e coreano, il campo è `true` per la maggior parte delle caratteristiche della personalità ma è `false` per quelle per cui i modelli del servizio non sono in grado di produrre risultati significativi. Il campo è `false` per un insieme costante di caratteristiche; per un elenco completo, vedi [Limitazioni per l'input in arabo e coreano](/docs/services/personality-insights/numeric.html#limitations). Non fare affidamento sui risultati di qualsiasi caratteristica per cui il campo è `false`.

    Per informazioni sul contenuto della risposta JSON del servizio, vedi [Descrizione di un profilo JSON](/docs/services/personality-insights/output.html).
-   L'output CSV include ora anche delle colonne aggiuntive le cui intestazioni sono denominate `*_significant`. Ogni colonna fornisce un valore booleano per indicare se una caratteristica è significativa. Per informazioni sul contenuto della risposta CSV del servizio, vedi [Descrizione di un profilo CSV](/docs/services/personality-insights/output-csv.html).
-   La versione dell'interfaccia specificata con il parametro `version` è `2017-10-13` per utilizzare la versione più recente dell'interfaccia.

## 18 settembre 2017
{: #September2017}

**Versione del servizio:** `3.3.0`<br/> **Versione dell'interfaccia:** `2016-10-19`

Il servizio ora supporta il contenuto di input in coreano (`ko`). Per informazioni sull'errore medio assoluto (MAE, Mean Absolute Error) e sulla correlazione media per l'input in coreano, vedi [Valori medi di MAE e correlazione per ogni lingua](/docs/services/personality-insights/science.html#precisePerLanguage).

I modelli del servizio non sono in grado di produrre percentili e punteggi non elaborati significativi per alcune caratteristiche della personalità dell'input in coreano. Per ulteriori informazioni sui risultati di queste caratteristiche, vedi [Limitazioni per l'input in arabo e coreano](/docs/services/personality-insights/numeric.html#limitations).

## 10 aprile 2017
{: #April2017}

**Versione del servizio:** `3.1.7`<br/> **Versione dell'interfaccia:** `2016-10-19`

-   Il servizio ha cambiato il modo in cui gestisce le richieste con grandi quantità di contenuto di input. Il servizio accetta un massimo di 20 MB di contenuto. Tuttavia, con i modelli basati su *GloVe*, i livelli di precisione si riducono a circa 3000 parole di input. Questo è diverso dai vecchi modelli, dove più testo produceva maggiore precisione. In generale, il servizio non ha più bisogno di tanto contenuto per produrre un profilo accurato. Ma il contenuto aggiuntivo richiede ulteriore tempo di elaborazione, che può causare il timeout di una richiesta prima del suo completamento.

    Pertanto, il servizio ora estrae e utilizza solo i primi 250 KB di contenuto, senza contare i markup HTML o JSON, dalle richieste di grandi dimensioni. Questa cifra non è associata a un numero esatto di parole, che varia in base alla lingua e alla natura del testo. In inglese, ad esempio, la lunghezza media delle parole è compresa tra quattro e cinque caratteri, quindi questa cifra fornisce circa 50.000 parole, ovvero almeno 15 volte più parole di quelle richieste dal servizio. Il campo `word_count` del JSON di risposta indica il numero di parole effettivamente utilizzate dal servizio per una richiesta, che può essere inferiore al numero di parole nell'input.

    Poiché basa ancora un profilo su molte più parole di quelle strettamente necessarie per la massima precisione, il servizio produce un profilo altrettanto accurato come in passato. Tuttavia, il servizio risponde molto più velocemente di prima. Per le richieste per le quali utilizza solo una parte del contenuto di input, il servizio restituisce il seguente messaggio di avvertenza `CONTENT_TRUNCATED` per rendere l'utente consapevole del fatto:

    `For maximum accuracy while also optimizing processing time, only the first 250KB of input text (excluding markup) was analyzed. Accuracy levels off at approximately 3K words so this did not affect the accuracy of the profile.`

    Per ulteriori informazioni, vedi [Immissione di input sufficiente](/docs/services/personality-insights/input.html#sufficient).
-   Il servizio è stato aggiornato con piccole correzioni di sicurezza.

## Release precedenti
{: #older}

-   [1 marzo 2017](#March2017)
-   [20 febbraio 2017](#February2017b)
-   [13 febbraio 2017](#February2017)
-   [13 gennaio 2017](#January2017)
-   [15 dicembre 2016](#December2016)
-   [15 novembre 2016](#November2016)
-   [20 ottobre 2016](#October2016b)
-   [12 ottobre 2016](#October2016a)
-   [31 agosto 2016](#August2016)
-   [14 luglio 2016](#July2016b)
-   [1 luglio 2016](#July2016a)
-   [7 giugno 2016](#June2016b)
-   [1 giugno 2016](#June2016a)
-   [17 maggio 2016](#May2016)
-   [18 marzo 2016](#March2016)
-   [9 luglio 2015](#July2015)
-   [23 febbraio 2015](#February2015)

### 1 marzo 2017
{: #March2017}

**Versione del servizio:** `3.1.6`<br/> **Versione dell'interfaccia:** `2016-10-19`

Il servizio {{site.data.keyword.personalityinsightsshort}} è stato aggiornato con piccoli miglioramenti alla registrazione.

### 20 febbraio 2017
{: #February2017b}

**Versione del servizio:** `3.1.5.1`<br/> **Versione dell'interfaccia:** `2016-10-19`

Il servizio Personality Insights è stato aggiornato con piccole correzioni di errori e di sicurezza e per migliorare la misurazione delle chiamate API.

### 13 febbraio 2017
{: #February2017}

**Versione del servizio:** `3.1.4`<br/> **Versione dell'interfaccia:** `2016-10-19`

-   L'elenco delle preferenze di consumo è stata perfezionato per includere solo quelle più importanti per comprendere le abitudini di vita dominanti di un individuo e le caratteristiche dei consumatori. L'elenco delle preferenze di consumo è stato ridotto da 51 a 42; le restanti preferenze esprimono la probabilità dell'autore di preferire prodotti, servizi e attività differenti in modo più conciso, rendendo ancora più semplice agire in base ai risultati. Il servizio non restituisce più le seguenti nove preferenze di consumo. Per ulteriori informazioni sulle preferenze rimanenti, vedi [Preferenze di consumo](/docs/services/personality-insights/preferences.html).

    <table>
      <caption>Tabella 1. Modifiche alle preferenze di consumo</caption>
      <tr>
        <th style="text-align:left">Categoria</th>
        <th style="text-align:left">Preferenze di consumo rimosse</th>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_shopping</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_automobile_resale_value</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_reading</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_read_motive_enjoyment</code>
            <code>consumption_preferences_read_motive_information</code>
            <code>consumption_preferences_read_motive_mandatory</code>
            <code>consumption_preferences_read_motive_relaxation</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_health_and_activity</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_adventurous_sports</code>
            <code>consumption_preferences_fast_food_frequency</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_volunteering</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_volunteering_time</code>
            <code>consumption_preferences_volunteer_learning</code>
          </p>
        </td>
      </tr>
    </table>

-   *Per l'input in arabo*, le informazioni sull'errore medio assoluto (MAE, Mean Absolute Error) e sulla correlazione media sono ora disponibili in [Valori medi di MAE e correlazione per ogni lingua](/docs/services/personality-insights/science.html#precisePerLanguage). Inoltre, i modelli del servizio non sono in grado di produrre percentili e punteggi non elaborati significativi per una serie di caratteristiche della personalità. Per ulteriori informazioni sui risultati di queste caratteristiche, vedi [Limitazioni per l'input in arabo e coreano](/docs/services/personality-insights/numeric.html#limitations).

### 13 gennaio 2017
{: #January2017}

**Versione del servizio:** `3.1.2.1`<br/> **Versione dell'interfaccia:** `2016-10-19`

Il servizio Personality Insights è stato aggiornato con alcune piccole correzioni di errori.

### 15 dicembre 2016
{: #December2016}

**Versione del servizio:** `3.1.1`<br/> **Versione dell'interfaccia:** `2016-10-19`

Per il testo di input in arabo, il servizio {{site.data.keyword.personalityinsightsshort}} utilizza ora la tecnica del word embedding open-source chiamata *GloVe* per sviluppare un profilo di personalità. Il servizio non utilizza più il dizionario psicolinguistico LIWC (Linguistic Inquiry and Word Count) per alcuna lingua. Per ulteriori informazioni su come il servizio sviluppa un ritratto della personalità, vedi [Modalità di deduzione delle caratteristiche della personalità](/docs/services/personality-insights/science.html#researchInfer).

### 15 novembre 2016
{: #November2016}

**Versione del servizio:** `3.1.0`<br/> **Versione dell'interfaccia:** `2016-10-19`

-   Per il testo di input in giapponese, il servizio {{site.data.keyword.personalityinsightsshort}} utilizza ora la tecnica del word embedding open-source chiamata *GloVe* per sviluppare un profilo di personalità; il servizio non utilizza più il dizionario psicolinguistico LIWC (Linguistic Inquiry and Word Count) per l'input in giapponese. Per ulteriori informazioni, vedi [Modalità di deduzione delle caratteristiche della personalità](/docs/services/personality-insights/science.html#researchInfer).
-   I campi `name` degli oggetti `ConsumptionPreferencesCategory` e `ConsumptionPreferences` vengono ora restituiti con le stringhe localizzate nella lingua specificata con l'intestazione di richiesta `Accept-Language`.
-   L'aggiornamento include piccole correzioni di errori.

### 20 ottobre 2016
{: #October2016b}

**Versione del servizio:** `3.0.0`<br/> **Versione dell'interfaccia:** `2016-10-19`

Il servizio {{site.data.keyword.personalityinsightsshort}} e la sua API sono stati aggiornati in modo significativo. L'API è stata incrementata dalla versione 2 alla versione 3 e offre nuove funzioni. Le sezioni rimanenti di questa nota sulla release descrivono le modifiche in dettaglio.

La versione 3 non è retrocompatibile con la versione 2. Si consiglia di migrare alla versione 3 per sfruttare le nuove funzioni e modifiche. La migrazione alla versione 3 consiste solo nell'aggiornamento e nella ridistribuzione delle tue applicazioni per utilizzare le modifiche descritte in queste note sulla release per la nuova versione. Non devi creare una nuova istanza del servizio in {{site.data.keyword.Bluemix_notm}}, dovrai solo richiamare l'API `v3`.

> **Nota:** la versione 2 dell'API {{site.data.keyword.personalityinsightsshort}} verrà rimossa dal servizio in un prossimo futuro. Si consiglia vivamente di migrare alla versione 3 il prima possibile. Per adesso, puoi accedere alla documentazione di riferimento per la versione 2 in [Riferimento API per v2 ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/watson/developercloud/personality-insights/api/v2/){: new_window}; puoi anche accedere allo strumento interattivo per testare le chiamate alla versione 2 e visualizzare le risposte in tempo reale dal servizio in [Explorer API per v2 ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v2){: new_window}.

#### Ulteriori informazioni sulla versione 3

Questa documentazione descrive ora la versione 3 dell'API {{site.data.keyword.personalityinsightsshort}}. Le seguenti sezioni riepilogano le modifiche per la nuova versione dell'interfaccia:

-   Per informazioni sulla chiamata del metodo `/v3/profile`, vedi [Richiesta di un profilo](/docs/services/personality-insights/input.html).
-   Per informazioni sulla risposta del metodo `/v3/profile`, vedi [Descrizione di un profilo JSON](/docs/services/personality-insights/output.html) e [Descrizione di un profilo CSV](/docs/services/personality-insights/output-csv.html).
-   Per i dettagli completi sull'interfaccia della versione 3, vedi il [Riferimento API ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

#### Modifiche ai parametri del metodo <code>/v3/profile</code>

I parametri del metodo `/v3/profile` sono stati modificati come segue:

-   L'API fornisce ora un parametro di query facoltativo denominato `consumption_preferences`. Il parametro accetta un valore booleano che indica se le informazioni dedotte sulle preferenze di consumo devono essere restituite con i risultati. Per impostazione predefinita, le informazioni non sono incluse nella risposta. Per ulteriori informazioni, vedi [Nuova funzione di preferenze di consumo](#cp).
-   L'API include ora un parametro di query obbligatorio denominato `version`. Il parametro accetta una stringa che identifica la versione richiesta dell'API e il formato della risposta come data nella forma `YYYY-MM-DD`; ad esempio, specifica `2016-10-19` per 19 ottobre 2016. Questo parametro consente al servizio di aggiornare la propria API o il formato della risposta per le nuove versioni senza interrompere i client esistenti. La stringa iniziale per la versione 3 dell'API è `2016-10-19`.

    La data che specifichi non deve necessariamente corrispondere a una versione del servizio; il servizio utilizza la versione che rientra nella data da te fornita. Se specifichi una data precedente alla data di rilascio della versione 3, il servizio utilizza la versione 3 dell'API. Se specifichi una data futura o comunque successiva alla versione più recente, il servizio utilizza l'ultima versione.
-   Il nome del parametro di query `include_raw` è ora `raw_scores`.
-   Il nome del parametro di query `headers` è ora `csv_headers`.

#### Nuova funzione di preferenze di consumo
{: #cp}

La funzione di preferenze di consumo fornisce un'indicazione della tendenza dell'autore a mostrare diverse tendenze di consumo. Quando passi il parametro di query `consumption_preferences` con il valore `true` al metodo `/v3/profile`, il servizio restituisce i seguenti risultati aggiuntivi con l'oggetto `Profile`:

-   Un campo `consumption_preferences` che fornisce un array di oggetti `ConsumptionPreferencesCategory`.
-   Ogni oggetto `ConsumptionPreferencesCategory` include i seguenti campi:
    -   `consumption_preference_category_id`: l'ID di una delle categorie delle preferenze di consumo
    -   `name`: il nome visibile all'utente della categoria.
    -   `consumption_preferences`: un array di oggetti `ConsumptionPreferences` che fornisce i risultati dedotti dal testo di input per le singole preferenze della categoria. 
-   Ogni oggetto `ConsumptionPreferences` include i seguenti campi:
    -   `consumption_preference_id`: l'ID di una delle preferenze di consumo
    -   `name`: il nome visibile all'utente della preferenza di consumo.
    -   `score`: il punteggio per la preferenza di consumo. Per molte preferenze, `0.0` indica improbabilità, `0.5` indica neutralità e `1.0` indica probabilità. I punteggi per alcune preferenze sono binari e non consentono un valore neutro. Il punteggio è un'indicazione di preferenza in base ai risultati dedotti dal testo di input, non un percentile normalizzato.

Per ulteriori informazioni sulle preferenze di consumo, vedi [Preferenze di consumo](/docs/services/personality-insights/preferences.html).

> **Nota:** attualmente il campo `name` per entrambi gli oggetti delle preferenze di consumo viene sempre restituito in inglese, indipendentemente dalla lingua specificata con l'intestazione di richiesta `Accept-Language`.

#### Modifiche a oggetti e campi JSON

Gli oggetti di input e output JSON e i relativi campi sono stati semplificati e chiarificati come segue:

-   Dagli oggetti `ContentItem` JSON che puoi passare al metodo `/v3/profile` con una richiesta sono stati rimossi i seguenti campi:
    -   `userid`
    -   `sourceid`
    -   `charset` (già obsoleto)

    Puoi passare questi oggetti nel corpo di una richiesta JSON sotto forma di elementi dell'array `contentItems` dell'oggetto `Content`.
-   Nell'oggetto `Profile` JSON restituito dal metodo `/v3/profile` sono stati modificati i seguenti campi:
    -   I seguenti campi sono stati rimossi:
        -   `id`
        -   `source`
    - Il campo `tree` è stato rimosso ed è stato sostituito da quattro nuovi campi:
        -   `personality` per le caratteristiche della personalità Big Five.
        -   `needs` per le caratteristiche delle Esigenze. 
        -   `values` per le caratteristiche dei Valori.
        -   `behavior` per i risultati temporali sulla distribuzione dei contenuti nei giorni della settimana e nelle ore del giorno. Questo campo viene restituito solo per l'input JSON che ha un indicatore di data e ora.

    Questa modifica sposta efficacemente i risultati a un livello superiore nell'oggetto `Profile` JSON, eliminando un livello di ricorsione.
    -   Il nome del campo `processed_lang` è ora `processed_language`.
-   Negli oggetti `Trait` JSON restituiti dal metodo `/v3/profile` sono stati rinominati i seguenti campi:
    -   Il nome del campo `id` dell'oggetto `Trait` JSON è ora `trait_id`.
    -   Il nome del campo `percentage` dell'oggetto `Trait` JSOn è ora `percentile`.
-   Negli oggetti `Trait` JSON restituiti dal metodo `/v3/profile` sono stati rimossi i seguenti campi:
    -   `sampling_error`
    -   `raw_sampling_error`

    Il servizio ora riporta un errore medio assoluto (MAE) che qualifica la precisione dei suoi risultati. Per ulteriori informazioni sul MAE per le diverse quantità di testo di input, vedi [Immissione di input sufficiente](/docs/services/personality-insights/input.html#sufficient).
-   Gli oggetti `Trait` JSON vengono ancora restituiti per i campi `personality`, `needs` e `values` dell'oggetto `Profile`. Ma il campo `behavior` restituisce un array di oggetti JSON denominato `Behavior` che hanno i seguenti campi:
    -   `trait_id`
    -   `name`
    -   `category`
    -   `percentage`

    Inoltre, le informazioni comportamentali non vengono più restituite come una struttura ad albero di valori. L'output consiste in un singolo array che elenca tutte le caratteristiche temporali (giorno della settimana e ora del giorno).
-   Il nome del campo `id` dell'oggetto `Warnings` JSON che può essere restituito dal metodo `/v3/profile` è ora `warnings_id`.

#### Modifiche agli ID JSON
{: #ids}

Gli ID JSON che il servizio restituisce per il campo `trait_id` (precedentemente `id`) dell'oggetto `Trait` e del nuovo oggetto `Behavior` sono stati modificati come segue:

-   Gli ID per le dimensioni Big Five iniziano ora con la stringa `big5_`.
-   Gli ID per gli aspetti Big Five iniziano ora con la stringa `facet_`.
-   Gli ID per le Esigenze iniziano ora con la stringa `need_`.
-   Gli ID per i Valori iniziano ora con la stringa `value_`.
-   Gli ID per tutte le caratteristiche temporali iniziano ora con la stringa `behavior_`.
-   Gli ID per le caratteristiche temporali relative all'ora del giorno utilizzano ora un formato di 24 ore a quattro cifre (ad esempio, `behavior_0000`) anziché il formato di 12 ore (ad esempio, `0:00 am`).
-   Tutti i caratteri sono ora in minuscolo.
-   Gli spazi e i trattini sono ora caratteri di sottolineatura. 

#### Modifiche alle intestazioni CSV
{: #headers}

Le intestazioni di colonna facoltative che il servizio può restituire per l'output CSV sono state modificate come segue:

-   Tutte le modifiche descritte per il `trait_id` dell'output JSON si applicano anche alle intestazioni CSV.
-   Le intestazioni dei punteggi non elaborati per le dimensioni Big Five iniziano ora con la stringa `big5_`.
-   Le intestazioni dei punteggi non elaborati per gli aspetti Big Five iniziano ora con la stringa `facet_`.
-   Le intestazioni dei punteggi non elaborati per le Esigenze iniziano ora con la stringa `need_`.
-   Le intestazioni dei punteggi non elaborati per i Valori iniziano ora con la stringa `value_`.
-   L'intestazione per la colonna della lingua elaborata è ora `processed_language` invece di `processed_lang`.
-   Le colonne `user` e `source_id` non vengono più restituite.
-   Tutti i caratteri sono ora in minuscolo.
-   Gli spazi e i trattini sono ora caratteri di sottolineatura. 

#### Rimozione del metodo <code>visualize</code>

La versione 2 dell'API del servizio includeva un metodo `visualize` obsoleto utilizzato in una release precedente per visualizzare i risultati di una chiamata al metodo `/v3/profile`. Il metodo `visualize` è stato rimosso dall'API del servizio. Il servizio continua a fornire una raccolta di file JavaScript che consentono la visualizzazione grafica di un profilo; per ulteriori informazioni, vedi [Visualizzazione di un profilo](/docs/services/personality-insights/developer-overview.html#visualize).

### 12 ottobre 2016
{: #October2016a}

Per il testo di input in spagnolo, il servizio {{site.data.keyword.personalityinsightsshort}} utilizza ora la tecnica del word embedding open-source chiamata *GloVe* per sviluppare un profilo di personalità; il servizio non utilizza più il dizionario psicolinguistico LIWC (Linguistic Inquiry and Word Count) per l'input in spagnolo. Il servizio ha iniziato a utilizzare il nuovo modello per il testo di input in inglese il 31 agosto; applicherà il nuovo modello alle restanti lingue di input nel prossimo futuro. Per ulteriori informazioni sul nuovo modello, vedi [Modalità di deduzione delle caratteristiche della personalità](/docs/services/personality-insights/science.html#researchInfer).

### 31 agosto 2016
{: #August2016}

Il servizio {{site.data.keyword.personalityinsightsshort}} utilizza ora un tecnica di word embedding open-source chiamata *GloVe* per sviluppare un profilo di personalità; per ulteriori informazioni, vedi [Modalità di deduzione delle caratteristiche della personalità](/docs/services/personality-insights/science.html#researchInfer). Al momento, il servizio utilizza il nuovo approccio solo per il testo di input in inglese. Per le altre lingue, il servizio continua ad utilizzare il dizionario psicolinguistico LIWC (Linguistic Inquiry and Word Count). Le versioni future del servizio utilizzeranno l'approccio open-vocabulary per tutte le lingue.

Per il nuovo modello utilizzato per l'input in inglese, il servizio riporta l'errore medio assoluto (MAE) dei risultati per il suo modello addestrato. Per informazioni su come cambia il MAE con diverse quantità di testo di input, vedi [Immissione di input sufficiente](/docs/services/personality-insights/input.html#sufficient). Le versioni future del servizio riporteranno il MAE per i modelli non inglesi e ti consiglieranno di utilizzarlo, al posto degli errori di campionamento, per determinare in che modo la precisione del servizio cambia in base alla quantità di testo di input fornita.

### 14 luglio 2016
{: #July2016b}

-   Per l'input in arabo, il servizio può ora troncare la quantità di testo di input per motivi di prestazioni. Ad una certa soglia, l'accuratezza dei risultati per l'arabo non migliora con più parole. Se il servizio tronca il testo di input in arabo, restituisce un'avvertenza `PARTIAL_TEXT_USED` con il seguente messaggio:

    `The text provided to compute the profile was trimmed for performance reasons. This action does not affect the accuracy of the output, as not all of the input text was required.`
-   L'aggiornamento include ulteriori correzioni di errori e miglioramenti interni.

### 1 luglio 2016
{: #July2016a}

-   I piani dei prezzi per il servizio sono stati modificati per offrire prezzi più bassi per gli utenti {{site.data.keyword.personalityinsightsshort}}. Per ulteriori informazioni, vedi il [Servizio {{site.data.keyword.personalityinsightsshort}} nel catalogo {{site.data.keyword.Bluemix_short}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://console.ng.bluemix.net/catalog/services/personality-insights/){: new_window}.
-   L'elenco delle lingue supportate per la risposta che puoi specificare con l'intestazione `Accept-Language` adesso include le seguenti:
    -   `ar` (Arabo)
    -   `de` (Tedesco)
    -   `en` (Inglese, impostazione predefinita)
    -   `es` (Spagnolo)
    -   `fr` (Francese)
    -   `it` (Italiano)
    -   `ja` (Giapponese)
    -   `ko` (Coreano)
    -   `pt-br` (Portoghese brasiliano)
    -   `zh-cn` (Cinese semplificato)
    -   `zh-tw` (Cinese tradizionale)

    Per ulteriori informazioni, vedi [Specifica delle lingue di richiesta e di risposta](/docs/services/personality-insights/input.html#languages).
-   Il metodo `/v2/profile` può ora restituire i seguenti codici di stato HTTP:
    -   429 *Too Many Requests*: il servizio sta elaborando troppe richieste per la lingua del contenuto. Attendi qualche secondo e ripeti la richiesta. Se stai inviando molte richieste per la lingua, valuta la possibilità di limitare la frequenza con cui invii le richieste.
    -   504 *Gateway Timeout*: la richiesta è scaduta o ha impiegato troppo tempo per l'elaborazione. Attendi qualche secondo e ripeti la richiesta. Se l'input conteneva un numero elevato di parole (ad esempio, più di 20.000), valuta la possibilità di ridurre il numero di parole mantenendo le linee guida per un input significativo.

    Il metodo non restituisce più 503 *Service Unavailable*. Per ulteriori informazioni sui possibili codici di risposta, vedi il [Riferimento API ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.
-   L'aggiornamento include ulteriori correzioni di errori e miglioramenti interni.

### 7 giugno 2016
{: #June2016b}

-   Il servizio ora supporta CORS (Cross-Origin Resource Sharing) per consentire ai client basati su browser di chiamare direttamente il servizio. Per ulteriori informazioni, vedi [Supporto CORS](/docs/services/personality-insights/developer-overview.html#CORS).
-   Le prestazioni del servizio durante l'elaborazione del testo giapponese sono notevolmente migliorate.
-   L'aggiornamento include ulteriori correzioni di errori e miglioramenti interni.

### 1 giugno 2016
{: #June2016a}

Il servizio {{site.data.keyword.personalityinsightsshort}} è stato aggiornato per correzioni di errori e miglioramenti interni. Inoltre, un ulteriore campo di livello superiore, `warnings`, è stato aggiunto ai risultati JSON restituiti dal servizio; per ulteriori informazioni, vedi il [Riferimento API ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

### 17 maggio 2016
{: #May2016}

Il servizio {{site.data.keyword.personalityinsightsshort}} è stato aggiornato per correzioni di errori e miglioramenti interni. 

### 18 marzo 2016
{: #March2016}

Il servizio ora supporta le seguenti lingue:

-   Quattro lingue per il testo di input: Arabo (`ar`), Inglese (`en`), Spagnolo (`es`) e Giapponese (`ja`). Per specificare la lingua, utilizza l'intestazione `Content-Language` per l'input in testo semplice e HTML o la proprietà `language` dell'oggetto `ContentItem` per l'input JSON.
-   Le stesse quattro lingue per la risposta. Per specificare la lingua della risposta, utilizza l'intestazione `Accept-Language`.

Puoi utilizzare qualsiasi combinazione di lingue per l'input e la risposta. In entrambi i casi, se non specifichi una lingua, il servizio utilizzerà l'inglese per impostazione predefinita. Per ulteriori informazioni, vedi [Specifica delle lingue di richiesta e di risposta](/docs/services/personality-insights/input.html#languages). Inoltre, fai riferimento al post del blog [Arabic and Japanese support is now available for {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.personalityinsightsshort}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/blogs/watson/2016/04/arabic-japanese-support-now-available-ibm-watson-personality-insights/){: new_window} per ulteriori informazioni.

> **Nota:** poiché richiede un numero di cicli di calcolo da analizzare significativamente maggiore rispetto ad altre lingue, l'elaborazione del contenuto in arabo richiede molto più tempo. Sebbene il servizio supporti la stessa restrizione di 20 MB sulla quantità di testo di input per tutte le lingue, il limite pratico per il contenuto in arabo potrebbe essere inferiore per evitare timeout. Anche il contenuto in giapponese impiega più tempo per essere elaborato, ma i ritardi sono meno significativi rispetto a quelli per l'arabo.

### 9 luglio 2015
{: #July2015}

-   *Supporto delle lingue.* Il servizio ora ti consente di analizzare sia i contenuti in inglese che in spagnolo. Puoi indicare la lingua del testo di input con l'intestazione `Content-Language` del metodo `/v2/profile`. Per informazioni su come specificare una lingua, vedi [Specifica delle lingue di richiesta e di risposta](/docs/services/personality-insights/input.html#languages).
-   *Punteggi non elaborati.* Il servizio ora ti consente di richiedere punteggi non elaborati ed errori di campionamento non elaborati calcolati dal testo di input e dai modelli del servizio. I valori non vengono normalizzati o confrontati con una popolazione campione. I punteggi non elaborati sono utili per i clienti che desiderano applicare una normalizzazione personalizzata per uno scenario specifico o che non richiedono un confronto con una popolazione campione. Richiedi i punteggi non elaborati impostando il parametro di query `include_raw` del metodo `/v2/profile` su `true`. Per ulteriori informazioni, vedi [Interpretazione dei risultati numerici](/docs/services/personality-insights/numeric.html).
-   *Miglioramenti del modello.* Sulla base degli ultimi studi, {{site.data.keyword.IBM_notm}} ha ulteriormente migliorato alcuni dei suoi approcci per dedurre le caratteristiche della personalità. Le modifiche sono trasparenti per gli utenti del servizio e non invalidano alcun risultato precedente ottenuto dal servizio. Per ulteriori informazioni sugli studi e sull'approccio del servizio alla deduzione, vedi [Modalità di deduzione delle caratteristiche della personalità](/docs/services/personality-insights/science.html#researchInfer).

### 23 febbraio 2015
{: #February2015}

A partire dal 23 febbraio 2015, il servizio {{site.data.keyword.personalityinsightsshort}} è la versione generalmente disponibile (GA) del precedente servizio User Modeling, che era disponibile come release beta. La release GA richiede che gli utenti eseguano la migrazione a un'istanza del nuovo servizio. Tra le versioni beta e GA del servizio esistono le seguenti differenze.

-   Il servizio {{site.data.keyword.personalityinsightsshort}} è retrocompatibile con il servizio User Modeling. Le differenze descritte in questa sezione offrono maggiore flessibilità e migliori risultati senza influire sulle applicazioni correnti. 
-   I parametri con cui crei il servizio in {{site.data.keyword.Bluemix_short}} sono cambiati. Adesso utilizzi il nome servizio `personality_insights` invece di `user_modeling` e il piano di servizio `"IBM Watson Personality Insights Monthly Plan"` invece di `user_modeling_free_plan`.
-   Il metodo `/v2/profile` accetta due nuovi formati di input. L'intestazione `Content-Type` ora accetta i formati di input in testo semplice (`text/plain`), che è l'impostazione predefinita, e in HTML (`text/html`), oltre a JSON (`application/json`).
-   Il metodo `/v2/profile` ora restituisce un nuovo formato di output. L'intestazione `Accept` accetta ora il formato di output CSV (`text/csv`) oltre a JSON (`application/json`), che è l'impostazione predefinita.
-   Il metodo `/v2/profile` ora include un nuovo elemento di output, `sampling_error`, per ogni caratteristica per cui riporta un valore percentuale. L'errore di campionamento viene restituito come un valore doppio che indica il livello di affidabilità del servizio nel percentile dell'autore in base al testo di input.
-   Il modello Esigenze utilizza tokenizzazione ed elaborazione migliorate per normalizzare meglio la distribuzione dei valori per le sue caratteristiche. Si consiglia di ricalcolare i risultati generati dall'API User Modeling.
-   Il metodo `visualize` è ora obsoleto e verrà rimosso completamente in una release futura. Puoi utilizzare il file JavaScript `personality.js` fornito con l'applicazione di esempio per ottenere risultati simili dal client. Il file JavaScript `textsummary.js` fornisce una formattazione aggiuntiva per i risultati del servizio.
