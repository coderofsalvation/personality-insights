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
{:go: .ph data-hd-programlang='go'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}
{:download: .download}
{:apikey: data-credential-placeholder='apikey'}
{:url: data-credential-placeholder='url'}
{:hide-dashboard: .hide-dashboard}

# Tutoriel d'initiation
{: #gettingStarted}

Le service {{site.data.keyword.personalityinsightsfull}} fournit un éclairage sur les caractéristiques de personnalité à partir de médias sociaux, de données d'entreprise ou d'autres communications numériques. Ce tutoriel vous permet de commencer rapidement à utiliser le service {{site.data.keyword.personalityinsightsshort}}. Les exemples vous montrent comment appeler la méthode `POST /v3/profile` du service avec différents types d'entrée et comment demander différents types de formats d'entrée et de sortie.
{: shortdesc}

Le tutoriel utilise les clés d'API {{site.data.keyword.cloud}} Identity et Access Management (IAM) pour l'authentification. Les anciennes instances de service peuvent continuer à utiliser les `{username}` et `{password}` de leurs données d'identification de service Cloud Foundry existantes pour l'authentification. Authentifiez-vous en utilisant l'approche qui convient à votre instance de service. Pour plus d'informations sur l'utilisation de l'authentification IAM par le service, voir la [mise à jour du service du 30 octobre 2018](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018) dans les notes sur l'édition.
{: important}

## Avant de commencer
{: #before-you-begin}

-   {: hide-dashboard} Créez une instance du service :
    1.  {: hide-dashboard} Accédez à la page [{{site.data.keyword.personalityinsightsshort}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://{DomainName}/catalog/services/personality-insights){: new_window} du catalogue {{site.data.keyword.cloud_notm}}.
    1.  {: hide-dashboard} Inscrivez-vous pour un compte {{site.data.keyword.cloud_notm}} gratuit ou connectez-vous.
    1.  {: hide-dashboard}Cliquez sur **Créer**. 
-   Copiez les données d'identification pour vous authentifier auprès de votre instance de service :
    1.  {: hide-dashboard}Dans le [tableau de bord {{site.data.keyword.cloud_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://{DomainName}/dashboard/apps){: new_window}, cliquez sur votre instance de service {{site.data.keyword.personalityinsightsshort}} pour accéder à la page du tableau de bord du service {{site.data.keyword.personalityinsightsshort}}.
    1.  Sur la page **Gérer**, cliquez sur **Afficher** pour afficher vos données d'identification.
    1.  Copiez les valeurs des zones `Clé d'API` et `URL`.
-   Vérifiez que vous disposez de la commande `curl`.
    -   Les exemples utilisent la commande `curl` pour appeler des méthodes de l'interface HTTP. Installez la version correspondant à votre système d'exploitation à partir du site [curl.haxx.se ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://curl.haxx.se/){: new_window}. Installez la version qui prend en charge le protocole SSL (Secure Sockets Layer). Prenez soin d'inclure le fichier binaire installé dans votre variable d'environnement `PATH`.

Lorsque vous entrez une commande, remplacez `{apikey}` et `{url}` par votre clé d’API et votre URL. Omettez les accolades de la commande car elles indiquent une valeur de variable. Une valeur réelle ressemble à l'exemple suivant :
{: hide-dashboard}

```bash
curl -X POST -u "apikey:L_HALhLVIksh1b73l97LSs6R_3gLo4xkujAaxm7i-b9x"
. . .
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{:pre}
{: hide-dashboard}

## Etape 1 : Envoyer une entrée de texte en clair et recevoir une sortie JSON de base
{: #example1}

Le premier exemple transmet le fichier en texte clair `profile.txt` à la méthode `POST /v3/profile` et demande une réponse JSON. 

1.  Téléchargez l'exemple de fichier <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="Icône de lien externe" title="Icône de lien externe"></a>.
1.  Exécutez la commande ci-après pour envoyer le fichier à la méthode `/v3/profile` et demander une réponse JSON. 
    -   L'en-tête `Content-Type` spécifie que l'entrée est un texte en clair `text/plain`. Le paramètre `charset` inclus avec l'en-tête identifie le codage de caractères du texte d'entrée. 
    -   L'en-tête `Accept` spécifie `application/json` pour indiquer que la sortie JSON est demandée.
    -   {: hide-dashboard} Remplacez `{apikey}` et `{url}` par vos données.
    -   Modifiez `{path_to_file}` afin de spécifier l'emplacement du fichier `profile.txt`.

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.txt \
    "{url}/v3/profile?version=2017-10-13"{: url}
    ```
    {: pre}

Le service renvoie un objet `Profile` JSON qui inclut des métadonnées de base, telles que le nombre de mots dans la demande, le modèle de langue avec lequel l'entrée a été traitée et les éventuels avertissements associés à l'entrée. Pour plus d'informations, voir [Objet de profil](/docs/services/personality-insights?topic=personality-insights-output#outputJSON).

Le profil comprend des informations sur la personnalité Big Five, les caractéristiques de type Besoins et Valeurs pour l'auteur qui sont déduites à partir du texte d'entrée. Le service renvoie un `percentile`, ou score normalisé, pour chaque caractéristique. Le service calcule le percentile en comparant les résultats de l'auteur aux résultats obtenus avec un échantillon de population. Pour plus d'informations, voir [Sortie des caractéristiques de personnalité](/docs/services/personality-insights?topic=personality-insights-output#traitJSON).

## Etape 2 : Envoyer une entrée JSON et recevoir une sortie JSON détaillée
{: #example2}

Le deuxième exemple transmet le fichier JSON `profile.json` à la méthode `/v3/profile`, là encore en demande une réponse JSON. L'exemple demande les préférences de consommation et les scores brut pour une analyse plus détaillée de l'entrée.

1.  Téléchargez l'exemple de fichier <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json<img src="../../icons/launch-glyph.svg" alt="Icône de lien externe" title="Icône de lien externe"></a>, contenant un jeu de messages Twitter.
1.  Exécutez la commande ci-après pour envoyer le fichier à la méthode `/v3/profile`. L'exemple spécifie `application/json` pour les en-têtes `Content-Type` et `Accept` ; le paramètre `charset` n'est pas nécessaire pour l'entrée JSON. L'exemple affecte aux paramètres de requête `consumption_preferences` et `raw_scores` la valeur `true`.

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.json \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"{: url}
    ```
    {: pre}

Le service renvoie un profil JSON comprenant les métadonnées et les caractéristiques renvoyées avec l'exemple précédent. Pour chaque caractéristique, le service comprend également un élément `raw_score`, qui représente le score de l'auteur pour la caractéristique basée uniquement sur le texte d'entrée, sans comparer les résultats à un échantillon de population.

Etant donné que le contenu d'entrée inclut des valeurs d'horodatage, le service renvoie également des caractéristiques comportementales. Il s'agit de caractéristiques temporelles qui indiquent le `pourcentage` d'objets de contenu ayant été créé chaque jour de la semaine et à chaque heure de la journée. Pour plus d'informations, voir [Sortie comportementale](/docs/services/personality-insights?topic=personality-insights-output#behaviorJSON).

Le service renvoie également des scores pour son jeu de préférences de consommation. Ces scores indiquent la propension de l'auteur à préférer différents produits et services et différentes activités sur la base des caractéristiques déduites. Pour plus d'informations, voir [Sortie des préférences de consommation](/docs/services/personality-insights?topic=personality-insights-output#preferenceJSON).

## Etape 3 : Envoyer une entrée JSON et recevoir une sortie CSV détaillée
{: #example3}

Le troisième exemple est semblable au deuxième ; il transmet le même contenu JSON et demande les mêmes résultats. Mais, cet exemple spécifie `text/csv` pour l'en-tête `Accept` afin de demander la réponse au format CSV. Il utilise l'option `--output` de la commande `curl` pour diriger les résultats vers un fichier nommé `profile.csv`. L'exemple affecte au paramètre de requête `csv_headers` la valeur `true` pour indiquer que les en-têtes de colonne doivent être renvoyés avec la sortie.

1.  Exécutez la commande ci-après pour envoyer le fichier JSON à la méthode `/v3/profile`. L'en-tête `Content-Type` identifie le contenu en entrée en tant que `application/json`, et l'en-tête `Accept` demande la sortie CSV, `text/csv`.

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary @{path_to_file}profile.json \
    --output profile.csv \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"{: url}
    ```
    {: pre}

Pour obtenir une description détaillée de la réponse et des en-têtes CSV, voir [Compréhension d'un profil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV).

## Etapes suivantes
{: #gsns}

-   En savoir plus sur la [demande d'un profil](/docs/services/personality-insights?topic=personality-insights-input) et sur la [compréhension d'un profil JSON](/docs/services/personality-insights?topic=personality-insights-output) et la [compréhension d'un profil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV)
-   En savoir plus sur les [modèles de personnalité](/docs/services/personality-insights?topic=personality-insights-models) Big Five, Besoins et Valeurs
-   En savoir plus sur l'API dans [API reference ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://{DomainName}/apidocs/personality-insights){: new_window}
-   Explorer l'exemple d'application [Node.js ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} pour en apprendre davantage sur le développement d'application à l'aide du service
