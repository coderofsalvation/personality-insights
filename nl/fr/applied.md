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

# Le service en action
{: #applied}

{{site.data.keyword.IBM_notm}} et d'autres chercheurs ont validé un grand nombre d'hypothèses liées à des applications réelles de caractéristiques de personnalité. Ces études ont contribué au développement du service {{site.data.keyword.personalityinsightsshort}}. Leurs résultats fournissent des connaissances relatives à certaines des procédures que vous pouvez utiliser pour appliquer le service à vos objectifs métier et de communications. Pour plus d'informations sur la recherche qui sous-tend le service {{site.data.keyword.personalityinsightsshort}}, voir [L'aspect scientifique du service](/docs/services/personality-insights/science.html).
{: shortdesc}

## Etudes menées par des chercheurs IBM
{: #appliedIBM}

Les études ci-après menées par des chercheurs {{site.data.keyword.IBM_notm}} indiquent que le fait d'appliquer les résultats du service peuvent générer des résultats tangibles dans de multiples domaines. Les études ont directement contribué au développement du service. Le tableau comprend des liens vers des sections comportant davantage d'informations sur chaque étude. 

<table>
  <caption>Tableau 3. Etudes menées par IBM</caption>
  <tr>
    <th style="text-align:left; width:25%">Etude</th>
    <th style="text-align:center; width:25%">Objets</th>
    <th style="text-align:left; width:50%">Effet des caractéristiques de personnalité</th>
  </tr>
  <tr>
    <td>
      <a href="#IBMrespond"><strong>Répondre à des tweets</strong></a>
      <br/>(collecte d'informations)
</td>
    <td style="text-align:center">2000 utilisateurs Twitter</td>
    <td>
      <strong>Plus enclins à répondre :</strong> Score élevé sur les dimensions et les facettes Big Five pour la recherche de sensations, la convivialité, le niveau d'activité, la fiabilité, la moralité, l'extraversion et l'amabilité
<br/><br/>
      <strong>Moins enclins à répondre : </strong> Score élevé sur les facettes Big Five pour la prudence et l'anxiété
</td>
  </tr>
  <tr>
    <td>
      <a href="#IBMretweet"><strong>Re-tweeter</strong></a>
      <br/>(diffusion d'informations)
</td>
    <td style="text-align:center">3500 utilisateurs Twitter</td>
    <td>
      <strong>Plus enclins à re-tweeter :</strong> Score élevé sur les dimensions et les facettes Big Five pour la modestie, l'ouverture et la convivialité
</td>
  </tr>
  <tr>
    <td>
      <a href="#IBMtarget"><strong>Publicité ciblée</strong></a>
<br/>(publicité non sollicitée)
</td>
    <td style="text-align:center">Plus de 6000 utilisateurs Twitter</td>
    <td>
      <strong>Répondre plus favorablement :</strong> Score élevé sur la dimension Big Five pour l'ouverture et score faible sur la dimension Big Five pour la portée émotionnelle
</td>
  </tr>
  <tr>
    <td>
      <a href="#IBMcampaign"><strong>Campagnes marketing</strong></a>
      <br/>(remboursement de coupon)
</td>
    <td style="text-align:center">Des milliers de clients de détail</td>
    <td>
      <strong>Plus enclins à répondre :</strong> Score élevé sur les facettes Big Five pour l'ordre, l'autodiscipline et la prudence et score faible sur la facette Big Five pour l'immodération
</td>
  </tr>
  <tr>
    <td>
      <a href="#IBMbrand"><strong>Préférence de marque</strong></a>
      <br/>(affinité de marque)
</td>
    <td style="text-align:center">600 utilisateurs Twitter</td>
    <td>
      <strong>Prédicteurs de préférence de marque :</strong> dimensions et facettes Big Five - tempérament consciencieux, conservation, ambition personnelle et amabilité ; Besoins - amour et idéal ; Valeur - hédonisme
</td>
  </tr>
  <tr>
    <td>
      <a href="#IBMmember"><strong>Satisfaction des membres</strong></a>
      <br/>(respect de la communauté)
</td>
    <td style="text-align:center">Plus de 3000 membres de communauté</td>
    <td>
      <strong>Prédicteurs de satisfaction des membres :</strong> caractéristiques telles que la colère, l'anxiété, le travail, les loisirs, l'inhibition, le consentement et l'utilisation du pronom à la première personne
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMreading"><strong>Préférence de lecture</strong></a>
<br/>(intérêt de contenu)
</td>
    <td style="text-align:center">Plus de 200 participants</td>
    <td>
      <strong>Intérêt pour les articles sur l'environnement :</strong> Score élevé pour le dépassement de soi
<br/><br/>
      <strong>Intérêt pour les articles sur le travail :</strong> Score élevé pour l'ambition personnelle
</td>
  </tr>
  <tr>
    <td>
      <a href="#IBMpreferences"><strong>Prédiction des préférences de consommation</strong></a>
<br/>(achat des consommateurs)
</td>
    <td style="text-align:center">Des centaines de milliers d'enregistrements de données</td>
    <td>
      <strong>Prédiction des préférences de consommateur :</strong> données démographiques et caractéristiques de personnalité
</td>
  </tr>
</table>

### Répondre à des tweets
{: #IBMrespond}

{{site.data.keyword.IBM_notm}} a découvert que des personnes ayant des caractéristiques de personnalité spécifiques répondent plus facilement à des tâches de collecte d'informations. {{site.data.keyword.IBM_notm}} a récemment réalisé une étude sur plus de 2000 utilisateurs Twitter afin de comprendre les facteurs qui influencent la propension à réagir à de telles tâches et de développer des modèles afin de prédire les réponses à des questions ([Mahmud et al., 2013](/docs/services/personality-insights/references.html#mahmud2013) et [Mahmud et al., 2014](/docs/services/personality-insights/references.html#mahmud2014)).

{{site.data.keyword.IBM_notm}} a formé le modèle qui a été utilisé pour l'étude à partir de deux jeux de données question-réponse dans lesquels des questions portant sur des emplacements ou sur des produits ont été posées à des utilisateurs Twitter. Les questions dépendaient selon que les utilisateurs avaient signalé qu'ils étaient présents à un emplacement ou qu'ils possédaient un produit. A l'instar des fonctions du modèle de prévision, {{site.data.keyword.IBM_notm}} a inclus le comportement social (par exemple, taux de réponse passé et activité de tweet), la disponibilité (par exemple, durée d'inactivité de l'utilisateur), les fonctions de catégorie du dictionnaire psycholinguistique LIWC (Linguistic Inquiry and Word Count) et les dimensions et facettes Big Five. 

{{site.data.keyword.IBM_notm}} a trouvé un ensemble de caractéristiques de personnalité Big Five significatives pour prédire la probabilité que présente une personne à répondre. Plus spécifiquement, {{site.data.keyword.IBM_notm}} a établi que les individus qui obtiennent un score élevé sur les dimensions et les facettes pour la recherche de sensations, la convivialité, le niveau d'activité, la fiabilité, la moralité, l'extraversion et l'amabilité sont plus enclins à répondre à des tweets. Sinon, les individus qui obtiennent un score élevé sur les facettes de prudence et d'anxiété sont moins enclins à répondre.
Ces résultats se sont avérés être significatifs d'un point de vue statistique (valeur p &lt; 0.05).

### Re-tweeter
{: #IBMretweet}

De même, {{site.data.keyword.IBM_notm}} a découvert que des personnes ayant des caractéristiques de personnalité spécifiques étaient plus nombreuses à répondre à des tâches de diffusion d'informations. {{site.data.keyword.IBM_notm}} a récemment mené une autre étude sur plus de 3500 utilisateurs Twitter afin de comprendre les facteurs qui augmentent la probabilité que présentent des individus à re-tweeter des informations et de développer des modèles afin de prédire un comportement qui consiste à re-tweeter ([Lee et al., 2014](/docs/services/personality-insights/references.html#lee2014)).

A l'instar des fonctions du modèle utilisé pour l'étude, {{site.data.keyword.IBM_notm}} a inclus l'activité de médias sociaux passée, les informations de profil de médias sociaux, la disponibilité, le dictionnaire LIWC et les dimensions et facettes Big Five. L'étude a démontré qu'un ensemble de caractéristiques Big Five est significatif pour prédire la propension à re-twitter. Par exemple, les résultats indiquent que des individus qui obtiennent un score élevé sur les dimensions et les facettes pour la modestie, l'ouverture et la convivialité sont plus enclins à diffuser des informations. Ces résultats se sont avérés être significatifs d'un point de vue statistique (valeur p &lt; 0.05).

### Publicité ciblée

{: #IBMtarget}

{{site.data.keyword.IBM_notm}} a découvert que des personnes ayant des caractéristiques de personnalité spécifiques répondent plus favorablement à des tâches de publicité ciblée. Récemment, {{site.data.keyword.IBM_notm}} a créé un service d'informations de voyage basé sur Twitter dans le but de tester l'hypothèse selon laquelle certains utilisateurs Twitter répondent plus favorablement à des publicités spontanées provenant du service. L'hypothèse a prédit que ces utilisateurs seraient plus enclins à cliquer sur un lien vers une publicité ou à suivre un compte. {{site.data.keyword.IBM_notm}} a mené deux études basées sur ce cas d'utilisation et les effets hypothétiques de personnalité ([Chen et al., 2015](/docs/services/personality-insights/references.html#chen2015)).

Dans le cadre d'une étude basée sur une enquête, {{site.data.keyword.IBM_notm}} a demandé à 133 utilisateurs Twitter d'indiquer de quelle façon ils répondraient probablement à un tweet faisant la publicité pour un service d'informations de voyage. {{site.data.keyword.IBM_notm}} a ensuite utilisé des questionnaires traditionnels pour mesurer la personnalité de ces utilisateurs. Dans le cadre d'une étude de terrain, {{site.data.keyword.IBM_notm}} a envoyé des tweets publicitaires au sujet du service à plus de 5900 utilisateurs Twitter qui voyagent. {{site.data.keyword.IBM_notm}} a ensuite utilisé le service {{site.data.keyword.personalityinsightsshort}} pour déduire les caractéristiques de personnalité des utilisateurs à partir de leurs derniers tweets. 

Les deux études ont généré des résultats cohérents : les individus qui obtiennent un score élevé sur la dimension d'ouverture et un score faible sur la dimension de portée émotionnelle (neuroticisme) répondent bel et bien plus favorablement à la publicité. Ces résultats sont avérés en dépit des différentes approches qui ont été utilisées par les études pour obtenir les caractéristiques de personnalité des utilisateurs. Le ciblage du 10 % d'utilisateurs qui obtiennent un score d'ouverture élevé et un score de portée émotionnelle faible a entraîné une augmentation de 6,8 % à 11,3 % du taux de clic et une augmentation de 4,7 % à 8,8 % du taux de suivi. Ces résultats se sont avérés être significatifs d'un point de vue statistique (valeur p &lt; 0.05).

### Campagnes marketing
{: #IBMcampaign}

{{site.data.keyword.IBM_notm}} a récemment travaillé avec un gros distributeur afin de déduire les caractéristiques de plusieurs milliers de ses clients qui participent à des campagnes marketing. Le distributeur envoie des bons de réduction à ses clients. Une réponse positive a été définie pour l'échange de n'importe quel bon de réduction. Selon une théorie psychologique, les individus qui obtiennent des scores élevés pour les facettes Big Five de l'ordre, de l'autodiscipline et de la prudence et des scores faibles pour la facette de l'immodération sont plus enclins à échanger des bons de réduction. 

{{site.data.keyword.IBM_notm}} a validé l'hypothèse en utilisant les données clients et les caractéristiques de personnalité déduites. {{site.data.keyword.IBM_notm}} a commencé par segmenter la population de clients en quartiles en fonction des caractéristiques de personnalité de chaque individu. En faisant appel à des scores de percentile normalisés pour les caractéristiques (avec une échelle de 1 à 100), {{site.data.keyword.IBM_notm}} a utilisé une combinaison linéaire afin de calculer un score combiné pour chaque client : 

*Ordre + Autodiscipline + Prudence + (100 - Immodération)*

{{site.data.keyword.IBM_notm}} a ensuite comparé les résultats des clients du quartile le plus élevé avec ceux des clients du quartile le plus bas, en ignorant la moitié de la population. L'étude a révélé que les individus possédant les caractéristiques supposées sont 40 % plus enclins à réagir à des bons de réduction que les individus issus d'un échantillon aléatoire de la population. 

### Préférence de marque
{: #IBMbrand}

{{site.data.keyword.IBM_notm}} a mené une étude sur plus de 600 utilisateurs Twitter afin de comprendre si les caractéristiques de personnalité Big Five, Valeurs et Besoins permettent de prédire les préférences des utilisateurs pour telle ou telle marque (s'ils aiment ou non une marque). L'étude a évalué 22 marques de six catégories : voitures de luxe, boissons, restauration rapide, distribution, shampoings et smartphones. {{site.data.keyword.IBM_notm}} a établi des données de référence pour la préférence de marque en réalisant une enquête auprès des utilisateurs. 

L'étude a démontré que les caractéristiques de personnalité peuvent prédire la préférence de marque avec un taux d'exactitude de 65 %. Plus spécifiquement, l'étude a révélé que les dimensions et facettes Big Five (tempérament consciencieux, conservation, ambition personnelle et amabilité), Besoins (amour et idéal) et Valeur (hédonisme) sont les caractéristiques les plus susceptibles de prédire la préférence de marque. 

### Satisfaction des membres
{: #IBMmember}

{{site.data.keyword.IBM_notm}} a réalisé une étude sur ses employés qui font partie de communautés d'espace de travail en ligne afin de déterminer si la langue qu'ils utilisent au sein des communautés a un rapport avec leur niveau de satisfaction vis-à-vis d'elles ([Matthews et al., 2015](/docs/services/personality-insights/references.html#matthews2015)). {{site.data.keyword.IBM_notm}} a mesuré la satisfaction des communautés en réalisant des enquêtes basées sur l'auto-déclaration. {{site.data.keyword.IBM_notm}} a examiné 142 communautés d'espace de travail. En fonction de la taille des communautés, {{site.data.keyword.IBM_notm}} a étudié 20 à 26 membres de chaque communauté. 

L'étude a démontré qu'il existe une corrélation entre la langue utilisée dans les communautés, telle qu'elle est mesurée par le dictionnaire LIWC, et la satisfaction des membres. Plus spécifiquement, l'étude a démontré que les catégories LIWC, telles que la colère, l'anxiété, le travail, les loisirs, l'inhibition, le consentement et l'utilisation du pronom à la première personne sont de bons prédicteurs de la satisfaction des membres. {{site.data.keyword.IBM_notm}} s'attend à ce que les caractéristiques qui sont calculées à partir du texte d'une communauté concordent bien avec la satisfaction des membres vis-à-vis de la communauté. 

### Préférence de lecture
{: #IBMreading}

{{site.data.keyword.IBM_notm}} a mené une étude visant à comprendre le lien entre la caractéristique Valeurs et les intérêts de lecture([Hsieh et al., 2014](/docs/services/personality-insights/references.html#hsieh2014)). {{site.data.keyword.IBM_notm}} a émis l'hypothèse suivante :

1.  Les individus qui obtiennent un score de dépassement de soi plus élevé seront plus intéressés par des articles concernant l'environnement.
1.  Les individus qui obtiennent un score d'ambition personnelle plus élevé seront plus intéressés par des articles concernant leur travail. 
1.  Les individus qui obtiennent un score d'hédonisme plus élevé seront plus intéressés par les contenus relatifs aux loisirs. 

{{site.data.keyword.IBM_notm}} a recruté plus de 200 participants pour l'étude auprès de la plateforme Amazon Mechanical Turk. Ces personnes ont participé à une enquête portant sur les caractéristiques Valeurs et répondu à des questions sur leur niveau d'intérêt pour la lecture de différents articles. 

L'étude a confirmé les deux premières hypothèses : les personnes ayant obtenu un score plus élevé pour la valeur de dépassement de soi ont montré un intérêt particulier pour la lecture d'articles concernant l'environnement et les personnes ayant obtenu un score plus élevé pour la valeur d'ambition personnelle ont montré un intérêt particulier pour la lecture d'articles concernant leur travail. Ces résultats se sont avérés être significatifs d'un point de vue statistique (valeur p &lt; 0.05).

Cependant, l'étude a révélé qu'il existe une faible corrélation entre la valeur hédonisme et un intérêt pour la lecture de contenus relatifs aux loisirs. Cette faible corrélation peut signifier que les personnes ne considèrent pas que la lecture est une activité hédoniste, quel que soit le sujet de l'article. 

### Prédiction des préférences de consommation
{: #IBMpreferences}

{{site.data.keyword.IBM_notm}} a collaboré avec [Acxiom ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](http://www.acxiom.com/){: new_window} pour déterminer si le portrait de personnalité d'un individu peut améliorer le niveau d'exactitude des prédictions relatives aux préférences de consommation des individus par rapport aux prédictions qui se fondent uniquement sur des attributs démographiques. L'étude a examiné 133 préférences de consommation pour environ 785 000 individus aux Etats-Unis. Le fait d'ajouter des caractéristiques de personnalité à des attributs démographiques a permis d'améliorer le niveau d'exactitude prédictive pour 115 préférences (86,5 %) et pour 23 des préférences, l'utilisation des seules caractéristiques de personnalité offre un meilleur niveau d'exactitude que l'utilisation des seuls attributs démographiques. 

L'étude était fondée sur deux technologies : les résultats du service {{site.data.keyword.IBM_notm}} {{site.data.keyword.personalityinsightsshort}} et le produit Acxiom InfoBase, plus spécifiquement les éléments de données InfoBase Customer Enhancement. Acxiom est un fournisseur de données démographiques de premier plan qui répond aux besoins marketing de ses clients. Les données démographiques d'Acxiom, telles que l'âge, le sexe, les revenus, la taille du foyer, la tranche de revenu, etc. permettent notamment d'analyser et d'améliorer des données clients dans le but d'identifier des opportunités de vente et de conservation, de combler les lacunes relatives aux informations de contact des clients, de fournir une assistance pour l'analyse des informations clients et d'identifier des prospects. 

L'étude a analysé 133 attributs de consommation de comportement en fonction de 22 caractéristiques {{site.data.keyword.personalityinsightsshort}} et quatre catégories démographiques (sexe, éducation, revenu du foyer et âge). Les résultats démontrent une meilleure exactitude prédictive pour 115 des 133 préférences de consommation lorsque les données démographiques sont complétées par des caractéristiques de personnalité. De plus, le niveau d'exactitude inférieur pour les 18 préférences restantes peut être dû à la nature de la comparaison et à la façon dont les données ont été calculées. Des expérimentations futures mettront en oeuvre des comparaisons plus complexes pour voir si une approche différente permet d'améliorer davantage le niveau d'exactitude. 

Les résultats globaux révèlent que les caractéristiques {{site.data.keyword.personalityinsightsshort}} sont utiles pour prédire différentes préférences de consommation. L'utilisation conjointe de données démographiques et de caractéristiques de personnalité produit généralement un meilleur niveau d'exactitude prédictive. Cela dit, l'utilisation de {{site.data.keyword.personalityinsightsshort}} uniquement est une bonne alternative lorsqu'aucune donnée démographique n'est disponible. 

Pour plus d'informations sur l'étude, voir <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Improving-Consumption-Preferences-Accuracy.pdf" download="Improving-Consumption-Preferences-Accuracy.pdf">Improving-Consumption-Preferences-Accuracy.pdf <img src="../../icons/launch-glyph.svg" alt="External link icon" title="Icône de lien externe" class="style-scope doc-content"></a>. Pour plus d'informations sur le modèle des préférences de consommation utilisé dans l'étude, voir [Liu et al. (2016)](/docs/services/personality-insights/references.html#liu2016).

## Etudes menées par d'autres chercheurs
{: #appliedOthers}

De nombreuses études menées par des chercheurs qui ne font pas partie d'{{site.data.keyword.IBM_notm}} révèlent qu'il existe une corrélation et une capacité de prédiction entre la personnalité et divers résultats. Les sections ci-après décrivent ces études, qui corroborent et renforcent les recherches décrites dans la section précédente. 

### Préférences des consommateurs
{: #otherConsumer}

-   [Hirsh et al. (2012)](/docs/services/personality-insights/references.html#hirsh2012) ont étudié la réaction d'individus par rapport à différents messages marketing. Ils ont découvert que les individus répondent de manière plus positive à des messages adaptés à leur personnalité. 
-   [Chen (2011)](/docs/services/personality-insights/references.html#chen2011) a établi que dans le contexte du marketing en ligne, les individus présentant une caractéristique d'ouverture élevée sont plus curieux intellectuellement et ouverts à de nouvelles idées. Ces individus sont par conséquent plus enclins à essayer de nouvelles choses. 
-   [Westfall (1962)](/docs/services/personality-insights/references.html#westfall1962) a découvert qu'il existe des différences de personnalité entre les individus qui possèdent un cabriolet et les individus qui possèdent une voiture standard ou de petite taille. Les consommateurs qui obtiennent un score élevé pour la dimension Amabilité et la facette Ordre de la dimension Tempérament consciencieux préfèrent les voitures traditionnelles. En revanche, les consommateurs qui obtiennent un score élevé pour la dimension Ouverture choisiront sans hésiter un cabriolet. 
-   [Choo et Mokhtarian (2002)](/docs/services/personality-insights/references.html#choo2002) ont examiné le lien entre le choix d'un type de véhicule et des facteurs, tels que la personnalité, le style de vie, l'attitude et des données démographiques. Ils ont constaté que les individus qui obtiennent un score élevé pour les facettes Intrépidité, Recherche de sensations et Rébellion sont susceptibles de préférer les voitures puissantes. En revanche, les individus qui obtiennent un score élevé pour la dimension Amabilité sont susceptibles de ne pas aimer les voitures puissantes. 
-   [Kassarjian (1971)](/docs/services/personality-insights/references.html#kassarjian1971) a constaté que les automobilistes ont généralement tendance à percevoir les types de voitures qu'ils achètent comme des prolongements de leur personnalité. La section [Conscience écologique](#otherEnvironment) décrit de quelle façon la personnalité d'un individu peut influencer la préférence de celui-ci pour des véhicules peu polluants. 
-   [Myszkowski et Storme (2012)](/docs/services/personality-insights/references.html#myszkowski2012) ont découvert que la caractéristique Ouverture prédit de manière significative la tendance d'un individu à préférer et à réagir à des produits bien conçus. Cette étude suggère que les individus présentant un *faible* niveau d'ouverture ont tendance à réagir de manière plus prononcée à l'apparence d'un produit, ce qui amplifie le choix pour des produits design. A l'inverse, les individus présentant un niveau d'ouverture *élevé* ont tendance à se focaliser davantage sur d'autres aspects des produits, ce qui les conduit à négliger l'aspect esthétique. 
-   [Lin (2002)](/docs/services/personality-insights/references.html#lin2002) et [Sarli et  Tat (2011)](/docs/services/personality-insights/references.html#sarli2011) ont rapporté que les caractéristiques de personnalité affectent les préférences de marque d'un individu. 

### Préférences personnelles
{: #otherPersonal}

-   [Hu et Pu (2011)](/docs/services/personality-insights/references.html#hu2011) ont constaté que dans le domaine de la musique, les recommandations ont plus d'impact lorsqu'elles exploitent les corrélations entre la personnalité des individus et leurs préférences en matière de musique. 
-   [Chamorro-Premuzic et Furnham (2007)](/docs/services/personality-insights/references.html#chamorro2007) ont également constaté que les différences individuelles de personnalité et les capacités cognitives peuvent déterminer la façon dont les individus ressentent la musique. [Rentfrow et Gosling (2003)](/docs/services/personality-insights/references.html#rentfrow2003) ont rapporté des résultats similaires dans une étude antérieure. 
-   [Golbeck et Norris (2013)](/docs/services/personality-insights/references.html#golbeck2013) ont constaté qu'il existait des corrélations entre la personnalité et les préférences en matière de films parmi les utilisateurs de Netflix. 

### Habitudes de dépenses
{: #otherSpending}

-   [Pirog et Roberts (2007)](/docs/services/personality-insights/references.html#pirog2007) ont mis en évidence le lien entre les habitudes en matière de dépenses et la personnalité. Ils se sont focalisé sur l'usage abusif des cartes de crédit parmi les étudiants. Ils ont découvert que les étudiants qui obtiennent un score élevé pour la caractéristique Tempérament consciencieux ont tendance à utiliser des cartes de débit ou de l'argent liquide et à ne pas faire un usage abusif de cartes de crédit. A l'inverse, les individus qui obtiennent un score élevé pour le neuroticisme (portée émotionnelle) sont enclins à faire un usage abusif de cartes de crédit. 

### Profilage de risques
{: #otherRisk}

-   [Lauriola et Levin (2001)](/docs/services/personality-insights/references.html#lauriola2001) ont démontré que la personnalité influence des prises de décision risquées dans des investissements financiers. Ils en ont conclu que les individus qui obtiennent un score élevé pour l'ouverture aux expériences ont tendance à faire des investissements risqués. En revanche, le neuroticisme (portée émotionnelle) peut rendre les individus moins enclins à prendre de tels risques. 
-   [Nicholson et al. (2001)](/docs/services/personality-insights/references.html#nicholson2001) a élaboré plus avant la corrélation entre les caractéristiques Big Five et les profils de risques. Leurs résultats révèlent que les individus présentant les caractéristiques Amabilité et Tempérament consciencieux sont moins enclins à prendre des risques en général. En revanche, les individus qui obtiennent un score élevé pour la caractéristique Extraversion sont plus enclins à prendre des décisions risquées. 
-   [Tok (2011)](/docs/services/personality-insights/references.html#tok2011) a identifié le lien entre des caractéristiques de personnalité Big Five et la pratique de sports d'aventure dangereux, tels que le ski, le vélo de montagne, l'aviation, la glisse, le parapente et la plongée. Quatre des caractéristiques Big Five influencent directement la pratique de sports dangereux : les individus qui obtiennent un score élevé pour les caractéristiques Extraversion, Ouverture et Neuroticisme (portée émotionnelle) ont une plus grande tendance à pratiquer ces sports ; les individus qui obtiennent un score faible pour la caractéristique Tempérament consciencieux sont moins enclins à pratiquer de tels sports. 
-   [Hymbaugh et Garrett (1974)](/docs/services/personality-insights/references.html#hymbaugh1974) ont étudié les caractéristiques de personnalité des individus qui pratiquent le saut en parachute. Ils ont découvert que ces individus présentent des caractéristiques Recherche de sensations et Intrépidité plus élevées que l'ensemble de la population.  

### Performances professionnelles
{: #otherProfessional}

-  [Barrick et Mount (1991)](/docs/services/personality-insights/references.html#barrick1991) ont examiné le lien entre des dimensions de personnalité Big Five et les performances professionnelles. Ils ont découvert que des dimensions de personnalité, telles que Tempérament consciencieux, sont liées aux performances professionnelles pour tous les groupes professionnels qu'ils ont étudiés (professionnels, responsables, ventes, police, emplois qualifiés et semi-qualifiés). 
-   [Hurtz et Donovan (2000)](/docs/services/personality-insights/references.html#hurtz2000) ont rapporté que la caractéristique de personnalité Tempérament consciencieux est celle qui est la plus prédictive concernant les performances professionnelles. 
-   [Lim et Ployhart (2004)](/docs/services/personality-insights/references.html#lim2004) ont découvert que l'extraversion est corrélée de manière positive avec des aptitudes à diriger. 
-   [Judge et al. (2002)](/docs/services/personality-insights/references.html#judge2002) ont rapporté que des individu extravertis sont plus satisfaits au travail ; le travail leur donne la possibilité d'expérimenter un niveau optimal de stimulation. A l'inverse, les individus introvertis sont moins satisfaits au travail en raison d'une stimulation trop importante. 
-   [van Vianen et al. (2012)](/docs/services/personality-insights/references.html#vanvianen2012) ont mis en évidence des différences individuelles en matière d'adaptabilité, ainsi que les causes, les corrélations et les conséquences de ces différences. Ils ont découvert que les caractéristiques Tempérament consciencieux, Extraversion et Ouverture sont corrélées de manière positive avec la souplesse professionnelle. 

### Performances scolaires
{: #otherAcademic}

-   [Chamorro-Premuzic et Furnham (2003)](/docs/services/personality-insights/references.html#chamorro2003) ont présenté une étude longitudinale dans laquelle ils ont découvert que les caractéristiques de personnalité ont un impact sur les performances scolaires. Plus spécifiquement, ils ont constaté que le neuroticisme (portée émotionnelle) peut porter atteinte aux performances scolaires et qu'un tempérament consciencieux peut mener à une brillante réussite scolaire. 
-   [Komarraju et Karau (2005)](/docs/services/personality-insights/references.html#komarraju2005) ont révélé que certaines caractéristiques de personnalité ont un impact sur le comportement des individus en matière d'apprentissage du développement personnel. L'étude révèle que les individus ayant une ouverture et un tempérament consciencieux développés ont souvent un plus grand intérêt que les autres pour l'apprentissage du développement personnel et qu'un niveau de neuroticisme (portée émotionnelle) élevé diminue la motivation pour ce type d'apprentissage. 

### Relations professionnelles
{: #otherProRelations}

-   [Flynn et Smith (2007)](/docs/services/personality-insights/references.html#flynn2007) ont découvert que la personnalité influence les préférences d'interaction entre des professionnels et des clients. Par exemple, les patients présentant un fort tempérament consciencieux et d'ouverture préfèrent être impliqués activement dans la prise de décision relative à leur traitement. Les patients présentant des niveaux élevés d'amabilité ou de portée émotionnelle (neuroticisme) préfèrent que les décisions médicales importantes les concernant soient prises par les médecins. 
-   [Duberstein et al. (2007)](/docs/services/personality-insights/references.html#duberstein2007) ont également rapporté que les personnalités des médecins affectent le niveau de satisfaction de leurs patients. Par exemple, les patients ont indiqué qu'ils étaient plus satisfaits avec des médecins ayant obtenu un score relativement élevé en matière d'ouverture et un score moyen en matière de tempérament consciencieux. 

### Relations personnelles
{: #otherPerRelations}

-   [Botwin et al. (1997)](/docs/services/personality-insights/references.html#botwin1997) ont découvert que la personnalité affecte les relations amoureuses. Les caractéristiques de personnalité du partenaire d'une personne sont significatives pour prédire une situation d'insatisfaction conjugale, en particulier lorsque le partenaire obtient un score plus faible que souhaité en matière d'amabilité, de portée émotionnelle et d'ouverture. 

### Santé
{: #otherHealth}

-   [Turiano et al. (2012)](/docs/services/personality-insights/references.html#turiano2012) ont présenté une étude longitudinale conduite sur une période de 10 ans au cours de laquelle ils ont constaté que des caractéristiques Big Five pouvaient prédire des résultats liés à la santé. Par exemple, toutes les caractéristiques, à l'exception de l'ouverture, ont prédit des informations de santé physique déterminées par auto-évaluation et toutes les caractéristiques, à l'exception de l'amabilité, ont prédit un nombre de jours de travail limité en raison de la santé physique. 
-   [Masui et al. (2006)](/docs/services/personality-insights/references.html#masui2006) ont constaté que les individus qui obtiennent un score élevé pour les caractéristiques de personnalité Tempérament consciencieux, Extraversion et Ouverture vivent plus longtemps. D'autres chercheurs ont également découvert un lien entre les caractéristiques de personnalité Big Five et l'espérance de vie. 
-   [Roberts et al. (2007)](/docs/services/personality-insights/references.html#roberts2007) ont rapporté que des caractéristiques de personnalité spécifiques prédisent des évolutions de vie importantes, par exemple, la mortalité, le divorce et la réussite professionnelle. 

### Régime alimentaire et activité physique
{: #otherDiet}

-   [Shepherd et Sparks (1994)](/docs/services/personality-insights/references.html#shepherd1994) ont développé le lien entre la personnalité et le choix des aliments. Leur étude révèle que les individus qui obtiennent des scores élevés pour la caractéristique Portée émotionnelle (Neuroticisme), en particulier pour la facette Immodération, ont tendance à consommer de la nourriture riche en matières grasses. 
-   [Elfhag et Morey (2008)](/docs/services/personality-insights/references.html#elfhag2008) ont révélé que la caractéristique Tempérament consciencieux est liée de façon positive à une préférence pour la nourriture pauvre en matières grasses. Plus précisément, les facettes Autodiscipline et Sens du devoir de la dimension Tempérament consciencieux influencent de façon positive la consommation de nourriture pauvre en matières grasses et (comme la gestion du poids est étroitement liée au choix des aliments) un contrôle régulier du poids. 
-   [Heaven at al. (2001)](/docs/services/personality-insights/references.html#heaven2001) a rapporté que la consommation de nourriture saine est liée à deux dimensions Big Five. Les personnes qui présentent un niveau de neuroticisme (portée émotionnelle) élevé sont généralement moins enclins à choisir une nourriture saine tandis que les individus ayant un tempérament consciencieux développé seront enclins à consommer de la nourriture saine. L'article mentionne également plusieurs facettes qui sont subtilement liées aux choix des aliments : il existe une corrélation positive entre les intérêts artistiques (issus de la dimension Ouverture) et l'autodiscipline (issue de la dimension Tempérament consciencieux) et une plus grande consommation de nourriture saine ; à l'inverse, il existe une corrélation quelque peu négative entre le fait d'être sujet au stress et le fait de consommer de la nourriture saine. 
-   [Lusk (2012)](/docs/services/personality-insights/references.html#lusk2012) a découvert que les amateurs de bons plats obtiennent des scores élevés pour la dimension Ouverture à l'expérience. La dimension Ouverture peut pousser des individus à goûter différents aliments et leur permettre de devenir des gastronomes.
-   [Courneya et Hellsten (1998)](/docs/services/personality-insights/references.html#courneya1998) ont découvert que la personnalité influence la tendance d'un individu à garder des habitudes associées à un style de vie sain, y compris la pratique d'une activité physique. Il existe une corrélation positive entre les dimensions Extraversion et Tempérament consciencieux et la pratique plus fréquente d'une activité physique, tandis que le neuroticisme (dimension Portée émotionnelle) peut avoir une influence négative sur la fréquence de la pratique d'une activité physique. 

### Dîners à l'extérieur
{: #otherDining}

-   [Kim et al. (2010)](/docs/services/personality-insights/references.html#kim2010) ont démontré qu'il existe une corrélation positive entre la dimension Ouverture à l'expérience et le fait de dîner plus souvent à l'extérieur. Les individus qui obtiennent un score faible pour la dimension Ouverture dînent généralement moins souvent à l'extérieur. 
-   [van Trijp et Steenkamp (1992)](/docs/services/personality-insights/references.html#vantrijp1992) ont constaté qu'il existe une corrélation entre le fait de dîner à l'extérieur et la facette Recherche de sensations de la dimension Extraversion. 

### Conscience écologique
{: #otherEnvironment}

-   [Griskevicius et al. (2010)](/docs/services/personality-insights/references.html#griskevicius2010) ont découvert que la personnalité d'un individu influence son intérêt pour les questions environnementales. Ils ont étudié le lien entre la personnalité et un comportement soucieux de l'environnement, par exemple, utiliser un véhicule peu polluant et adopter un mode de vie écologique, pratiquer le jardinage, le recyclage, etc. Pour la plupart des individus, des niveaux élevés d'amabilité, d'ouverture et de tempérament consciencieux sont associés à une plus grande propension à adopter un comportement soucieux de l'environnement. 
-   [Fraj et Martinez (2006)](/docs/services/personality-insights/references.html#fraj2006) ont découvert que la personnalité influence la décision d'acheter des produits qui sont sans danger pour l'environnement. Les individus présentant des caractéristiques, telles que l'extraversion, l'amabilité et un tempérament consciencieux, sont plus enclins à acheter ce type de produit. 

### Service communautaire
{: #otherCommunity}

-   [Penner et al. (2005)](/docs/services/personality-insights/references.html#penner2005) ont mis en évidence le fait que la personnalité d'un individu affecte son engagement dans un service communautaire. Dans un article de synthèse, les auteurs mentionnent plusieurs facteurs de personnalité qui influencent un comportement prosocial. Ils ont découvert que l'extraversion et l'amabilité influencent positivement l'engagement dans un service communautaire. Plus spécifiquement, les facettes Altruisme et Coopération de la dimension Amabilité peuvent avoir le plus gros impact, tandis que la facette Convivialité de la dimension Extraversion a une corrélation positive plus subtile avec l'engagement dans un service communautaire. 

### Religion et spiritualité
{: #otherReligion}

-   [Adorno et al. (1950)](/docs/services/personality-insights/references.html#adorno1950), dans leur ouvrage devenu classique, *The Authoritarian Personality*, rapportent qu'il existe peut-être une corrélation entre les caractéristiques de personnalité et la religion. Ils suggèrent que les individus ayant un score élevé pour la dimension Amabilité sont plus religieux et que les individus ayant un score élevé pour la dimension Rébellion sont moins enclins à assister à des événements religieux et spirituels. 
