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

# Présentation pour les développeurs
{: #overviewDevelopers}

Vous pouvez utiliser le service {{site.data.keyword.personalityinsightsshort}} via une API REST (Representational State Transfer) HTTP. Plusieurs DSK (Software Development Kit) sont également disponibles pour simplifier le développement d'application dans différents langages et environnements.
{: shortdesc}

## Programmation à l'aide du service
{: #programming}

Pour produire un profil de personnalité, vous envoyez un texte à la méthode `POST /v3/profile` HTTP du service. Vous pouvez soumettre un texte brut, un contenu HTML ou un contenu JSON. Le service peut renvoyer son analyse au format JSON ou CSV. 

Pour chaque caractéristique de personnalité, le service signale un *percentile*, score normalisé qui décrit la mesure dans laquelle l'écriture de l'auteur montre une caractéristique dans un échantillon de population. Si cela est demandé, le service renvoie également un *score brut*, valeur absolue qui n'est pas normalisée pour un échantillon de population. Si un horodatage est affecté à l'entrée, le service fournit un récapitulatif des habitudes d'écriture de l'auteur par rapport au jour de la semaine et à l'heure de la journée. Et, si cela est demandé, le service renvoie également un score de probabilité pour chacune de ses préférences de consommation disponibles. 

Pour plus d'informations sur l'utilisation du service, voir

-   [Demande d'un profil](/docs/services/personality-insights/input.html)
-   [Compréhension d'un profil JSON](/docs/services/personality-insights/output.html)
-   [Compréhension d'un profil CSV](/docs/services/personality-insights/output-csv.html)

### Visualisation d'un profil
{: #visualize}

Le service fournit une collection de fichiers JavaScript qui activent la visualisation graphique d'un profil. Les scripts facilitent l'utilisation du service avec la mise en cache et les réseaux de distribution de contenu. Ils reposent sur JavaScript, jQuery, HTML et SVG avec la bibliothèque de documents guidés par les données (`D3.js`) pour décrire les résultats. Pour plus d'informations sur ces fichiers côté client, voir les exemples d'application mentionnés dans [Utilisation de SDK](#sdks) ; pour plus d'informations sur `D3.js`, voir [d3js.org ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://d3js.org/){: new_window}.

### Prise en charge de CORS
{: #CORS}

Le service prend en charge le partage de ressources d'origine croisée (CORS) pour permettre aux clients basés sur le navigateur d'émettre des demandes asynchrones directement vers le service à partir de scripts frontaux. La fonction CORS permet aux clients de demander des ressources à partir d'un domaine situé en dehors du domaine à partir duquel la demande a été émise ; elle permet aux applications Web de contourner la règle de sécurité de même origine, car sinon cela empêcherait les demandes de ce type. Pour plus d'informations, voir [enable-cors.org ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://enable-cors.org/){: new_window}.

## Utilisation de SDK
{: #sdks}

Le service {{site.data.keyword.personalityinsightsshort}} prend en charge un certain nombre de SDK pour un développement d'application simplifié. Les SDK sont disponibles pour un grand nombre de plateformes et de langages de programmation populaires, y compris Node.js, Java, Python et Apple iOS. Pour obtenir la liste complète des SDK ainsi que des informations relatives à leur utilisation, voir [SDK {{site.data.keyword.watson}}](/docs/services/watson/getting-started-sdks.html). Tous les SDK sont disponibles à partir de [l'espace-noms watson-developer-cloud ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/watson-developer-cloud){: new_window} sur GitHub.

Le service met également à votre disposition les exemples d'application suivants pour vous permettre de vous initier à son utilisation :

-   Vous pouvez accéder à une application qui utilise le SDK Node.js dans le [référentiel personality-insights-nodejs![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window}.
-   Vous pouvez accéder à une application qui utilise le SDK Java dans le [référentiel personality-insights-java![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/watson-developer-cloud/personality-insights-java){: new_window}.

Pour le développement mobile, voir [{{site.data.keyword.watson}} Developer Cloud Swift SDK![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/watson-developer-cloud/swift-sdk){: new_window}. Tous les SDK prennent en charge l'authentification via vos données d'identification de service ou un jeton d'authentification. 

## En savoir plus sur le développement d'application
{: #learn}

Le service {{site.data.keyword.personalityinsightsshort}} prend en charge deux modèles de programmation typiques, le modèle d'*interaction directe*, dans lequel le client communique directement avec le service, et le modèle de *relais via un proxy*, dans lequel le client et le service échangent toutes les données (demandes et résultats) via une application proxy qui réside dans {{site.data.keyword.Bluemix_short}}.

Pour plus d'informations sur l'utilisation des services {{site.data.keyword.watson}} Developer Cloud et de {{site.data.keyword.Bluemix_notm}}, voir la documentation suivante : 

-   Pour une introduction à l'utilisation des services {{site.data.keyword.watson}} et de {{site.data.keyword.Bluemix_notm}}, voir [Initiation à {{site.data.keyword.watson}} et {{site.data.keyword.Bluemix_notm}}](/docs/services/watson/index.html).
-   Pour une introduction au développement des applications des services {{site.data.keyword.watson}} dans {{site.data.keyword.Bluemix_notm}}, quel que soit le langage utilisé, voir [Approches de développement {{site.data.keyword.Bluemix_notm}}](/docs/services/watson/getting-started-bluemix.html).
-   Pour plus d'informations sur les deux modèles de programmation disponibles pour le développement d'applications {{site.data.keyword.watson}}, voir [Modèles de programmation pour les services {{site.data.keyword.watson}}](/docs/services/watson/getting-started-develop.html) :
    -   Avec le modèle Relais via un proxy, le client s'appuie sur un serveur proxy qui réside dans {{site.data.keyword.Bluemix_notm}} pour communiquer avec le service ; il transmet toutes les demandes via l'application proxy. Le relais des demandes via un proxy s'appuie uniquement sur les données d'identification du service pour l'authentification auprès du service. Voir [Données d'identification du service pour les services {{site.data.keyword.watson}} ](/docs/services/watson/getting-started-credentials.html).
    -   Avec le modèle d'interaction directe, le client utilise l'application proxy dans {{site.data.keyword.Bluemix_notm}} uniquement dans le but d'obtenir un jeton d'authentification pour le service, après quoi il communique directement avec le service. Le modèle d'interaction directe utilise des données d'identification de service pour obtenir un jeton. Voir [Jetons pour l'authentification](/docs/services/watson/getting-started-tokens.html).
-   Pour plus d'informations sur le contrôle de la journalisation de demande par défaut qui est effectuée pour tous les services {{site.data.keyword.watson}}, voir[Contrôle de la journalisation de demande pour les services {{site.data.keyword.watson}}](/docs/services/watson/getting-started-logging.html).
