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

# Présentation pour les développeurs
{: #overviewDevelopers}

Vous pouvez utiliser le service {{site.data.keyword.personalityinsightsshort}} via une API REST (Representational State Transfer) HTTP. Plusieurs kits de développement de logiciels (SDK) sont également disponibles pour simplifier le développement d'application dans différents langages.
{: shortdesc}

## Programmation à l'aide du service
{: #programming}

Pour produire un profil de personnalité, vous envoyez un texte à la méthode `POST /v3/profile` HTTP du service. Vous pouvez soumettre un texte brut, un contenu HTML ou un contenu JSON. Le service peut renvoyer son analyse au format JSON ou CSV.

Pour chaque caractéristique de la personnalité, le service indique un *percentile*. Le percentile est un score normalisé qui décrit la mesure dans laquelle l'écriture de l'auteur montre une caractéristique dans un échantillon de population. Si cela est demandé, le service renvoie également un *score brut*, valeur absolue qui n'est pas normalisée pour un échantillon de population. Si un horodatage est affecté à l'entrée, le service fournit un récapitulatif des habitudes d'écriture de l'auteur pour chaque jour de la semaine et heure de la journée. Et, si cela est demandé, le service renvoie également un score de probabilité pour chacune de ses préférences de consommation disponibles.

Pour plus d'informations sur l'utilisation du service, voir

-   [Demande d'un profil](/docs/services/personality-insights?topic=personality-insights-input)
-   [Compréhension d'un profil JSON](/docs/services/personality-insights?topic=personality-insights-output)
-   [Compréhension d'un profil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV)

### Visualisation d'un profil
{: #visualize}

Le service fournit une collection de fichiers JavaScript qui activent la visualisation graphique d'un profil. Les scripts facilitent l'utilisation du service avec la mise en cache et les réseaux de distribution de contenu. Ils reposent sur JavaScript, jQuery, HTML et SVG avec la bibliothèque de documents guidés par les données (`D3.js`) pour décrire les résultats. Pour plus d'informations sur `D3.js`, voir [d3js.org ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://d3js.org/){: new_window}.

### Prise en charge de CORS
{: #CORS}

Le service prend en charge le partage de ressources d'origine croisée (CORS). CORS permet aux clients basés sur le navigateur d'émettre des demandes asynchrones directement vers le service à partir de scripts frontaux. CORS contourne la politique de sécurité de même origine, qui autrement empêche ce type de demande. 

A l'aide de CORS, les pages Web peuvent demander des ressources à un domaine étranger, situé en dehors du domaine d'où provient la demande. Pour plus d'informations, voir [enable-cors.org ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://enable-cors.org/){: new_window}.

## Utilisation de kits de développement de logiciels (SDK) 
{: #sdks}

Des logiciels SDK sont disponibles pour le service {{site.data.keyword.personalityinsightsshort}} afin de simplifier le développement d’applications. Les logiciels SDK {{site.data.keyword.ibmwatson}} sont disponibles pour de nombreux langages de programmation et plateformes populaires.

-   Pour obtenir une liste complète des logiciels SDK et des liens vers les logiciels SDK de GitHub, voir [Utilisation de logiciels SDK](/docs/services/watson?topic=watson-using-sdks).
-   Pour des informations détaillées sur toutes les méthodes des SDK Node, Java, Python, Ruby et Go pour le service {{site.data.keyword.personalityinsightsshort}}, voir la [Référence d'API ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://{DomainName}/apidocs/personality-insights){: new_window}. 

## En savoir plus sur le développement d'applications
{: #learn-overview}

Pour plus d'informations sur l'utilisation des services {{site.data.keyword.watson}} et {{site.data.keyword.cloud}}, voir les sections suivantes :

-   Pour une introduction à l'utilisation des services {{site.data.keyword.watson}} avec {{site.data.keyword.cloud_notm}}, voir [Initiation à {{site.data.keyword.watson}} et {{site.data.keyword.cloud_notm}}](/docs/services/watson?topic=watson-about).
-   Toutes les nouvelles instances de service utilisent {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) pour l'authentification. Les anciennes instances de service peuvent continuer à utiliser les `{username}` et `{password}` de leurs données d'identification de service Cloud Foundry existantes pour l'authentification. Pour plus d'informations sur l'authentification auprès du service, voir la [mise à jour du service du 30 octobre 2018](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018) dans les notes sur l'édition. 
-   La consignation des demandes est désactivée pour le service {{site.data.keyword.personalityinsightsshort}}. Le service ne consigne pas et ne conserve pas les données des demandes et des réponses, que l'en-tête de requête `X-Watson-Learning-Opt-Out` soit défini ou non. 
