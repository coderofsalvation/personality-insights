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

# Demande d'un profil
{: #input}

Pour analyser du contenu, utilisez la méthode de demande HTTP `POST` afin d'appeler la méthode `/v3/profile` du service {{site.data.keyword.personalityinsightsshort}}. Vous pouvez transmettre au service un maximum de 20 Mo de contenu à analyser via le corps de la demande. Cependant, le service nécessite beaucoup moins d’informations pour produire un profil de personnalité précis. Pour plus d'informations, voir [Indication d'entrées suffisantes](#sufficient).
{: shortdesc}

La méthode `/v3/profile` comprend des paramètres qui vous permettent de spécifier le type de contenu qui doit être transmis au service et renvoyé par le service, ainsi que la langue de chaque type de contenu. Le service renvoie toujours un profil qui fournit un éclairage sur les caractéristiques de personnalité de l'auteur du texte d'entrée. Vous pouvez également demander des scores bruts et des préférences de consommation.

Les sections décrites ci-après décrivent les paramètres de la méthode `/v3/profile`. Pour toute information sur les résultats d'une demande, voir [Compréhension d'un profil JSON](/docs/services/personality-insights?topic=personality-insights-output) et [Compréhension d'un profil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV). Pour en savoir plus sur la méthode `/v3/profile`, voir le document [Référence d'API ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://{DomainName}/apidocs/personality-insights){: new_window}.

La consignation des demandes est désactivée pour le service {{site.data.keyword.personalityinsightsshort}}. Que vous définissiez ou non l'en-tête de requête `X-Watson-Learning-Opt-Out`, le service ne consigne pas et ne conserve pas les données des demandes et des réponses.
{: note}

## Indication des formats de demande et de réponse
{: #formats}

Vous utilisez les paramètres d'en-tête `Content-Type` et `Accept` pour indiquer le format du contenu que vous transmettez à la méthode et le format de la réponse du service. Vous pouvez utiliser n'importe quelle combinaison de formats pris en charge pour la demande et la réponse.

<table>
  <caption>Tableau 1. Indication des formats de demande et de réponse</caption>
  <tr>
    <th style="width:10%; text-align:left; vertical-align:bottom">
      Format
    </th>
    <th style="width:26%; text-align:center; vertical-align:bottom">
      Argument
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      Pris en charge par<br/>
      <code>Content-Type</code>
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      Pris en charge par<br/>
      <code>Accept</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Texte brut
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/plain</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Oui (par défaut)<br/><br/>
      Le service traite le texte brut sans modification.
    </td>
    <td style="text-align:center; vertical-align:top">
      Non
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      HTML
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/html</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Oui<br/><br/>
      Le service retire des balises du contenu avant de traiter le texte.
</td>
    <td style="text-align:center; vertical-align:top">
      Non
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      JSON
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>application/json</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Oui<br/><br/>
      Le contenu doit être conforme au modèle défini par l'objet <code>Content</code>, qui est un tableau d'objets <code>ContentItem</code>.
    </td>
    <td style="text-align:center; vertical-align:top">
      Oui<br/><br/>
      Le service renvoie ses résultats sous la forme d'un objet <code>Profile</code>.
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      CSV
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/csv</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Non
    </td>
    <td style="text-align:center; vertical-align:top">
      Oui<br/><br/>
      Par défaut, le service renvoie une ligne unique de résultats numériques.
      Affectez au paramètre de requête facultatif <code>csv_headers</code> la valeur <code>true</code> afin de demander des en-têtes pour chaque colonne de la sortie.
    </td>
  </tr>
</table>

### Spécification du jeu de caractères
{: #charset}

Par défaut, le service utilise les jeux de caractères suivants pour le contenu en entrée :

-   *Pour le texte brut et le contenu HTML,* le service utilise le jeu de caractères ISO (International Standards OrganizationSO) 8859-1 (lequel correspond au jeu de caractères ASCII) d'après la spécification HTTP version 1.1.
-   *Pour le contenu JSON,* le service utilise systématiquement le jeu de caractères UTF (Unicode Transformation Format) 8, conformément à la Section 8.1 de l'organisme IETF (International Engineering Task Force) : [RFC (Request for Comment - Demande de changement) 7159 ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://tools.ietf.org/html/rfc7159#section-8.1){: new_window}.

Lorsque vous soumettez un texte brut ou un contenu HTML, ajoutez le paramètre `charset` avec l'en-tête `Content-Type` pour indiquer le codage de caractères du texte d'entrée. L'exemple suivant spécifie le codage de caractères UTF-8 pour l'entrée de texte brut :

```
Content-Type: text/plain;charset=utf-8
```
{: codeblock}

En utilisant le paramètre `charset`, vous pouvez éviter tout problème potentiel associé à des caractères non ASCII ou non imprimables. Si vous transmettez des données UTF-8 sans spécifier le jeu de caractères, les caractères spéciaux peuvent générer des résultats incorrects ou des erreurs HTTP de niveau 400 ou 500. 

### Utilisation de la commande curl 
{: #charsetCurl}

Pour empêcher toute erreur lors de l'utilisation de la commande `curl`, transmettez toujours le contenu via l'option `--data-binary` de la commande `curl` afin de conserver tout codage UTF-8 du contenu. Si vous utilisez l'option `--data` pour le transmettre en tant que contenu ASCII, la commande peut traiter l'entrée, ce qui peut entraîner des problèmes pour les données codées en UTF-8.

Par exemple, la commande `curl` ci-après utilise correctement l'option `--data-binary` pour envoyer le contenu du *nom de fichier* spécifié sans traitement supplémentaire. La commande spécifie le paramètre `charset` avec l'en-tête `Content-Type` et elle demande le format de réponse JSON avec l'en-tête `Accept`. 

```bash
curl -X POST -u "apikey:{apikey}"
--header "Content-Type: text/plain;charset=utf-8"
--header "Accept: application/json"
--data-binary @{filename}
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{: pre}

Pour obtenir d'autres exemples d'appel du service avec différents formats de demande et de réponse, voir la rubrique [Tutoriel d'initiation](/docs/services/personality-insights?topic=personality-insights-gettingStarted).

## Spécification d'entrée JSON
{: #json}

Pour transmettre une entrée JSON, utilisez l'objet `Content`. L'objet inclut un tableau d'objets `ContentItem`, chacun d'eux comportant un élément du contenu. La seule zone requise de l'objet est `content`, qui fournit le texte à analyser. Les autres zones facultatives sont 

-   `id` (chaîne) est un ID unique pour l'objet de contenu.
-   `created` (entier) est une valeur d'horodatage UNIX qui indique à quel moment l'objet de contenu a été créé.
-   `updated` (entier) est une valeur d'horodatage UNIX qui indique à quel moment l'objet de contenu a été mis à jour pour la dernière fois.
-   `contenttype` (chaîne) indique le type de l'objet de contenu : `text/plain` ou `text/html`.
-   `language` (chaîne) indique la langue de l'objet de contenu : `ar` (arabe), `en` (anglais), `es` (espagnol), `ja` (japonais) ou `ko` (coréen). Voir la rubrique [Indication des langues de demande et de réponse](#languages-input).
-   `parentid` (chaîne) est l'`id` de l'élément parent de l'objet de contenu.
-   `reply` (booléen) indique si l'objet de contenu est une réponse à un autre objet.
-   `forward` (booléen) indique si l'objet de contenu est un réacheminement ou une copie d'un autre objet.

L'entrée JSON convient parfaitement au contenu provenant de Twitter ou d'autres réseaux sociaux et qui est constitué de plusieurs conversations ou articles. Au lieu de concaténer l'ensemble du texte de l'auteur en une seule chaîne, vous pouvez utiliser JSON pour soumettre les données telles qu'elles. Cette approche présente l'autre avantage de permettre au service de savoir quelles parties du texte sont liées. 

### Exemple d'entrée JSON
{: jsonExample}

Les exemples contenus dans la rubrique [Tutoriel d'initiation](/docs/services/personality-insights?topic=personality-insights-gettingStarted) utilisent l'exemple de fichier JSON <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Icône de lien externe" title="Icône de lien externe"></a>. Le fichier inclut une série de messages Twitter. L'exemple ci-après illustre les premiers tweets provenant du fichier.

```javascript
{
  "contentItems": [
    {
      "content": "Wow, I liked @TheRock before, now I really SEE how special he is. The daughter story was IT for me. So great! #MasterClass",
      "contenttype": "text/plain",
      "created": 1447639154000,
      "id": "666073008692314113",
      "language": "en"
    },
    {
      "content": ".@TheRock how did you Know to listen to your gut and Not go back to football? #MasterClass",
      "contenttype": "text/plain",
      "created": 1447638226000,
      "id": "666069114889179136",
      "language": "en"
    },
    . . .
  ]
}
```
{: codeblock}

## Indication des langues de demande et de réponse
{: #languages-input}

Vous pouvez utiliser les paramètres d'en-tête `Content-Language` et `Accept-Language` pour indiquer la langue du contenu d'entrée et la langue de la réponse du service. Vous pouvez utiliser n'importe quelle combinaison de langues prises en charge pour la demande et la réponse. Si vous n'indiquez pas de langue, le service utilise ses modèles formés en anglais pour son analyse et l'anglais pour ses résultats. Le tableau ci-après répertorie les langues d'entrée et de sortie prises en charge et identifie les arguments que vous utilisez avec les paramètres de langue.

<table style="width:90%">
  <caption>Tableau 2. Indication des langues de demande et de réponse</caption>
  <tr>
    <th style="width:28%; text-align:left; vertical-align:bottom">
      Langue
    </th>
    <th style="width:12%; text-align:center; vertical-align:bottom">
      Argument
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      Pris en charge par<br/>
      <code>Content-Language</code>
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      Pris en charge par<br/>
      <code>Accept-Language</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      Arabe
    </td>
    <td style="text-align:center">
      <code>ar</code>
    </td>
    <td style="text-align:center">
      Oui
    </td>
    <td style="text-align:center">
      Oui
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Anglais
    </td>
    <td style="text-align:center">
      <code>en</code>
    </td>
    <td style="text-align:center">
      Oui
    </td>
    <td style="text-align:center">
      Oui
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Japonais
    </td>
    <td style="text-align:center">
      <code>ja</code>
    </td>
    <td style="text-align:center">
      Oui
    </td>
    <td style="text-align:center">
      Oui
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Coréen
    </td>
    <td style="text-align:center">
      <code>ko</code>
    </td>
    <td style="text-align:center">
      Oui
    </td>
    <td style="text-align:center">
      Oui
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Espagnol
    </td>
    <td style="text-align:center">
      <code>es</code>
    </td>
    <td style="text-align:center">
      Oui
    </td>
    <td style="text-align:center">
      Oui
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Portugais brésilien
    </td>
    <td style="text-align:center">
      <code>pt-br</code>
    </td>
    <td style="text-align:center">
      Non
    </td>
    <td style="text-align:center">
      Oui
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Français
    </td>
    <td style="text-align:center">
      <code>fr</code>
    </td>
    <td style="text-align:center">
      Non
    </td>
    <td style="text-align:center">
      Oui
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Allemand
    </td>
    <td style="text-align:center">
      <code>de</code>
    </td>
    <td style="text-align:center">
      Non
    </td>
    <td style="text-align:center">
      Oui
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Italien
    </td>
    <td style="text-align:center">
      <code>it</code>
    </td>
    <td style="text-align:center">
      Non
    </td>
    <td style="text-align:center">
      Oui
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Chinois simplifié
    </td>
    <td style="text-align:center">
      <code>zh-cn</code>
    </td>
    <td style="text-align:center">
      Non
    </td>
    <td style="text-align:center">
      Oui
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Chinois traditionnel
    </td>
    <td style="text-align:center">
      <code>zh-tw</code>
    </td>
    <td style="text-align:center">
      Non
    </td>
    <td style="text-align:center">
      Oui
    </td>
  </tr>
</table>

Soumettez la totalité du texte dans la même langue ; ne mélangez pas plusieurs langues dans la même demande. Pour les arguments de langue à deux caractères, le service traite les variantes régionales comme langue parent ; par exemple, il interprète `en-US` comme `en`.

### Indication d'une langue pour un contenu JSON
{: #languageJSON}

Pour un texte brut et une entrée HTML, l'en-tête `Content-Language` est le seul moyen d'indiquer la langue. Pour une entrée JSON, vous pouvez également indiquer la langue de chaque objet de contenu individuel en utilisant le paramètre `language` de l'objet `ContentItem`. Pour JSON, une langue indiquée avec l'en-tête `Content-Language` se substitue à celle qui est indiquée pour un objet de contenu ; le service ignore les objets de contenu qui indiquent une autre langue. 

Omettez l'en-tête `Content-Type` afin de baser la langue uniquement sur la spécification des objets de contenu. Le service utilise la langue la plus répandue parmi les objets de contenu, ce qui génère les meilleurs résultats possibles. Il calcule le nombre d'objets de contenu pour chaque langue et sélectionne la langue la plus fréquente. Si plusieurs langues présentent la même fréquence maximale, le service utilise cette qui atteint cette valeur en premier. Une fois de plus, le service ignore les objets de contenu qui spécifient une autre langue.

### Considérations relatives à la langue
{: #languageNotes}

Considérez les points suivants lorsque vous soumettez un texte d'entrée :

-   *Pour l'anglais*, les résultats sont basés sur les normes culturelles américaines. Si vous analysez le texte anglais à partir d'une autre culture, vous devrez peut-être ajuster les résultats. 
-   *Pour l'arabe*, le service peut tronquer la quantité de texte d'entrée pour des raisons de performance. A un certain seuil, l'exactitude des résultats pour l'arabe ne s'améliore pas avec davantage de mots. Si le service tronque l'entrée en arabe, il renvoie un message d'avertissement pour vous informer qu'il a réduit la quantité de texte d'entrée qu'il avait utilisée pour le profil.
-   *Pour l'arabe et le coréen*, le service ne peut pas renvoyer des résultats significatifs pour un sous-ensemble de caractéristiques. Pour plus d'informations, voir [Limitations pour les entrées en arabe et en coréen](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).

Pour obtenir des généralités sur l'utilisation du texte traduit, voir [Déduction de personnalité à partir du texte traduit](/docs/services/personality-insights?topic=personality-insights-guidance#translation).

## Indication d'entrées suffisantes
{: #sufficient}

Un profil de personnalité significatif peut être créé uniquement lorsqu'un nombre suffisant de données d'une quantité et d'une qualité convenables sont fournies. Etant donné que l'utilisation de la langue varie naturellement d'un document à un autre et de temps en temps, un petit exemple de texte peut ne pas être représentatif des modèles de langue d'un individu. De plus, différentes caractéristiques et différents supports convergent à des taux différents. 

Vous pouvez envoyer au service jusqu'à 20 Mo de contenu en entrée. Jusqu'à un certain point, davantage de mots sont susceptibles de produire de meilleurs résultats et d'améliorer la précision du service en réduisant l'écart entre les résultats prévus et le score réel de l'auteur. Mais l'exactitude se stabilise à environ 3000 mots d'entrée et tout contenu supplémentaire ne contribue pas à l'exactitude du profil. Par conséquent, le service extrait et utilise uniquement les 250 premiers Ko de contenu, sans compter le marquage HTML ou JSON, provenant de demandes de grande taille.

Ce chiffre ne correspond pas à un nombre exact de mots, qui varie en fonction de la langue et de la nature du texte. En anglais, par exemple, la longueur de mot moyenne se situe entre quatre et cinq caractères, par conséquent, ce chiffre fournit environ 50 000 mots. Ce nombre est au moins 15 fois supérieur au nombre de mots dont le service a besoin pour produire un profil précis. En tronquant les entrées longues, le service améliore les temps de réponse sans sacrifier la précision. La zone `word_count` du format JSON de la réponse indique le nombre de mots que le service utilise pour une demande, ce qui peut être inférieur au nombre de mots soumis. 

Le service ne valide que le nombre de mots que vous soumettez. Si vous envoyez suffisamment de mots, le service génère un profil. Le service ne vérifie pas les mots ou les phrases en double. Cette validation est subjective et doit être laissée à l'utilisateur, qui peut avoir des raisons valables de soumettre ce type d'entrées. Par conséquent, il est possible d'obtenir un profil en soumettant plusieurs fois le même mot ou la même phrase, mais le profil obtenu n'est pas nécessairement significatif.
{: note}

### Directives et recommandations
{: #sufficientGuidelines}

Le tableau suivant présente deux valeurs pour différentes quantités de texte d'entrée :

-   Valeur *MAE moyenne* sur toutes les caractéristiques basée sur le nombre de mots fournis en entrée. Plus la valeur MAE est petite, plus les résultats du service sont proches des scores que l'auteur recevrait s'il suivait un test de personnalité. 
-   Valeur *Corrélation moyenne* entre les scores déduits et réels sur toutes les caractéristiques. Plus la corrélation est proche de 1, meilleures sont les prédictions. Les corrélations supérieures à 0,2 sont considérées comme acceptables ; les corrélations supérieures à 0,4 sont rares. 

Les informations sont basées sur des données en anglais, mais les directives générales s'appliquent à toutes les langues. Pour plus d'informations sur les valeurs MAE moyenne et Corrélation moyenne, y compris les statistiques spécifiques des langues, voir [Niveau de précision du service](/docs/services/personality-insights?topic=personality-insights-science#researchPrecise).

<table style="width:80%">
  <caption>Tableau 3. Valeurs MAE moyenne et Corrélation moyenne</caption>
  <tr>
    <th style="text-align:center; vertical-align:bottom; width:24%">Nombre de mots</th>
    <th style="text-align:center; width:38%">MAE moyenne<br/>sur toutes les caractéristiques</th>
    <th style="text-align:center; width:38%">Corrélation moyenne<br/>sur toutes les caractéristiques</th>
  </tr>
  <tr>
    <td style="text-align:center">3000</td>
    <td style="text-align:center">12,1 %</td>
    <td style="text-align:center">0,257</td>
  </tr>
  <tr>
    <td style="text-align:center">1200</td>
    <td style="text-align:center">12,2 %</td>
    <td style="text-align:center">0,237</td>
  </tr>
  <tr>
    <td style="text-align:center">600</td>
    <td style="text-align:center">12,3 %</td>
    <td style="text-align:center">0,212</td>
  </tr>
  <tr>
    <td style="text-align:center">300</td>
    <td style="text-align:center">12,5 %</td>
    <td style="text-align:center">0,175</td>
  </tr>
  <tr>
    <td style="text-align:center">100</td>
    <td style="text-align:center">12,7 %</td>
    <td style="text-align:center">0,095</td>
  </tr>
</table>

Comme indiqué dans les instructions suivantes, {{site.data.keyword.IBM_notm}} recommande de fournir au moins 1200 mots, cela dit, si vous fournissez au moins 600 mots, vous obtenez des résultats acceptables :

-   Avec 3000 mots, la précision maximale du service est atteinte.
-   Avec au moins 1200 mots, le système génère une valeur MAE qui se situe dans les deux pour cent de la meilleure valeur MAE pouvant être renvoyée par le service.
-   Avec une fourchette comprise entre 600 et 1200 mots, le système génère une valeur MAE qui se situe dans les trois pour cent de la meilleure valeur MAE pouvant être renvoyée par le service.
-   Avec moins de 600 mots, un avertissement est généré, mais le service peut tout de même analyser l'entrée.
-   Avec moins de 100 mots, une erreur est générée.

Ces instructions peuvent vous aider à adapter la fiabilité des résultats à votre application. Par exemple, pour une application ordinaire qui recommande des films, la précision n'est sans doute pas une priorité. Pour une application qui émet des recommandations plus critiques, vous souhaiterez sûrement obtenir des résultats plus précis. Pour plus d'informations sur la façon dont le service déduit des caractéristiques de personnalité, voir [Mode de déduction des caractéristiques de personnalité](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).

## Demande de scores bruts
{: #rawScores-input}

Le service renvoie toujours des scores normalisés pour chaque caractéristique de personnalité (dimension et facette Big Five, Besoins et Valeurs) dans le cadre de sa réponse. Le service peut également signaler un objet `raw_score` pour chaque caractéristique si vous affectez au paramètre de requête `raw_scores` la valeur `true`. Les scores bruts représentent les résultats des caractéristiques, basés uniquement sur le texte d'entrée de l'auteur et le modèle pour ces caractéristiques, sans comparer les résultats à un échantillon de population. Pour plus d'informations sur l'utilisation de scores bruts, voir [Scores bruts des caractéristiques de personnalité](/docs/services/personality-insights?topic=personality-insights-numeric#rawScores-numeric).

## Demande de préférences de consommation
{: #preferences-input}

Le service renvoie toujours des résultats pour les modèles de personnalité. Lorsque vous affectez au paramètre de requête `consumption_preferences` la valeur `true`, le service renvoie également la valeur `scores` pour différentes préférences de consommation. Le service détermine les préférences sur la base des caractéristiques de personnalité qu'il déduit à partir du texte d'entrée. Ces résultats indiquent la propension de l'auteur à préférer différents produits et services et différentes activités. Les entreprises peuvent utiliser les résultats pour mieux comprendre les aspirations de l'auteur et pour personnaliser les communications et les offres pour l'auteur.

Pour plus d'informations sur les différentes préférences de consommation, voir [Préférences de consommation](/docs/services/personality-insights?topic=personality-insights-preferences). Pour toute information sur l'interprétation des résultats numériques pour une préférence, voir [Scores des préférences de consommation](/docs/services/personality-insights?topic=personality-insights-numeric#scores).

## Indication de la version d'interface
{: #version}

Tous les appels vers la méthode `/v3/profile` doivent inclure le paramètre de requête `version` pour indiquer la version de l'API et du format de réponse de l'API que vous souhaitez utiliser. Vous spécifiez la version en tant que date au format `AAAA-MM-JJ` ; par exemple, spécifiez `2017-10-13` pour le 13 octobre 2017 (la dernière version). Le paramètre permet au service de mettre à jour son API et son format de réponse vers les nouvelles versions sans entraîner de rupture avec les clients existants. Pour plus d’informations sur toutes les versions disponibles, voir les [Notes sur l'édition](/docs/services/personality-insights?topic=personality-insights-release-notes).

Il n'est pas nécessaire que la date que vous spécifiez corresponde exactement à une version du service ; le service utilise la version qui n'est pas ultérieure à la date que vous indiquez. Si vous indiquez une date antérieure à l'édition initiale de la version 3 (`2016-10-19`), le service utilise cette version de l'API. Si vous indiquez une date qui se situe dans le futur ou qui est postérieure à la version la plus récente, le service utilise la version la plus récente.
