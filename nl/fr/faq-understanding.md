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

# Compréhension d'un profil
{: #output}

1.  <span style="color:#003F69">Comment puis-je interpréter les scores qui sont renvoyés par le service ?</span>

    -   La rubrique [Interprétation des résultats numériques](/docs/services/personality-insights/numeric.html) explique comment interpréter le percentile qui est renvoyé par le service. Elle inclut également des informations sur les pourcentages de comportement et les scores bruts et les préférences de consommation facultatifs qui peuvent être renvoyés par le service. 

1.  <span style="color:#003F69">Pourquoi le fait d'ajouter les scores des facettes d'une dimension ne génère-t-il pas le score pour cette dimension ?</span>

    -   La réponse à cette question se trouve dans la rubrique [Percentiles des caractéristiques de personnalité](/docs/services/personality-insights/numeric.html#percentiles). En résumé, le service calcule le percentile normalisé indépendamment pour chaque dimension et facette. Il n'existe aucune relation mathématique entre une dimension et ses facettes.

1.  <span style="color:#003F69">Quand dois-je utiliser le score brut au lieu du score de percentile ?</span>

    -   La rubrique [Scores bruts des caractéristiques de personnalité](/docs/services/personality-insights/numeric.html#rawScores) permet de mieux comprendre quand utiliser l'une ou l'autre de ces options. En résumé, vous pouvez utiliser un score brut lorsque vous souhaitez développer une normalisation personnalisée pour un scénario spécifique ou lorsqu'une comparaison avec un échantillon de la population n'est pas requise. Si vous avez besoin de savoir de quelle façon les résultats d'un auteur sont comparés à un échantillon de la population, utilisez les scores de percentile. 

1.  <span style="color:#003F69">Comment puis-je normaliser un score brut pour un score de percentile ?</span>

    -   La rubrique [Scores bruts des caractéristiques de personnalité](/docs/services/personality-insights/numeric.html#rawScores) fournit des conseils de haut niveau pour la normalisation d'un score brut et traite de l'approche d'{{site.data.keyword.IBM_notm}} en matière de normalisation.

1.  <span style="color:#003F69">Comment puis-je interpréter la visualisation {{site.data.keyword.personalityinsightsshort}} ?</span>

    -   La rubrique [Interprétation des résultats numériques](/docs/services/personality-insights/numeric.html) explique comment interpréter les résultats numériques qui sont affichés dans la visualisation. 
