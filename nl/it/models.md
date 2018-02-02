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

# Modelli di personalità
{: #models}

Il servizio {{site.data.keyword.personalityinsightsshort}} si basa sulla psicologia del linguaggio in combinazione con gli algoritmi di analisi dei dati. Il servizio analizza il contenuto che invii e restituisce un profilo di personalità per l'autore dell'input. Il servizio deduce le caratteristiche della personalità in base a tre modelli:
{: shortdesc}

-   Le caratteristiche della personalità *Big Five* rappresentano il modello
          più utilizzato per descrivere generalmente come una persona si
          relaziona con il mondo. Il modello include cinque dimensioni primarie:
    -   [*Gradevolezza*](/docs/services/personality-insights/agreeableness.html) è la tendenza di una persona a essere
              compassionevole e cooperativa verso gli altri.
    -   [*Coscienziosità*](/docs/services/personality-insights/conscientiousness.html) è la tendenza di una persona ad agire
              in modo organizzato o riflessivo.
    -   [*Estroversione*](/docs/services/personality-insights/extraversion.html) è la tendenza di una persona
              a cercare stimoli in compagnia di altri.
    -   [*Stabilità emotiva*](/docs/services/personality-insights/emotional-range.html), indicata anche come *Nevroticismo* o *Reazioni naturali*, è la misura in cui le emozioni di una persona sono sensibili al suo ambiente.
    -   [*Apertura mentale*](/docs/services/personality-insights/openness.html) è la misura in cui una persona
              è aperta a sperimentare una varietà di attività.

    Ognuna di queste dimensioni di livello superiore ha sei aspetti che caratterizzano ulteriormente un individuo a seconda della dimensione.
-   Le [Esigenze](/docs/services/personality-insights/needs.html) descrivono quali aspetti di un prodotto
          verranno accolti da una persona. Il modello include dodici esigenze della caratteristica.
-   I [Valori](/docs/services/personality-insights/values.html) descrivono i fattori motivanti che influenzano il processo decisionale di una persona. Il modello include cinque valori.

Per ulteriori informazioni su come sono stati sviluppati i modelli e su come vengono utilizzati dal servizio, vedi [La scienza alla base del servizio](/docs/services/personality-insights/science.html).

## Descrizioni delle caratteristiche della personalità Big Five
{: #bigFive}

Ogni dimensione Big Five è descritta da tre tabelle:

-   *Aspetti* introduce gli aspetti della dimensione e descrive gli individui che ottengono un punteggio elevato su ogni aspetto.
-   *Serie di caratteristiche* presenta descrizioni generali che potrebbero applicarsi a individui i cui punteggi mostrano più o meno ogni aspetto della dimensione, oltre ai termini che potrebbero descrivere tali individui. Per una pratica tabella su singola pagina che riepiloga le tabelle *Serie di caratteristiche* relative agli aspetti di tutte e cinque le dimensioni, vedi <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Facet-Characteristics.pdf" download="Personality-Insights-Facet-Characteristics.pdf">Personality-Insights-Facet-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="Icona link esterno" title="Icona link esterno" class="style-scope doc-content"></a>.
-   *Dimensioni primarie e secondarie* presenta informazioni che collegano la dimensione ad altre dimensioni, descrivendo combinazioni di caratteristiche della personalità. La tabella fornisce informazioni su come le caratteristiche primarie e secondarie potrebbero essere correlate per rappresentare la personalità composita di un individuo. Per una pratica tabella su singola pagina che riepiloga le tabelle *Caratteristiche primarie e secondarie* per tutte e cinque le dimensioni, vedi <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Dimension-Characteristics.pdf" download="Personality-Insights-Dimension-Characteristics.pdf">Personality-Insights-Dimension-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="Icona link esterno" title="Icona link esterno" class="style-scope doc-content"></a>.
