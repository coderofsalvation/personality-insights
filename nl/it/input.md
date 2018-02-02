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

# Richiesta di un profilo
{: #input}

Per analizzare il contenuto, utilizza il metodo di richiesta `POST` HTTP per richiamare il metodo `/v3/profile` del servizio {{site.data.keyword.personalityinsightsshort}}. Puoi passare al servizio un massimo di 20 MB di contenuto da analizzare tramite il corpo della richiesta, ma il servizio richiede molto meno input per produrre un profilo di personalità accurato; per ulteriori informazioni, vedi [Immissione di input sufficiente](#sufficient).
{: shortdesc}

Il metodo `/v3/profile` include parametri che ti consentono di specificare il tipo di contenuto che il servizio dovrà ricevere e restituire, nonché la lingua di ciascun tipo di contenuto. Il servizio restituisce sempre un profilo che fornisce informazioni sulle caratteristiche della personalità dell'autore del testo di input. Puoi anche richiedere che il servizio restituisca risultati non elaborati e preferenze di consumo.

Le seguenti sezioni descrivono i parametri del metodo `/v3/profile`. Per informazioni sui risultati di una richiesta, vedi [Descrizione di un profilo JSON](/docs/services/personality-insights/output.html) e [Descrizione di un profilo CSV](/docs/services/personality-insights/output-csv.html). Per informazioni dettagliate sul metodo `/v3/profile`, vedi il [Riferimento API ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

## Specifica dei formati di richiesta e di risposta
{: #formats}

Puoi utilizzare i parametri di intestazione `Content-Type` e `Accept` per indicare il formato del contenuto che passi al metodo e il formato della risposta del servizio. Puoi utilizzare qualsiasi combinazione di formati supportati per la richiesta e la risposta.

<table>
  <caption>Tabella 1. Specifica dei formati di richiesta e di risposta</caption>
  <tr>
    <th style="width:10%; text-align:left; vertical-align:bottom">
      Formato
    </th>
    <th style="width:26%; text-align:center; vertical-align:bottom">
      Argomento
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      Supportato da<br/>
      <code>Content-Type</code>
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      Supportato da<br/>
      <code>Accept</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Testo semplice
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/plain</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Sì (impostazione predefinita)<br/><br/>
      Il servizio elabora il testo semplice senza modifiche.
    </td>
    <td style="text-align:center; vertical-align:top">
      No
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      HTML
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/html</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Sì<br/><br/>
      Il servizio rimuove le tag dal contenuto prima di elaborarlo.
    </td>
    <td style="text-align:center; vertical-align:top">
      No
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      JSON
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>application/json</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Sì<br/><br/>
      Il contenuto deve essere conforme al modello definito
      dall'oggetto <code>Content</code>, che è un array
      di oggetti <code>ContentItem</code>.
    </td>
    <td style="text-align:center; vertical-align:top">
      Sì (impostazione predefinita)<br/><br/>
      Il servizio restituisce i risultati come oggetto
      <code>Profile</code>.
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      CSV
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/csv</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      No
    </td>
    <td style="text-align:center; vertical-align:top">
      Sì<br/><br/>
      Per impostazione predefinita, il servizio restituisce una singola riga di risultati numerici
      Imposta il parametro di query facoltativo <code>csv_headers</code>
      su <code>true</code> per richiedere intestazioni con ogni colonna dell'output.
    </td>
  </tr>
</table>

### Specifica dei set di caratteri
{: #charset}

Per impostazione predefinita, il servizio utilizza i seguenti set di caratteri per il contenuto di input:

-   *Per il contenuto in testo semplice e HTML,* il servizio utilizza il set di caratteri ISO (International Standards Organization) 8859-1 (in pratica il set di caratteri ASCII) per la specifica HTTP versione 1.1.
-   *Per il contenuto JSON,* il servizio utilizza sempre il set di caratteri UTF (Unicode Transformation Format)-8 per la Sezione 8.1 dell'International Engineering Task Force (IETF) [Richiesta di commento (RFC) 7159 ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://tools.ietf.org/html/rfc7159#section-8.1){: new_window}.

Quando invii il contenuto in testo semplice o HTML, includi il parametro `charset` nell'intestazione `Content-Type` per la codifica dei caratteri del testo di input. Il seguente esempio specifica la codifica di caratteri UTF-8 per l'input in testo semplice:

```
Content-Type: text/plain;charset=utf-8
```
{: codeblock}

Utilizzando il parametro `charset`, puoi evitare potenziali problemi associati a caratteri non ASCII o non stampabili. Se passi i dati UTF-8 senza specificare il set di caratteri, i caratteri speciali possono provocare risultati non corretti o errori HTTP 4*nn* o 5*nn*.

### Utilizzo di cURL
{: #charsetCurl}

Per evitare errori durante l'utilizzo di cURL, passa sempre il contenuto tramite l'opzione `--data-binary` del comando `curl` per preservare qualsiasi codifica UTF-8 per il contenuto. Se utilizzi l'opzione `--data` per passare il contenuto in formato ASCII, il comando può elaborare l'input, il che può causare problemi per i dati codificati in UTF-8.

Ad esempio, il seguente comando `curl` utilizza correttamente l'opzione `--data-binary` per pubblicare i contenuti del *nome file* specificato senza ulteriore elaborazione. Il comando utilizza anche il parametro `charset` con l'intestazione `Content-Type` e richiede esplicitamente il formato di risposta JSON predefinito.

```bash
curl -X POST --user {username}:{password}
--header "Content-Type: text/plain;charset=utf-8"
--header "Accept: application/json"
--data-binary @{filename}
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{: pre}

Per ulteriori esempi di chiamata al servizio con diversi formati di richiesta e risposta, vedi l'[Esercitazione introduttiva](/docs/services/personality-insights/getting-started.html).

## Specifica dell'input JSON
{: #json}

Per passare l'input JSON, utilizza l'oggetto `Content`. L'oggetto include un array di oggetti `ContentItem`, ciascuno dei quali contiene un elemento del contenuto. L'unico campo obbligatorio dell'oggetto è `content`, che fornisce il testo da analizzare. Gli altri campi facoltativi ti consentono di specificare quanto segue:

-   `id` (stringa) è un ID univoco per l'elemento di contenuto.
-   `created` (numero intero) è una data/ora UNIX che indica quando è stato creato l'elemento di contenuto.
-   `updated` (numero intero) è una data/ora UNIX che indica quando l'elemento di contenuto è stato aggiornato l'ultima volta.
-   `contenttype` (stringa) indica il tipo di elemento di contenuto, `text/plain` o `text/html`.
-   `language` (stringa) indica la lingua dell'elemento di contenuto: `ar` (Arabo), `en` (Inglese), `es` (Spagnolo), `ja` (Giapponese) o `ko` (Coreano). Vedi [Specifica delle lingue di richiesta e di risposta](#languages).
-   `parentid` (stringa) è l'`id` dell'elemento principale dell'elemento di contenuto.
-   `reply` (booleano) indica se l'elemento di contenuto è una risposta a un altro elemento.
-   `forward` (booleano) indica se l'elemento di contenuto è un inoltro o una copia di un altro elemento.

L'input JSON è adatto per i contenuti di Twitter o di altri social network composti da più conversazioni o post. Invece di concatenare tutto il testo dell'autore in una singola stringa, puoi usare JSON per inviare i dati così come sono. Questo ha l'ulteriore vantaggio di far sapere al servizio quali parti del testo sono correlate.

### Input JSON di esempio
{: jsonExample}

Gli esempi riportati nell'[Esercitazione introduttiva](/docs/services/personality-insights/getting-started.html) utilizzano il file JSON di esempio <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Icona link esterno" title="Icona link esterno" class="style-scope doc-content"></a>. Il file include una serie di messaggi di Twitter. Il seguente esempio mostra i primi tweet del file.

```javascript
{
  "contentItems": [
    {
      "content": "Wow, I liked @TheRock before, now I really SEE how special he is. The daughter story was IT for me. So great! #MasterClass",
      "contenttype": "text/plain",
      "created": 1447639154000,
      "id": "666073008692314113",
      "language": "en"
    },
    {
      "content": ".@TheRock how did you Know to listen to your gut and Not go back to football? #Masterclass",
      "contenttype": "text/plain",
      "created": 1447638226000,
      "id": "666069114889179136",
      "language": "en"
    },
    . . .
  ]
}
```
{: codeblock}

## Specifica delle lingue di richiesta e di risposta
{: #languages}

Puoi utilizzare i parametri di intestazione `Content-Language` e `Accept-Language` per indicare la lingua del contenuto di input e la lingua della risposta del servizio. Puoi utilizzare qualsiasi combinazione di lingue supportate per la richiesta e la risposta. Se non indichi una lingua, il servizio utilizza i suoi modelli addestrati in inglese per l'analisi e l'inglese per i risultati. La seguente tabella elenca le lingue di input e output supportate e identifica gli argomenti che utilizzi con i parametri relativi alla lingua.

<table style="width:90%">
  <caption>Tabella 2. Specifica delle lingue di richiesta e di risposta</caption>
  <tr>
    <th style="width:28%; text-align:left; vertical-align:bottom">
      Lingua
    </th>
    <th style="width:12%; text-align:center; vertical-align:bottom">
      Argomento
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      Supportato da<br/>
      <code>Content-Language</code>
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      Supportato da<br/>
      <code>Accept-Language</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      Arabo
    </td>
    <td style="text-align:center">
      <code>ar</code>
    </td>
    <td style="text-align:center">
      Sì
    </td>
    <td style="text-align:center">
      Sì
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Inglese
    </td>
    <td style="text-align:center">
      <code>en</code>
    </td>
    <td style="text-align:center">
      Sì
    </td>
    <td style="text-align:center">
      Sì
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Giapponese
    </td>
    <td style="text-align:center">
      <code>ja</code>
    </td>
    <td style="text-align:center">
      Sì
    </td>
    <td style="text-align:center">
      Sì
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Coreano
    </td>
    <td style="text-align:center">
      <code>ko</code>
    </td>
    <td style="text-align:center">
      Sì
    </td>
    <td style="text-align:center">
      Sì
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Spagnolo
    </td>
    <td style="text-align:center">
      <code>es</code>
    </td>
    <td style="text-align:center">
      Sì
    </td>
    <td style="text-align:center">
      Sì
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Portoghese brasiliano
    </td>
    <td style="text-align:center">
      <code>pt-br</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Sì
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Francese
    </td>
    <td style="text-align:center">
      <code>fr</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Sì
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Tedesco
    </td>
    <td style="text-align:center">
      <code>de</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Sì
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Italiano
    </td>
    <td style="text-align:center">
      <code>it</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Sì
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Cinese semplificato
    </td>
    <td style="text-align:center">
      <code>zh-cn</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Sì
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Cinese tradizionale
    </td>
    <td style="text-align:center">
      <code>zh-tw</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Sì
    </td>
  </tr>
</table>

Invia tutto il testo nella stessa lingua; non mescolare più lingue nella stessa richiesta. Per gli argomenti di lingua a due caratteri, il servizio tratta le varianti regionali come lingua principale; ad esempio, interpreta `en-US` come `en`.

### Specifica di una lingua per il contenuto JSON
{: #languageJSON}

Per l'input in testo semplice e HTML, l'intestazione `Content-Language` è l'unico modo per specificare la lingua. Per l'input JSON, puoi anche specificare la lingua di ogni singolo elemento di contenuto utilizzando il parametro `language` dell'oggetto `ContentItem`. Tuttavia, una lingua specificata con l'intestazione `Content-Language` sovrascrive una lingua specificata per un elemento contenuto; il servizio ignora gli elementi di contenuto che specificano una lingua diversa.

Ometti l'intestazione `Content-Type` per basare la lingua esclusivamente sulla specifica degli elementi di contenuto. Il servizio utilizza la lingua più prevalente tra gli elementi di contenuto, che fornisce i migliori risultati possibili. Conta il numero di elementi di contenuto per ciascuna lingua e seleziona la lingua con la frequenza più alta. Se più lingue hanno la stessa frequenza massima, il servizio utilizza la lingua che raggiunge per prima quel valore. Ancora una volta, il servizio ignora gli elementi di contenuto che specificano una lingua diversa.

### Considerazioni sulla lingua
{: #languageNotes}

Tieni conto delle seguenti informazioni quando inoltri il testo di input:

-   *Per l'inglese,* i risultati sono basati sulle norme culturali statunitensi. Se analizzi il testo in inglese da una cultura diversa, potresti dover regolare i risultati di conseguenza.
-   *Per l'arabo,* il servizio può troncare la quantità di testo di input per motivi di prestazioni. Ad una certa soglia, l'accuratezza dei risultati per l'arabo non migliora con più parole. Se il servizio tronca l'input in arabo, restituisce un messaggio di avvertenza per informarti che ha ridotto la quantità di testo di input che ha utilizzato per il profilo.
-   *Per l'arabo e il coreano,* il servizio non è in grado di restituire risultati significativi per un sottoinsieme di caratteristiche. Per ulteriori informazioni, vedi [Limitazioni per l'input in arabo e coreano](/docs/services/personality-insights/numeric.html#limitations).

Per informazioni generali sull'utilizzo del testo tradotto, vedi [Deduzione della personalità dal testo tradotto](/docs/services/personality-insights/guidance.html#translation).

## Immissione di input sufficiente
{: #sufficient}

Un profilo di personalità significativo può essere creato solo quando vengono forniti dati sufficienti di quantità e qualità adeguate. Poiché l'uso della lingua varia naturalmente da un documento a un altro e da un momento a un altro, un piccolo campione di testo potrebbe non essere rappresentativo dei modelli di lingua generali di una persona. Inoltre, caratteristiche e supporti differenti convergono a ritmi un po' diversi.

Fino ad un certo punto, è probabile che più parole producano risultati migliori, migliorando la precisione del servizio riducendo la deviazione tra i risultati previsti e il punteggio effettivo dell'autore. Puoi inviare al servizio fino a 20 MB di contenuto di input, ma i livelli di precisione si riducono a circa 3000 parole di input; il contenuto aggiuntivo non contribuisce ulteriormente all'accuratezza del profilo. Pertanto, il servizio estrae e utilizza solo i primi 250 KB di contenuto, senza contare i markup HTML o JSON, dalle richieste di grandi dimensioni.

Questa cifra non è associata a un numero esatto di parole, che varia in base alla lingua e alla natura del testo. In inglese, ad esempio, la lunghezza media delle parole è compresa tra quattro e cinque caratteri, quindi questa cifra fornisce circa 50.000 parole, ovvero almeno 15 volte più parole di quelle richieste dal servizio per produrre un profilo accurato. Troncando input lunghi, il servizio migliora il tempo di risposta senza sacrificare la precisione. Il campo `word_count` del JSON di risposta indica il numero di parole effettivamente utilizzate dal servizio per una richiesta, che può essere inferiore al numero di parole inoltrate.

### Linee guida e suggerimenti
{: #sufficientGuidelines}

La seguente tabella riporta due valori per diverse quantità di testo di input:

-   L'*errore medio assoluto (MAE Average Mean Absolute Error)* tra tutte le caratteristiche in base al numero di parole fornite come input. Più piccolo è il MAE, più i risultati del servizio sono vicini ai punteggi che l'autore potrebbe ricevere effettuando un vero test della personalità. 
-   La *correlazione media* tra i punteggi dedotti e quelli effettivi tra tutte le caratteristiche. Più la correlazione è vicina a 1, migliori saranno le previsioni, sebbene le correlazioni superiori a 0,2 siano considerate accettabili e quelle superiori a 0,4 siano rare.

Le informazioni sono basate su dati in lingua inglese, ma le linee guida generali si applicano a tutte le lingue. Per ulteriori informazioni sul MAE e sulla correlazione media, comprese le statistiche specifiche della lingua, vedi [Precisione del servizio](/docs/services/personality-insights/science.html#researchPrecise).

<table style="width:80%">
  <caption>Tabella 3. Valori medi di MAE e correlazione</caption>
  <tr>
    <th style="text-align:center; vertical-align:bottom; width:24%">Numero di parole</th>
    <th style="text-align:center; width:38%">MAE medio<br/>tra tutte le
      caratteristiche</th>
    <th style="text-align:center; width:38%">Correlazione media<br/>tra tutte le
      caratteristiche</th>
  </tr>
  <tr>
    <td style="text-align:center">3000</td>
    <td style="text-align:center">12,1%</td>
    <td style="text-align:center">0,257</td>
  </tr>
  <tr>
    <td style="text-align:center">1200</td>
    <td style="text-align:center">12,2%</td>
    <td style="text-align:center">0,237</td>
  </tr>
  <tr>
    <td style="text-align:center">600</td>
    <td style="text-align:center">12,3%</td>
    <td style="text-align:center">0,212</td>
  </tr>
  <tr>
    <td style="text-align:center">300</td>
    <td style="text-align:center">12,5%</td>
    <td style="text-align:center">0,175</td>
  </tr>
  <tr>
    <td style="text-align:center">100</td>
    <td style="text-align:center">12,7%</td>
    <td style="text-align:center">0,095</td>
  </tr>
</table>

Come indicato dalle seguenti linee guida, {{site.data.keyword.IBM_notm}} consiglia di fornire almeno 1200 parole, ma anche l'immissione di almeno 600 parole produce risultati accettabili:

-   3000 parole sono sufficienti per raggiungere la massima precisione del servizio.
-   Almeno 1200 parole producono un MAE che è compreso nel due percento del miglior MAE che il servizio può restituire.
-   Da 600 a 1200 parole producono un MAE che è compreso nel tre percento del miglior MAE che il servizio può restituire.
-   Meno di 600 parole generano un'avvertenza, ma il servizio analizza ancora l'input.
-   Meno di 100 parole generano un errore.

Queste linee guida possono aiutarti ad adattare l'affidabilità dei risultati alla tua applicazione. Ad esempio, per un'applicazione casuale che consiglia i film, potresti accettare tranquillamente una minore precisione; per un'applicazione che propone suggerimenti più importanti, è probabile che tu richieda risultati più precisi. Per ulteriori informazioni su come il servizio deduce le caratteristiche della personalità, vedi [Modalità di deduzione delle caratteristiche della personalità](/docs/services/personality-insights/science.html#researchInfer).

## Richiesta di punteggi non elaborati
{: #rawScores}

Il servizio restituisce sempre punteggi normalizzati per ogni caratteristica della personalità (dimensione e aspetto Big Five, Esigenza e Valore) come parte della sua risposta. Il servizio può anche riportare un `raw_score` per ogni caratteristica se imposti il parametro di query `raw_scores` su `true`. I punteggi non elaborati rappresentano i punteggi per le caratteristiche basati esclusivamente sul testo dell'autore e sul modello di quella caratteristica, senza confrontare i risultati con una popolazione campione. Per ulteriori informazioni sull'utilizzo dei punteggi non elaborati, vedi [Punteggi non elaborati per le caratteristiche della personalità](/docs/services/personality-insights/numeric.html#rawScores).

## Richiesta di preferenze di consumo
{: #preferences}

Il servizio restituisce sempre risultati per i modelli di personalità. Quando imposti il parametro di query `consumption_preferences` su `true`, il servizio restituisce anche i `scores` per una varietà di preferenze di consumo in base alle caratteristiche della personalità che deduce dal testo di input. Questi risultati indicano la tendenza dell'autore a preferire prodotti, servizi e attività differenti. Le aziende possono utilizzare i risultati per comprendere meglio le inclinazioni dell'autore e personalizzare per lui le comunicazioni e le offerte.

Per ulteriori informazioni sulle diverse preferenze di consumo, vedi [Preferenze di consumo](/docs/services/personality-insights/preferences.html). Per informazioni sull'interpretazione dei risultati numerici per una preferenza, vedi [Punteggi per le preferenze di consumo](/docs/services/personality-insights/numeric.html#scores).

## Specifica della versione dell'interfaccia
{: #version}

Tutte le chiamate al metodo `/v3/profile` devono includere il parametro di query `version` per indicare la versione dell'API del servizio e il formato di risposta che vuoi utilizzare. La versione deve essere specificata come una data nel formato `YYYY-MM-DD`; ad esempio, specifica `2017-10-13` per 13 ottobre 2017. Il parametro consente al servizio di aggiornare la propria API e il formato di risposta per le nuove versioni senza interrompere i client esistenti.

La data che specifichi non deve necessariamente corrispondere a una versione del servizio; il servizio utilizza la versione che rientra nella data da te fornita. Se specifichi una data precedente al rilascio iniziale della versione 3, il servizio utilizza la versione 3 dell'API. Se specifichi una data futura o comunque successiva alla versione più recente, il servizio utilizza l'ultima versione.
