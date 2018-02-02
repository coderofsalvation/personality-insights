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

# Modèles de personnalité
{: #models}

Le service {{site.data.keyword.personalityinsightsshort}} est basé sur la psychologie de langage combinée aux algorithmes d'analyse de données. Le service analyse le contenu que vous envoyez et renvoie un profil de personnalité pour l'auteur de l'entrée. Le service déduit des caractéristiques de personnalité en fonction de trois modèles :
{: shortdesc}

-   Les caractéristiques de personnalité *Big Five* constituent
le modèle le plus utilisé pour décrire de façon générale la manière dont une
personne se comporte avec les autres. Le modèle inclut cinq dimensions primaires : 
    -   L'[*amabilité*](/docs/services/personality-insights/agreeableness.html) est la tendance d'une personne à être
bienveillante et à coopérer avec les autres.
    -   Le [*tempérament consciencieux*](/docs/services/personality-insights/conscientiousness.html) est la tendance
d'une personne à agir de façon organisée ou réfléchie.
    -   L'[*extraversion*](/docs/services/personality-insights/extraversion.html) est la tendance d'une personne à
rechercher une stimulation auprès des autres.
    -   La [*portée émotionnelle*](/docs/services/personality-insights/emotional-range.html) (ou *neuroticisme* ou
*réactions naturelles*) est la mesure dans laquelle les émotions d'une personne dépendent de l'environnement de celle-ci.

    -   L'[*ouverture*](/docs/services/personality-insights/openness.html) est la mesure dans laquelle une
personne est prête à expérimenter diverses activités.

Chacune de ces dimensions de niveau supérieur possède six facettes qui
caractérisent un individu de façon plus approfondie selon la dimension.
-   Les caractéristiques de type [Besoins](/docs/services/personality-insights/needs.html) décrivent quels sont
les aspects d'un
produit qui trouveront un écho chez une personne. Le modèle inclut douze besoins en termes de caractéristique :
-   Les caractéristiques de type [Valeurs](/docs/services/personality-insights/values.html) décrivent les facteurs qui motivent la prise de décision d'une personne. Le modèle inclut cinq valeurs. 

Pour plus d'informations sur la façon dont les modèles ont été développés et sur la façon dont le service les utilise, voir [L'aspect scientifique du service](/docs/services/personality-insights/science.html).

## Description des caractéristiques de personnalité Big Five
{: #bigFive}

Chaque dimension Big Five est décrite par trois tableaux :

-   Le tableau *Facettes* présente les facettes de la dimension et décrit les individus qui obtiennent des notes élevées pour chaque facette. 
-   Le tableau *Plage de caractéristiques* présente des descriptions générales susceptibles de s'appliquer à des individus dont les notes témoignent d'une proportion plus importante ou plus faible de chaque facette de la dimension, ainsi que des termes décrivant ces individus. Pour un tableau à une page pratique récapitulant les tableaux *Plage de caractéristiques* pour les facettes des cinq dimensions, voir <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Facet-Characteristics.pdf" download="Personality-Insights-Facet-Characteristics.pdf">Personality-Insights-Facet-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="External link icon" title="Icône de lien externe" class="style-scope doc-content"></a>.
-   Le tableau *Dimensions principale et secondaires* présente des informations qui relient la dimension à d'autres dimensions en décrivant des combinaisons de caractéristiques de personnalité. Le tableau fournit un éclairage intéressant sur la façon dont les caractéristiques principale et secondaires peuvent être mises en corrélation pour représenter la personnalité composite d'un individu. Pour un tableau à une page pratique récapitulant les tableaux *Dimensions principale et secondaires* pour les cinq dimensions, voir <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Dimension-Characteristics.pdf" download="Personality-Insights-Dimension-Characteristics.pdf">Personality-Insights-Dimension-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="External link icon" title="Icône de lien externe" class="style-scope doc-content"></a>.
