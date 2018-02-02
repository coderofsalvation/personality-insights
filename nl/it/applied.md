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

# Il servizio in azione
{: #applied}

{{site.data.keyword.IBM_notm}} e altri ricercatori hanno convalidato molte ipotesi relative alle applicazioni reali delle caratteristiche della personalità. Questi studi hanno contribuito a guidare lo sviluppo del servizio {{site.data.keyword.personalityinsightsshort}}. I loro risultati forniscono informazioni approfondite su alcuni dei molti modi in cui puoi applicare il servizio ai tuoi obiettivi aziendali e di comunicazione. Per ulteriori informazioni sulla ricerca che sta alla base del servizio {{site.data.keyword.personalityinsightsshort}}, vedi [La scienza alla base del servizio](/docs/services/personality-insights/science.html).
{: shortdesc}

## Studi condotti da ricercatori IBM
{: #appliedIBM}

I seguenti studi condotti dai ricercatori {{site.data.keyword.IBM_notm}} indicano che l'applicazione dei risultati del servizio può produrre risultati tangibili in più domini. Gli studi hanno contribuito direttamente allo sviluppo del servizio. La tabella include i link alle sezioni con ulteriori informazioni su ogni studio.

<table>
  <caption>Tabella 3. Studi di IBM</caption>
  <tr>
    <th style="text-align:left; width:25%">Studio</th>
    <th style="text-align:center; width:25%">Soggetti</th>
    <th style="text-align:left; width:50%">Effetto delle caratteristiche
    della personalità</th>
  </tr>
  <tr>
    <td>
      <a href="#IBMrespond"><strong>Risposta ai tweet</strong></a>
      <br/>(raccolta di informazioni)
    </td>
    <td style="text-align:center">2000 utenti Twitter</td>
    <td>
      <strong>Più probabilità di risposta:</strong> alto punteggio sulle dimensioni e sugli aspetti Big Five
      di desiderio di stimoli, cordialità, livello di attività,
      socievolezza, fiducia, moralità, estroversione e
      gradevolezza<br/><br/>
      <strong>Meno probabilità di risposta:</strong> alto punteggio sugli aspetti Big Five
      di prudenza e ansia
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMretweet"><strong>Retweet</strong></a>
      <br/>(diffusione di informazioni)
    </td>
    <td style="text-align:center">3500 utenti Twitter</td>
    <td>
      <strong>Più probabilità di retweet:</strong> alto punteggio sulle dimensioni e
      sugli aspetti Big Five modestia, apertura mentale e cordialità
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMtarget"><strong>Annunci mirati</strong></a>
      <br/>(pubblicità non richiesta)
    </td>
    <td style="text-align:center">Più di 6000 utenti Twitter
    </td>
    <td>
      <strong>Risposta più favorevole:</strong> alto punteggio sulla dimensione Big Five di
      apertura mentale e basso punteggio sulla dimensione Big Five di stabilità emotiva
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMcampaign"><strong>Campagne di marketing</strong></a>
      <br/>(riscatto di coupon)
    </td>
    <td style="text-align:center">Migliaia di clienti di negozi al dettaglio</td>
    <td>
      <strong>Più probabilità di risposta:</strong> alto punteggio sugli aspetti Big Five di
      ordine, autodisciplina e prudenza e basso punteggio sull'aspetto
      Big Five di smoderatezza
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMbrand"><strong>Preferenza di marca</strong></a>
      <br/>(affinità di marca)
    </td>
    <td style="text-align:center">600 utenti Twitter</td>
    <td>
      <strong>Predittori di preferenza di marca:</strong> dimensioni e aspetti Big Five
      di coscienziosità, conservazione, auto-miglioramento
      e gradevolezza, Esigenze di amore e ideali e Valore di edonismo
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMmember"><strong>Soddisfazione dei membri</strong></a>
      <br/>(adempimento della community)
    </td>
    <td style="text-align:center">Più di 3000 membri della community</td>
    <td>
      <strong>Predittori di soddisfazione dei membri:</strong> caratteristiche come
      rabbia, ansia, lavoro, svago, inibizione, assenso e utilizzo
      del pronome di prima persona
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMreading"><strong>Preferenza di lettura</strong></a>
      <br/>(interesse ai contenuti)
    </td>
    <td style="text-align:center">Più di 200 partecipanti</td>
    <td>
      <strong>Interesse per gli articoli ambientali:</strong> alto punteggio sul Valore di
      autotrascendenza <br/><br/>
      <strong>Interesse per gli articoli relativi al lavoro:</strong> alto punteggio sul Valore di
      auto-miglioramento
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMpreferences"><strong>Previsione delle preferenze
      di consumo</strong></a><br/>(acquisto dei consumatori)
    </td>
    <td style="text-align:center">Centinaia di migliaia di record di dati</td>
    <td>
      <strong>Previsione delle preferenze dei consumatori:</strong> dati demografici e
      caratteristiche della personalità
    </td>
  </tr>
</table>

### Risposta ai tweet
{: #IBMrespond}

{{site.data.keyword.IBM_notm}} ha scoperto che le persone con specifiche caratteristiche della personalità rispondono più prontamente alle attività di raccolta delle informazioni. {{site.data.keyword.IBM_notm}} hanno recentemente condotto uno studio su oltre 2000 utenti di Twitter per comprendere i fattori che influenzano la probabilità di rispondere a tali attività e sviluppare modelli per prevedere le risposte alle domande ([Mahmud et al., 2013](/docs/services/personality-insights/references.html#mahmud2013) e [Mahmud et al., 2014](/docs/services/personality-insights/references.html#mahmud2014)).

{{site.data.keyword.IBM_notm}} ha addestrato il modello utilizzato nello studio mediante due set di dati di domande e risposte in cui agli utenti di Twitter venivano poste domande relative alla posizione o al prodotto. Le domande dipendevano dalla circostanza che gli utenti riferissero di essere presenti in una posizione o di possedere un prodotto. Come funzioni del modello di previsione, {{site.data.keyword.IBM_notm}} ha incluso il comportamento sociale (ad esempio, l'ultimo tasso di risposta e l'attività di tweet), la prontezza (ad esempio, per quanto tempo l'utente è inattivo), le funzioni di categoria del dizionario psicolinguistico LIWC (Linguistic Inquiry and Word Count) e le dimensioni e gli aspetti Big Five.

{{site.data.keyword.IBM_notm}} ha trovato un insieme di caratteristiche della personalità Big Five che sono significative nel predire la probabilità di rispondere. Nello specifico, {{site.data.keyword.IBM_notm}} ha scoperto che le persone che ottengono un alto punteggio sulle dimensioni e sugli aspetti di desiderio di stimoli, cordialità, livello di attività, socievolezza, fiducia, moralità, estroversione e gradevolezza rispondono con maggiore probabilità ai tweet. In alternativa, le persone che ottengono un punteggio elevato sugli aspetti di prudenza e ansia sono meno propensi a rispondere. Questi risultati sono stati ritenuti statisticamente significativi (valore p &lt; 0,05).

### Retweet
{: #IBMretweet}

In modo analogo, {{site.data.keyword.IBM_notm}} ha anche scoperto che le persone con specifiche caratteristiche della personalità rispondono in numero maggiore alle attività di diffusione di informazioni. {{site.data.keyword.IBM_notm}} hanno recentemente condotto un altro studio su più di 3500 utenti di Twitter per comprendere i fattori che aumentano la probabilità di retweettare le informazioni e sviluppare modelli per prevedere il comportamento di retweet ([Lee et al., 2014](/docs/services/personality-insights/references.html#lee2014)).

Come funzioni del modello utilizzato nello studio, {{site.data.keyword.IBM_notm}} ha incluso l'ultima attività dei social media, le informazioni sul profilo dei social media, la prontezza, il dizionario LIWC e le dimensioni e gli aspetti Big Five. Lo studio ha scoperto che un insieme di caratteristiche Big Five è significativo nel predire la tendenza al retweet. Ad esempio, i risultati indicano che le persone che ottengono un punteggio elevato sulle dimensioni e sugli aspetti di modestia, apertura mentale e cordialità sono più propensi a diffondere le informazioni. I risultati sono stati statisticamente significativi (valore p &lt; 0,05).

### Annunci mirati
{: #IBMtarget}

{{site.data.keyword.IBM_notm}} ha rilevato che le persone con specifiche caratteristiche della personalità rispondono in modo più favorevole agli annunci mirati. Di recente, {{site.data.keyword.IBM_notm}} ha creato un servizio di informazioni di viaggio basato su Twitter per testare l'ipotesi che alcuni utenti di Twitter avrebbero risposto in modo più favorevole agli annunci pubblicitari non richiesti dal servizio. L'ipotesi prevedeva che tali utenti sarebbero stati più propensi a fare clic su un link per un annuncio o a seguire un account. {{site.data.keyword.IBM_notm}} ha condotto due studi basati su questo caso di utilizzo e sugli effetti ipotizzati della personalità ([Chen et al., 2015](/docs/services/personality-insights/references.html#chen2015)).

In uno studio di indagine, {{site.data.keyword.IBM_notm}} ha chiesto a 133 utenti di Twitter di segnalare la loro probabile risposta a un tweet che pubblicizza un servizio di informazioni di viaggio. {{site.data.keyword.IBM_notm}} ha quindi utilizzato questionari tradizionali per misurare le personalità degli utenti. In uno studio sul campo, {{site.data.keyword.IBM_notm}} ha inviato tweet che pubblicizzano il servizio a più di 5900 utenti di Twitter che viaggiano. {{site.data.keyword.IBM_notm}} ha quindi usato il servizio {{site.data.keyword.personalityinsightsshort}} per dedurre le caratteristiche della personalità degli utenti dai loro ultimi tweet.

I due studi hanno prodotto risultati uniformi: le persone che ottengono un alto punteggio sulla dimensione di apertura mentale e un basso punteggio sulla dimensione di stabilità emotiva (nevroticismo) rispondono in effetti in modo più favorevole agli annunci. Questi risultati sono veri nonostante i diversi approcci che sono stati utilizzati dagli studi per ottenere le caratteristiche della personalità degli utenti. Gli annunci mirati al 10 percento degli utenti con alta apertura mentale e bassa stabilità emotiva hanno aumentato il tasso di clic dal 6,8 all'11,3 percento e il tasso di follow dal 4,7 all'8,8 percento. I risultati sono stati statisticamente significativi (valore p &lt; 0,05).

### Campagne di marketing
{: #IBMcampaign}

{{site.data.keyword.IBM_notm}} ha recentemente collaborato con un grande rivenditore per dedurre le caratteristiche di migliaia di clienti coinvolti in campagne di marketing. Il rivenditore ha inviato coupon ai suoi clienti. Una risposta positiva è stata definita come riscatto di un qualsiasi coupon. Secondo la teoria della psicologia, le persone che ottengono un alto punteggio sugli aspetti Big Five di ordine, autodisciplina e prudenza e un basso punteggio sull'aspetto di smoderatezza sono più propensi a riscattare i coupon.

{{site.data.keyword.IBM_notm}} ha convalidato l'ipotesi utilizzando i dati dei clienti e le caratteristiche della personalità dedotte. {{site.data.keyword.IBM_notm}} ha prima segmentato la popolazione dei clienti in quartili in base alle caratteristiche della personalità individuali. Utilizzando punteggi percentili normalizzati per le caratteristiche (con una scala da 1 a 100), {{site.data.keyword.IBM_notm}} ha utilizzato una combinazione lineare per calcolare un punteggio combinato per ciascun cliente:

*Ordine + autodisciplina + prudenza + (100 - smoderatezza)*

{{site.data.keyword.IBM_notm}} ha poi confrontato i risultati per i clienti nel quartile più alto con quelli nel quartile più basso, ignorando la metà della popolazione. Lo studio ha scoperto che le persone con le caratteristiche ipotizzate hanno il 40 percento in più di probabilità di rispondere ai coupon rispetto alle persone appartenenti alla popolazione casuale. 

### Preferenza di marca
{: #IBMbrand}

{{site.data.keyword.IBM_notm}} ha condotto uno studio su oltre 600 utenti di Twitter per capire se le caratteristiche della personalità Big Five, Valori ed Esigenze possono predire le preferenze degli utenti per le diverse marche (se una marca piace o meno). Lo studio ha valutato 22 marche di sei categorie: auto di lusso, bevande, fast food, vendita al dettaglio, shampoo e smartphone. {{site.data.keyword.IBM_notm}} ha stabilito la verità di base per la preferenza di marca conducendo un'indagine tra gli utenti. 

Lo studio ha rilevato che le caratteristiche della personalità possono predire la preferenza di marca con un'accuratezza del 65 percento. Nello specifico, lo studio ha scoperto che le dimensioni e gli aspetti Big Five di coscienziosità, conservazione, auto-miglioramento e gradevolezza, le Esigenze di amore e ideali e il Valore di edonismo sono tra le caratteristiche più probabili per prevedere la preferenza di marca.

### Soddisfazione degli membri
{: #IBMmember}

{{site.data.keyword.IBM_notm}} ha condotto uno studio tra i suoi dipendenti che fanno parte di community di lavoro online per indagare se il linguaggio che usano nelle community è correlato al loro livello di soddisfazione con le community ([Matthews et al., 2015](/docs/services/personality-insights/references.html#matthews2015)). {{site.data.keyword.IBM_notm}} ha misurato la soddisfazione della community tramite indagini auto-segnalate.{{site.data.keyword.IBM_notm}} ha esaminato 142 community di lavoro; in base alla dimensione della community, {{site.data.keyword.IBM_notm}} ha intervistato da 20 a 26 membri di ogni community.

Lo studio ha rilevato che l'uso del linguaggio nelle community, come misurato dal dizionario LIWC, è in correlazione con la soddisfazione dei membri. Nello specifico, lo studio ha scoperto che le categorie LIWC come rabbia, ansia, lavoro, svago, inibizione, assenso e pronome di prima persona sono buoni predittori della soddisfazione dei membri. {{site.data.keyword.IBM_notm}} prevede che le caratteristiche calcolate dal testo in una community siano correlate adeguatamente alla soddisfazione dei membri della community.

### Preferenza di lettura
{: #IBMreading}

{{site.data.keyword.IBM_notm}} ha condotto uno studio per comprendere la relazione tra i Valori e gli interessi di lettura ([Hsieh et al., 2014](/docs/services/personality-insights/references.html#hsieh2014)). {{site.data.keyword.IBM_notm}} ha ipotizzato che

1.  Le persone con un valore di autotrascendenza più alto dimostreranno interesse per la lettura di articoli sull'ambiente
1.  Le persone con un valore di auto-miglioramento più alto mostreranno interesse per la lettura di articoli sul lavoro
1.  Le persone con un valore di edonismo più alto mostreranno un maggiore interesse per i contenuti di svago.

{{site.data.keyword.IBM_notm}} ha reclutato più di 200 partecipanti per lo studio dal mercato Amazon Mechanical Turk. I partecipanti hanno completato un'indagine sui Valori e hanno risposto a domande sul loro livello di interesse nella lettura di diversi articoli. 

Lo studio ha convalidato le prime due ipotesi: i partecipanti con un punteggio più alto sul Valore di autotrascendenza hanno mostrato interesse per la lettura di articoli sull'ambiente e i partecipanti con un punteggio più alto sul Valore di auto-miglioramento hanno mostrato interesse per la lettura di articoli sul lavoro. Questi risultati sono stati statisticamente significativi (valore p &lt; 0,05).

Tuttavia, lo studio ha osservato una debole correlazione tra il Valore di edonismo e un interesse per la lettura di articoli di svago. Questo collegamento debole potrebbe indicare che le persone non considerano la lettura un'attività edonistica, indipendentemente dall'argomento dell'articolo. 

### Previsione delle preferenze di consumo
{: #IBMpreferences}

{{site.data.keyword.IBM_notm}} ha collaborato con [Acxiom ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://www.acxiom.com/){: new_window} per verificare se il ritratto della personalità di un individuo può migliorare la precisione predittiva delle preferenze di consumo degli individui rispetto alle previsioni basate esclusivamente su attributi demografici. Lo studio ha esaminato 133 preferenze di consumo per circa 785.000 individui negli Stati Uniti. L'aggiunta delle caratteristiche di Personality Insights ai dati demografici ha migliorato la precisione predittiva per 115 preferenze (86,5 percento) e, per 23 delle preferenze, l'utilizzo del solo Personality Insights fornisce una precisione migliore rispetto all'uso dei soli dati demografici.

Lo studio era basato su due tecnologie: i risultati del servizio {{site.data.keyword.IBM_notm}} {{site.data.keyword.personalityinsightsshort}} e il prodotto Acxiom InfoBase, in particolare gli elementi di dati InfoBase Customer Enhancement&trade;. Acxiom è un fornitore leader nel settore di dati demografici per le esigenze di marketing dei clienti. I dati demografici di Acxiom, come età, sesso, reddito, dimensione del nucleo familiare, fascia di reddito e così via, possono aiutare ad analizzare e migliorare i dati dei clienti per identificare opportunità di vendita e di fidelizzazione, colmare le lacune nelle informazioni di contatto dei clienti, assistere nell'analisi delle informazioni dei clienti e identificare le prospettive e altro ancora.

Lo studio ha analizzato 133 attributi di consumo comportamentale sulla base di 22 caratteristiche di {{site.data.keyword.personalityinsightsshort}} e quattro categorie demografiche (sesso, istruzione, reddito familiare ed età). I risultati mostrano che 115 delle 133 preferenze di consumo esibivano una migliore precisione predittiva quando i dati demografici sono stati ampliati con le caratteristiche della personalità. Inoltre, la mancanza di miglioramento delle restanti 18 preferenze potrebbe essere dovuta alla natura del confronto e al modo in cui sono stati calcolati i dati. Esperimenti futuri tenteranno confronti più complessi per vedere se un diverso approccio migliora ulteriormente la precisione.

I risultati complessivi rivelano che le caratteristiche di {{site.data.keyword.personalityinsightsshort}} sono utili nel predire le varie preferenze di consumo. L'utilizzo dei dati demografici insieme alle caratteristiche della personalità fornisce di solito una migliore precisione predittiva. Ma {{site.data.keyword.personalityinsightsshort}} da solo è una buona alternativa quando i dati demografici non sono disponibili.

Per ulteriori informazioni sullo studio, vedi <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Improving-Consumption-Preferences-Accuracy.pdf" download="Improving-Consumption-Preferences-Accuracy.pdf">Improving-Consumption-Preferences-Accuracy.pdf <img src="../../icons/launch-glyph.svg" alt="Icona link esterno" title="Icona link esterno" class="style-scope doc-content"></a>. Per ulteriori informazioni sul modello di preferenze di consumo utilizzato nello studio, vedi [Liu et al. (2016)](/docs/services/personality-insights/references.html#liu2016).

## Studi condotti da altri ricercatori
{: #appliedOthers}

Molti studi condotti da ricercatori al di fuori di {{site.data.keyword.IBM_notm}} indicano che la personalità può prevedere ed essere correlata a risultati diversi. Le seguenti sezioni descrivono questi studi, che confermano e rafforzano la ricerca descritta nella sezione precedente.

### Preferenze dei consumatori
{: #otherConsumer}

-   [Hirsh et al. (2012)](/docs/services/personality-insights/references.html#hirsh2012) hanno intervistato le persone sui vari messaggi di marketing. Hanno scoperto che le persone rispondono in modo più positivo ai messaggi adattati alla loro personalità.
-   [Chen (2011)](/docs/services/personality-insights/references.html#chen2011) ha rilevato che nel contesto del marketing online, le persone con maggiore apertura mentale sono più intellettualmente curiose e aperte a nuove idee. Quindi queste persone sono più propense a provare cose nuove.
-   [Westfall (1962)](/docs/services/personality-insights/references.html#westfall1962) ha rilevato che esistono differenze di personalità tra i proprietari di auto decappottabili e i proprietari di auto standard o compatte. I consumatori che ottengono un punteggio elevato nella dimensione di gradevolezza e nell'aspetto di ordine della dimensione di coscienziosità preferiscono le macchine tradizionali. I consumatori che ottengono un punteggio elevato nella dimensione di apertura mentale potrebbero, d'altra parte, indicare una macchina decappottabile come prima scelta.
-   [Choo e Mokhtarian (2002)](/docs/services/personality-insights/references.html#choo2002) hanno esaminato la relazione tra scelta del tipo di veicolo e fattori come personalità, stile di vita, attitudine e dati demografici. Hanno scoperto che le persone che ottengono un punteggio elevato negli aspetti di spirito di avventura, desiderio di stimoli e sfida dell'autorità potrebbero preferire automobili dalle potenti prestazioni. Le persone che ottengono un punteggio elevato nella dimensione di gradevolezza potrebbero, tuttavia, non apprezzare le automobili potenti. 
-   [Kassarjian (1971)](/docs/services/personality-insights/references.html#kassarjian1971) ha scoperto che i proprietari di automobili di solito tendono a percepire il tipo di automobile che acquistano come estensione della loro personalità. In [Coscienza ambientale](#otherEnvironment) viene descritto come la personalità di un individuo possa influenzare la sua preferenza per i veicoli a basse emissioni.
-   [Myszkowski e Storme (2012)](/docs/services/personality-insights/references.html#myszkowski2012) hanno scoperto che l'apertura mentale predice in modo significativo la tendenza delle persone a preferire e rispondere a prodotti ben progettati. Il loro studio suggerisce che le persone con *bassa* apertura mentale tendono a rispondere in modo più intenso all'aspetto di un prodotto, amplificando le scelte di prodotto orientate alla progettazione. Al contrario, le persone con *alta* apertura mentale tendono a concentrarsi maggiormente su altri aspetti del prodotto, portandoli a ignorare le caratteristiche estetiche.
-   [Lin (2002)](/docs/services/personality-insights/references.html#lin2002) e [Sarli and Tat (2011)](/docs/services/personality-insights/references.html#sarli2011) hanno riportato che le caratteristiche della personalità influiscono sulle preferenze di marca di ognuno.

### Preferenze personali
{: #otherPersonal}

-   [Hu e Pu (2011)](/docs/services/personality-insights/references.html#hu2011) hanno rilevato che nel settore della musica i consigli hanno più successo quando sfruttano le correlazioni tra la personalità delle persone e le loro preferenze musicali.
-   [Chamorro-Premuzic e Furnham (2007)](/docs/services/personality-insights/references.html#chamorro2007) hanno anche segnalato che le differenze individuali di personalità e abilità cognitive potrebbero determinare come le persone sperimentano la musica. [Rentfrow e Gosling (2003)](/docs/services/personality-insights/references.html#rentfrow2003) hanno riportato risultati simili in uno studio precedente.
-   [Golbeck e Norris (2013)](/docs/services/personality-insights/references.html#golbeck2013) hanno trovato correlazioni tra personalità e preferenze cinematografiche tra gli utenti di Netflix&trade;.

### Abitudini di spesa
{: #otherSpending}

-   [Pirog e Roberts (2007)](/docs/services/personality-insights/references.html#pirog2007) hanno rivelato la relazione tra abitudini di spesa e personalità. Si sono concentrati sull'"uso improprio" (o "abuso") delle carte di credito tra gli studenti universitari. Hanno scoperto che gli studenti che ottengono un punteggio elevato in coscienziosità tendono a utilizzare carte di debito o contanti e a non abusare delle carte di credito. Al contrario, un alto nevroticismo (stabilità emotiva) è probabilmente associato a un uso eccessivo delle carte di credito. 

### Profili di rischio
{: #otherRisk}

-   [Lauriola e Levin (2001)](/docs/services/personality-insights/references.html#lauriola2001) hanno dimostrato che la personalità influenza il comportamento decisionale rischioso degli individui negli investimenti finanziari. Hanno concluso che le persone che ottengono un punteggio elevato nell'apertura alle esperienze tendono a fare investimenti rischiosi. Al tempo stesso, il nevroticismo (stabilità emotiva) potrebbe rendere le persone meno disposte a correre tali rischi.
-   [Nicholson et al. (2001)](/docs/services/personality-insights/references.html#nicholson2001) hanno sviluppato ulteriormente la correlazione tra le caratteristiche Big Five e i profili di rischio. Le loro scoperte rivelano che la gradevolezza e la coscienziosità riducono la disponibilità delle persone a rischiare in generale. Al contrario, le persone che ottengono un punteggio elevato in estroversione hanno maggiori probabilità di prendere decisioni rischiose. 
-   [Tok (2011)](/docs/services/personality-insights/references.html#tok2011) ha identificato la relazione tra le caratteristiche della personalità Big Five e la partecipazione a sport avventurosi e rischiosi come sci, mountain bike, volo, deltaplano, parapendio e immersioni. Quattro delle caratteristiche Big Five influenzano direttamente la partecipazione agli sport rischiosi: alti punteggi in estroversione, apertura mentale e nevroticismo (stabilità emotiva) aumentano la probabilità di partecipazione a questi sport; un alto punteggio in coscienziosità riduce la volontà di partecipare.
-   [Hymbaugh e Garrett (1974)](/docs/services/personality-insights/references.html#hymbaugh1974) hanno studiato le caratteristiche della personalità dei paracadutisti. Hanno scoperto che i paracadutisti di solito hanno uno spirito di avventura e desiderio di stimoli maggiore rispetto alla popolazione generale. 

### Prestazioni professionali
{: #otherProfessional}

-  [Barrick e Mount (1991)](/docs/services/personality-insights/references.html#barrick1991) hanno esplorato la relazione tra le dimensioni delle personalità Big Five e le prestazioni lavorative. Hanno scoperto che le dimensioni della personalità come la coscienziosità sono legate alle prestazioni lavorative per tutti i gruppi di lavoro che hanno studiato (professionisti, manager, vendite, polizia, qualificati e semi-qualificati).
-   [Hurtz e Donovan (2000)](/docs/services/personality-insights/references.html#hurtz2000) hanno riportato che la coscienziosità è la caratteristica della personalità più predittiva delle prestazioni lavorative.
-   [Lim e Ployhart (2004)](/docs/services/personality-insights/references.html#lim2004) hanno rilevato che l'estroversione è positivamente correlata con le abilità di leadership.
-   [Judge et al. (2002)](/docs/services/personality-insights/references.html#judge2002) hanno riportato che le persone estroverse sono più soddisfatte sul posto di lavoro; il lavoro dà loro l'opportunità di sperimentare un livello ottimale di stimolazione. Al contrario, gli individui introversi sono meno soddisfatti sul posto di lavoro a causa di troppa stimolazione.
-   [van Vianen et al. (2012)](/docs/services/personality-insights/references.html#vanvianen2012) hanno riportato le differenze individuali nell'adattabilità e nelle sue cause, correlazioni e conseguenze. Hanno scoperto che la coscienziosità, l'estroversione e l'apertura mentale si correlano positivamente con l'adattabilità professionale.

### Rendimento scolastico
{: #otherAcademic}

-   [Chamorro-Premuzic e Furnham (2003)](/docs/services/personality-insights/references.html#chamorro2003) hanno riportato uno studio longitudinale in cui hanno scoperto che le caratteristiche della personalità influiscono sul rendimento scolastico. Nello specifico, hanno scoperto che il nevroticismo (stabilità emotiva) potrebbe compromettere il rendimento scolastico e che la coscienziosità potrebbe portare a risultati accademici più elevati.
-   [Komarraju e Karau (2005)](/docs/services/personality-insights/references.html#komarraju2005) hanno rilevato che alcune caratteristiche della personalità influenzano il comportamento di un individuo rispetto all'apprendimento dell'auto-miglioramento. Lo studio rivela che un'alta apertura mentale e coscienziosità spesso portano ad un maggiore interesse nell'apprendimento dell'auto-miglioramento e che l'alto nevroticismo (stabilità emotiva) diminuisce la motivazione per tale apprendimento.

### Relazioni professionali
{: #otherProRelations}

-   [Flynn e Smith (2007)](/docs/services/personality-insights/references.html#flynn2007) hanno rilevato che la personalità influenza le preferenze di interazione tra professionisti e clienti. Ad esempio, i pazienti con un alto grado di coscienziosità e apertura mentale preferiscono essere coinvolti attivamente nella decisione del trattamento da intraprendere. I pazienti con alti livelli di gradevolezza o stabilità emotiva (nevroticismo) preferiscono che i medici prendano l'iniziativa nelle decisioni importanti sulla salute.
-   [Duberstein et al. (2007)](/docs/services/personality-insights/references.html#duberstein2007) hanno riportato analogamente che le personalità dei medici influenzano il livello di soddisfazione dei loro pazienti. Ad esempio, i pazienti hanno riferito di essere più soddisfatti con i medici che hanno ottenuto punteggi relativamente alti nell'apertura mentale e medi nella coscienziosità.

### Relazioni personali
{: #otherPerRelations}

-   [Botwin et al. (1997)](/docs/services/personality-insights/references.html#botwin1997) hanno scoperto che la personalità influenza le relazioni romantiche. Le caratteristiche della personalità del partner determinano in modo significativo l'insoddisfazione coniugale, in particolare quando il partner ottiene un punteggio inferiore in termini di gradevolezza, stabilità emotiva e apertura mentale di quanto desiderato. 

### Salute
{: #otherHealth}

-   [Turiano et al. (2012)](/docs/services/personality-insights/references.html#turiano2012) hanno riportato uno studio longitudinale su un arco temporale di 10 anni in cui è emerso che le caratteristiche Big Five prevedevano risultati correlati alla salute. Ad esempio, tutte le caratteristiche tranne l'apertura mentale hanno previsto la salute fisica percepita e tutte le caratteristiche tranne la gradevolezza hanno previsto un numero di giorni di lavoro limitato a causa della salute fisica.
-   [Masui et al. (2006)](/docs/services/personality-insights/references.html#masui2006) hanno rilevato che i punteggi più alti nelle specifiche caratteristiche della personalità di coscienziosità, estroversione e apertura mentale sono associati alla longevità. Altri ricercatori hanno anche scoperto una relazione tra le caratteristiche della personalità Big Five e l'aspettativa di vita.
-   [Roberts et al. (2007)](/docs/services/personality-insights/references.html#roberts2007) hanno riportato che specifiche caratteristiche della personalità predicono fasi importanti della vita, come la mortalità, il divorzio e il successo sul lavoro. 

### Dieta ed esercizio
{: #otherDiet}

-   [Shepherd e Sparks (1994)](/docs/services/personality-insights/references.html#shepherd1994) hanno sviluppato la relazione tra personalità e scelta dei cibi. Il loro studio rivela che le persone con un punteggio elevato in stabilità emotiva (nevroticismo), specialmente nell'aspetto di smoderatezza, tendono a consumare cibi ricchi di grassi.
-   [Elfhag e Morey (2008)](/docs/services/personality-insights/references.html#elfhag2008) hanno rivelato che la coscienziosità è correlata positivamente a una preferenza per i cibi a basso contenuto di grassi. Nello specifico, gli aspetti di autodisciplina e doverosità della dimensione di coscienziosità influenzano positivamente il consumo di cibi a basso contenuto di grassi e (poiché la gestione del peso è strettamente correlata alla scelta del cibo) il regolare controllo del peso.
-   [Heaven at al. (2001)](/docs/services/personality-insights/references.html#heaven2001) hanno riportato che il consumo di cibi sani è correlato a due dimensioni Big Five. Le persone con alto nevroticismo (stabilità emotiva) sono in genere meno propense a scegliere cibi sani, mentre le persone con alta coscienziosità li preferiscono. Il documento cita anche alcuni aspetti precisamente collegati alla scelta del cibo: gli interessi artistici (dalla dimensione di apertura mentale) e l'autodisciplina (dalla dimensione di coscienziosità) sono correlati positivamente a un maggiore consumo di cibi sani; al contrario, essere suscettibili allo stress ha una correlazione alquanto negativa con il consumo di tali alimenti.
-   [Lusk (2012)](/docs/services/personality-insights/references.html#lusk2012) ha scoperto che gli amanti del cibo ottengono un alto punteggio nell'apertura all'esperienza. L'apertura mentale potrebbe motivare le persone a provare cibi diversi e aiutarli a diventare veri intenditori di cibo. 
-   [Courneya e Hellsten (1998)](/docs/services/personality-insights/references.html#courneya1998) hanno scoperto che la personalità influenza la tendenza di un individuo a perseguire abitudini associate a uno stile di vita sano, incluso l'esercizio fisico. L'estroversione e la coscienziosità sono correlate positivamente a un esercizio fisico più frequente, mentre il nevroticismo (stabilità emotiva) potrebbe influenzare negativamente la frequenza dell'esercizio.

### Mangiare fuori
{: #otherDining}

-   [Kim et al. (2010)](/docs/services/personality-insights/references.html#kim2010) hanno dimostrato che l'apertura all'esperienza è correlata positivamente a mangiare fuori più spesso. Le persone che ottengono un basso punteggio nell'apertura mentale di solito preferiscono mangiare fuori meno spesso.
-   [van Trijp e Steenkamp (1992)](/docs/services/personality-insights/references.html#vantrijp1992) hanno scoperto che il mangiare fuori è correlato all'aspetto di desiderio di stimoli (desiderio di sensazioni) della dimensione di estroversione. 

### Coscienza ambientale
{: #otherEnvironment}

-   [Griskevicius et al. (2010)](/docs/services/personality-insights/references.html#griskevicius2010) hanno scoperto che la personalità di una persona influenza il suo interesse per le questioni ambientali. Hanno studiato la relazione tra la personalità e il comportamento pro-ambientale, come l'utilizzo di veicoli a basse emissioni e il perseguimento di una vita più attenta all'ecologia, al giardinaggio, al riciclaggio e così via. Per la maggior parte delle persone, i livelli più elevati di gradevolezza, apertura mentale e coscienziosità sono associati a una maggiore inclinazione a un comportamento pro-ambientale.
-   [Fraj e Martinez (2006)](/docs/services/personality-insights/references.html#fraj2006) hanno scoperto che la personalità influenza la decisione di acquistare prodotti che rispettano l'ambiente. Le persone caratterizzate da aspetti di personalità come l'estroversione, la gradevolezza e la coscienziosità sono più propense ad acquistare tali prodotti.

### Servizio alla comunità
{: #otherCommunity}

-   [Penner et al. (2005)](/docs/services/personality-insights/references.html#penner2005) hanno riportato che la personalità di un individuo influenza il suo impegno nel servizio alla comunità. In un documento di revisione, gli autori hanno riepilogato diversi fattori di personalità che influenzano il comportamento prosociale. Hanno scoperto che l'estroversione e la gradevolezza hanno influenze positive sull'impegno nel servizio alla comunità. In particolare, gli aspetti di altruismo e cooperazione della dimensione di gradevolezza potrebbero avere il massimo impatto, mentre l'aspetto di socievolezza della dimensione di estroversione ha una correlazione positiva più precisa con il servizio alla comunità.

### Religione e spiritualità
{: #otherReligion}

-   [Adorno et al. (1950)](/docs/services/personality-insights/references.html#adorno1950), nel loro libro classico *The Authoritarian Personality*, riportano una possibile correlazione tra le caratteristiche della personalità e la religione. Essi suggeriscono che le persone che ottengono un alto punteggio in gradevolezza sono più religiose, mentre quelle con un alto punteggio in sfida dell'autorità sono meno motivate a partecipare a pratiche religiose e spirituali.
