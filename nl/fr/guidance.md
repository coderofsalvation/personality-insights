---

copyright:
  years: 2015, 2017
lastupdated: "2017-08-13"

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

# Conseils d'utilisation
{: #guidance}

Les utilisateurs appliquent le service {{site.data.keyword.personalityinsightsshort}} à un nombre croissant de cas d'utilisation. Ils ont appliqué le service pour offrir des recommandations de produit personnalisés à des clients via des bornes en magasin. Ils ont exploré et analysé les différences dans les personnalités des présidents des Etats-Unis déduites à partir de leurs discours sur l'état de l'Union. Et ils ont intégré le service avec un autre produit dans le portefeuille {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}}, , {{site.data.keyword.watson}} Explorer, pour démontrer de quelle façon un conseiller en investissements peut offrir des options appropriées basées sur les portraits de personnalité des investisseurs. (Pour plus d'informations, voir [Cas d'utilisation](/docs/services/personality-insights/usecases.html).)
{: shortdesc}

Lors du développement de ces cas d'utilisation et d'autres cas d'utilisation potentielle, {{site.data.keyword.IBM_notm}} a eu des conversations avec des banques, des prestataires de santé, des entreprises de gestion d'expérience client et des agences fédérales. Ces conversations génèrent souvent des questions que les scénarios d'utilisation applicables. Certaines de ces questions et les liens vers les réponses correspondantes sont disponibles sous la forme de foires aux questions. La perspective d'{{site.data.keyword.IBM_notm}} sur un certain nombre de questions supplémentaires est la suivante :

-   Quel type de texte est préférable pour déduire la personnalité d'un individu ? Le texte doit-il nécessairement être réflectif par nature ? Si tel est le cas, quelle est la portée de cette caractéristique et comment mesurer la réflexion ? Voir [Quel type de texte est optimal pour déduire une personnalité ?](#optimal)
-   Comment interpréter un texte qui est écrit par une personne au sujet d'une autre personne ? La personnalité d'un auteur peut-elle être déduite à partir des travaux de fiction de ce dernier ? Un texte écrit par plusieurs individus peut-il être combiné pour obtenir un portrait de personnalité ? Voir [Interprétation des résultats obtenus à partir de différents types de texte](#interpreting).
-   Des portraits de personnalité peuvent-ils être déduits à partir d'un texte qui est généré par des services de transcription ou de traduction ? Voir [Déduction d'une personnalité à partir d'un texte généré](#inferring). 
-   Des portraits de personnalité peuvent-ils être appliqués à des applications, telles que la mise en correspondance d'individus, la surveillance et la prédiction en matière de santé mentale et la surveillance d'éléments radicaux et indésirables via des médias sociaux ? Voir [Utilisation de portraits de personnalité pour des applications spécifiques](#applying).
-   La personnalité d'un individu peut-elle évoluer à mesure que celui-ci vieillit ? Voir [La personnalité d'une personne peut-elle changer au fil du temps ?](#evolve)

## Quel type de texte est optimal pour déduire une personnalité ?
{: #optimal}

Quel type de texte est le plus adapté pour déduire une personnalité ? Le texte doit-il être de type réflectif, introspectif, formel ou informel ? Comment peut-on mesurer les mots qui sont utilisés dans la vie de tous les jours ? Ces mots sont-ils réflectifs par nature ? Les réponses à ces questions peuvent vous aider à sélectionner l'entrée la plus appropriée afin d'appliquer le service plus efficacement. 

Les travaux menés par {{site.data.keyword.IBM_notm}} sur le service {{site.data.keyword.personalityinsightsshort}} sont basés sur le principe fondamental que les mots utilisés par une personne dans la vie de tous les jours révèlent des traits de sa personnalité ([Pennebaker et al., 2001](/docs/services/personality-insights/references.html#pennebaker2001), and [Pennebaker et al., 2007](/docs/services/personality-insights/references.html#pennebaker2007)). Le service peut analyser des mots qui sont écrits par des individus sur eux-mêmes ou sur n'importe quel sujet, mais les individus doivent choisir et écrire les mots pour le service afin de générer un portrait de personnalité exact. 

{{site.data.keyword.IBM_notm}} pense que, idéalement, le texte qui est utilisé pour déduire les besoins de personnalité d'un individu doivent être de type réflectif. Les écrits basés sur la réflexion exposent les expériences personnelles et les réponses de l'auteur. Avec ces écrits, l'auteur doit placer un certain nombre de pistes de réflexion dans les mots qui sont choisis. Par exemple, le texte peut inclure les opinions, les attitudes, les sentiments et les observations sur quelqu'un ou quelque chose de la part de la personne qui écrit ou il peut exprimer les opinions positives ou les opinions négatives de cette dernière, mais il doit refléter les mots qu'elle a choisis. 

{{site.data.keyword.IBM_notm}} n'a trouvé aucune référence explicite dans la littérature psycholinguistique sur la nécessité d'inclure des éléments de réflexion dans le texte utilisé pour déduire la personnalité. Toutefois, {{site.data.keyword.IBM_notm}} a constaté que certaines études utilisent des mots provenant de textes recueillis dans le cadre d'une expérience en laboratoire au cours de laquelle il a été demandé à des personnes  d'écrire des petits essais sur des sujets donnés. Ce type d'écriture requiert implicitement un certain nombre de pistes de réflexion. D'autres études utilisent des textes provenant d'échantillons naturels, tels que des blogues sur différents sujets, des tweets sur Twitter, des courriers électroniques, ou même des éléments de communication extraits du jeu *World of Warcraft*. Toutes ces études partent du principe que les mots utilisés dans la vie de tous les jours sont révélateurs de traits de personnalité car ils tendent à refléter les réflexions de la personne qui les écrit. 

D'autres études démontrent que les écrits émotionnels, les écrits de contrôle, les blogues et les transcriptions de discours sont appropriés pour déduire des traits de personnalité. En revanche, l'utilisation des articles scientifiques pour la déduction de traits de personnalité est très marginale. De plus, la littérature indique que parvenir à mesurer précisément des traits de personnalité s'avère beaucoup plus compliqué lorsqu'un texte

-   manque d'authenticité, par exemple de sarcasme, d'ironie, de modification intenses, ou de plusieurs auteurs
-   comporte des fautes d'orthographe, des mots techniques, des mots ayant plusieurs significations, des négations et des phrases plutôt que des mots simples
-   comporte des groupes de comparaison inappropriés, par exemple, des écrits professionnels plutôt que des écrits personnels et des écrits techniques plutôt que des écrits émotionnels

## Interprétation des résultats obtenus à partir de différents types de texte
{: #interpreting}

Le type de texte à analyser peut avoir un impact considérable sur la qualité des résultats du service {{site.data.keyword.personalityinsightsshort}}. Les sections ci-après expliquent comment interpréter les résultats obtenus à partir de différentes sources : 

-   [Interprétation des résultats obtenus à partir d'un texte écrit par d'autres personnes](#writingaboutothers)
-   [Interprétation des résultats obtenus à partir d'oeuvres fictives](#fictionalworks)
-   [Interprétation des résultats obtenus à partir d'un texte écrit par plusieurs individus](#multipleindividuals)

### Interprétation des résultats obtenus à partir d'un texte écrit par d'autres personnes
{: #writingaboutothers}

Pour pouvoir déduire de manière fiable la personnalité d'un individu, est-il nécessaire que le texte soit écrit *par* l'individu lui-même ou peut-il être écrit par une autre personne *au sujet* de cet individu ? Lorsqu'une personne écrit un texte au sujet d'une autre personne, à laquelle de ces deux personnes correspond la personnalité déduite à partir du texte ? 

{{site.data.keyword.IBM_notm}} a le sentiment est que les écrits reflètent toujours la personnalité de leur auteur, quel qu'en soit le sujet. Par exemple, si un individu A écrit un texte au sujet d'un individu B, une analyse du texte permet de déduire la personnalité de l'individu A. Même si l'individu A écrit un texte au sujet de l'individu B, c'est l'individu A qui choisit les mots permettant d'exprimer des choses sur l'individu B. Cependant, {{site.data.keyword.IBM_notm}} n'a mené aucune étude dans le but de tester ce scénario de manière explicite. 

### Interprétation des résultats obtenus à partir d'oeuvres fictives
{: #fictionalworks}

{{site.data.keyword.IBM_notm}} ne recommande d'avoir recours aux oeuvres fictives d'un auteur pour déduire la personnalité de ce dernier. Lorsqu'ils écrivent une fiction, les auteurs dressent volontairement le portrait de chaque personnage de manière différente. Ils construisent un dialogue qui reflète les personnalités des personnages et ils prédéfinissent la personnalité de chaque personnage dans leur tête. 

L'utilisation d'un texte dont la finalité est de refléter la personnalité d'un personnage de fiction pour déduire la personnalité de son créateur est sujet à caution. Bien que chaque auteur ait un style unique, les personnages sont toujours volontairement prédéfinis. En revanche, la personnalité d'un auteur peut être déduite à partir des essais non fictionnels, des transcriptions d'entretien ou d'autres éléments, tels que des introductions, des prologues, des remerciements ou des dédicaces, réalisés par l'auteur. 

### Interprétation des résultats obtenus à partir d'un texte écrit par plusieurs individus
{: #multipleindividuals}

L'un des cas d'utilisation les plus courants pour le service {{site.data.keyword.personalityinsightsshort}} consiste à analyser les suiveurs d'une marque ou d'une entreprise. Les suiveurs sont définis en tant que personnes qui suivent une entreprise sur Twitter ou sur une page Facebook publique. Dans ce scénario, l'objectif est de dériver la personnalité globale des suiveurs d'une entreprise. La méthode préférée consiste à collecter suffisamment de texte écrit par les membres d'un groupe pour calculer la personnalité de chaque membre individuel, puis de regrouper les personnalités dans des groupes distincts. Ces groupes représentent des personnes ayant des caractéristiques de personnalité distinctes qui suivent l'entreprise. 

Si le texte fourni par les membres d'un groupe n'est pas suffisant, le texte écrit par plusieurs membres peut être combiné et analysé afin de produire un portrait de personnalité moyen ou composite pour l'ensemble du groupe. Cette approche peut générer une indication des qualités dominantes du groupe, mais plus la population est variée, plus l'exactitude de cette méthode diminue. Il convient de faire preuve de prudence lors de l'interprétation de portraits obtenus à partir de la combinaison de textes provenant de plusieurs individus. Les travaux réalisés par {{site.data.keyword.IBM_notm}} dans ce domaine en sont encore à leur début ; {{site.data.keyword.IBM_notm}} communiquera ses résultats lorsque ceux-ci seront concluants. 

## Déduction d'une personnalité à partir d'un texte généré
{: #inferring}

L'analyse d'un texte qui est généré par les services de transcription ou de traduction peut avoir un impact sur la fiabilité des résultats du service {{site.data.keyword.personalityinsightsshort}}. Les sections suivantes présentent les effets de la déduction d'une personnalité à partir d'un texte généré :

-   [Déduction d'une personnalité à partir de transcriptions de discours](#transcription)
-   [Déduction d'une personnalité à partir d'un texte traduit](#translation)

### Déduction d'une personnalité à partir de transcriptions de discours
{: #transcription}

Les moteurs de transcription de discours, tels que le service {{site.data.keyword.IBM_notm}} {{site.data.keyword.speechtotextshort}}, génèrent un texte écrit à partir de mots prononcés. Etant donné qu'à chaque moteur de transcription est associée une plage d'exactitude spécifique, les clients qui transcrivent le discours en texte afin de l'utiliser comme entrée dans le service {{site.data.keyword.personalityinsightsshort}} doivent savoir que les résultats varient de façon significative en fonction des performances du moteur. Plus spécifiquement, {{site.data.keyword.IBM_notm}} conseille aux clients et aux partenaires commerciaux de déterminer la qualité de la transcription par rapport à deux types d'erreurs :

-   *Retrait :* un mot prononcé est omis de la transcription.
-   *Substitution :* un mot prononcé n'est pas correctement transcrit.

La substitution peut constituer un problème plus grave car elle est susceptible d'introduire des mots qui n'ont pas été prononcés mais qui correspondent à des mots qui ont été utilisés pour déterminer la personnalité. Avant d'utiliser un texte transcrit, vous devez envisager de corriger manuellement le texte d'un recueil de test et de comptabiliser les erreurs trouvées. Ensuite, vous pouvez comparer les résultats du texte généré automatiquement avec la version corrigée manuellement afin de déterminer les différences de résultats liées à des erreurs de transcription. 

### Déduction d'une personnalité à partir d'un texte traduit
{: #translation}

Des services de traduction traduisent un texte dans une autre langue. Comme pour la transcription de discours, l'on peut se demander si le texte traduit peut être utilisé comme entrée dans le service {{site.data.keyword.personalityinsightsshort}}. {{site.data.keyword.IBM_notm}} ne recommande pas d'utiliser le texte obtenu après avoir été traduit par les services de traduction comme entrée dans le service {{site.data.keyword.personalityinsightsshort}}. Selon le service de traduction, les résultats de la traduction et de la déduction de personnalité peuvent varier de manière significative. Les mots, leur sens, ainsi que les sensibilités culturelles tendent à se retrouver perdus lors de la traduction, ce qui génère des résultats incorrects. 

{{site.data.keyword.IBM_notm}} recommande d'utiliser comme entrée uniquement le texte qui est écrit dans des langues pour lesquelles le service {{site.data.keyword.personalityinsightsshort}} est activé. Les versions du service pour lesquelles une langue est activée effectuent l'analyse syntaxique du texte d'entrée dans sa langue maternelle, utilisent des dictionnaires en langue maternelle pour identifier des caractéristiques de personnalité et utilisent des modèles qui sont calibrés pour la langue maternelle afin de produire des résultats statistiques. Si vous devez analyser le texte traduit, {{site.data.keyword.IBM_notm}} vous recommande de commencer par traduire des échantillons de texte en faisant appel aux services d'un expert en langage humain. Vous pouvez ensuite comparer les résultats obtenus par le service {{site.data.keyword.personalityinsightsshort}} à partir du texte traduit manuellement et du texte traduit automatiquement pour comprendre les différences de résultats. 

{{site.data.keyword.IBM_notm}} continuera d'ajouter des langues pour répondre aux demandes de plus en plus croissantes des entreprises. {{site.data.keyword.IBM_notm}} comprend que la prise en charge de votre langue maternelle par le service {{site.data.keyword.personalityinsightsshort}} n'est peut-être pas suffisamment rapide pour répondre à vos objectifs. {{site.data.keyword.IBM_notm}} réalise actuellement des tests visant à comparer les résultats obtenus à partir de l'activation de langue maternelle aux résultats obtenus à l'aide des services de traduction et communiquera ses résultats dès qu'ils seront disponibles. 

## Utilisation de portraits de personnalité pour des applications spécifiques
{: #applying}

Le service {{site.data.keyword.personalityinsightsshort}} peut être appliqué à un nombre incalculable de cas d'utilisation. Les sections suivantes décrivent l'utilisation de portraits de personnalité pour quelques objectifs spécifiques :

-   [Mise en correspondance d'individus](#matching)
-   [Surveillance et prédiction en matière de santé mentale](#mentalhealth)
-   [Surveillance d'éléments radicaux et indésirables via des médias sociaux](#monitoring)

### Mise en correspondance d'individus
{: #matching}

Etablir une bonne compatibilité entre des personnes peut permettre d'améliorer l'interaction et les résultats en matière de relations. Cela vaut lorsqu'il s'agit de constituer des équipes au sein d'une entreprise et en matière d'interaction avec des clients au sein d'une vaste gamme de branches d'activité. Lors d'une étude de mise en correspondance entre des médecins et des patients, des chercheurs ont découvert que les patients préfèrent des médecins qui leur ressemblent. Une mise en correspondance efficace entre des médecins et des patients crée un climat de confiance et encourage la communication, ce qui peut permettre d'améliorer la conformité et les résultats dans un traitement plus efficace ([Godager, 2012](/docs/services/personality-insights/references.html#godager2012)).

La personnalité influence également les préférences d'interaction entre des professionnels et des clients. Par exemple, les patients présentant un fort tempérament consciencieux et d'ouverture préfèrent être impliqués activement dans la prise de décision relative à leur traitement. Les patients présentant des niveaux élevés d'amabilité ou de neuroticisme préfèrent que les décisions médicales importantes les concernant soient prises par les médecins ([Flynn &amp; Smith, 2007](/docs/services/personality-insights/references.html#flynn2007)).

### Surveillance et prédiction en matière de santé mentale
{: #mentalhealth}

{{site.data.keyword.IBM_notm}} considère que les diagnostics médicaux sont mieux établis par des professionnels de santé formés. Il peut être possible de détecter des signes de pathologie mentale chez des individus à partir des mots qu'ils emploient. Mais, {{site.data.keyword.IBM_notm}} n'a réalisé aucune recherche dans cet espace pour mener des études de données de référence ou explorer la possibilité d'établir une base scientifique pour ces travaux. 

Les clients et les partenaires commerciaux qui sont intéressés par l'utilisation du service {{site.data.keyword.personalityinsightsshort}} dans le but d'établir des diagnostics relatifs à la santé mentale sont encouragés à concevoir et mener des expérimentations de données de référence pour ce type de cas d'utilisation. Des recherches actives et continues dans ce domaine impliquent de mener des travaux ayant pour but de lier la personnalité aux résultats en matière de santé ([Israel et al., 2014](/docs/services/personality-insights/references.html#israel2014)) et de prédire  le post-partum et d'autres formes de dépression à partir des médias sociaux ([De Choudhury et al., 2013a](/docs/services/personality-insights/references.html#dechoudhury2013a) et [De Choudhury et al., 2013b](/docs/services/personality-insights/references.html#dechoudhury2013b)).

### Surveillance d'éléments radicaux et indésirables via des médias sociaux
{: #monitoring}

Des organismes gouvernementaux répartis dans le monde entier sont constamment à la recherche de moyens leur permettant de détecter le plus tôt possible des signes de radicalisation chez des individus ou des groupes d'individus par le biais des médias sociaux. Déduire des traits de personnalité à partir des écrits réalisés par des individus est une application traditionnelle du service {{site.data.keyword.personalityinsightsshort}}. Par conséquent, il n'est pas surprenant que l'utilisation du service pour déduire des éléments radicaux et indésirables via des médias sociaux soit un cas d'utilisation viable. Des déductions fiables ne requièrent pas seulement des caractéristiques de personnalité mais également un ensemble d'autres attributs, tels que le sexe, l'âge et l'emplacement géographique. {{site.data.keyword.IBM_notm}} n'a réalisé aucune étude permettant de valider ou d'invalider ce cas d'utilisation. Les clients et les partenaires commerciaux sont encouragés à mener des études visant à explorer ce cas d'utilisation en fonction de leurs objectifs et exigences spécifiques. 

## La personnalité d'une personne peut-elle changer au fil du temps ?
{: #evolve}

La personnalité d'une personne peut-elle changer au fil du temps ? Si tel est le cas, avec quelle fréquence le service {{site.data.keyword.personalityinsightsshort}} doit-il être utilisé pour déduire la personnalité d'une personne ? Différentes études sont venues confirmer et infirmer la théorie selon laquelle la personnalité d'un individu se stabilise lorsque celui atteint l'âge adulte. Lors d'une étude majeure menée en 1890 dans le but de mesurer la stabilité de la personnalité et intitulée *The Principles of Psychology*, le psychologue William James diplômé d'Harvard constatait que "Pour la plupart d'entre nous, lorsque nous atteignons l'âge de trente ans, notre tempérament s'est figé comme de l'enduit et il ne peut plus s'assouplir.". Mais, des études plus récentes démontrent que la personnalité change effectivement au fil du temps : 

-   [Helson et al. (2002)](/docs/services/personality-insights/references.html#helson2002) stipulent "l'idée selon laquelle le changement de personnalité est davantage prononcé avant l'âge de 30 ans, puis atteint un pallier n'a reçu aucun soutien". Les auteurs ont réalisé une étude longitudinale sur deux cohortes sur une période de 40 ans. Ils constatent que les étapes de la vie et le climat social sont des facteurs significatifs de changement de personnalité chez les individus ayant atteint l'âge adulte. Ainsi, ils notent que les "scores en matière de dominance et d'indépendance atteignent un niveau maximum chez les deux cohortes à la cinquantaine et que les scores en matière de responsabilité ont atteint les niveaux les plus bas lors des années emblématiques de la culture de l'individualisme". 
-   Le document [Scollon et Diener (2006)](/docs/services/personality-insights/references.html#scollon2006) s'attachent à examiner les différences individuelles en matière de changement d'extraversion, de neuroticisme et de satisfaction dans le travail et dans les relations au fil du temps. Les auteurs constatent qu'une augmentation de la satisfaction dans le travail et les relations était associée à une diminution du neuroticisme et à une augmentation de l'extraversion au fil du temps. 
-   Le document [Roberts et Mroczek (2008)](/docs/services/personality-insights/references.html#roberts2008) stipulent qu'il existe des preuves visant à démontrer un "changement de niveau moyen dans les traits de personnalité, ainsi que des différences individuelles au cours d'un cycle de vie". Les auteurs constatent que les personnes montrent davantage de confiance en soi, de chaleur, de sang-froid et de stabilité émotionnelle avec l'âge. Ces changements sont prédominants chez les jeunes adultes (âgés de 20 à 40 ans). De plus, le changement de niveau moyen dans les caractéristiques de personnalité se produit vers la cinquantaine ou chez les personnes du troisième âge, ce qui indique que l'individu peut voir ses caractéristiques de personnalité changer à n'importe quel âge. 

Sur la base de ces études, {{site.data.keyword.IBM_notm}} recommande aux utilisateurs du service {{site.data.keyword.personalityinsightsshort}} de toujours travailler avec les données les plus récentes et avec le plus de données disponibles. {{site.data.keyword.IBM_notm}} recommande également aux utilisateurs d'actualiser les portraits de personnalité à intervalles réguliers afin de capturer les personnalités changeantes des individus. Si {{site.data.keyword.IBM_notm}} a tendance à considérer que l'évolution de la personnalité est limitée, elle n'a mené aucune étude visant à examiner les limites supérieures et inférieures de cette évolution. 

On peut se demander avec quelle régularité il convient d'actualiser les portraits de personnalité d'individus. {{site.data.keyword.IBM_notm}} recommande de vérifier la disponibilité de nouvelles données et de nouveaux textes pour un individu donné. Si un individu a produit une quantité importante de nouveau texte depuis que son portrait de personnalité a été obtenu, il peut s'avérer judicieux d'actualiser celui-ci. Cette approche non seulement capture la nature évolutive de la personnalité, si l'on accepte le fait que cette personnalité puisse évoluer, mais elle permet également au service {{site.data.keyword.personalityinsightsshort}} de travailler avec davantage de mots, ce qui est susceptible d'augmenter la précision des résultats du service. 
