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

# Disciplines scientifiques sous-jacentes au service
{: #science}

Une théorie bien acceptée en matière de psychologie, de marketing et dans d'autres domaines stipule que le langage humain reflète la personnalité, la façon de penser, le réseautage social et l'état émotionnel. La fréquence à laquelle on utilise certaines catégories de mots peut fournir des indices sur ces caractéristiques. Plusieurs chercheurs ont découvert que les variations dans l'utilisation de mots dans des écrits, tels que des blogues, des essais et des tweets peuvent prédire des aspects de personnalité ([Fast et Funder, 2008](/docs/services/personality-insights?topic=personality-insights-references#fast2008); [Gill et collab., 2009](/docs/services/personality-insights?topic=personality-insights-references#gill2009); [Golbeck et collab., 2011](/docs/services/personality-insights?topic=personality-insights-references#golbeck2011); [Hirsh et Peterson, 2009](/docs/services/personality-insights?topic=personality-insights-references#hirsh2009) et [Yarkoni, 2010](/docs/services/personality-insights?topic=personality-insights-references#yarkoni2010)).
{: shortdesc}

{{site.data.keyword.IBM_notm}} a mené une série d'études afin de comprendre si les caractéristiques de personnalité déduites des données de médias sociaux peuvent prédire le comportement et les préférences des personnes. {{site.data.keyword.IBM_notm}} a découvert que des personnes ayant des caractéristiques de personnalité spécifiques avaient répondu et retweeté un grand nombre de fois lors de tâches de collecte et de diffusion d'informations. Par exemple, les individus qui obtiennent des notes élevées pour la recherche de sensations sont plus enclins à répondre, contrairement aux individus qui obtiennent des notes élevées pour la prudence ([Mahmud et collab., 2013](/docs/services/personality-insights?topic=personality-insights-references#mahmud2013)). De même, les individus qui obtiennent des notes élevées pour la modestie, l'ouverture et la convivialité sont plus enclins à diffuser des informations ([Lee et collab., 2014](/docs/services/personality-insights?topic=personality-insights-references#lee2014)).

{{site.data.keyword.IBM_notm}} a également découvert que les individus qui obtiennent un score d'ouverture élevé et un score de portée émotionnelle faible(neuroticisme) déduits à partir d'une langue de média social ont répondu plus favorablement (par exemple en cliquant sur un lien publicitaire ou en suivant un compte). Ces résultats sont corroborés par une vérification de la vérité sur le terrain basée sur des enquêtes. Par exemple, le ciblage des 10 % d'utilisateurs qui obtiennent le score d'ouverture le plus élevé et le score de portée émotionnelle le plus faible a entraîné une augmentation du taux de clics de 6,8 % à 11,3 % et du taux de suivi de 4,7 % à 8,8 %. 

Plusieurs études récentes ont révélé des résultats similaires pour les caractéristiques qui étaient calculées à partir de données de média social. Une étude récente avec des données de commerce de détail a révélé que les individus qui obtiennent des notes élevées pour l'ordre, l'autodiscipline et la prudence et des notes faibles pour l'immodération sont 40 % plus enclins à réagir à des bons de réduction que les individus issus d'un échantillon aléatoire de la population. Une seconde étude a permis d'établir que des individus avec des valeurs spécifiques ont démontré des intérêts de lecture spécifiques ([Hsieh et collab., 2014](/docs/services/personality-insights?topic=personality-insights-references#hsieh2014)). Par exemple, les personnes ayant obtenu une valeur de dépassement de soi supérieure ont montré un intérêt particulier pour la lecture d'articles concernant l'environnement et les personnes ayant obtenu une valeur d'ambition personnelle supérieure ont montré un intérêt particulier pour la lecture d'articles concernant le travail. Une troisième étude portant sur plus de 600 utilisateurs Twitter a permis d'établir que les caractéristiques de personnalité d'une personne peuvent prédire les préférences de marque de cette dernière avec un niveau de précision de 65 %.

Les sections ci-après complètent ces résultats et décrivent la recherche et le développement qui sous-tendent le service {{site.data.keyword.personalityinsightsshort}}. Pour plus d'informations sur les études qui appliquent le service à des scénarios tangibles, voir [Le service en action](/docs/services/personality-insights?topic=personality-insights-applied).

## Compréhension des modèles de personnalité
{: #researchModels}

Pour le service {{site.data.keyword.personalityinsightsshort}}, {{site.data.keyword.IBM_notm}} a développé des modèles qui déduisent des scores pour les dimensions et les facettes Big Five et les caractéristiques Besoins et Valeurs à partir d'informations contenues dans un texte. Les modèles renvoyés par le service sont basés sur les recherches menées en psychologie, psycholinguistique et marketing :

-   [Big Five](/docs/services/personality-insights?topic=personality-insights-models) est l'un des modèles de personnalité les plus étudiés parmi ceux développés par des psychologues ([Costa et McCrae, 1992](/docs/services/personality-insights?topic=personality-insights-references#costa1992), et [Norman, 1963](/docs/services/personality-insights?topic=personality-insights-references#norman1963)). Il est le modèle de personnalité le plus utilisé pour décrire la manière dont une
personne se comporte de façon générale avec les autres. Le service calcule les cinq dimensions et les trente facettes du modèle. Les dimensions sont souvent référencées par les initiales *OCEAN*, où *O* signifie Openness (ouverture), *C* signifie Conscientiousness (tempérament consciencieux), *E* signifie Extraversion (extraversion), *A* signifie Agreeableness (amabilité) et *N* signifie Neuroticism (neuroticisme). (Etant donné que le terme Neuroticism peut avoir une signification clinique, le service présente les éclairages associés sous l'en-tête Portée émotionnelle, plus générique.)
-   Les caractéristiques [Besoins](/docs/services/personality-insights?topic=personality-insights-needs) représentent un aspect essentiel du comportement humain. Les recherches publiées suggèrent que plusieurs types de besoins humains sont universels et influencent directement le comportement du consommateur ([Kotler et Armstrong, 2013](/docs/services/personality-insights?topic=personality-insights-references#kotler2013) et [Ford, 2005](/docs/services/personality-insights?topic=personality-insights-references#ford2005)). Les douze catégories de besoins rapportées par le service sont décrites dans la littérature sur le marketing comme autant de désirs que l'on cherche à assouvir lorsque l'on pense à un produit ou à un service. 
-   Les caractéristiques [Valeurs](/docs/services/personality-insights?topic=personality-insights-values) présentent ce qui est le plus important pour un individu. Il s'agit de "buts désirables universels dont l'importance varie et qui servent de lignes directrices dans la vie des gens" ([Schwartz, 2006](/docs/services/personality-insights?topic=personality-insights-references#schwartz2006)). Schwartz résume cinq caractéristiques communes à toutes les valeurs : 

    1.  Les valeurs sont des croyances. 
    1.  Les valeurs sont une construction de motivation. 
    1.  Les valeurs transcendent les actions et les situations spécifiques. 
    1.  Les valeurs guident la sélection ou l'évaluation des actions, des politiques, des personnes et des événements. 
    1.  Les valeurs varient en fonction de l'importance relative et peuvent être classées par importance. 

    Le service calcule les cinq valeurs humaines de base proposées par Schwartz et validées dans plus de vingt pays ([Schwartz, 1992](/docs/services/personality-insights?topic=personality-insights-references#schwartz1992)).

## Comment les caractéristiques de personnalité sont-elles déduites ?
{: #researchInfer}

Le service {{site.data.keyword.personalityinsightsshort}} déduit des caractéristiques de personnalité à partir d'informations contenues dans un texte sur la base d'une approche de vocabulaire ouvert. Cette méthode reflète la dernière tendance dans les recherches réalisées sur la déduction de la personnalité ([Arnoux et collab., 2017](/docs/services/personality-insights?topic=personality-insights-references#arnoux2017), [Schwartz et collab., 2013](/docs/services/personality-insights?topic=personality-insights-references#schwartz2013) et [Plank et Hovy, 2015](/docs/services/personality-insights?topic=personality-insights-references#plank2015)).

Le service commence par segmenter le texte d'entrée afin de développer une représentation dans un espace à *n* dimensions. Le service utilise une technique d'imbrication de mots open source, [GloVe ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](http://nlp.stanford.edu/projects/glove/){: new_window}, afin d'obtenir une représentation de vecteur pour les mots inclus dans le texte d'entrée ([Pennington et collab., 2014](/docs/services/personality-insights?topic=personality-insights-references#pennington2014)). Ensuite, il alimente cette représentation avec un algorithme d'apprentissage automatique qui déduit un profil de personnalité avec les caractéristiques Big Five, Besoins et Valeurs. Pour former l'algorithme, le service utilise les scores obtenus à partir d'enquêtes réalisées auprès de milliers d'utilisateurs, ainsi que les données issues de leurs fils Twitter. 

{{site.data.keyword.IBM_notm}} a développé de la même manière des modèles pour toutes les langues prises en charge. Les modèles ont été développés indépendamment d'éléments démographiques, tels que l'âge, le sexe ou la culture. {{site.data.keyword.IBM_notm}} développera éventuellement des modèles propres à différentes catégories démographiques.

Les versions antérieures du service utilisaient le dictionnaire psycholinguistique LIWC (Linguistic Inquiry and Word Count) avec son modèle d'apprentissage automatique. Toutefois, l'approche de vocabulaire ouvert est plus performante que le modèle basé sur le dictionnaire LIWC. Pour plus d'informations sur la précision du service pour chaque langue en termes de valeurs MAE moyenne et Corrélation moyenne, voir [Niveau de précision du service](#researchPrecise). Pour obtenir des conseils sur l'indication du texte d'entrée afin d'obtenir les résultats les plus exacts, voir [Indication d'entrées suffisantes](/docs/services/personality-insights?topic=personality-insights-input#sufficient).

## Niveau de précision du service
{: #researchPrecise}

{{site.data.keyword.IBM_notm}} a mené une étude de validation afin de comprendre l'exactitude de l'approche du service pour déduire un profil de personnalité. {{site.data.keyword.IBM_notm}} a collecté les réponses à une enquête et les fils Twitter fournis par 1500 à 2000 participants pour toutes les caractéristiques et toutes les langues. Pour établir des *données de référence*, les participants ont passé quatre groupes de tests psychométriques standard :

-   Big Five avec 50 éléments dérivés d'International Personality Item Pool (IPIP)
-   Facette avec 120 éléments dérivés d'IPIP Neuroticism, Extraversion &amp; Openness (IPIP-NEO)
-   Besoins fondamentaux avec 52 éléments développés par {{site.data.keyword.IBM_notm}}
-   Valeurs de base avec 26 éléments développés par Schwartz

{{site.data.keyword.IBM_notm}} a ensuite comparé les scores qui étaient dérivés de ses modèles aux scores basés sur l'enquête pour les utilisateurs Twitter. Sur la base de ces résultats, {{site.data.keyword.IBM_notm}} a déterminé la valeur [MAE (Mean Absolute Error) moyenne](#preciseMAE) et la valeur [Corrélation moyenne](#preciseCorrelation) entre les scores déduits et réels pour les différentes catégories des caractéristiques de personnalité. La rubrique [Valeur MAE moyenne et valeur Corrélation moyenne par langue](#precisePerLanguage) fournit les valeurs statistiques pour chaque langue prise en charge. 

### Valeur MAE (Mean Absolute Error) moyenne
{: #preciseMAE}

La valeur *MAE (Mean Absolute Error)* est une métrique qui sert à mesurer la différence entre les valeurs réelles et prédites. Pour le service {{site.data.keyword.personalityinsightsshort}}, la valeur réelle, ou données de référence, correspond au score de personnalité qui a été obtenu en administrant une enquête de personnalité. La valeur prédite correspond au score produit par les modèles du service.

{{site.data.keyword.IBM_notm}} a calculé la valeur MAE en bénéficiant de la valeur absolue de la différence entre les scores réels et les scores prédits. {{site.data.keyword.IBM_notm}} a utilisé la valeur absolue, car prévoir plus ou moins la valeur réelle n’est pas pertinent. Tant qu'il existe une différence, le modèle est pénalisé par l'ampleur de l'erreur. Plus la valeur MAE est faible, plus les performances du modèle sont élevées. {{site.data.keyword.IBM_notm}} utilise une échelle de 0 à 1 pour la valeur MAE, où 0 signifie qu'il n'y a aucune erreur (la valeur prédite et la valeur réelle sont rigoureusement identiques) et 1 désigne une erreur maximale.

### Corrélation moyenne
{: #preciseCorrelation}

La valeur *Corrélation moyenne* est un terme statistique qui mesure l'interdépendance de deux variables. Avec cette métrique, {{site.data.keyword.IBM_notm}} a mesuré la corrélation entre les scores déduits et réels pour les différentes catégories de caractéristiques de personnalité. Si le score prédit assure le suivi des résultats réels, le score de corrélation est élevé, sinon, il est faible.

{{site.data.keyword.IBM_notm}} mesure la corrélation sur une échelle de -1 à 1 :

-   1 indique une relation linéaire parfaite (croissante) directe. 
-   -1 indique une relation linéaire parfaite inverse (décroissante). 

Dans tous les cas de figure, la valeur se situe entre ces extrêmes. Si les variables sont indépendantes (elles n'ont absolument aucune relation), la corrélation est 0.

{{site.data.keyword.IBM_notm}} recherche des nombres proches de 1 pour des prévisions optimales. Mais il est difficile de prédire des personnalités sur la seule base d'un texte et il est rare de voir des corrélations dépasser 0,4 pour ces types de modèles psychologiques. Dans les recherches publiées pour ce domaine, les corrélations supérieures à 0,2 sont considérées comme acceptables. 

### Valeur MAE moyenne et valeur Corrélation moyenne par langue
{: #precisePerLanguage}

Le tableau ci-après présente les résultats MAE et de corrélation moyens par langue pour le service {{site.data.keyword.personalityinsightsshort}}. Les résultats placent le service au premier plan de la déduction de personnalité à partir de données textuelles, comme indiqué par [Schwartz et collab., (2013)](/docs/services/personality-insights?topic=personality-insights-references#schwartz2013) et [Plank et Hovy (2015)](/docs/services/personality-insights?topic=personality-insights-references#plank2015). 

<table summary="Pour chaque ligne identifiant une langue dans la première colonne, les deux lignes suivantes fournissent le MAE moyen et la corrélation moyenne pour les dimensions Big Five, les facettes Big Five, les besoins et les valeurs.">
  <caption>Tableau 1. Valeurs MAE moyenne et Corrélation moyenne par langue</caption>
  <tr>
    <th id="language" style="text-align:left; vertical-align:bottom">
      Langue
    </th>
    <th id="dimensions" style="text-align:center; vertical-align:bottom">
      Dimensions Big Five
    </th>
    <th id="facets" style="text-align:center; vertical-align:bottom">
      Facettes Big Five
    </th>
    <th id="needs" style="text-align:center; vertical-align:bottom">
      Besoins
    </th>
    <th id="values" style="text-align:center; vertical-align:bottom">
      Valeurs
    </th>
  </tr>
  <tr>
    <th id="arabic" headers="language" colspan="5" style="text-align:left">
      **Arabe**
    </th>
  </tr>
  <tr>
    <td headers="language arabic" style="text-align:left">
      MAE moyenne
    </td>
    <td headers="dimensions arabic" style="text-align:center">
      0,09
    </td>
    <td headers="facets arabic" style="text-align:center">
      0,12
    </td>
    <td headers="needs arabic" style="text-align:center">
      0,11
    </td>
    <td headers="values arabic" style="text-align:center">
      0,10
    </td>
  </tr>
  <tr>
    <td headers="language arabic" style="text-align:left">
      Corrélation moyenne
    </td>
    <td headers="dimensions arabic" style="text-align:center">
      0,17
    </td>
    <td headers="facets arabic" style="text-align:center">
      0,14
    </td>
    <td headers="needs arabic" style="text-align:center">
      0,13
    </td>
    <td headers="values arabic" style="text-align:center">
      0,14
    </td>
  </tr>
  <tr>
    <th id="english" headers="language" colspan="5" style="text-align:left">
      **Anglais**
    </th>
  </tr>
  <tr>
    <td headers="language english" style="text-align:left">
      MAE moyenne
    </td>
    <td headers="dimensions english" style="text-align:center">
      0,12
    </td>
    <td headers="facets english" style="text-align:center">
      0,12
    </td>
    <td headers="needs english" style="text-align:center">
      0,11
    </td>
    <td headers="values english" style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td headers="language english" style="text-align:left">
      Corrélation moyenne
    </td>
    <td headers="dimensions english" style="text-align:center">
      0,33
    </td>
    <td headers="facets english" style="text-align:center">
      0,28
    </td>
    <td headers="needs english" style="text-align:center">
      0,22
    </td>
    <td headers="values english" style="text-align:center">
      0,24
    </td>
  </tr>
  <tr>
    <th id="japanese" headers="language" colspan="5" style="text-align:left">
      **Japonais**
    </th>
  </tr>
  <tr>
    <td headers="language japanese" style="text-align:left">
      MAE moyenne
    </td>
    <td headers="dimensions japanese" style="text-align:center">
      0,11
    </td>
    <td headers="facets japanese" style="text-align:center">
      0,12
    </td>
    <td headers="needs japanese" style="text-align:center">
      0,11
    </td>
    <td headers="values japanese" style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td headers="language japanese" style="text-align:left">
      Corrélation moyenne
    </td>
    <td headers="dimensions japanese" style="text-align:center">
      0,27
    </td>
    <td headers="facets japanese" style="text-align:center">
      0,22
    </td>
    <td headers="needs japanese" style="text-align:center">
      0,25
    </td>
    <td headers="values japanese" style="text-align:center">
      0,19
    </td>
  </tr>
  <tr>
    <th id="korean" headers="language" colspan="5" style="text-align:left">
      **Coréen**
    </th>
  </tr>
  <tr>
    <td headers="language korean" style="text-align:left">
      MAE moyenne
    </td>
    <td headers="dimensions korean" style="text-align:center">
      0,11
    </td>
    <td headers="facets korean" style="text-align:center">
      0,12
    </td>
    <td headers="needs korean" style="text-align:center">
      0,11
    </td>
    <td headers="values korean" style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td headers="language korean" style="text-align:left">
      Corrélation moyenne
    </td>
    <td headers="dimensions korean" style="text-align:center">
      0,21
    </td>
    <td headers="facets korean" style="text-align:center">
      0,21
    </td>
    <td headers="needs korean" style="text-align:center">
      0,13
    </td>
    <td headers="values korean" style="text-align:center">
      0,12
    </td>
  </tr>
  <tr>
    <th id="spanish" headers="language" colspan="5" style="text-align:left">
      **Espagnol**
    </th>
  </tr>
  <tr>
    <td headers="language spanish" style="text-align:left">
      MAE moyenne
    </td>
    <td headers="dimensions spanish" style="text-align:center">
      0,10
    </td>
    <td headers="facets spanish" style="text-align:center">
      0,12
    </td>
    <td headers="needs spanish" style="text-align:center">
      0,12
    </td>
    <td headers="values spanish" style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td headers="language spanish" style="text-align:left">
      Corrélation moyenne
    </td>
    <td headers="dimensions spanish" style="text-align:center">
      0,35
    </td>
    <td headers="facets spanish" style="text-align:center">
      0,21
    </td>
    <td headers="needs spanish" style="text-align:center">
      0,24
    </td>
    <td headers="values spanish" style="text-align:center">
      0,19
    </td>
  </tr>
</table>

Pour calculer les scores en percentiles, {{site.data.keyword.IBM_notm}} a collecté un très grand nombre de données d'utilisateurs Twitter et calculé leurs portraits de personnalité : 

-   Un million d'utilisateurs pour l'anglais 
-   Deux cent mille utilisateurs pour le coréen 
-   Cent mille utilisateurs pour l'arabe et pour le japonais 
-   Quatre-vingt mille utilisateurs pour l'espagnol 

{{site.data.keyword.IBM_notm}} a ensuite comparé les scores bruts de chaque profil calculé à la distribution de profils à partir des jeux de données afin de déterminer les percentiles.

Pour l'entrée en arabe et en coréen, le service est incapable de produire des percentiles et des scores bruts significatifs pour certaines caractéristiques de personnalité. Pour plus d'informations, voir [Limitations pour les entrées en arabe et en coréen](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).
{: note}

## Compréhension des préférences de consommation
{: #researchPrefs}

La relation entre la personnalité et le comportement d'achat a été étudiée sur différents produits et services :

-   [Chen (2007)](/docs/services/personality-insights?topic=personality-insights-references#chen2007), lors de tests réalisés sur les préférences en matière de nourriture biologique, a indiqué que les caractéristiques de personnalité d'un individu jouent un rôle important dans l'établissement de critères de choix de nourriture personnels. 
-   [Schlegelmilch et collab., (1996)](/docs/services/personality-insights?topic=personality-insights-references#schlegelmilch1996) ont exploré la relation entre les variables de personnalité et le comportement d'achat favorable à l'environnement. Les auteurs ont démontré que la conscience écologique globale des consommateurs a un impact positif sur les décisions d'achats écologiques.
-   [Hymbaugh et Garrett (2007)](/docs/services/personality-insights?topic=personality-insights-references#hymbaugh1974) ont étudié la relation entre la personnalité et le saut en parachute et établi que les personnes qui obtiennent un score élevé pour la quête d'aventures et la recherche de sensations s'adonnent généralement au saut en parachute. (Pour plus d'informations, voir [Profilage de risques](/docs/services/personality-insights?topic=personality-insights-applied#otherRisk).)

Appliquer ces relations connues entre les comportements de consommation et la personnalité constitue un véritable défi. La plupart de ces travaux a utilisé des données de personnalité dérivées d'enquêtes et leurs modèles ne sont pas accessibles au public. Par conséquent, {{site.data.keyword.IBM_notm}} a décidé d'apprendre directement ces modèles de préférence de consommation. Lors de la formation des modèles, {{site.data.keyword.IBM_notm}} a utilisé les scores de personnalité renvoyés par le service {{site.data.keyword.personalityinsightsshort}} en tant que fonctions. Par conséquent, lorsque vous appliquerez ces modèles pour calculer les caractéristiques de personnalité d'un utilisateur avec le service, il est fort probable que les prédictions seront plus exactes.

## Comment les préférences de consommation sont-elles déduites ?
{: #researchInferPrefs}

Le service {{site.data.keyword.personalityinsightsshort}} déduit les préférences de consommation en fonction des résultats de son profil de personnalité pour l'auteur du texte d'entrée. D'après la littérature existante, {{site.data.keyword.IBM_notm}} a identifié 104 préférences de consommation dont la corrélation avec la personnalité a été prouvée. Il s'agit notamment de préférences relatives aux achats, au cinéma, à la musique et à d'autres catégories. {{site.data.keyword.IBM_notm}} a ensuite créé une enquête psychométrique afin d'évaluer l'aspiration d'un individu pour chaque comportement de consommation.

{{site.data.keyword.IBM_notm}} a obtenu des réponses à cette enquête de la part d'environ 600 individus pour lesquels elle disposait également de données Twitter (plus de 200 tweets publiés pour chaque utilisateur). {{site.data.keyword.IBM_notm}} a soumis les tweets au service afin de collecter un profil de personnalité pour chaque individu. Elle a ensuite créé un classificateur pour chaque préférence de consommation, où la fonction d'entrée définie correspondait aux informations de personnalité.

A des fins d'inclusion avec le service, {{site.data.keyword.IBM_notm}} a sélectionné uniquement les préférences de consommation pour lesquelles les performances de la classification basée sur la personnalité étaient au moins 9 % supérieures à celles obtenues avec la classification aléatoire. Sur les 104 préférences d'origine, 42 ont répondu à ce critère et sont exposées en tant que préférences de consommation par le service.

<!--
COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016

## How media influence inferred characteristics

{{site.data.keyword.IBM_notm}} conducted a validation study to understand the effect of media on inferred characteristics. To determine the accuracy of the service's approach to estimating characteristics, {{site.data.keyword.IBM_notm}} compared scores that were derived by its models with survey-based scores for Twitter users (for instance, approximately 500 users for English and more than 600 for Spanish).

To establish ground truth, participants took three sets of standard psychometric tests: 50-item Big Five (derived from the International Personality Item Pool, or IPIP), 52-item fundamental Needs (developed by {{site.data.keyword.IBM_notm}}), and 26-item basic Values (developed by Schwartz). {{site.data.keyword.IBM_notm}} conducted the study in two phases:

-   For the first study, conducted in 2013, {{site.data.keyword.IBM_notm}} recruited 256 Twitter users ([Gou and others, 2014](/docs/services/personality-insights?topic=personality-insights-references#gou2014)). Although the models were learned from different sources, {{site.data.keyword.IBM_notm}} found that for more than 80 percent of the Twitter users, scores for characteristics that were inferred for all three models correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80). Specifically, scores that were derived by the service correlated with survey-based scores as follows:
    -   For 80.8 percent of participants' Big Five scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.75)
    -   For 86.6 percent of participants' Needs scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80)
    -   For 98.21 percent of participants' Values scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.55)
-   For the second study, conducted in 2015, {{site.data.keyword.IBM_notm}} recruited another set of 237 Twitter users. The study found that for Big Five and Values, scores for inferred characteristics correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.07 and 0.21) for every Twitter user. For needs, such significant correlation was observed for 90 percent of the users (p value &lt; 0.05 and correlation coefficient between 0.01 and 0.20).

In both studies, participants also rated on a five-point scale how well each derived characteristic matched their perceptions of themselves. Their ratings suggest that the inferred characteristics largely matched their self-perceptions. Specifically, means of all ratings were above 3 ("somewhat") out of 5 ("perfect").

-   For the 256 Twitter users of the first study, means were 3.4 (with a standard deviation of 1.14) for Big Five, 3.39 (with a standard deviation of 1.34) for Needs, and 3.13 (with a standard deviation of 1.17) for Values.
-   For the 237 Twitter users of the second study, means were 3.31 (with a standard deviation of 1.18) for Big Five, 3.37 (with a standard deviation of 1.22) for Needs, and 3.36 (with a standard deviation of 1.18) for Values.

COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016
-->

## Remarques que les enquêtes de personnalité
{: #researchSurveys}

Lors du développement du service {{site.data.keyword.personalityinsightsshort}}, {{site.data.keyword.IBM_notm}} s'est appuyée sur des enquêtes de personnalité afin d'établir des données de référence en matière de déduction de personnalité. Les données de référence correspondent aux données factuelles obtenues via une observation directe plutôt qu'une déduction. Une mesure courante de l'exactitude de n'importe quel modèle d'apprentissage automatique consiste à comparer les scores déduits par le modèle à des données de référence. Les sections précédentes décrivent comment {{site.data.keyword.IBM_notm}} a utilisé des enquêtes pour valider l'exactitude du service.

Les remarques suivantes apportent des précisions sur l'utilisation d'enquêtes de personnalité et l'estimation de personnalité à partir d'enquêtes :

-   Les enquêtes de personnalité sont longues et prennent beaucoup de temps. Les résultats sont contraints par le nombre d'utilisateurs Twitter désireux (et disponibles) de participer à l'étude menée par {{site.data.keyword.IBM_notm}}. {{site.data.keyword.IBM_notm}} prévoit de mener des études de validation avec davantage d'utilisateurs, et avec des utilisateurs d'autres médias en ligne, tels que les courriers électroniques, les blogues et les forums.
-   L'estimation de personnalité basée sur des enquêtes s'appuie sur l'auto-déclaration, ce qui ne reflète pas toujours exactement la personnalité d'un individu. Certains utilisateurs peuvent donner des réponses erronées à ces enquêtes. Pour réduire le bruit, {{site.data.keyword.IBM_notm}} a filtré les réponses à l'enquête en incluant des questions de vérification et en annulant les enquêtes complétées trop rapidement.
-   Si la corrélation entre les scores déduits et les scores basés sur des enquêtes est à la fois positive et significative, les résultats impliquent que les scores déduits peuvent ne pas toujours être corrélés avec les résultats basés sur des enquêtes. Les chercheurs qui ne font pas partie d'{{site.data.keyword.IBM_notm}} ont également réalisé des expériences afin de comparer le niveau de correspondance entre les scores déduits et les scores obtenus par des enquêtes, et aucun d'eux n'a signalé de correspondance cohérente : 
    -   [Golbeck et collab., (2011)](/docs/services/personality-insights?topic=personality-insights-references#golbeck2011) ont rapporté un taux d'erreur de 10 à 18 % des scores déduits, mis en correspondance avec des scores basés sur des enquêtes. 
    -   [Sumner et collab., (2012)](/docs/services/personality-insights?topic=personality-insights-references#sumner2012) ont rapporté un taux d'exactitude d'environ 65 % pour la prédiction de personnalité. 
    -   [Mairesse et Walker (2006)](/docs/services/personality-insights?topic=personality-insights-references#mairesse2006) ont rapporté un taux d'exactitude de 60 à 70 % pour la prédiction de personnalité Big Five. 

Dans les recherches publiées, il est largement admis que les scores auto-déclarés provenant d'enquêtes de personnalité ne correspondent pas toujours aux scores qui sont déduits de données textuelles. En revanche, et plus important encore, {{site.data.keyword.IBM_notm}} a constaté que les caractéristiques déduites de données textuelles peuvent souvent prédire de manière fiable un comportement réel. 
