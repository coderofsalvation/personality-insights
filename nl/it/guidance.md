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

# Indicazioni di utilizzo
{: #guidance}

Gli utenti stanno applicando il servizio {{site.data.keyword.personalityinsightsshort}} a un numero crescente di casi di utilizzo. Applicano il servizio per offrire ai clienti consigli personalizzati sui prodotti tramite chioschi in negozio. Esplorano e analizzano le differenze nelle personalità dei presidenti degli Stati Uniti come dedotte dai loro Discorsi sullo stato dell'Unione. E integrano il servizio con un altro prodotto nel portfolio {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}}, {{site.data.keyword.watson}} Explorer, per dimostrare come un consulente per gli investimenti possa offrire opzioni adeguate in base ai ritratti di personalità degli investitori. (Per ulteriori informazioni, vedi [Casi di utilizzo](/docs/services/personality-insights?topic=personality-insights-usecases).)
{: shortdesc}

Durante lo sviluppo di questi e altri possibili casi di utilizzo, {{site.data.keyword.IBM_notm}} ha parlato con banche, operatori sanitari, società di gestione dell'esperienza del cliente e agenzie federali. Queste conversazioni spesso generano domande sugli scenari di utilizzo applicabili.

-   Qual è il tipo di testo migliore per dedurre la personalità di un individuo? Il testo deve essere di natura riflessiva? Se è così, quanto riflessivo e come si misura la riflessione? Vedi [Qual è il tipo di testo ottimale per dedurre la personalità?](#optimal)
-   Come si interpreta il testo scritto da una persona in merito a un'altra persona? La personalità di un autore può essere dedotta dalle sue opere narrative? Il testo scritto da più persone può essere combinato per ottenere un ritratto di personalità? Vedi [Interpretazione dei risultati da diversi tipi di testo](#interpreting).
-   I ritratti di personalità possono essere dedotti dal testo generato dai servizi di trascrizione o traduzione? Vedi [Deduzione della personalità dal testo generato](#inferring).
-   I ritratti di personalità possono essere applicati ad applicazioni come l'abbinamento di individui, il monitoraggio e la previsione della salute mentale e il monitoraggio di elementi radicali e violenti tramite i social media? Vedi [Utilizzo di ritratti di personalità per applicazioni specifiche](#applying).
-   La personalità di un individuo si evolve con l'età? Vedi [La personalità di una persona cambia nel tempo?](#evolve)

## Qual è il tipo di testo ottimale per dedurre la personalità?
{: #optimal}

Che tipo di testo è più adatto per dedurre la personalità? Il testo deve essere riflessivo, autoriflessivo, formale o informale? Come si misurano le parole usate nella vita quotidiana? Queste parole sono di natura riflessiva? Le risposte a queste domande possono aiutarti a selezionare l'input più appropriato per applicare il servizio nel modo più efficace.

Il lavoro di {{site.data.keyword.IBM_notm}} sul servizio {{site.data.keyword.personalityinsightsshort}} si basa sulla premessa fondamentale che le parole che una persona utilizza nella vita quotidiana rivelano la sua personalità ([Pennebaker e altri, 2001](/docs/services/personality-insights?topic=personality-insights-references#pennebaker2001) e [Pennebaker e altri, 2007](/docs/services/personality-insights?topic=personality-insights-references#pennebaker2007)). Il servizio può analizzare le parole scritte dagli individui su loro stessi o su qualsiasi argomento. Affinché il servizio generi un ritratto di personalità accurato, gli individui devono scegliere e scrivere le parole. 

{{site.data.keyword.IBM_notm}} crede che il testo che viene utilizzato per dedurre la personalità dell'individuo debba, idealmente, essere riflessivo. La scrittura riflessiva espone le esperienze e le risposte personali dell'autore. Richiede che l'autore metta una certa quantità di pensiero nelle parole che vengono scelte. Ad esempio, il testo può includere le opinioni, gli atteggiamenti, i sentimenti e le osservazioni dello scrittore su qualcuno o qualcosa. Può anche esprimere ciò che piace o non piace allo scrittore. Ma deve riflettere la scelta di parole dello scrittore. 

{{site.data.keyword.IBM_notm}} non ha trovato riferimenti espliciti nella letteratura psicolinguistica sulla necessità di una riflessione nel testo usato per dedurre la personalità. Tuttavia, {{site.data.keyword.IBM_notm}} ha osservato che alcuni studi utilizzano parole tratte da testi raccolti in un ambiente di laboratorio in cui alle persone è stato chiesto di scrivere brevi saggi su argomenti specifici. Questo tipo di scrittura richiede implicitamente una certa dose di riflessione. Altri studi hanno utilizzato testi tratti da esempi naturali come blog su vari argomenti, tweet, e-mail o persino comunicazioni estratte dal gioco *World of Warcraft*. Tutti questi studi presumono che le parole utilizzate nella vita quotidiana rivelino la personalità perché tendono a riflettere i pensieri dello scrittore. 

Altri studi dimostrano che la scrittura emotiva, la scrittura controllata, i blog e le trascrizioni vocali sono adatti per dedurre la personalità. Al contrario, gli articoli scientifici sono solo marginalmente adatti per dedurre la personalità. Inoltre, la letteratura indica che arrivare a una misura precisa della personalità è ulteriormente complicato da un testo che

-   è privo di autenticità, come sarcasmo, ironia, modifica intesta o più autori
-   include errori ortografici, parole tecniche, significati alternativi per le parole, negazione e frasi piuttosto che singole parole
-   include gruppi di confronto inappropriati, come la scrittura professionale rispetto a quella personale e la scrittura tecnica rispetto a quella emotiva

## Interpretazione dei risultati da diversi tipi di testo
{: #interpreting}

Il tipo di testo da analizzare può avere un effetto significativo sulla qualità dei risultati del servizio {{site.data.keyword.personalityinsightsshort}}. Le seguenti sezioni illustrano come interpretare i risultati ottenuti da fonti diverse:

-   [Interpretazione dei risultati dal testo su altre persone](#writingaboutothers)
-   [Interpretazione dei risultati dalle opere narrative](#fictionalworks)
-   [Interpretazione dei risultati dal testo da più individui](#multipleindividuals)

### Interpretazione dei risultati dal testo su altre persone
{: #writingaboutothers}

Per dedurre in modo attendibile la personalità di un individuo, il testo deve essere scritto *dall'*individuo o può essere scritto *sull'*individuo da qualcun altro? Quando una persona scrive in merito a un'altra persona, quale personalità viene dedotta dal testo?

L'intuizione di {{site.data.keyword.IBM_notm}} è che la scrittura riflette sempre la personalità dell'autore, indipendentemente dall'argomento. Ad esempio, se l'individuo A scrive un testo sull'individuo B, un'analisi del testo deduce la personalità dell'individuo A. Sebbene l'individuo A stia scrivendo sull'individuo B, è l'individuo A che sceglie le parole per esprimere qualcosa sull'individuo B. Tuttavia, {{site.data.keyword.IBM_notm}} non ha testato esplicitamente questo scenario.

### Interpretazione dei risultati dalle opere narrative
{: #fictionalworks}

{{site.data.keyword.IBM_notm}} non consiglia di dedurre la personalità di un autore dalle sue opere narrative. Quando scrivono narrativa, gli autori descrivono ogni personaggio in modo diverso, costruiscono un dialogo per riflettere le personalità dei loro personaggi e predefiniscono la personalità di ogni personaggio nella loro mente.

L'utilizzo di un testo che è pensato per riflettere la personalità di un personaggio immaginario personificato per dedurre la personalità del creatore di quel personaggio è discutibile. Mentre ogni autore ha uno stile unico, i personaggi sono sempre volutamente preconfigurati. Tuttavia, la personalità di un autore può essere dedotta dai libri di saggistica dell'autore, dalle trascrizioni di interviste o da altri lavori come presentazioni, prologhi, riconoscimenti o dediche. 

### Interpretazione dei risultati dal testo da più individui
{: #multipleindividuals}

Un caso di utilizzo comune del servizio {{site.data.keyword.personalityinsightsshort}} è l'analisi dei follower di un marchio o di un'azienda. I follower sono definiti come persone che seguono un'azienda su Twitter o su una pagina pubblica di Facebook. In questo scenario, l'obiettivo è ricavare la personalità generale dei follower di un'azienda. Un metodo preferito consiste nel raccogliere sufficiente testo scritto dai membri di un gruppo per calcolare la personalità di ogni singolo membro. Le personalità vengono quindi raggruppate in gruppi distinti. Questi gruppi rappresentano persone con caratteristiche distintive della personalità che seguono l'azienda.

Se dai membri del gruppo non è disponibile testo sufficiente, il testo che è stato scritto da molti membri può essere combinato e analizzato per produrre un ritratto di personalità medio o composito per il gruppo. Questo approccio può fornire un'indicazione delle qualità dominanti del gruppo, ma la precisione di questo metodo diminuisce con la diversità della popolazione. Occorre prestare attenzione quando interpreti i ritratti ottenuti dall'aggregazione del testo di più individui. Il lavoro di {{site.data.keyword.IBM_notm}} in questo settore è ancora nelle sue fasi iniziali; {{site.data.keyword.IBM_notm}} riporterà le sue conclusioni una volta scoperti risultati convincenti.

## Deduzione della personalità dal testo generato
{: #inferring}

L'analisi del testo generato dai servizi di trascrizione o traduzione può influire sull'affidabilità dei risultati del servizio {{site.data.keyword.personalityinsightsshort}}. Le seguenti sezioni illustrano gli effetti della deduzione della personalità dal testo generato:

-   [Deduzione della personalità dalle trascrizioni vocali](#transcription)
-   [Deduzione della personalità dal testo tradotto](#translation)

### Deduzione della personalità dalle trascrizioni vocali
{: #transcription}

I motori di trascrizione vocale, come ad esempio il servizio {{site.data.keyword.IBM_notm}} {{site.data.keyword.speechtotextshort}}, generano testo scritto dal testo vocale. I diversi motori di trascrizione hanno diverse gamme di precisione. I clienti che trascrivono la voce in testo da utilizzare come input per il servizio {{site.data.keyword.personalityinsightsshort}} devono essere consapevoli che i risultati possono variare notevolmente a seconda delle prestazioni del motore. Nello specifico, {{site.data.keyword.IBM_notm}} consiglia a clienti e partner commerciali di determinare la qualità della trascrizione rispetto a due tipi di errori:

-   *Rimozione:* una parola pronunciata viene omessa dalla trascrizione.
-   *Sostituzione:* una parola pronunciata viene trascritta in modo errato.

La sostituzione può essere un problema più serio perché può introdurre parole che non sono state pronunciate ma che corrispondono alle parole utilizzate per determinare la personalità. Prima di utilizzare il testo trascritto, considera la possibilità di correggere manualmente il testo di una raccolta di prova e di contare gli errori che trovi. Quindi, confronta i risultati del testo generato automaticamente con la versione corretta manualmente per determinare la varianza nei risultati a causa degli errori di trascrizione.

### Deduzione della personalità dal testo tradotto
{: #translation}

I servizi di traduzione linguistica traducono il testo scritto in una lingua in un'altra lingua. Come per la trascrizione vocale, sorge la domanda se il testo tradotto possa essere usato come input per il servizio {{site.data.keyword.personalityinsightsshort}}. {{site.data.keyword.IBM_notm}} non consiglia di utilizzare il testo ottenuto dai servizi di traduzione come input per il servizio {{site.data.keyword.personalityinsightsshort}}. A seconda del servizio di traduzione, i risultati della traduzione e della deduzione della personalità possono variare notevolmente. Le parole, i loro sensi e le sensibilità culturali tendono a perdersi nella traduzione, producendo risultati non validi.

{{site.data.keyword.IBM_notm}} consiglia di utilizzare come input solo il testo scritto nelle lingue in cui il servizio {{site.data.keyword.personalityinsightsshort}} è abilitato. Le versioni del servizio abilitate alla lingua

-   Analizzano il testo di input nella sua lingua nativa. 
-   Utilizzano dizionari di lingua nativa per identificare le caratteristiche della personalità.
-   Utilizzano modelli calibrati per la lingua nativa per produrre risultati statistici.

Se devi analizzare il testo tradotto, {{site.data.keyword.IBM_notm}} ti consiglia di tradurre prima manualmente del testo di esempio utilizzando i servizi di un esperto di linguaggi umani. Puoi quindi confrontare i risultati che il servizio {{site.data.keyword.personalityinsightsshort}} ottiene dal testo tradotto manualmente e automaticamente per comprendere la varianza nei risultati.

{{site.data.keyword.IBM_notm}} continua ad aggiungere più lingue all'aumentare della domanda aziendale. {{site.data.keyword.IBM_notm}} comprende che il servizio {{site.data.keyword.personalityinsightsshort}} potrebbe non supportare la tua lingua madre abbastanza velocemente per i tuoi scopi. {{site.data.keyword.IBM_notm}} sta conducendo dei test per confrontare i risultati provenienti dall'abilitazione della lingua nativa con i risultati ottenuti dai servizi di traduzione linguistica e riferirà i risultati non appena saranno disponibili. 

## Utilizzo di ritratti di personalità per applicazioni specifiche
{: #applying}

Il servizio {{site.data.keyword.personalityinsightsshort}} può essere applicato a innumerevoli casi di utilizzo. Le seguenti sezioni descrivono l'utilizzo di ritratti di personalità per alcuni scopi specifici:

-   [Abbinamento di individui](#matching)
-   [Monitoraggio e previsione della salute mentale](#mentalhealth)
-   [Monitoraggio di elementi radicali e violenti tramite i social media](#monitoring)

### Abbinamento di individui
{: #matching}

Creare un buon abbinamento tra le persone può migliorare l'interazione e gli esiti nelle relazioni. Questa nozione si applica anche al team building all'interno di un'azienda e per l'interazione con i clienti in una vasta gamma di settori. In uno studio sull'abbinamento medico-paziente, i ricercatori hanno scoperto che i pazienti preferiscono i medici che sono simili a loro. In effetti, l'abbinamento di medici e pazienti crea fiducia e incoraggia la comunicazione, che può migliorare l'accordo e portare a un trattamento più efficace ([Godager, 2012](/docs/services/personality-insights?topic=personality-insights-references#godager2012)).

La personalità influenza anche le preferenze di interazione tra professionisti e clienti. Ad esempio, i pazienti con un alto grado di coscienziosità e apertura mentale preferiscono essere coinvolti attivamente nella decisione del trattamento da intraprendere. I pazienti con alti livelli di gradevolezza o nevroticismo preferiscono che i medici prendano l'iniziativa nelle decisioni importanti sulla salute ([Flynn e Smith, 2007](/docs/services/personality-insights?topic=personality-insights-references#flynn2007)).

### Monitoraggio e previsione della salute mentale
{: #mentalhealth}

{{site.data.keyword.IBM_notm}} ritiene che la diagnosi della malattia sia eseguita meglio da un professionista medico qualificato. Potrebbe essere possibile rilevare alcuni segnali dello stato mentale delle persone dal loro uso delle parole. Tuttavia, {{site.data.keyword.IBM_notm}} non ha condotto studi di verifica di base o esplorato la possibilità di stabilire una base scientifica per tale lavoro. 

I clienti e i partner commerciali che sono interessati a utilizzare il servizio {{site.data.keyword.personalityinsightsshort}} per la diagnosi della salute mentale sono invitati a progettare e condurre esperimenti di verità di base per tali casi di utilizzo. La ricerca attiva in questa area include il lavoro che mette in relazione la personalità con gli esiti di salute ([Israel e altri, 2014](/docs/services/personality-insights?topic=personality-insights-references#israel2014)). Include anche un lavoro che mira a prevedere il post parto e altre forme di depressione dai social media ([De Choudhury e altri, 2013a](/docs/services/personality-insights?topic=personality-insights-references#dechoudhury2013a) e [De Choudhury e altri, 2013b](/docs/services/personality-insights?topic=personality-insights-references#dechoudhury2013b)).

### Monitoraggio di elementi radicali e violenti tramite i social media
{: #monitoring}

Le agenzie governative di tutto il mondo sono costantemente alla ricerca di modi per rilevare i primi segnali della radicalizzazione di individui o gruppi di individui attraverso i canali dei social media. La deduzione della personalità dalla scrittura degli individui è un'applicazione tradizionale del servizio {{site.data.keyword.personalityinsightsshort}}. Quindi non sorprende che l'utilizzo del servizio per dedurre elementi radicali e violenti tramite i social media sia un caso di utilizzo percorribile. Deduzioni affidabili richiedono non solo le caratteristiche della personalità, ma una miriade di altri attributi come il sesso, l'età e l'area geografica. {{site.data.keyword.IBM_notm}} non ha studi per convalidare o invalidare questo caso di utilizzo. I clienti e i partner commerciali sono invitati a condurre degli studi per esplorare questo caso di utilizzo in base ai loro obiettivi e requisiti specifici.

## La personalità di una persona cambia nel tempo?
{: #evolve}

La personalità di una persona evolve nel tempo? Se è così, con quale frequenza dovrebbe essere utilizzato il servizio {{site.data.keyword.personalityinsightsshort}} per dedurre la personalità di una persona? Diversi studi riportano prove a favore e contro la teoria secondo cui la personalità di una persona si stabilizza nell'età adulta. Nel suo lavoro fondamentale del 1890 sulla misurazione della stabilizzazione della personalità, *The Principles of Psychology*, lo psicologo di Harvard, William James, ha osservato che "Il carattere della maggior parte di noi si solidifica come il gesso entro i trent'anni, per non ammorbidirsi mai più". Ma studi più recenti riportano che la personalità si evolve nel tempo:

-   [Helson e altri (2002)](/docs/services/personality-insights?topic=personality-insights-references#helson2002) riferisce che "l'idea che il cambiamento di personalità sia più pronunciato prima dei 30 anni e poi raggiunga un livello fisso non ha ricevuto alcun sostegno". Gli autori hanno condotto uno studio longitudinale su due coorti per un periodo di 40 anni. Osservano che il periodo di vita e il clima sociale sono fattori significativi nel cambiamento di personalità nell'età adulta. Commentano che "I punteggi su Dominanza e Indipendenza hanno raggiunto il picco nella fascia media di entrambe le coorti e i punteggi su Responsabilità sono stati più bassi durante gli anni culminanti della cultura dell'individualismo".
-   [Scollon e Diener (2006)](/docs/services/personality-insights?topic=personality-insights-references#scollon2006) si sono proposti di esaminare le differenze individuali nel cambiamento di estroversione, nevroticismo e soddisfazione nel lavoro e nelle relazioni nel tempo. Gli autori sottolineano che un aumento della soddisfazione nel lavoro e nelle relazioni è associato a diminuzioni di nevroticismo e aumenti di estroversione nel tempo.
-   [Roberts e Mroczek (2008)](/docs/services/personality-insights?topic=personality-insights-references#roberts2008) commentano che esistono prove per "cambiamenti di livello medio nei tratti della personalità, così come per le differenze individuali nei cambiamenti nel corso della vita". Gli autori osservano che le persone mostrano maggiore autostima, calore, autocontrollo e stabilità emotiva con l'età. Questi cambiamenti predominano nella giovane età adulta (dai 20 ai 40 anni). Inoltre, il cambiamento di livello medio delle caratteristiche della personalità si verifica nella mezza età e nella vecchiaia, mostrando che le caratteristiche della personalità possono cambiare a qualsiasi età.

In base a questi studi, {{site.data.keyword.IBM_notm}} consiglia che gli utenti del servizio {{site.data.keyword.personalityinsightsshort}} lavorino sempre con i dati più recenti e con il maggior numero possibile di dati disponibili. {{site.data.keyword.IBM_notm}} consiglia inoltre che gli utenti aggiornino i ritratti della personalità a intervalli regolari per catturare le personalità in evoluzione degli individui. Anche se {{site.data.keyword.IBM_notm}} tende a credere che la personalità si evolva entro certi limiti, non ha condotto studi per esaminare i limiti superiori e inferiori di questa evoluzione.

Ci si potrebbe chiedere con quale regolarità aggiornare i ritratti della personalità degli individui. L'indicazione di {{site.data.keyword.IBM_notm}} è di cercare la disponibilità di nuovi dati e testi da un individuo. Se un individuo ha scritto una quantità considerevole di nuovo testo dal momento in cui è stato ottenuto il suo ritratto di personalità, è opportuno aggiornare il ritratto. Questo approccio cattura la natura in evoluzione della personalità, se si sceglie di accettare che la personalità si evolve. Offre inoltre al servizio {{site.data.keyword.personalityinsightsshort}} il vantaggio di lavorare con più parole, che a sua volta può aumentare la precisione dei risultati del servizio. 
