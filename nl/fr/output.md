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

# Compréhension d'un profil JSON
{: #output}

Lorsque vous utilisez la méthode `POST /v3/profile` pour analyser du contenu, le service renvoie les résultats de son analyse en tant qu'objet `Profile` JSON lorsque vous spécifiez `application/json` avec l'en-tête `Accept` d'une demande. La portée de la sortie JSON dépend des paramètres que vous spécifiez avec la demande. Elle dépend également du fait que le texte saisi représente ou non des données horodatées, telles que le texte associé à un flux Twitter.
{: shortdesc}

Les sections ci-après décrivent le contenu d'une réponse au format JSON. La totalité de l'exemple de sortie est produite par l'exemple de fichier JSON<a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Icône de lien externe" title="Icône de lien externe"></a> qui est utilisé dans le [tutoriel d'initiation](/docs/services/personality-insights?topic=personality-insights-gettingStarted). Pour toute information sur les sorties CSV, voir[Compréhension d'un profil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV).

## Objet Profile
{: #outputJSON}

L'objet `Profile` est l'objet JSON de niveau supérieur renvoyé par le service. L'objet comporte les zones suivantes :

-   `word_count` (entier) fournit le nombre de mots du contenu d'entrée qui ont été utilisés pour générer le profil. Ce nombre peut être inférieur au nombre de mots de l'entrée si la demande a soumis une importante quantité de contenu. Si le nombre de mots ne correspond pas à un seuil minimum, la sortie comprend une zone `word_count_message` qui fournit des conseils supplémentaires. 
-   `processed language` (chaîne) décrit le modèle de langue que le service a utilisé pour traiter l'entrée : `ar` (arabe), `en` (anglais), `es` (espagnol), `ja` (japonais) ou `ko` (coréen).
-   `personality` est un tableau récursif d'objets `Trait` qui décrit les dimensions et les facettes Big Five déduites à partir du texte d'entrée. 
-   `needs` est un tableau d'objets `Trait` qui décrit les besoins déduits à partir du texte d'entrée. 
-   `values` est un tableau d'objets `Trait` qui décrit les valeurs déduites à partir du texte d'entrée. 
-   `behavior` est un tableau d'objets `Behavior` qui décrit la distribution du contenu au fil des jours de la semaine et des heures de la journée. Le service renvoie la zone uniquement pour l'entrée JSON qui est horodatée.
-   `consumption_preferences` est un tableau d'objets `ConsumptionPreferencesCategory` qui fournit des résultats pour chaque catégorie de préférences de consommation. Les éléments du tableau fournissent des informations pour les préférences individuelles de cette catégorie. Le service renvoie la zone uniquement si le paramètre de requête `consumption_preferences` de la demande a pour valeur `true`.
-   `warnings` est un tableau d'objets `Warning` qui fournit les messages sur le texte d'entrée. Le tableau est vide si l'entrée n'a généré aucun avertissement.

### Exemple de réponse
{: #JSONExample}

L'exemple de sortie ci-après montre la structure de niveau supérieur d'un objet `Profile`. La sortie inclut toujours les zones `personality`, `needs` et `values`. S'il s'agit d'une entrée JSON horodatée, la réponse inclut la zone `behavior`. Et si la demande réclame également les préférences de consommation, la réponse inclut la zone `consumption_preferences`. Dans cet exemple, l'entrée ne génère aucun avertissement.

```javascript
{
  "word_count": 15223,
  "processed_language": "en",
  "personality": [
     . . .
  ],
  "needs": [
     . . .
  ],
  "values": [
     . . .
  ],
  "behavior": [
     . . .
  ],
  "consumption_preferences": [
     . . .
   ],
  "warnings": []
}
```
{: codeblock}

## Sortie des caractéristiques de personnalité
{: #traitJSON}

L'objet `Profile` comprend toujours les zones `personality`, `needs` et `values` pour tous les types d'entrée. Chacune de ces zones contient un tableau d'objets `Trait` qui décrit les caractéristiques de personnalité des attributs de ce type de caractéristique. Pour les caractéristiques Besoins et Valeurs, le tableau comporte un niveau unique qui les décrit. Pour les caractéristiques Big Five, un tableau de niveau supérieur décrit les dimensions et des tableaux de second niveau décrivent les facettes de chaque dimension.

-   `trait_id` (chaîne) est un ID unique de la caractéristique à laquelle les résultats appartiennent :
    -   `big5_{characteristic}` pour les dimensions de personnalité Big Five
    -   `facet_{characteristic}` pour les facettes de personnalité Big Five
    -   `need_{characteristic}` pour les caractéristiques Besoins
    -   `value_{characteristic}` pour les caractéristiques Valeurs
-   `name` (chaîne) est un nom visible par l'utilisateur de la caractéristique
-   `category` (chaîne) est la catégorie de la caractéristique :
    -   `personality` pour les caractéristiques de personnalité Big Five
    -   `needs` pour les caractéristiques Besoins
    -   `values` pour les caractéristiques Valeurs
-   `percentile` (double) est le percentile normalisé de la caractéristique. Pour plus d'informations, voir [Percentiles des caractéristiques de personnalité](/docs/services/personality-insights?topic=personality-insights-numeric#percentiles).
-   `raw_score` (double) est le score brut de la caractéristique. La zone est renvoyée uniquement si vous demandez des scores bruts en affectant au paramètre de requête `raw_scores` la valeur `true`. Pour plus d'informations, voir [Scores bruts des caractéristiques de personnalité](/docs/services/personality-insights?topic=personality-insights-numeric#rawScores-numeric).
-   `significant` (booléen) indique si la caractéristique est significative pour la langue d'entrée. La zone comporte toujours la valeur `true` pour toutes les caractéristiques des entrées en anglais, en espagnol et en japonais. La zone comporte la valeur `false` pour le sous-ensemble de caractéristiques des entrées en arabe et en coréen pour lesquelles les modèles du service ne peuvent pas générer des résultats significatifs. Pour plus d'informations, voir [Limitations pour les entrées en arabe et en coréen](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).
-   `children` est un tableau d'objets `Trait` qui fournit des résultats plus détaillés pour les facettes de chaque dimension Big Five telle qu'elle est déduite du texte d'entrée. Le tableau est renvoyé uniquement pour les dimensions Big Five.

### Exemple de réponse
{: #traitExample}

L'exemple de sortie suivant montre des fragments de la sortie pour les caractéristiques Big Five, Besoins et Valeurs. Comme indiqué, seules les caractéristiques Big Five comportent un tableau d'objets enfants (`children`) pour leurs facettes respectives.

```javascript
{
  . . .
  "personality": [
    {
      "trait_id": "big5_openness",
      "name": "Openness",
      "category": "personality",
      "percentile": 0.8011555009553,
      "raw_score": 0.77565404255038,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_adventurousness",
          "name": "Adventurousness",
          "category": "personality",
          "percentile": 0.89755869047319,
          "raw_score": 0.54990704031219,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_conscientiousness",
      "name": "Conscientiousness",
      "category": "personality",
      "percentile": 0.81001753184176,
      "raw_score": 0.66899984888815,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_achievement_striving",
          "name": "Achievement striving",
          "category": "personality",
          "percentile": 0.84613299226628,
          "raw_score": 0.74240118454888,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_extraversion",
      "name": "Extraversion",
      "category": "personality",
      "percentile": 0.64980796071382,
      "raw_score": 0.56817738781166,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_activity_level",
          "name": "Activity level",
          "category": "personality",
          "percentile": 0.88220584913965,
          "raw_score": 0.60106995926143,
          "significant": true
        },
      ]
    },
    {
      "trait_id": "big5_agreeableness",
      "name": "Agreeableness",
      "category": "personality",
      "percentile": 0.94786124793821,
      "raw_score": 0.80677815631809,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_altruism",
          "name": "Altruism",
          "category": "personality",
          "percentile": 0.99241983824205,
          "raw_score": 0.79028406290747,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_neuroticism",
      "name": "Emotional range",
      "category": "personality",
      "percentile": 0.5008224041628,
      "raw_score": 0.46748200007024,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_anger",
          "name": "Fiery",
          "category": "personality",
          "percentile": 0.17640022058508,
          "raw_score": 0.48490315691802,
          "significant": true
        },
        . . .
      ]
    }
  ],
  "needs": [
    {
      "trait_id": "need_challenge",
      "name": "Challenge",
      "category": "needs",
      "percentile": 0.67362332054511,
      "raw_score": 0.75196348037675,
      "significant": true
    },
    . . .
  ],
  "values": [
    {
      "trait_id": "value_conservation",
      "name": "Conservation",
      "category": "values",
      "percentile": 0.89268222856139,
      "raw_score": 0.72135308187423,
      "significant": true
    },
    . . .
  ],
  . . .
}
```
{: codeblock}

## Sortie de comportement
{: #behaviorJSON}

Si l'entrée vers le service est l'entrée JSON qui comporte des horodatages pour les objets de contenu individuels, l'objet `Profile` inclut une zone `behavior`. La zone comporte un objet `Behavior` pour chaque jour de la semaine et chaque heure du jour.

-   `trait_id` (chaîne) est un ID unique de la caractéristique à laquelle les résultats appartiennent :
    -   `behavior_{day}` pour les jours de la semaine (par exemple, `behavior_sunday`).
    -   `behavior_{hour}` pour les heures du jour (par exemple, `behavior_0000`).
-   `name` (chaîne) est un nom visible par l'utilisateur de la caractéristique
-   `category` (chaîne) est la catégorie de la caractéristique, qui est toujours `behavior`.
-   `percentage` (double) est le pourcentage d'objets de contenu qui se sont produits au cours de ce jour de la semaine ou de cette heure du jour. Pour plus d'informations, voir [Pourcentages des caractéristiques de comportement](/docs/services/personality-insights?topic=personality-insights-numeric#percentages).

### Exemple de réponse
{: #behaviorExample}

La sortie suivante illustre des fragments de la sortie de comportement pour les caractéristiques temporelles :

```javascript
{
  . . .
  "behavior": [
    {
      "trait_id": "behavior_sunday",
      "name": "Sunday",
      "category": "behavior",
      "percentage": 0.21392532795156
    },
    {
      "trait_id": "behavior_monday",
      "name": "Monday",
      "category": "behavior",
      "percentage": 0.42583249243189
    },
    . . .
    {
      "trait_id": "behavior_saturday",
      "name": "Saturday",
      "category": "behavior",
      "percentage": 0.077699293642785
    },
    {
      "trait_id": "behavior_0000",
      "name": "0:00 am",
      "category": "behavior",
      "percentage": 0.4561049445005
    },
    {
      "trait_id": "behavior_0100",
      "name": "1:00 am",
      "category": "behavior",
      "percentage": 0.12209889001009
    },
    . . .
    {
      "trait_id": "behavior_2300",
      "name": "11:00 pm",
      "category": "behavior",
      "percentage": 0.12310797174571
    }
  ],
  . . .
}
```
{: codeblock}

## Sortie des préférences de consommation
{: #preferenceJSON}

Si le paramètre de requête `consumption_preferences` a pour valeur `true`, l'objet `Profile` comprend une zone `consumption_preferences`. La zone comprend un objet `ConsumptionPreferencesCategory` pour chaque catégorie de préférences.

-   `consumption_preference_category_id` (chaîne) est l'ID unique de la catégorie des préférences de consommation auxquelles les résultats appartiennent sous la forme `consumption_preferences_{category}`.
-   `name` (chaîne) est le nom visible par l'utilisateur de la catégorie des préférences de consommation.
-   `consumption_preferences` est un tableau d'objets `ConsumptionPreferences` qui fournit des résultats pour les préférences individuelles de la catégorie.

Chaque préférence individuelle d'une catégorie est décrite via un objet `ConsumptionPreferences`. Certaines catégories ont une seule préférence ; d'autres en ont beaucoup plus. 

-   `consumption_preference_id` (chaîne) est l'ID unique de la préférence de consommation à laquelle les résultats appartiennent sous la forme `consumption_preferences_{preference}`.
-   `name` (chaîne) est le nom visible par l'utilisateur de la préférence de consommation.
-   `score` (double) est un score qui indique la propension de l'auteur à préférer l'objet. Pour plus d'informations, voir [Scores des préférences de consommation](/docs/services/personality-insights?topic=personality-insights-numeric#scores).

### Exemple de réponse
{: #preferenceExample}

La sortie suivante illustre des fragments de la sortie des préférences de consommation :

```javascript
{
  . . .
  "consumption_preferences": [
    {
      "consumption_preference_category_id": "consumption_preferences_shopping",
      "name": "Purchasing Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_automobile_ownership_cost",
          "name": "Likely to be sensitive to ownership cost when buying automobiles",
          "score": 0
        },
        . . .
      ]
    },
    {
      "consumption_preference_category_id": "consumption_preferences_health_and_activity",
      "name": "Health & Activity Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_eat_out",
          "name": "Likely to eat out frequently",
          "score": 1
        },
        . . .
      ]
    },
    . . .
    {
      "consumption_preference_category_id": "consumption_preferences_volunteering",
      "name": "Volunteering Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_volunteer",
          "name": "Likely to volunteer for social causes",
          "score": 0
        }
      ]
    }
  ],
  . . .
}
```
{: codeblock}
