---

copyright:
  years: 2015, 2017
lastupdated: "2017-09-13"

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

# Descrizione di un profilo
{: #output}

1.  <span style="color:#003F69">Come posso interpretare i punteggi restituiti dal servizio?</span>

    -   [Interpretazione dei risultati numerici](/docs/services/personality-insights/numeric.html) descrive come interpretare il percentile restituito dal servizio. Include anche informazioni sulle percentuali di comportamento e i punteggi non elaborati facoltativi e le preferenze di consumo che il servizio può restituire. 

1.  <span style="color:#003F69">Perché l'aggiunta di punteggi per gli aspetti di una dimensione non produce il punteggio per quella dimensione?</span>

    -   [Percentili per le caratteristiche della personalità](/docs/services/personality-insights/numeric.html#percentiles) risponde a questa domanda. In sintesi, il servizio calcola il percentile normalizzato per ogni dimensione e aspetto in modo indipendente. Non esiste alcuna relazione matematica tra una dimensione e i suoi aspetti.

1.  <span style="color:#003F69">Quando devo usare il punteggio non elaborato al posto del punteggio percentile?</span>

    -   [Punteggi non elaborati per le caratteristiche della personalità](/docs/services/personality-insights/numeric.html#rawScores) fornisce informazioni utili su questa scelta. In breve, puoi utilizzare un punteggio non elaborato quando vuoi sviluppare una normalizzazione personalizzata per uno scenario specifico o quando non è richiesto il confronto con una popolazione campione. Se hai bisogno di sapere come vengono confrontati i risultati di un autore con una popolazione campione, usa i punteggi percentili.

1.  <span style="color:#003F69">Come posso normalizzare un punteggio non elaborato in un punteggio percentuale?</span>

    -   [Punteggi non elaborati per le caratteristiche della personalità](/docs/services/personality-insights/numeric.html#rawScores) fornisce una guida di alto livello per la normalizzazione di un punteggio non elaborato e illustra l'approccio di {{site.data.keyword.IBM_notm}} alla normalizzazione.

1.  <span style="color:#003F69">Come posso interpretare la visualizzazione di {{site.data.keyword.personalityinsightsshort}}?</span>

    -   [Interpretazione dei risultati numerici](/docs/services/personality-insights/numeric.html) descrive come interpretare i risultati numerici mostrati nella visualizzazione.
