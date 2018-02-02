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

# Interprétation des résultats numériques
{: #numeric}

Le service {{site.data.keyword.personalityinsightsshort}} renvoie des résultats numériques pour chacune des caractéristiques de personnalité et de comportement et pour chacune des préférences de consommation. Les valeurs diffèrent au regard des informations qu'elles fournissent.
{: shortdesc}

> **Remarque :** pour l'entrée en arabe et en coréen, le service est incapable de produire des percentiles et des scores bruts significatifs pour un certain nombre de caractéristiques de personnalité. Pour plus d'informations, voir [Limitations pour les entrées en arabe et en coréen](#limitations).

## Percentiles des caractéristiques de personnalité
{: #percentiles}

Pour chaque demande, le service signale toujours un score normalisé en tant que `percentile` pour chacune des caractéristiques Big Five, Valeurs et Besoins. Les scores normalisés représentent un classement de percentile pour chaque caractéristique basée sur les qualités déduites à partir du texte d'entrée. Le service calcule les scores normalisés en comparant le score brut du texte de l'auteur aux résultats obtenus à partir d'un échantillon de la population. Le service signale chaque percentile en tant que doublon compris entre 0 et 1. 

Par exemple, un percentile de `0.64980796071382` pour la caractéristique de personnalité `big5_extraversion` indique que l'auteur du texte a obtenu un score dans le 65e percentile de cette caractéristique. Les écrits de l'auteur démontrent la propension dans des proportions comprises entre 34 % et 64 % de l'échantillon de population. La précision du percentile dépend du nombre de mots qui ont été soumis comme entrée avec la demande. Pour plus d'informations, voir [Indication d'entrées suffisantes](/docs/services/personality-insights/input.html#sufficient).

> **Remarque :** il n'existe aucune relation mathématique entre les percentiles renvoyés pour les dimensions et les facettes Big Five. Le service calcule le percentile normalisé indépendamment pour chaque dimension et facette en fonction des corrélations entre les scores des participants à une enquête pour cette dimension ou facette et les mots qu'ils utilisent. Par conséquent, même si les facettes fournissent des descriptions de dimensions plus granulaires, le fait d'ajouter les scores pour les six facettes d'une dimension ne génère pas nécessairement le percentile pour cette dimension. Il en est de même pour les scores bruts.

## Scores bruts des caractéristiques de personnalité
{: #rawScores}

Si vous spécifiez la valeur `true` pour le paramètre de requête `raw_scores` de la demande, le service renvoie un élément `raw_score` pour chaque caractéristique de personnalité. Les scores bruts représentent le score de la caractéristique spécifique uniquement en fonction du texte de l'auteur et du modèle de cette caractéristique, sans comparer les résultats à un échantillon de la population. Les scores bruts peuvent être interprétés en tant que scores que l'auteur doit recevoir après avoir passé un texte de personnalité. 

Le service signale chaque score brut en tant que doublon compris entre 0 et 1. Un score plus élevé signale généralement une plus grande probabilité pour que cette caractéristique soit présente chez l'auteur. Toutefois, les scores bruts doivent être considérés dans leur ensemble. En pratique, la plage de valeurs doit être nettement inférieure à la plage comprise entre 0 et 1. Par conséquent, le score d'un individu doit être examiné dans le contexte de tous les scores et de leurs plages de valeurs. Or, généralement, un score brut de `0.56817738781166` par exemple pour la caractéristique de personnalité `big5_extraversion` indique que l'auteur aurait obtenu ce score lors d'un test de personnalité. Comparez ce score brut au percentile normalisé renvoyé pour le même auteur et la même caractéristique lors de la section précédente. 

Le service met des scores bruts à la disposition des utilisateurs qui souhaitent appliquer une normalisation personnalisée pour un scénario spécifique ou lorsqu'une comparaison avec un échantillon de population n'est pas nécessaire. Les utilisateurs qui souhaitent comparer les caractéristiques d'un auteur à un large échantillon de population peuvent utiliser les scores normalisés. Les utilisateurs qui souhaitent dériver leurs propres scores de percentile normalisés à partir des données brutes peuvent comparer les scores bruts à un autre échantillon de la population et appliquer une approche différente de normalisation. 

Afin de normaliser un score brut à un percentile pour une caractéristique spécifique, comparez le score brut à un échantillon de population pour lequel la moyenne et l'écart type pour la caractéristique sont connus. Par exemple, {{site.data.keyword.IBM_notm}} a mené des études visant à collecter des données à partir d'un vaste échantillon d'utilisateurs Twitter. {{site.data.keyword.IBM_notm}} a calculé les scores des utilisateurs pour chacune des caractéristiques de personnalité et a établi la moyenne et l'écart type pour chacune d'elles. Afin de calculer le score de percentile pour un score brut déduit à partir de son analyse de texte d'entrée, le service utilise la moyenne et l'écart type dérivés de son échantillon d'utilisateurs Twitter pour cette caractéristique. 

## Pourcentages des caractéristiques de comportement
{: #percentages}

Si vous soumettez des données JSON dont les objets de contenu contiennent des horodatages, le service renvoie un `pourcentage` pour chaque caractéristique de comportement. Les caractéristiques de comportement identifient la distribution temporelle de l'entrée. Le pourcentage indiquent le nombre d'objets de contenu qui se sont produits à chaque jour de la semaine et à chaque heure de la journée. Par exemple, le pourcentage `0.4561049445005` pour la caractéristique de comportement `behavior_0000` signifie qu'environ 46 % des objets de contenu ont été créés entre minuit et 1 heure du matin. 

## Scores des préférences de consommation
{: #scores}

Si vous spécifiez la valeur `true` pour le paramètre de requête `consumption_preferences` de la demande, le service renvoie des préférences de consommation comportant chacune un `score`. Le service dérive le score à partir des caractéristiques de personnalité qu'il déduit à partir du texte d'entrée. Le score est un doublon indiquant quelles sont les chances que l'auteur du texte préfère l'objet. Il s'agit d'une indication de préférence et non d'un pourcentage normalisé. 

Pour certaines préférences, les trois valeurs possibles pour le score sont les suivantes :

-   `0.0` : il est très peu probable que l'auteur préfère l'objet. Pour certaines préférences, cette valeur peut signifier que le niveau d'intérêt de l'auteur est très bas. 
-   `0.5` : l'auteur est neutre par rapport à l'objet. Pour certaines préférences, cette valeur peut signifier que le niveau d'intérêt de l'auteur est moyen. 
-   `1.0` : il est très probable que l'auteur préfère l'objet. Pour certaines préférences, cette valeur signifie que le niveau d'intérêt de l'auteur est élevé. 

Pour les autres préférences, le score représente une valeur binaire. Il est très peu probable (`0.0`) ou très probable (`1.0`) que l'auteur du texte d'entrée soit intéressé par l'objet, ou bien l'auteur a niveau d'intérêt bas ou élevé. Dans certains cas, le score peut représenter un simple oui ou aucune réponse (par exemple, est-il probable que l'auteur ait une expérience de bénévolat pour des causes sociales). 

Pour obtenir la liste complète de toutes les préférences par catégorie et la plage de résultats correspondante, voir[Préférences de consommation](/docs/services/personality-insights/preferences.html).

## Limitations pour les entrées en arabe et en coréen
{: #limitations}

Pour l'entrée en arabe et en coréen, les modèles du service sont incapables de produire des résultats significatifs pour un sous-ensemble de  caractéristiques de personnalité. Pour les caractéristiques suivantes, les scores de percentile normalisés sont toujours `0.5` et les scores bruts correspondent toujours à la moyenne de la distribution d'origine. La valeur de la zone `significant` pour chacune de ces caractéristiques est toujours `false`. Ne vous fiez *pas* aux résultats obtenus pour ces caractéristiques dans le cadre du profil de personnalité de l'auteur. 

<table>
  <caption>Tableau 1. Caractéristiques dont les résultats ne sont pas significatifs</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
Caractéristiques </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      Résultats pour l'arabe<br/>qui ne sont pas significatifs
</th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      Résultats pour le coréen<br/>qui ne sont pas significatifs
</th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Dimensions Big Five
</td>
    <td style="text-align:left; vertical-align:top">
Portée émotionnelle
</td>
    <td style="text-align:left; vertical-align:top">
      Néant
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Facettes Big Five
</td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; line-height:110%; padding:0px">
          *Amabilité* : Altruisme, Coopération, Modestie et Confiance
</li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Tempérament consciencieux* : Persévérance et Sens du devoir
</li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Extraversion* : Gaieté et cordialité (sociabilité)
</li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Portée émotionnelle* : colère (passion), prompt à s'inquiéter, immodération et susceptibilité
</li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Ouverture* : intrépidité, imagination et intellect
</li>
      </ul>
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; padding:0px">
          *Extraversion* : recherche de sensations
</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
Besoins</td>
    <td style="text-align:left; vertical-align:top">
      Idéal, liberté, amour, pragmatisme et structure
</td>
    <td style="text-align:left; vertical-align:top">
      Liberté et stabilité
    </td>
  </tr>
  </tr>
    <td style="text-align:left; vertical-align:top">
valeurs</td>
    <td style="text-align:left; vertical-align:top">
      Ambition personnelle
</td>
    <td style="text-align:left; vertical-align:top">
Conservatisme
</td>
  </tr>
</table>
