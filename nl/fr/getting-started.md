---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-18"

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
{:download: .download}

# Tutoriel d'initiation

Le service {{site.data.keyword.personalityinsightsfull}} fournit un éclairage sur les caractéristiques de personnalité à partir de médias sociaux, de données d'entreprise ou d'autres communications numériques. Ce tutoriel vous permet de commencer rapidement à utiliser le service {{site.data.keyword.personalityinsightsshort}}. Les exemples vous montrent comment appeler la méthode `POST /v3/profile` du service avec différents types d'entrée et comment demander différents types de formats d'entrée et de sortie.
{: shortdesc}

## Avant de commencer
{: #before-you-begin}

- Créez une instance du service :
    - {: download} Si cela s'affiche, cela signifie que vous avez créé votre instance de service A présent, procurez-vous vos données d'identification. 
    - Créez un projet à partir d'un service :
        1.  Accédez à la page {{site.data.keyword.watson}} Developer Console [Services ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://console.{DomainName}/developer/watson/services){: new_window}. 
        1.  Sélectionnez {{site.data.keyword.personalityinsightsshort}}, cliquez sur **Add Services**, puis inscrivez-vous afin de recevoir un compte {{site.data.keyword.Bluemix_notm}} gratuit ou connectez-vous. 
        1.  Entrez `personality-tutorial` comme nom du projet et cliquez sur **Create Project**.
- Copiez les données d'identification pour vous authentifier auprès de votre instance de service :
    - {: download} A partir du tableau de bord du service (affiché) :
        1.  Cliquez sur l'onglet **Service credentials**. 
        1.  Cliquez sur **View credentials** under **Actions**.
        1.  Copiez les valeurs `username`, `password` et `url`.
        {: download}
    - A partir du projet **personality-tutorial** dans Developer Console, copiez les valeurs `username`, `password` et `url` pour `"personality_insights"` à partir de la section **Credentials**. 
- Assurez-vous que vous disposez de cURL :
    - Les exemples utilisent cURL pour appeler des méthodes de l'interface HTTP. Installez la version de votre système d'exploitation à partir du site [curl.haxx.se ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://curl.haxx.se/){: new_window}. Installez la version qui prend en charge le protocole SSL (Secure Sockets Layer). Prenez soin d'inclure le fichier binaire installé sur votre variable d'environnement `PATH`. 

<!-- Remove this text after dedicated instances have the Developer Console: begin -->

Si vous utilisez {{site.data.keyword.Bluemix_dedicated_notm}}, vous créez une instance de service à partir de la page[{{site.data.keyword.personalityinsightsshort}} ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://console.{DomainName}/catalog/services/personality-insights/){: new_window} dans le catalogue. Pour savoir comment rechercher des données d'identification du service, voir [Données d'identification de service pour des services Watson ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](/docs/services/watson/getting-started-credentials.html#getting-credentials-manually){: new_window}.

<!-- Remove this text after dedicated instances have the Developer Console: end -->

## Etape 1 : Envoyer une entrée de texte en clair et recevoir une sortie JSON de base
{: #example1}

Le premier exemple transmet le fichier en texte clair `profile.txt` à la méthode `valider/v3/profile` et demande implicitement la réponse JSON par défaut. 

1.  Téléchargez l'exemple de fichier <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="External link icon" title="Icône de lien externe" class="style-scope doc-content"></a>.
1.  Exécutez la commande ci-après pour envoyer le fichier à la méthode `/v3/profile` et demander la réponse JSON par défaut. Le paramètre `charset` inclus avec l'en-tête `Content-Type` spécifie le codage de caractères du texte d'entrée. 
    -   Remplacez `{username}` et `{password}` par vos données d'identification de service obtenus à l'étape précédente. 
    -   Modifiez `{path_to_file}` afin de spécifier l'emplacement du fichier `profile.txt`. 

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --data-binary "@{path_to_file}profile.txt" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
    ```
    {: pre}

Le service renvoie un objet `Profile` JSON qui inclut des métadonnées de base, telles que le nombre de mots dans la demande, le modèle de langue avec lequel l'entrée a été traitée et les éventuels avertissements associés à l'entrée. Pour plus d'informations, voir [Objet de profil](/docs/services/personality-insights/output.html#outputJSON).

Le profil comprend des informations sur la personnalité Big Five personality, les caractéristiques de type Besoins et Valeurs pour l'auteur qui sont déduites à partir du texte d'entrée. Le service renvoie un `percentile`, ou score normalisé, pour chaque caractéristique. Le service calcule le percentile en comparant les résultats de l'auteur aux résultats obtenus avec un échantillon de population. Pour plus d'informations, voir [Sortie des caractéristiques de personnalité](/docs/services/personality-insights/output.html#traitJSON).

## Step 2: Envoyer une entrée JSON et recevoir une sortie JSON détaillée
{: #example2}

Le deuxième exemple transmet le fichier JSON `profile.json` à la méthode `/v3/profile`, là encore en acceptant la réponse JSON par défaut. L'exemple demande les préférences de consommation et les scores brut pour une analyse plus détaillée de l'entrée. 

1.  Téléchargez l'exemple de fichier <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json<img src="../../icons/launch-glyph.svg" alt="External link icon" title="Icône de lien externe" class="style-scope doc-content"></a>, contenant un jeu de messages Twitter.
1.  Exécutez la commande ci-après pour envoyer le fichier à la méthode `/v3/profile`. L'exemple spécifie `application/json` pour l'en-tête `Content-Type` ; le paramètre `charset` n'est pas nécessaire pour l'entrée JSON. L'exemple affecte aux paramètres de requête `consumption_preferences` et `raw_scores` la valeur `true`.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --data-binary "@{path_to_file}profile.json" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"
    ```
    {: pre}

Le service renvoie un profil JSON comprenant les métadonnées et les caractéristiques renvoyées avec l'exemple précédent. Pour chaque caractéristique, le service comprend également un élément `raw_score`, qui représente le score de l'auteur pour la caractéristique basée uniquement sur le texte d'entrée, sans comparer les résultats à un échantillon de population. 

Etant donné que le contenu d'entrée inclut des valeurs d'horodatage, le service renvoie également des caractéristiques comportementales. Il s'agit de caractéristiques temporelles qui indiquent le `pourcentage` d'objets de contenu ayant été créé chaque jour de la semaine et à chaque heure de la journée. Pour plus d'informations, voir[Sortie comportementale](/docs/services/personality-insights/output.html#behaviorJSON).

Le service renvoie également des scores pour son jeu de préférences de consommation. Ces scores indiquent la propension de l'auteur à préférer différents produits et services et différentes activités sur la base des caractéristiques déduites. Pour plus d'informations, voir [Sortie des préférences de consommation](/docs/services/personality-insights/output.html#preferenceJSON).

## Etape 3 : Envoyer une entrée JSON et recevoir une sortie CSV détaillée
{: #example3}

Le troisième exemple est semblable au deuxième ; il transmet le même contenu JSON et demande les mêmes résultats. Mais, cet exemple spécifie `text/csv` pour l'en-tête `Accept` afin de demander la réponse au format CSV. Il utilise l'option `--output` de la commande cURL pour diriger les résultats vers un fichier nommé `profile.csv`. L'exemple affecte au paramètre de requête `csv_headers` la valeur `true` pour indiquer que les en-têtes de colonne doivent être renvoyés avec la sortie. 

1.  Exécutez la commande ci-après pour envoyer le fichier JSON à la méthode `/v3/profile`. 

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary "@{path_to_file}profile.json" \
    --output profile.csv \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"
    ```
    {: pre}

Pour obtenir une description détaillée de la réponse et des en-têtes CSV, voir [Compréhension d'un profil CSV](/docs/services/personality-insights/output-csv.html).

## Etapes suivantes

-   En savoir plus sur la [demande d'un profil](/docs/services/personality-insights/input.html) et sur la [compréhension d'un profil JSON](/docs/services/personality-insights/output.html) et la [compréhension d'un profil CSV](/docs/services/personality-insights/output-csv.html)
-   En savoir plus sur les [modèles de personnalité](/docs/services/personality-insights/models.html) Big Five, Besoins et Valeurs 
-   En savoir plus sur l'API dans [API reference ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}
-   Interagir avec l'API dans [API Explorer ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v3){: new_window}
-   Explorer l'exemple d'application [Node.js ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} pour en apprendre davantage sur le développement d'application à l'aide du service
