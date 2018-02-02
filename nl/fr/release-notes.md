---

copyright:
  years: 2015, 2017
lastupdated: "2017-11-28"

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

# Notes sur l'édition
{: #release-notes}

Les sections ci-après documentent les nouvelles fonctions et les modifications apportées à chaque édition du service {{site.data.keyword.personalityinsightsshort}}. Sauf indication contraire, toutes les modifications étaient rétrocompatibles et étaient disponibles de manière automatique et transparente pour toutes les applications nouvelles et existantes.
{: shortdesc}

> **Remarque :** les notes sur l'édition documentent la *version de service* et la *version d'interface* pour toutes les mises à jour récentes. Vous spécifiez la *version d'interface* avec le paramètre de requête `version` pour utiliser les nouvelles fonctions et la fonctionnalité rendues disponibles via cette mise à jour. Le service renvoie les deux versions avec l'en-tête de réponse `X-Service-Api-Version`. 

## 13 octobre 2017
{: #October2017}

**Version de service :** `3.4.0`<br/> **Version d'interface :** `2017-10-13`

-   L'objet `Trait` d'un profil de personnalité inclut désormais une zone `significant` supplémentaire. Un objet `Trait` distinct signale les résultats pour chaque dimension Big Five, chaque facette Big Five, Besoin et Valeur. La zone `significant` de chaque instance de l'objet indique si les résultats pour cette caractéristique sont significatives pour la langue d'entrée (`Content-Language`) de la demande :

    -   Pour l'anglais, l'espagnol et le japonais, la zone est toujours `true` pour toutes les caractéristiques de personnalité. 
    -   Pour l'arabe et le coréen, la zone est `true` pour la plupart des caractéristiques de personnalité, mais elle est `false` pour les caractéristiques de personnalité pour lesquelles les modèles du service ne peuvent pas produire de résultats significatifs. La zone est `false` pour un ensemble de caractéristiques constant ; pour une liste complète, voir [Limitations pour les entrées en arabe et en coréen](/docs/services/personality-insights/numeric.html#limitations). Ne vous fiez pas aux résultats des caractéristiques pour lesquelles la zone est `false`.

    Pour toute information sur le contenu de réponse JSON du service, voir [Compréhension d'un profil JSON](/docs/services/personality-insights/output.html).
-   En outre, la sortie CSV inclut désormais des colonnes supplémentaires dont les en-têtes sont nommés `*_significant`. Chaque colonne fournit une valeur booléenne qui indique si une caractéristique est significative. Pour toute information sur le contenu de réponse CSV d'un service, voir [Compréhension d'un profil CSV](/docs/services/personality-insights/output-csv.html).
-   La version d'interface spécifiée avec le paramètre `version` est `2017-10-13` pour utiliser la dernière version de l'interface.

## 18 septembre 2017
{: #September2017}

**Version de service :** `3.3.0`<br/> **Version d'interface :** `2016-10-19`

Le service prend désormais en charge un contenu d'entrée en coréen (`ko`). Pour toute information sur la valeur MAE (Mean Absolute Error) moyenne et la valeur Corrélation moyenne pour les entrées en coréen, voir [Valeur MAE moyenne et valeur Corrélation moyenne par langue](/docs/services/personality-insights/science.html#precisePerLanguage).

Les modèles du service sont incapables de produire des percentiles et des scores bruts significatifs pour un petit nombre de caractéristiques de personnalité des entrées en coréen. Pour plus d'informations sur les résultats de ces caractéristiques, voir [Limitations pour les entrées en arabe et en coréen](/docs/services/personality-insights/numeric.html#limitations).

## 10 avril 2017
{: #April2017}

**Version de service :** `3.1.7`<br/> **Version d'interface :** `2016-10-19`

-   Le service a modifié la façon dont il traite les demandes ayant de grandes quantités de contenu d'entrée. Le service accepte 20 Mo de contenu au maximum. Toutefois, avec les modèles basés sur *GloVe*, l'exactitude se stabilise à environ 3000 mots d'entrée. Cela diffère des anciens modèles, dans lesquels davantage de texte produisait une exactitude supérieure. En général, le service n'a plus besoin d'autant de contenu pour produire un profil précis. Mais tout contenu supplémentaire nécessite un temps de traitement supplémentaire, ce qui peut provoquer un dépassement de délai avant le traitement d'une demande. 

    Par conséquent, le service extrait et utilise désormais uniquement les 250 premiers Ko de contenu, sans compter le marquage HTML ou JSON, provenant de demandes de grande taille. Ce chiffre ne correspond pas à un nombre exact de mots, qui varie en fonction de la langue et de la nature du texte. En anglais, par exemple, la longueur de mot moyenne se situe entre quatre et cinq caractères, par conséquent, ce chiffre fournit environ 50 000 mots, ce qui représente un nombre de mots au moins 15 fois supérieur au nombre de mots dont le service a besoin. La zone `word_count` du format JSON de la réponse indique le nombre de mots que le service utilise en réalité pour une demande, ce qui peut être inférieur au nombre de mots dans l'entrée. 

    Etant donné qu'il fonde toujours un profil sur un nombre de mots largement supérieur au nombre de mots nécessaires pour une exactitude maximum, le service produit un profil tout aussi exact que par le passé. Toutefois, le service répond beaucoup plus vite qu'avant. Pour les demandes pour lesquelles il utilise uniquement une partie du contenu d'entrée, le service renvoie le message d'avertissement `CONTENT_TRUNCATED` suivant pour que l'utilisateur soit conscient de ce qui suit :

    `Pour obtenir une précision maximale tout en optimisant le temps de traitement, seuls les 250 premiers Ko de texte d'entrée (à l'exclusion du balisage) étaient analysés. L'exactitude se stabilise à environ 3000 mots, par conséquent, cela n'affectait pas l'exactitude du profil.`

    Pour plus d'informations, voir [Indication d'entrées suffisantes](/docs/services/personality-insights/input.html#sufficient).
-   Le service a été mis à jour avec des petits correctifs de sécurité. 

## Editions antérieures
{: #older}

-   [1 mars 2017](#March2017)
-   [20 février 2017](#February2017b)
-   [13 février 2017](#February2017)
-   [13 janvier 2017](#January2017)
-   [15 décembre 2016](#December2016)
-   [15 novembre 2016](#November2016)
-   [20 octobre 2016](#October2016b)
-   [12 octobre 2016](#October2016a)
-   [31 août 2016](#August2016)
-   [14 juillet 2016](#July2016b)
-   [1 juillet 2016](#July2016a)
-   [7 juin 2016](#June2016b)
-   [1 juin 2016](#June2016a)
-   [17 mai 2016](#May2016)
-   [18 mars 2016](#March2016)
-   [9 juillet 2015](#July2015)
-   [23 février 2015](#February2015)

### 1 mars 2017
{: #March2017}

**Version de service :** `3.1.6`<br/> **Version d'interface :** `2016-10-19`

Le service {{site.data.keyword.personalityinsightsshort}} a été mis à jour avec des petites améliorations apportées à la consignation. 

### 20 février 2017
{: #February2017b}

**Version de service :** `3.1.5.1`<br/> **Version d'interface :** `2016-10-19`

Le service Personality Insights a été mis à jour avec des petits correctifs de sécurité et d'incident et pour améliorer le décompte des appels API. 

### 13 février 2017
{: #February2017}

**Version de service :** `3.1.4`<br/> **Version d'interface :** `2016-10-19`

-   La liste des préférences de consommation a été affinée de manière à inclure uniquement les préférences les plus importantes afin de comprendre les habitudes dominantes d'un individu en matière de style de vie et de consommation. La liste des préférences de consommation est passée de 51 à 42 entrées ; les entrées restantes expriment la propension de l'auteur à préférer différents produits et services et différentes activités de manière plus concise, permettant de faciliter la prise de mesures en fonction des résultats. Le service ne renvoie plus les neuf préférences de consommation ci-après. Pour plus d'informations sur les préférences restantes, voir [Préférences de consommation](/docs/services/personality-insights/preferences.html). 

    <table>
      <caption>Tableau 1. Modifications apportées aux préférences de consommation</caption>
      <tr>
        <th style="text-align:left">Catégorie</th>
        <th style="text-align:left">Préférences de consommation retirées</th>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_shopping</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_automobile_resale_value</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_reading</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_read_motive_enjoyment</code>
            <code>consumption_preferences_read_motive_information</code>
            <code>consumption_preferences_read_motive_mandatory</code>
            <code>consumption_preferences_read_motive_relaxation</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_health_and_activity</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_adventurous_sports</code>
            <code>consumption_preferences_fast_food_frequency</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_volunteering</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_volunteering_time</code>
            <code>consumption_preferences_volunteer_learning</code>
          </p>
        </td>
      </tr>
    </table>

-   *Pour les entrées en arabe*, des informations sur la valeur MAE (Mean Absolute Error) moyenne et la valeur Corrélation moyenne sont désormais disponibles dans la rubrique [Valeur MAE moyenne et valeur Corrélation moyenne par langue](/docs/services/personality-insights/science.html#precisePerLanguage). En outre, les modèles du service sont incapables de produire des percentiles et des scores bruts significatifs pour un groupe de caractéristiques de personnalité. Pour plus d'informations sur les résultats de ces caractéristiques, voir [Limitations pour les entrées en arabe et en coréen](/docs/services/personality-insights/numeric.html#limitations).

### 13 janvier 2017
{: #January2017}

**Version de service :** `3.1.2.1`<br/> **Version d'interface :** `2016-10-19`

Le service Personality Insights a été mis à jour avec un petit nombre de correctifs d'incident. 

### 15 décembre 2016
{: #December2016}

**Version de service :** `3.1.1`<br/> **Version d'interface :** `2016-10-19`

Pour le texte d'entrée en arabe, le service {{site.data.keyword.personalityinsightsshort}} utilise désormais la technique d'imbrication de mots open source appelée *GloVe* pour développer un profil de personnalité. Le service n'utilise plus le dictionnaire psycholinguistique LIWC (Linguistic Inquiry and Word Count) pour aucune langue. Pour plus d'informations sur la façon dont le service développe un portrait de personnalité, voir [Mode de déduction des caractéristiques de personnalité](/docs/services/personality-insights/science.html#researchInfer).

### 15 novembre 2016
{: #November2016}

**Version de service :** `3.1.0`<br/> **Version d'interface :** `2016-10-19`

-   Pour le texte d'entrée en japonais, le service {{site.data.keyword.personalityinsightsshort}} utilise désormais la technique d'imbrication de mots open source appelée *GloVe* pour développer un profil de personnalité ; le service n'utilise plus le dictionnaire psycholinguistique LIWC (Linguistic Inquiry and Word Count) pour les entrées en japonais. Pour plus d'informations, voir [Mode de déduction des caractéristiques de personnalité](/docs/services/personality-insights/science.html#researchInfer).
-   La zone `name` des objets `ConsumptionPreferencesCategory` et `ConsumptionPreferences` est désormais renvoyée avec des chaînes localisées dans la langue spécifiée avec l'en-tête de requête `Accept-Language`. 
-   La mise à jour inclut un petit nombre de correctifs d'incident. 

### 20 octobre 2016
{: #October2016b}

**Version de service :** `3.0.0`<br/> **Version d'interface :** `2016-10-19`

Le service {{site.data.keyword.personalityinsightsshort}} et son API ont fait l'objet d'une mise à jour importante. L'API a été incrémentée de la version 2 vers la version 3 et offre de nouvelles fonctions. Les sections restantes de cette note sur l'édition décrivent ces modifications de façon détaillée. 

La version 3 n'est pas rétrocompatible avec la version 2. Vous êtes encouragé à migrer vers la version 3 afin de bénéficier des nouvelles fonctions et des modifications. La migration vers la version 3 consiste uniquement à mettre à jour et à redéployer vos applications afin d'utiliser les modifications décrites dans les notes sur l'édition pour la nouvelle version. Vous n'avez pas besoin de créer une nouvelle instance du service dans {{site.data.keyword.Bluemix_notm}} ; il vous suffit d'appeler l'API `v3`. 

> **Remarque :** la version 2 de l'API {{site.data.keyword.personalityinsightsshort}} sera prochainement retirée du service. Nous vous encourageons fortement à migrer vers la version 3 dès que possible. Vous pouvez dés à présent accéder à la documentation de référence de la version 2 sur le site [API reference for v2 ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/watson/developercloud/personality-insights/api/v2/){: new_window} ; vous pouvez également accéder à l'outil interactif pour tester les appels vers la version 2 et afficher les réponses réelles du service sur le site [API explorer for v2 ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v2){: new_window}.

#### Informations supplémentaires sur la version 3 

Cette documentation décrit désormais la version 3 de l'API {{site.data.keyword.personalityinsightsshort}}. Les sections ci-après récapitulent les modifications apportées à la nouvelle version de l'interface :

-   Pour toute information sur l'appel de la méthode `/v3/profile`, voir [Demande d'un profil](/docs/services/personality-insights/input.html).
-   Pour toute information sur la réponse d'une méthode `/v3/profile`, voir [Compréhension d'un profil JSON](/docs/services/personality-insights/output.html) et [Compréhension d'un profil CSV](/docs/services/personality-insights/output-csv.html).
-   Pour obtenir des informations détaillées et complètes sur l'interface de la version 3, voir [API reference ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

#### Modifications apportées aux paramètres de la méthode <code>/v3/profile</code>

Les paramètres de la méthode `/v3/profile` ont été modifiés comme suit :

-   L'API offre désormais un paramètre de requête facultatif nommé `consumption_preferences`. Le paramètre accepte une valeur booléenne indiquant si les informations déduites sur les préférences de consommation doivent être renvoyées avec les résultats. Par défaut, ces informations ne sont pas incluses dans la réponse. Pour plus d'informations, voir [Nouvelle fonction Préférences de consommation](#cp).
-   L'API inclut désormais un paramètre de requête obligatoire nommé `version`. Le paramètre accepte une chaîne qui identifie la version demandée de l'API et le format de réponse en tant que date au format `AAAA-MM-JJ` ; par exemple, spécifiez `2016-10-19` pour le 19 octobre 2016. Ce paramètre permet au service de mettre à jour son API ou son format de réponse vers les nouvelles versions sans entraîner de rupture avec les clients existants. La chaîne initiale pour la version 3 de l'API est `2016-10-19`.

Il n'est pas nécessaire que la date que vous spécifiez corresponde exactement à une version du service ; le service utilise la version qui n'est pas ultérieure à la date que vous indiquez. Si vous indiquez une date antérieure à la date d'édition de la version 3, le service utilise la version 3 de l'API. Si vous indiquez une date qui se situe dans le futur ou qui est postérieure à la version la plus récente, le service utilise la version la plus récente.
-   Le nom du paramètre de requête `include_raw` est désormais `raw_scores`.
-   Le nom du paramètre de requête `headers` est désormais `csv_headers`.

#### Nouvelle fonction Préférences de consommation
{: #cp}

La fonction Préférences de consommation fournit une indication de la tendance de l'auteur à montrer différentes tendances de consommation. Lorsque vous transmettez le paramètre de requête `consumption_preferences` avec une valeur `true` à la méthode `/v3/profile`, le service renvoie les résultats supplémentaires suivants avec l'objet `Profile` : 

-   Une zone `consumption_preferences` qui fournit un tableau d'objet `ConsumptionPreferencesCategory`. 
-   Chaque objet `ConsumptionPreferencesCategory` inclut les zones suivantes :
    -   `consumption_preference_category_id` : ID de l'une des catégories de préférences de consommation.
    -   `name` : nom visible par l'utilisateur de la catégorie. 
    -   `consumption_preferences` : tableau d'objets `ConsumptionPreferences` qui fournit des résultats déduits à partir du texte d'entrée pour les préférences individuelles de la catégorie. 
-   Chaque objet `ConsumptionPreferences` inclut les zones suivantes :
    -   `consumption_preference_id` : ID de l'une des préférences de consommation. 
    -   `name` : nom visible par l'utilisateur de la préférence de consommation. 
    -   `score` : score de la préférence de consommation. Pour de nombreuses préférences, `0.0` signifie "peu probable", `0.5` signifie "neutre" et `1.0` signifie "probable". Les scores pour certaines préférences sont binaires et n'autorisent pas une valeur neutre. Le score est une indication de la préférence basée sur les résultats déduits à partir du texte d'entrée, et non un percentile normalisé. 

Pour plus d'informations sur les préférences de consommation, voir [Préférences de consommation](/docs/services/personality-insights/preferences.html).

> **Remarque :** actuellement, la zone `name` pour les objets des préférences de consommation est toujours renvoyée en anglais, quelle que soit la langue spécifiée avec l'en-tête de demande `Accept-Language`. 

#### Modifications apportées aux objets et zones JSON

Les objets d'entrée et de sortie JSON et leurs zones ont été simplifiés et clarifiés comme suit :

-   Les zones suivantes ont été retirées des objets `ContentItem` JSON que vous pouvez transmettre à la méthode `/v3/profile` avec une demande : 
    -   `userid`
    -   `sourceid`
    -   `charset` (précédemment obsolète)

    Vous transmettez ces objets dans le corps d'une demande JSON en tant qu'éléments du tableau `contentItems` de l'objet `Content`.
-   Les zones suivantes de l'objet `Profile` JSON qui est renvoyé par la méthode `/v3/profile` ont changé :
    -   Les zones suivantes ont été retirées :
        -   `id`
        -   `source`
    - La zone `tree` a été retirée. Elle a été remplacée par quatre nouvelles zones :
        -   `personality` pour les caractéristiques de personnalité Big Five. 
        -   `needs` pour les caractéristiques Besoins. 
        -   `values` pour les caractéristiques Valeurs. 
        -   `behavior` pour les résultats temporels sur la distribution du contenu au fil des jours de la semaine et des heures du jour. Cette zone est renvoyée uniquement pour l'entrée JSON qui est horodatée. 

    Cette modification déplace les résultats vers un niveau supérieur dans l'objet `Profile` JSON, éliminant un niveau de récursivité.
    -   Le nom de la zone `processed_lang` est désormais `processed_language`.
-   Les zones suivantes des objets `Trait` qui sont renvoyés par la méthode `/v3/profile` ont été renommées :
    -   Le nom de la zone `id` de l'objet `Trait` JSON est désormais `trait_id`.
    -   Le nom de la zone `percentage` de l'objet `Trait` JSON est désormais `percentile`.
-   Les zones suivantes des objets `Trait` JSON qui sont renvoyés par la méthode `/v3/profile` ont été retirées :
    -   `sampling_error`
    -   `raw_sampling_error`

    Le service renvoie désormais une valeur MAE (Mean Absolute Error) moyenne qui qualifie la précision de ses résultats. Pour plus d'informations sur la valeur MAE pour les différentes quantités de texte d'entrée, voir [Indication d'entrées suffisantes](/docs/services/personality-insights/input.html#sufficient).
-   Les objets `Trait` JSON sont toujours renvoyés pour les zones `personality`, `needs` et `values` de l'objet `Profile`. Mais, la zone `behavior` renvoie un tableau d'objets JSON nommés `Behavior` qui comportent les zones suivantes :
    -   `trait_id`
    -   `name`
    -   `category`
    -   `percentage`

    De plus, les informations sur le comportement ne sont plus renvoyées sous la forme d'une arborescence de valeurs. La sortie comprend un seul tableau qui répertorie toutes les caractéristiques temporelles (jour de la semaine et heure du jour).
-   Le nom de la zone `id` de l'objet `Warnings` JSON qui peut être renvoyé par la méthode `/v3/profile` est désormais `warnings_id`.

#### Modifications apportées aux ID JSON
{: #ids}

Les ID JSON que le service renvoie pour la zone `trait_id` (anciennement appelée `id`) de l'objet `Trait` et le nouvel objet `Behavior` ont été modifiés comme suit : 

-   Les ID des dimensions Big Five commencent désormais par la chaîne `big5_`.
-   Les ID des facettes Big Five commencent désormais par la chaîne `facet_`.
-   Les ID des caractéristiques Besoins commencent désormais par la chaîne `need_`.
-   Les ID des caractéristiques Valeurs commencent désormais par la chaîne `value_`.
-   Les ID de toutes les caractéristiques temporelles commencent désormais par la chaîne `behavior_`.
-   Les ID des caractéristiques temporelles liées à l'heure du jour utilisent désormais un délai de 24 heures composé de quatre chiffres (par exemple, `behavior_0000`) au lieu d'un délai de 12 heures (par exemple, `0:00 am`).
-   Tous les caractères sont désormais en minuscules.
-   Les espaces et les traits d'union sont désormais des traits de soulignement. 

#### Modifications apportées aux en-têtes CSV
{: #headers}

Les en-têtes de colonne facultatifs que le service peut renvoyer pour la sortie CSV ont été modifiés comme suit :

-   Toutes les modifications décrites pour l'objet `trait_id` de la sortie JSON s'appliquent désormais aux en-têtes CSV. 
-   Les en-têtes des scores bruts pour les dimensions Big Five commencent désormais par la chaîne `big5_`.
-   Les en-têtes des scores bruts pour les facettes Big Five commencent désormais par la chaîne `facet_`.
-   Les en-têtes des scores bruts pour les caractéristiques Besoins commencent désormais par la chaîne `need_`.
-   Les en-têtes des scores bruts pour les caractéristiques Valeurs commencent désormais par la chaîne `value_`.
-   L'en-tête de la colonne de langue traitée est désormais `processed_language` et non `processed_lang`.
-   Les colonnes `user` et `source_id` ne sont plus renvoyées. 
-   Tous les caractères sont désormais en minuscules.
-   Les espaces et les traits d'union sont désormais des traits de soulignement. 

#### Retrait de la méthode <code>visualize</code>

La version 2 de l'API du service comportait une méthode `visualize` obsolète qui était utilisée dans une édition précédente afin de visualiser les résultats d'un appel émis vers la méthode `/v3/profile`. La méthode `visualize` a été retirée de l'API du service. Le service continue de fournir une collection de fichiers JavaScript qui permettent de visualiser graphiquement un profil. Pour plus d'informations, voir [Visualisation d'un profil](/docs/services/personality-insights/developer-overview.html#visualize).

### 12 octobre 2016
{: #October2016a}

Pour le texte d'entrée en espagnol, le service {{site.data.keyword.personalityinsightsshort}} utilise désormais la technique d'imbrication de mots open source appelée *GloVe* pour développer un profil de personnalité ; le service n'utilise plus le dictionnaire psycholinguistique LIWC (Linguistic Inquiry and Word Count) pour les entrées en espagnol. Le service a commencé à utiliser le nouveau modèle pour le texte d'entrée en anglais le 31 août ; il appliquera le nouveau modèle aux autres langues à une date ultérieure. Pour plus d'informations sur le nouveau modèle, voir [Mode de déduction des caractéristiques de personnalité](/docs/services/personality-insights/science.html#researchInfer).

### 31 août 2016
{: #August2016}

Le service {{site.data.keyword.personalityinsightsshort}} utilise désormais une technique d'imbrication de mots open source appelée *GloVe* pour développer un profil de personnalité. Pour plus d'informations, voir [Mode de déduction des caractéristiques de personnalité](/docs/services/personality-insights/science.html#researchInfer). Pour l'instant, le service utilise la nouvelle approche uniquement pour le texte d'entrée en anglais. Pour les autres langues, le service continue d'utiliser le dictionnaire psycholinguistique LIWC (Linguistic Inquiry and Word Count). Les futures versions du service utiliseront l'approche de vocabulaire ouvert pour toutes les langues. 

Pour le nouveau modèle utilisé pour le texte d'entrée en anglais, le service renvoie la valeur MAE (Mean Absolute Error) moyenne des résultats pour son modèle formé. Pour plus d'informations sur la façon dont la valeur MAE change avec différentes quantités de texte d'entrée, voir [Indication d'entrées suffisantes](/docs/services/personality-insights/input.html#sufficient). Les futures versions du service renverront la valeur MAE pour les modèles qui ne sont pas en anglais et vous recommanderont de l'utiliser, contrairement à des erreurs d'échantillonnage, afin de déterminer de quelle façon la précision du service change en fonction de la quantité de texte d'entrée que vous indiquez. 

### 14 juillet 2016
{: #July2016b}

-   Pour le texte d'entrée en arabe, le service peut désormais tronquer le texte d'entrée pour des raisons de performance. A un certain seuil, l'exactitude des résultats pour l'arabe ne s'améliore pas avec davantage de mots. Si le service tronque le texte d'entrée en arabe, il renvoie le message d'avertissement `PARTIAL_TEXT_USED` suivant : 

    `The text provided to compute the profile was trimmed for performance reasons. This action does not affect the accuracy of the output, as not all of the input text was required.`
-   La mise à jour inclut d'autres correctifs d'incident et améliorations internes. 

### 1 juillet 2016
{: #July2016a}

-   Les plans de tarification du service ont été modifiés pour offrir des prix inférieurs aux utilisateurs {{site.data.keyword.personalityinsightsshort}}. Pour plus d'informations, voir le service [{{site.data.keyword.personalityinsightsshort}} dans le catalogue {{site.data.keyword.Bluemix_short}} ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://console.ng.bluemix.net/catalog/services/personality-insights/){: new_window}.
-   La liste des langues de réponse prises en charge que vous pouvez spécifier avec l'en-tête `Accept-Language` inclut désormais ce qui suit :
    -   `ar` (arabe)
    -   `de` (allemand)
    -   `en` (anglais, valeur par défaut)
    -   `es` (espagnol)
    -   `fr` (français)
    -   `it` (italien)
    -   `ja` (japonais)
    -   `ko` (coréen)
    -   `pt-br` (portugais brésilien)
    -   `zh-cn` (chinois simplifié)
    -   `zh-tw` (chinois traditionnel)

    Pour plus d'informations, voir [Indication des langues de demande et de réponse](/docs/services/personality-insights/input.html#languages).
-   La méthode `/v2/profile` peut désormais renvoyer les codes d'état HTTP suivants :
    -   429 *Too Many Requests* : le service traite actuellement un trop grand nombre de demandes pour la langue de contenu. Attendez quelques instants et relancez votre demande. Si vous soumettez un grand nombre de demandes pour la langue, vous devez envisager de réguler le taux auquel vous soumettez vos demandes. 
    -   504 *Gateway Timeout* : un dépassement de délai s'est produit pour la demande ou le temps de traitement de celle-ci s'est prolongé. Attendez quelques instants et relancez votre demande. Si l'entrée contenait un nombre élevé de mots (par exemple, plus de 20 000), vous devez envisager de réduire le nombre de mots tout en suivant les instructions pour un texte d'entrée significatif. 

    La méthode ne renvoie plus le message 503 *Service Unavailable*. Pour plus d'informations sur les codes de réponse possibles, voir[API reference ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.
-   La mise à jour inclut d'autres correctifs d'incident et améliorations internes. 

### 7 juin 2016
{: #June2016b}

-   Le service prend désormais en charge le partage de ressources d'origine croisée (CORS) pour permettre aux clients basés sur le navigateur d'appeler directement le service. Pour plus d'informations, voir [Prise en charge de CORS](/docs/services/personality-insights/developer-overview.html#CORS).
-   Les performances du service lors du traitement du texte en japonais ont été améliorées de manière significative. 
-   La mise à jour inclut d'autres correctifs d'incident et améliorations internes. 

### 1 juin 2016
{: #June2016a}

Le service {{site.data.keyword.personalityinsightsshort}} a été mis à jour avec des correctifs d'incident et des améliorations internes. Une autre zone de niveau supérieur, `warnings`, a également été ajoutée aux résultats JSON renvoyés par le service ; pour plus d'informations, voir [API reference ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

### 17 mai 2016
{: #May2016}

Le service {{site.data.keyword.personalityinsightsshort}} a été mis à jour avec des correctifs d'incident et des améliorations internes. 

### 18 mars 2016
{: #March2016}

Le service prend désormais en charge les langues répertoriées suivantes :

-   Quatre langues pour son texte d'entrée : l'arabe (`ar`), l'anglais (`en`), l'espagnol (`es`) et le japonais (`ja`). Pour spécifier la langue, utilisez l'en-tête `Content-Language` HTTP pour le texte brut et l'entrée HTML ou la propriété `language` de l'objet `ContentItem` pour l'entrée JSON. 
-   Quatre langues identiques pour sa réponse. Pour spécifier la langue de la réponse, utilisez l'en-tête `Accept-Language`. 

Vous pouvez utiliser n'importe quelle combinaison de langues pour la demande et la réponse. Dans les deux cas, si vous n'indiquez pas de langue, le service utilise l'anglais par défaut.   Pour plus d'informations, voir [Indication des langues de demande et de réponse](/docs/services/personality-insights/input.html#languages).
Pour plus d'informations, voir également l'article de blogue [Arabic and Japanese support is now available for {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.personalityinsightsshort}} ![External link icon](../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/blogs/watson/2016/04/arabic-japanese-support-now-available-ibm-watson-personality-insights/){: new_window}. 

> **Remarque :** étant donné que l'arabe nécessite beaucoup plus de cycles de calcul pour l'analyse que d'autres langues, le traitement du contenu en arabe prend beaucoup plus de temps. Bien que le service prenne en charge la même restriction de 20 Mo en matière de quantité de texte d'entrée pour toutes les langues, la limite pratique pour le contenu en arabe peut être inférieure afin d'éviter tout dépassement de délai. Le temps de traitement du contenu en japonais est également plus long, mais les délais sont moins importants que pour l'arabe. 

### 9 juillet 2015
{: #July2015}

-   *Support de langue.* Le service vous permet désormais d'analyser un contenu en anglais et en espagnol. Vous indiquez la langue du texte d'entrée avec l'en-tête `Content-Language` de la méthode `/v2/profile`. Pour plus d'informations sur la spécification d'une langue, voir[Indication des langues de demande et de réponse](/docs/services/personality-insights/input.html#languages).
-   *Scores bruts.* Le service vous permet désormais de demander des scores bruts et des erreurs d'échantillonnage brutes calculés à partir du texte d'entrée et des modèles du service. Les valeurs ne sont pas normalisées ni comparées avec un échantillon de population. Les scores bruts sont utiles pour les clients qui souhaitent appliquer une normalisation personnalisée pour un scénario spécifique ou lorsqu'une comparaison avec un échantillon de population n'est pas nécessaire. Vous demandez des scores bruts en affectant au paramètre de requête `include_raw` de la méthode `/v2/profile` la valeur `true`. Pour plus d'informations, voir [Interprétation des résultats numériques](/docs/services/personality-insights/numeric.html).
-   *Améliorations des modèles.* Sur la base de ses dernières études, {{site.data.keyword.IBM_notm}} a amélioré davantage certaines de ses approches de déduction des caractéristiques de personnalité. Les modifications sont transparentes pour les utilisateurs du service et n'invalident aucun des précédents résultats obtenus à partir du service. Pour plus d'informations sur les études et l'approche du service en matière de déduction, voir [Mode de déduction des caractéristiques de personnalité](/docs/services/personality-insights/science.html#researchInfer).

### 23 février 2015
{: #February2015}

A compter du 23 février 2015, le service {{site.data.keyword.personalityinsightsshort}} est la version de disponibilité générale de l'ancien service de modélisation utilisateur, qui était disponible en tant que version bêta. La version de disponibilité générale nécessite que les utilisateurs effectuent une migration vers une instance du nouveau service. Les différences ci-après  existent entre les versions bête et de disponibilité générale du service. 

-   Le service {{site.data.keyword.personalityinsightsshort}} est compatible en amont avec le service de modélisation utilisateur. Les différences décrites dans cette section fournissent une plus grande flexibilité et des résultats améliorés sans affecter les applications en cours. 
-   Les paramètres avec lesquels vous créez le service dans {{site.data.keyword.Bluemix_short}} ont changé. Vous utilisez désormais un nom de service`personality_insights` au lieu de `user_modeling` et un plan de service `"IBM Watson Personality Insights Monthly Plan"` au lieu de `user_modeling_free_plan`.
-   La méthode `/v2/profile` accepte deux nouveaux formats d'entrée. L'en-tête `Content-Type` accepte désormais le texte brut des formats d'entrée (`text/plain`), qui est défini par défaut, et HTML (`text/html`), en plus de JSON (`application/json`).
-   La méthode `/v2/profile` renvoie désormais un nouveau format de sortie. L'en-tête `Accept` accepte désormais la format CSV de sortie (`text/csv`) en plus de JSON (`application/json`), qui est défini par défaut. 
-   La méthode `/v2/profile` inclut désormais un nouvel élément de sortie, `sampling_error`, pour chaque caractéristique pour laquelle il renvoie une valeur de pourcentage. L'erreur d'échantillonnage est renvoyée sous la forme d'une valeur double précision qui indique le niveau de confiance du service dans le percentile de l'auteur sur la base du texte d'entrée. 
-   Le modèle Besoins emploie un marquage sémantique et un traitement améliorés afin de mieux normaliser la distribution de valeurs pour ses caractéristiques. Il est recommandé de recalculer les résultats qui ont été générés par l'API de modélisation utilisateur. 
-   La méthode `visualize` est désormais obsolète et sera entièrement retirée dans une édition future. Vous pouvez utiliser le fichier JavaScript `personality.js` qui est fourni avec l'exemple d'application pour obtenir des résultats similaires à partir du client. Le fichier JavaScript`textsummary.js` fournit un formatage supplémentaire pour les résultats du service. 
