---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-27"

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

# A propos
{: #about}

> **Mise à jour du service :** *le service {{site.data.keyword.personalityinsightsshort}} a été mis à jour le 18 novembre 2018. Le service est maintenant disponible sur le site {{site.data.keyword.cloud}} de Londres. Pour plus d'informations, voir la [Mise à jour du service du 18 novembre 2018](/docs/services/personality-insights?topic=personality-insights-release-notes#November2018b) dans les notes sur l'édition.*

Le service {{site.data.keyword.personalityinsightsfull}} fournit une interface de programme d'application (API) permettant d'obtenir un éclairage à partir de médias sociaux, de données d'entreprise ou d'autres communications numériques. Le service utilise une analyse linguistique pour déduire les caractéristiques de personnalité intrinsèques d'individus à partir de communications numériques, telles que des e-mails, des messages texte, des tweets et des articles publiés sur un forum.
{: shortdesc}

Le service déduit des portraits d'individus reflétant leurs
caractéristiques de personnalité à partir de médias sociaux potentiellement
riches en informations. Il peut également déterminer les préférences de consommation des individus, qui indiquent leur propension à préférer différents produits et services et différentes activités.

## Caractéristiques de personnalité
{: #models-index}

Le service {{site.data.keyword.personalityinsightsshort}} déduit des caractéristiques de personnalité basées sur trois modèles principaux :

-   Les caractéristiques de personnalité **Big Five** constituent
le modèle le plus utilisé pour décrire de façon générale la manière dont une
personne se comporte avec les autres. Le modèle comprend cinq dimensions principales : *Amabilité*, *Tempérament consciencieux*, *Extraversion*, *Portée émotionnelle* et *Ouverture*. Chacune de ces dimensions possède six facettes qui
caractérisent un individu de façon plus approfondie selon la dimension.
-   Les caractéristiques de type **Besoins** décrivent quels sont
les aspects d'un
produit qui devraient trouver un écho chez une personne. Le modèle inclut douze besoins caractéristiques : *Enthousiasme*, *Harmonie*, *Curiosité*, *Idéal*, *Comportement clanique*, *Extériorisation*, *Liberté*, *Amour*, *Pragmatisme*, *Stabilité*, *Combativité* et *Structure*.
-   Les caractéristiques de type **Valeurs** décrivent les facteurs qui motivent la prise de décision d'une personne. Le modèle inclut cinq valeurs : *Dépassement de soi/Solidarité*, *Conservatisme/Tradition*, *Hédonisme/Se faire plaisir*, *Ambition personnelle/Réussite* et *Ouverture au changement/Enthousiasme*.

Pour plus d'informations, voir [Modèles de personnalité](/docs/services/personality-insights?topic=personality-insights-models).

## Préférences de consommation
{: #preferences-index}

En fonction des caractéristiques de personnalité déduites à partir du texte saisi, le service peut également renvoyer une indication des préférences de consommation de l'auteur. Les préférences de consommation indiquent la propension de l'auteur à rechercher différents produits et services et à exécuter différentes activités. Le service regroupe les préférences individuelles en huit catégories : *Achats*, *Musique*, *Cinéma*, *Lecture et apprentissage*, *Santé et activité*, *Bénévolat*, *Ecologie* et *Esprit d'entreprise*. Chaque catégorie contient entre une et une douzaine de préférences individuelles.

Pour plus d'informations, voir [Préférences de consommation](/docs/services/personality-insights?topic=personality-insights-preferences).

## Avantages du service
{: #benefits}

En tant que service de base de la plateforme {{site.data.keyword.ibmwatson}}, le service {{site.data.keyword.personalityinsightsshort}} peut fournir des connaissances pouvant aider les entreprises.

-   Comprendre leurs clients de manière plus approfondie en apprenant leurs préférences, en améliorant leur satisfaction et en renforçant les relations avec eux.
-   Améliorer la prospection de nouveaux clients, la fidélisation de leurs clients et leur engagement auprès de ces derniers.
-   Orienter et personnaliser de façon poussée leurs propositions et leurs interactions
afin de
mieux adapter leurs produits, services, campagnes et autres communications à des clients particuliers.

Pour plus d'informations sur la manière dont vous pouvez bénéficier des avantages liés au service, voir [Cas d'utilisation](/docs/services/personality-insights?topic=personality-insights-usecases).

## Support de langue
{: #languages-index}

Le service prend en charge les langues répertoriées ci-après. Vous pouvez utiliser n'importe quelle combinaison de langues prises en charge pour la demande et la réponse, mais une seule langue doit être utilisée pour la totalité du texte saisi. Pour plus d'informations, voir [Indication des langues de demande et de réponse](/docs/services/personality-insights?topic=personality-insights-input#languages-input).

<table style="width:75%">
  <caption>Tableau 1. Langues prises en charge</caption>
  <tr>
    <th style="width:50%; text-align:center">
      Langues de demande
    </th>
    <th style="width:50%; text-align:center">
      Langues de réponse
    </th>
  </tr>
  <tr>
    <td style="text-align:center; vertical-align:top">
      Arabe<br/>
      Anglais<br/>
      Japonais<br/>
      Coréen<br/>
      Espagnol
    </td>
    <td style="text-align:center; vertical-align:top">
      Arabe<br/>
      Anglais<br/>
      Japonais<br/>
      Coréen<br/>
      Espagnol<br/>
      Portugais brésilien<br/>
      Français<br/>
      Allemand<br/>
      Italien<br/>
      Chinois simplifié<br/>
      Chinois traditionnel
    </td>
  </tr>
</table>

## HIPAA
{: hipaa}

La prise en charge de la loi américaine HIPAA (Health Insurance Portability and Accountability Act) ne s’applique pas au service {{site.data.keyword.personalityinsightsshort}}. Le service est sans état. Il ne stocke aucune donnée utilisateur sur {{site.data.keyword.cloud_notm}}. 

## En savoir plus sur le service
{: #learn-index}

-   Une [démonstration rapide ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://personality-insights-demo.ng.bluemix.net/){: new_window} du service {{site.data.keyword.personalityinsightsshort}} analyse le texte saisi afin de développer un portrait de personnalité incluant les préférences de consommation de l'auteur. 
-   Les applications dans [Kits de démarrage de {{site.data.keyword.watson}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](http://www.ibm.com/watson/developercloud/starter-kits.html){: new_window} contiennent des démonstrations du service. 
-   Les rubriques [Le service en action](/docs/services/personality-insights?topic=personality-insights-applied) et [L'aspect scientifique du service](/docs/services/personality-insights?topic=personality-insights-science) fournissent des informations sur les recherches sur lesquelles repose le service.
-   Le service {{site.data.keyword.personalityinsightsshort}} dans [{{site.data.keyword.cloud_notm}} Catalog ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://{DomainName}/catalog/services/personality-insights/){: new_window} décrivent les plans de tarification du service.
