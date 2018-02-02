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

# La scienza alla base del servizio
{: #science}

Una teoria ben accettata di psicologia, marketing e altri campi è che il linguaggio umano riflette la personalità, lo stile di pensiero, le connessioni sociali e gli stati emotivi. La frequenza con cui utilizziamo determinate categorie di parole può fornire indizi su queste caratteristiche. Diversi ricercatori hanno scoperto che le variazioni nell'uso delle parole in scritti come blog, saggi e tweet possono prevedere aspetti della personalità ([Fast &amp; Funder, 2008](/docs/services/personality-insights/references.html#fast2008), [Gill et al., 2009](/docs/services/personality-insights/references.html#gill2009), [Golbeck et al., 2011](/docs/services/personality-insights/references.html#golbeck2011), [Hirsh &amp; Peterson, 2009](/docs/services/personality-insights/references.html#hirsh2009) e [Yarkoni, 2010](/docs/services/personality-insights/references.html#yarkoni2010)).
{: shortdesc}

{{site.data.keyword.IBM_notm}} ha condotto una serie di studi per capire se le caratteristiche della personalità dedotte dai dati dei social media possano predire il comportamento e le preferenze delle persone. {{site.data.keyword.IBM_notm}} ha scoperto che le persone con specifiche caratteristiche della personalità hanno risposto e re-tweettato in numero maggiore nelle attività di raccolta e di diffusione delle informazioni. Ad esempio, le persone che ottengono un punteggio elevato sul desiderio di stimoli hanno maggiori probabilità di rispondere, mentre quelle che ottengono punteggi alti sulla prudenza hanno meno probabilità di farlo ([Mahmud et al., 2013](/docs/services/personality-insights/references.html#mahmud2013)). Allo stesso modo, le persone che ottengono punteggi elevati in termini di modestia, apertura mentale e cordialità hanno maggiori probabilità di diffondere informazioni ([Lee et al., 2014](/docs/services/personality-insights/references.html#lee2014)).

{{site.data.keyword.IBM_notm}} ha anche riscontrato che le persone con un'elevata apertura mentale e una bassa stabilità emotiva (nevroticismo), come dedotto dal linguaggio dei social media, hanno risposto in modo più favorevole (ad esempio, facendo clic su un link pubblicitario o seguendo un account), risultati che sono stati corroborati da un controllo di verità di base basato su indagini. Ad esempio, gli annunci mirati al 10 percento degli utenti in termini di alta apertura mentale e bassa stabilità emotiva hanno portato all'aumento del tasso di clic dal 6,8 percento all'11,3 percento e del tasso di follow dal 4,7 percento all'8,8 percento.

Diversi studi recenti hanno rivelato risultati simili per caratteristiche che sono state calcolate dai dati dei social media. Uno studio recente con i dati dei negozi al dettaglio ha rilevato che le persone che ottengono un punteggio elevato in termini di ordine, autodisciplina e prudenza e un basso punteggio in smoderatezza sono il 40 percento più propensi a rispondere ai coupon rispetto alla popolazione casuale. Un secondo studio ha rilevato che le persone con determinati valori mostravano specifici interessi di lettura ([Hsieh et al. 2014](/docs/services/personality-insights/references.html#hsieh2014)). Ad esempio, le persone con un valore di autotrascendenza più alto hanno dimostrato interesse per la lettura di articoli sull'ambiente e le persone con un valore di auto-miglioramento più alto hanno mostrato intesse per la lettura di articoli sul lavoro. Un terzo studio su oltre 600 utenti di Twitter ha rilevato che le caratteristiche della personalità di una persona possono prevedere la preferenza di marca con una precisione del 65 percento.

Le seguenti sezioni si espandono su questi risultati di alto livello per descrivere la ricerca e lo sviluppo alla base del servizio {{site.data.keyword.personalityinsightsshort}}. Per ulteriori informazioni sugli studi che applicano il servizio a scenari tangibili, vedi [Il servizio in azione](/docs/services/personality-insights/applied.html).

## Descrizione dei modelli di personalità
{: #researchModels}

Per il servizio {{site.data.keyword.personalityinsightsshort}}, {{site.data.keyword.IBM_notm}} ha sviluppato modelli per dedurre punteggi per le dimensioni e gli aspetti Big Five, le Esigenze e i Valori da informazioni testuali. I modelli riportati dal servizio si basano sulla ricerca nei campi della psicologia, della psicolinguistica e del marketing:

-   [Big Five](/docs/services/personality-insights/models.html) è uno degli studi migliori sui modelli di personalità sviluppati dagli psicologi ([Costa &amp; McCrae, 1992](/docs/services/personality-insights/references.html#costa1992) e [Norman, 1963](/docs/services/personality-insights/references.html#norman1963)). È il modello di personalità più utilizzato per descrivere come una persona si relaziona generalmente con il mondo. Il servizio calcola le cinque dimensioni e i trenta aspetti del modello. Le dimensioni sono spesso indicate dal mnemonico *OCEAN*, dove *O* sta per Openness (apertura mentale), *C* per Conscientiousness (coscienziosità), *E* per Extraversion (estroversione), *A* per Agreeableness (gradevolezza) e *N* per Neuroticism (nevroticismo). (Poiché il termine nevroticismo può avere un significato clinico specifico, il servizio presenta tali informazioni sotto la voce "Stabilità emotiva" più generalmente applicabile.)
-   Le [Esigenze](/docs/services/personality-insights/needs.html) sono un importante aspetto del comportamento umano. La letteratura scientifica suggerisce che diversi tipi di esigenze umane sono universali e influenzano direttamente il comportamento dei consumatori ([Kotler &amp; Armstrong, 2013](/docs/services/personality-insights/references.html#kotler2013) e [Ford, 2005](/docs/services/personality-insights/references.html#ford2005)). Le dodici categorie di esigenze segnalate dal servizio sono descritte nella letteratura di marketing come desideri che una persona spera di soddisfare quando considera un prodotto o un servizio. 
-   I [Valori](/docs/services/personality-insights/values.html) trasmettono ciò che è più importante per un individuo. Sono "obiettivi desiderabili e trans-situazionali, di importanza variabile, che servono come principi guida nella vita delle persone" ([Schwartz, 2006](/docs/services/personality-insights/references.html#schwartz2006)). Schwartz riassume cinque caratteristiche comuni a tutti i valori: (1) i valori sono credenze; (2) i valori sono un costrutto motivazionale; (3) i valori trascendono azioni e situazioni specifiche; (4) i valori guidano la selezione o la valutazione di azioni, politiche, persone ed eventi e (5) i valori variano in base alla relativa importanza e possono essere classificati di conseguenza. Il servizio calcola i cinque valori umani fondamentali proposti da Schwartz e convalidati in più di venti paesi ([Schwartz, 1992](/docs/services/personality-insights/references.html#schwartz1992)).

## Modalità di deduzione delle caratteristiche della personalità
{: #researchInfer}

Il servizio {{site.data.keyword.personalityinsightsshort}} deduce le caratteristiche della personalità da informazioni testuali in base a un approccio open-vocabulary. Questo metodo riflette l'ultima tendenza nella ricerca sulla deduzione della personalità ([Arnoux et al., 2017](/docs/services/personality-insights/references.html#arnoux2017), [Schwartz et al., 2013](/docs/services/personality-insights/references.html#schwartz2013) e [Plank &amp; Hovy, 2015](/docs/services/personality-insights/references.html#plank2015)).

Il servizio innanzitutto converte il testo di input per sviluppare una rappresentazione in uno spazio *n*-dimensionale. Il servizio utilizza la tecnica del word embedding open-source chiamata [GloVe ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://nlp.stanford.edu/projects/glove/){: new_window} per ottenere una rappresentazione vettoriale per le parole nel testo di input ([Pennington et al., 2014](/docs/services/personality-insights/references.html#pennington2014)). Quindi immette questa rappresentazione in un algoritmo di machine learning che deduce un profilo di personalità con le caratteristiche di Big Five, Esigenze e Valori. Per addestrare l'algoritmo, il servizio utilizza i punteggi ottenuti dalle indagini condotte tra migliaia di utenti insieme ai dati dei loro feed Twitter. 

{{site.data.keyword.IBM_notm}} ha sviluppato i modelli per tutte le lingue supportate in modo identico. I modelli sono stati sviluppati indipendentemente dai dati demografici dell'utente, come età, sesso o cultura. In futuro, {{site.data.keyword.IBM_notm}} potrebbe sviluppare modelli specifici per diverse categorie demografiche.

Le versioni precedenti del servizio utilizzavano il dizionario psicolinguistico LIWC (Linguistic Inquiry and Word Count) insieme al modello di machine learning. Tuttavia, l'approccio open-vocabulary appena descritto supera il modello basato su LIWC in termini di prestazioni. Per ulteriori informazioni sulla precisione del servizio per ogni lingua in termini di errore medio assoluto (MAE) e correlazione media, vedi [Precisione del servizio](#researchPrecise). Per indicazioni su come fornire testo di input per ottenere i risultati più accurati, vedi [Immissione di input sufficiente](/docs/services/personality-insights/input.html#sufficient).

## Precisione del servizio
{: #researchPrecise}

{{site.data.keyword.IBM_notm}} ha condotto uno studio di convalida per comprendere l'accuratezza dell'approccio del servizio per dedurre un profilo di personalità. {{site.data.keyword.IBM_notm}} ha raccolto risposte alle indagini e feed Twitter tra 1500 e 2000 partecipanti per tutte le caratteristiche e le lingue. Per stabilire la *verità di base*, i partecipanti hanno effettuato quattro serie di test psicometrici standard:

-   50 elementi Big Five derivati da International Personality Item Pool (IPIP)
-   120 elementi Aspetto derivati da IPIP Neuroticism, Extraversion &amp; Openness (IPIP-NEO)
-   52 elementi Esigenze fondamentali sviluppati da {{site.data.keyword.IBM_notm}}
-   26 elementi Valori di base sviluppati da Schwartz

{{site.data.keyword.IBM_notm}} ha quindi confrontato i punteggi ottenuti dai suoi modelli con i punteggi basati sulle indagini per gli utenti di Twitter. In base a questi risultati, {{site.data.keyword.IBM_notm}} ha determinato l'[errore medio assoluto (MAE)](#preciseMAE) e la [correlazione media](#preciseCorrelation) tra i punteggi dedotti e quelli effettivi per le diverse categorie di caratteristiche della personalità. [Valori medi di MAE e correlazione per ogni lingua](#precisePerLanguage) fornisce i valori statistici per ciascuna lingua supportata.

### Errore medio assoluto
{: #preciseMAE}

*Errore medio assoluto (MAE, Mean Absolute Error)* è una metrica che viene utilizzata per misurare la differenza tra i valori effettivi e quelli previsti. Per il servizio {{site.data.keyword.personalityinsightsshort}}, il valore effettivo, o verità di base, è il punteggio della personalità ottenuto mediante la somministrazione di un'indagine sulla personalità. Il valore previsto è il punteggio prodotto dai modelli del servizio.

{{site.data.keyword.IBM_notm}} ha calcolato il MAE prendendo la media del valore assoluto della differenza tra i punteggi effettivi e previsti. {{site.data.keyword.IBM_notm}} ha utilizzato il valore assoluto perché una previsione approssimativa del valore effettivo è irrilevante; finché c'è una differenza, il modello è penalizzato dalla grandezza dell'errore. Più basso è il MAE, migliori sono le prestazioni del modello. {{site.data.keyword.IBM_notm}} utilizza una scala da 0 a 1 per il MAE, dove 0 significa nessun errore (il valore previsto è esattamente lo stesso del valore effettivo) e 1 significa errore massimo.

### Correlazione media
{: #preciseCorrelation}

*Correlazione media* è un termine statistico che misura l'interdipendenza di due variabili. Con questa metrica, {{site.data.keyword.IBM_notm}} ha misurato la correlazione tra i punteggi dedotti e quelli effettivi per le diverse categorie di caratteristiche della personalità. Se il punteggio previsto si avvicina ai risultati effettivi, il punteggio di correlazione è alto; altrimenti, il punteggio è basso. 

{{site.data.keyword.IBM_notm}} misura la correlazione su scala da -1 a 1: 1 indica una perfetta relazione lineare diretta (crescente) e -1 indica una perfetta relazione lineare inversa (decrescente). In tutti gli altri casi, il valore si trova tra questi estremi. Se le variabili sono indipendenti (non hanno alcuna relazione), la correlazione è 0.

{{site.data.keyword.IBM_notm}} cerca i numeri più vicini a 1 per ottenere migliori previsioni. Ma le personalità sono difficili da prevedere basandosi esclusivamente sul testo ed è raro vedere correlazioni superiori a 0,4 per questi tipi di modelli psicologici. Nella letteratura scientifica per questo dominio, le correlazioni superiori a 0,2 sono considerate accettabili. 

### Valori medi di MAE e correlazione per ogni lingua
{: #precisePerLanguage}

La seguente tabella mostra i risultati di MAE e correlazione media per ogni lingua per il servizio {{site.data.keyword.personalityinsightsshort}}. I risultati mettono il servizio al centro della deduzione della personalità dai dati testuali come indicato da [Schwartz et al. (2013)](/docs/services/personality-insights/references.html#schwartz2013) e [Plank and Hovy (2015)](/docs/services/personality-insights/references.html#plank2015).

<table>
  <caption>Tabella 1. Valori medi di MAE e correlazione per lingua</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      Lingua
    </th>
    <th style="text-align:center; vertical-align:bottom">
      Dimensioni Big Five
    </th>
    <th style="text-align:center; vertical-align:bottom">
      Aspetti Big Five
    </th>
    <th style="text-align:center; vertical-align:bottom">
      Esigenze
    </th>
    <th style="text-align:center; vertical-align:bottom">
      Valori
    </th>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Inglese**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      MAE medio
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Correlazione media
    </td>
    <td style="text-align:center">
      0,33
    </td>
    <td style="text-align:center">
      0,28
    </td>
    <td style="text-align:center">
      0,22
    </td>
    <td style="text-align:center">
      0,24
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Spagnolo**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      MAE medio
    </td>
    <td style="text-align:center">
      0,10
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Correlazione media
    </td>
    <td style="text-align:center">
      0,35
    </td>
    <td style="text-align:center">
      0,21
    </td>
    <td style="text-align:center">
      0,24
    </td>
    <td style="text-align:center">
      0,19
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Giapponese**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      MAE medio
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Correlazione media
    </td>
    <td style="text-align:center">
      0,27
    </td>
    <td style="text-align:center">
      0,22
    </td>
    <td style="text-align:center">
      0,25
    </td>
    <td style="text-align:center">
      0,19
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Arabo**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      MAE medio
    </td>
    <td style="text-align:center">
      0,09
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,10
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Correlazione media
    </td>
    <td style="text-align:center">
      0,17
    </td>
    <td style="text-align:center">
      0,14
    </td>
    <td style="text-align:center">
      0,13
    </td>
    <td style="text-align:center">
      0,14
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Coreano**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      MAE medio
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Correlazione media
    </td>
    <td style="text-align:center">
      0,21
    </td>
    <td style="text-align:center">
      0,21
    </td>
    <td style="text-align:center">
      0,13
    </td>
    <td style="text-align:center">
      0,12
    </td>
  </tr>
</table>

Per calcolare i punteggi percentili, {{site.data.keyword.IBM_notm}} ha raccolto un set di dati molto ampio di utenti di Twitter (un milione di utenti per l'inglese, 200.000 utenti per il coreano, 100.000 utenti per l'arabo e il giapponese e 80.000 utenti per lo spagnolo) e ha calcolato i loro ritratti di personalità. {{site.data.keyword.IBM_notm}} ha quindi confrontato i punteggi non elaborati di ciascun profilo calcolato con la distribuzione dei profili da tali set di dati per determinare i percentili. 

> **Nota:** per l'input in arabo e coreano, il servizio non è in grado di produrre percentili e punteggi non elaborati significativi per alcune delle caratteristiche della personalità. Per ulteriori informazioni, vedi [Limitazioni per l'input in arabo e coreano](/docs/services/personality-insights/numeric.html#limitations).

## Descrizione delle preferenze di consumo
{: #researchPrefs}

La relazione tra personalità e comportamento d'acquisto è stata studiata attraverso una varietà di prodotti e servizi:

-   [Chen (2007)](/docs/services/personality-insights/references.html#chen2007), mentre testava le preferenze relative agli alimenti biologici, ha indicato che le caratteristiche della personalità di un individuo svolgono un ruolo importante nello stabilire criteri personali di scelta del cibo. 
-   [Schlegelmilch at al. (1996)](/docs/services/personality-insights/references.html#schlegelmilch1996) ha esplorato la relazione tra le variabili di personalità e il comportamento di acquisto pro-ambientale. Gli autori hanno dimostrato che la coscienza ambientale globale dei consumatori ha un impatto positivo sulle decisioni di acquisto ecologiche.
-   [Hymbaugh e Garrett (2007)](/docs/services/personality-insights/references.html#hymbaugh1974) hanno studiato la relazione tra personalità e paracadutismo e hanno scoperto che le persone che ottengono un punteggio elevato in spirito di avventura e desiderio di stimoli generalmente praticano il paracadutismo. (Per ulteriori informazioni, vedi [Profili di rischio](/docs/services/personality-insights/applied.html#otherRisk).)

Applicare queste relazioni note tra i comportamenti di consumo e la personalità è una sfida: la maggior parte di questi lavori ha utilizzato dati sulla personalità derivati da indagini e i loro modelli non sono disponibili al pubblico. Pertanto, {{site.data.keyword.IBM_notm}} ha deciso di studiare direttamente questi modelli di preferenza di consumo. Durante l'addestramento dei modelli, {{site.data.keyword.IBM_notm}} ha utilizzato i punteggi di personalità restituiti dal servizio {{site.data.keyword.personalityinsightsshort}} come funzioni. Di conseguenza, quando applichi questi modelli per calcolare le caratteristiche della personalità di un utente con il servizio, è probabile che le previsioni siano più accurate.

## Modalità di deduzione delle preferenze di consumo
{: #researchInferPrefs}

Il servizio {{site.data.keyword.personalityinsightsshort}} deduce le preferenze di consumo in base ai risultati del suo profilo di personalità per l'autore del testo di input. Dalla letteratura esistente, {{site.data.keyword.IBM_notm}} ha identificato 104 preferenze di consumo che hanno dimostrato essere correlate alla personalità. Queste includono le preferenze relative ad acquisti, film, musica e altre categorie. {{site.data.keyword.IBM_notm}} ha quindi creato un'indagine psicometrica per valutare l'inclinazione di un individuo per ogni comportamento di consumo.

{{site.data.keyword.IBM_notm}} ha ottenuto risposte alla sua indagine da circa 600 persone per le quali aveva anche dati di Twitter (più di 200 tweet scritti personalmente da ciascun utente). {{site.data.keyword.IBM_notm}} ha inoltrato i tweet al servizio per raccogliere un profilo di personalità per ogni individuo. Quindi ha creato un classificatore per ogni preferenza di consumo, in cui l'insieme di funzioni di input era costituito dalle informazioni sulla personalità. 

Per l'inclusione con il servizio, {{site.data.keyword.IBM_notm}} ha selezionato solo le preferenze di consumo per le quali la classificazione basata sulla personalità ha ottenuto risultati migliori del 9 percento rispetto alla classificazione casuale. Delle 104 preferenze originali, 42 hanno soddisfatto questo criterio e sono esposte come preferenze di consumo dal servizio.

<!--
COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016

## How media influence inferred characteristics

{{site.data.keyword.IBM_notm}} conducted a validation study to understand the effect of media on inferred characteristics. To determine the accuracy of the service's approach to estimating characteristics, {{site.data.keyword.IBM_notm}} compared scores that were derived by its models with survey-based scores for Twitter users (for instance, approximately 500 users for English and more than 600 for Spanish).

To establish ground truth, participants took three sets of standard psychometric tests: 50-item Big Five (derived from the International Personality Item Pool, or IPIP), 52-item fundamental Needs (developed by {{site.data.keyword.IBM_notm}}), and 26-item basic Values (developed by Schwartz). {{site.data.keyword.IBM_notm}} conducted the study in two phases:

-   For the first study, conducted in 2013, {{site.data.keyword.IBM_notm}} recruited 256 Twitter users ([Gou et al., 2014](/docs/services/personality-insights/references.html#gou2014)). Although the models were learned from different sources, {{site.data.keyword.IBM_notm}} found that for more than 80 percent of the Twitter users, scores for characteristics that were inferred for all three models correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80). Specifically, scores that were derived by the service correlated with survey-based scores as follows:
    -   For 80.8 percent of participants' Big Five scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.75)
    -   For 86.6 percent of participants' Needs scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80)
    -   For 98.21 percent of participants' Values scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.55)
-   For the second study, conducted in 2015, {{site.data.keyword.IBM_notm}} recruited another set of 237 Twitter users. The study found that for Big Five and Values, scores for inferred characteristics correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.07 and 0.21) for every Twitter user. For needs, such significant correlation was observed for 90 percent of the users (p value &lt; 0.05 and correlation coefficient between 0.01 and 0.20).

In both studies, participants also rated on a five-point scale how well each derived characteristic matched their perceptions of themselves. Their ratings suggest that the inferred characteristics largely matched their self-perceptions. Specifically, means of all ratings were above 3 ("somewhat") out of 5 ("perfect").

-   For the 256 Twitter users of the first study, means were 3.4 (with a standard deviation of 1.14) for Big Five, 3.39 (with a standard deviation of 1.34) for Needs, and 3.13 (with a standard deviation of 1.17) for Values.
-   For the 237 Twitter users of the second study, means were 3.31 (with a standard deviation of 1.18) for Big Five, 3.37 (with a standard deviation of 1.22) for Needs, and 3.36 (with a standard deviation of 1.18) for Values.

COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016
-->

## Note sulle indagini sulla personalità
{: #researchSurveys}

Durante lo sviluppo del servizio {{site.data.keyword.personalityinsightsshort}}, {{site.data.keyword.IBM_notm}} ha utilizzato le indagini sulla personalità per stabilire dati di verità di base per la deduzione della personalità. La verità di base si riferisce ai dati reali ottenuti attraverso l'osservazione diretta piuttosto che attraverso la deduzione. Una tipica misura di precisione per qualsiasi modello di machine learning è confrontare i punteggi dedotti dal modello con i dati di verità di base; le sezioni precedenti descrivono come {{site.data.keyword.IBM_notm}} ha utilizzato le indagini per convalidare la precisione del servizio. 

Le seguenti note chiariscono l'uso delle indagini sulla personalità e la stima della personalità basata sull'indagine:

-   Le indagini sulla personalità sono lunghe e richiedono tempo per essere completate. I risultati sono quindi limitati dal numero di utenti di Twitter disposti e disponibili a partecipare allo studio di {{site.data.keyword.IBM_notm}}. {{site.data.keyword.IBM_notm}} prevede di condurre studi di convalida con più utenti, nonché con gli utenti di altri media online come e-mail, blog e forum. 
-   La stima della personalità basata sull'indagine si basa sull'auto-segnalazione, che potrebbe non essere sempre un vero riflesso della personalità di un individuo: alcuni utenti potrebbero dare risposte irrilevanti a tali indagini. Per ridurre questi aspetti marginali, {{site.data.keyword.IBM_notm}} ha filtrato le risposte all'indagine includendo domande di controllo dell'attenzione e scartando le indagini completate troppo rapidamente.
-   Mentre la correlazione tra i punteggi dedotti e quelli basati sull'indagine è sia positiva che significativa, i risultati implicano che i punteggi dedotti potrebbero non essere sempre correlati ai risultati basati sull'indagine. Ricercatori esterni a {{site.data.keyword.IBM_notm}} hanno anche fatto esperimenti per confrontare il modo in cui i punteggi dedotti corrispondono a quelli ottenuti dalle indagini e nessuno ha riportato una corrispondenza pienamente coerente:
    -   [Golbeck et al. (2011)](/docs/services/personality-insights/references.html#golbeck2011) ha riportato un tasso di errore compreso tra il 10 e il 18 percento durante il confronto dei punteggi dedotti con i punteggi basati sull'indagine.
    -   [Sumner et al. (2012)](/docs/services/personality-insights/references.html#sumner2012) ha riportato circa il 65 percento di precisione per la previsione della personalità.
    -   [Mairesse e Walker (2006)](/docs/services/personality-insights/references.html#mairesse2006) hanno riportato una precisione del 60-70 percento per la previsione della personalità Big Five.

In generale, nella letteratura scientifica è ampiamente accettato che i punteggi auto-segnalati dalle indagini sulla personalità non sempre corrispondano pienamente ai punteggi dedotti dal testo. Ciò che è più importante, tuttavia, è che {{site.data.keyword.IBM_notm}} ha scoperto che le caratteristiche dedotte dal testo possono prevedere in modo affidabile una varietà di comportamenti del mondo reale.
