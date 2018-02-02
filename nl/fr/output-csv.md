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

# Compréhension d'un profil CSV
{: #outputCSV}

Le service renvoie les résultats de son analyse au format CSV lorsque vous spécifiez `text/csv` avec l'en-tête `Accept` d'une demande. La sortie CSV fournit des informations similaires à celles fournies par la sortie JSON. Comme pour JSON, les informations contenues dans la sortie CSV varient selon que l'entrée représente des données horodatées et que l'utilisateur demande des scores bruts et des préférences de consommation.
{: shortdesc}

Toutefois, contrairement à JSON, la sortie CSV est renvoyée sous la forme d'un nombre fixe de colonnes. La première ligne de la sortie est constituée de libellés de colonne facultatifs, inclus uniquement si vous affectez au paramètre de requête `csv_headers` de la demande la valeur `true`. La seconde ligne de la sortie, toujours présente, contient les résultats de l'analyse. 

Les sections ci-après répertorient et décrivent brièvement toutes les colonnes de la sortie CSV dans l'ordre exact de leur apparition dans les résultats. Les tableaux décrivent les colonnes par groupement logique, y compris le nombre de colonnes dans chaque groupe et leurs libellés facultatifs. En dehors du nombre de mots, toutes les données numériques sont renvoyées sous la forme de valeurs double précision. 

Pour plus d'informations sur la signification des colonnes CSV, voir [Compréhension d'un profil JSON](/docs/services/personality-insights/output.html) et [Interprétation des résultats numériques](/docs/services/personality-insights/numeric.html).

## Caractéristiques et métadonnées de base
{: #basicCSV}

Les colonnes suivantes sont toujours présentes dans la sortie CSV pour toutes les demandes :

<table>
  <caption>Tableau 1. Colonnes CSV pour les caractéristiques et les métadonnées de base
</caption>
  <tr>
    <th style="width:25%; text-align:left; vertical-align:bottom">Groupement<br/>(nombre de colonnes)</th>
    <th style="width:25%; text-align:left; vertical-align:bottom">Libellés facultatifs</th>
    <th style="text-align:left; vertical-align:bottom">Description</th>
  </tr>
  <tr>
    <td>
      Amabilité Big Five<br/>Percentiles<br/>(7 colonnes)
</td>
    <td>
      big5_agreeableness<br/>facet_altruism<br/>
      facet_cooperation<br/>facet_modesty<br/>
      facet_morality<br/>facet_sympathy<br/>
      facet_trust
    </td>
    <td>
      Score de percentile normalisé pour l'auteur du texte par rapport à la dimension ou à la facette nommée.
</td>
  </tr>
  <tr>
    <td>
      Tempérament consciencieux Big Five<br/>Percentiles<br/>(7 colonnes)
</td>
    <td>
      big5_conscientiousness<br/>facet_achievement_striving
      <br/>facet_cautiousness<br/>facet_dutifulness<br/>
      facet_orderliness<br/>facet_self_discipline<br/>
      facet_self_efficacy
    </td>
    <td>
      Score de percentile normalisé pour l'auteur du texte par rapport à la dimension ou à la facette nommée.
</td>
  </tr>
  <tr>
    <td>
      Extraversion Big Five<br/>Percentiles<br/>(7 colonnes)
</td>
    <td>
      big5_extraversion<br/>facet_activity_level
      <br/>facet_assertiveness<br/>facet_cheerfulness<br/>
      facet_excitement_seeking<br/>facet_friendliness<br/>
      facet_gregariousness
    </td>
    <td>
      Score de percentile normalisé pour l'auteur du texte par rapport à la dimension ou à la facette nommée.
</td>
  </tr>
  <tr>
    <td>
      Portée émotionnelle Big Five<br/>Percentiles<br/>(7 colonnes)
</td>
    <td>
      big5_neuroticism<br/>facet_anger<br/>
      facet_anxiety<br/>facet_depression<br/>
      facet_immoderation<br/>facet_self_consciousness<br/>
      facet_vulnerability
    </td>
    <td>
      Score de percentile normalisé pour l'auteur du texte par rapport à la dimension ou à la facette nommée.
</td>
  </tr>
  <tr>
    <td>
      Ouverture Big Five<br/>Percentiles<br/>(7 colonnes)
</td>
    <td>
      big5_openness<br/>facet_adventurousness<br/>
      facet_artistic_interests<br/>facet_emotionality<br/>
      facet_imagination<br/>facet_intellect<br/>
      facet_liberalism
    </td>
    <td>
      Score de percentile normalisé pour l'auteur du texte par rapport à la dimension ou à la facette nommée.
</td>
  </tr>
  <tr>
    <td>
      Besoins - Percentiles<br/>(12 colonnes)
</td>
    <td>
      need_liberty<br/>need_ideal<br/>
      need_love<br/>need_practicality<br/>
      need_self_expression<br/>need_stability<br/>
      need_structure<br/>need_challenge<br/>
      need_closeness<br/>need_curiosity<br/>
      need_excitement<br/>need_harmony
    </td>
    <td>
      Score de percentile normalisé pour l'auteur du texte par rapport au besoin nommé.
</td>
  </tr>
  <tr>
    <td>
      Valeurs - Percentiles<br/>(5 colonnes)
</td>
    <td>
      value_conservation<br/>value_hedonism<br/>
      value_openness_to_change<br/>value_self_enhancement<br/>
      value_self_transcendence
    </td>
    <td>
      Score de percentile normalisé pour l'auteur du texte par rapport à la valeur nommée.
</td>
  </tr>
  <tr>
    <td>
      Jours de la semaine<br/>Pourcentages<br/>(7 colonnes)
</td>
    <td>
      behavior_sunday<br/>behavior_monday<br/>
      behavior_tuesday<br/>behavior_wednesday<br/>
      behavior_thursday<br/>behavior_friday<br/>
      behavior_saturday
    </td>
    <td>
      Si le texte d'entrée comporte un horodatage, il s'agit du pourcentage de l'entrée associée à chaque jour de la semaine ;
      si l'entrée ne comporte pas d'horodatage, tous les pourcentages portent la valeur <code>0.0</code>.
    </td>
  </tr>
  <tr>
    <td>
      Heures du jour<br/>Pourcentages<br/>(24 colonnes)
</td>
    <td>
      behavior_0000<br/><em>à</em><br/>behavior_2300
    </td>
    <td>
      Si le texte d'entrée comporte un horodatage, il s'agit du pourcentage de l'entrée associée à chaque heure du jour ;
      si l'entrée ne comporte pas d'horodatage, tous les pourcentages portent la valeur <code>0.0</code>.
    </td>
  </tr>
  <tr>
    <td>
      Nombre de mots et<br/>langue <br/>(2 colonnes)
</td>
    <td>
      word_count<br/>processed_language
    </td>
    <td>
      Entier indiquant le nombre de mots présents dans le texte d'entrée et identificateur à deux lettres associé au modèle de langue qui est utilisé par le service pour analyser le texte.
</td>
  </tr>
</table>

## Scores bruts
{: #rawCSV}

Les colonnes suivantes sont présentes uniquement si vous demandez des scores bruts en affectant au paramètre de requête `raw_scores` la valeur `true`. Dans tous les cas, la colonne est une valeur double précision qui fournit le score brut de l'auteur pour la dimension, la facette, le besoin ou la valeur. 

<table>
  <caption>Tableau 2. Colonnes CSV pour les scores bruts</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Groupement<br/>(nombre de colonnes)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Libellés facultatifs</th>
  </tr>
  <tr>
    <td>
      Amabilité Big Five<br/>Scores bruts<br/>(7 colonnes)
</td>
    <td>
      big5_agreeableness_raw<br/>facet_altruism_raw<br/>
      facet_cooperation_raw<br/>facet_modesty_raw<br/>
      facet_morality_raw<br/>facet_sympathy_raw<br/>
      facet_trust_raw
    </td>
  </tr>
  <tr>
    <td>
      Tempérament consciencieux Big Five<br/>Scores bruts<br/>(7 colonnes)
</td>
    <td>
      big5_conscientiousness_raw<br/>facet_achievement_striving_raw<br/>
      facet_cautiousness_raw<br/>facet_dutifulness_raw<br/>
      facet_orderliness_raw<br/>facet_self_discipline_raw<br/>
      facet_self_efficacy_raw
    </td>
  </tr>
  <tr>
    <td>
      Extraversion Big Five<br/>Scores bruts<br/>(7 colonnes)
</td>
    <td>
      big5_extraversion_raw<br/>facet_activity_level_raw<br/>
      facet_assertiveness_raw<br/>facet_cheerfulness_raw<br/>
      facet_excitement_seeking_raw<br/>facet_friendliness_raw<br/>
      facet_gregariousness_raw
    </td>
  </tr>
  <tr>
    <td>
      Portée émotionnelle Big Five<br/>Scores bruts<br/>(7 colonnes)
</td>
    <td>
      big5_neuroticism_raw<br/>facet_anger_raw<br/>
      facet_anxiety_raw<br/>facet_depression_raw<br/>
      facet_immoderation_raw<br/>facet_self_consciousness_raw<br/>
      facet_vulnerability_raw
    </td>
  </tr>
  <tr>
    <td>
      Ouverture Big Five<br/>Scores bruts<br/>(7 colonnes)
</td>
    <td>
      big5_openness_raw<br/>facet_adventurousness_raw<br/>
      facet_artistic_interests_raw<br/>facet_emotionality_raw<br/>
      facet_imagination_raw<br/>facet_intellect_raw<br/>
      facet_liberalism_raw
    </td>
  </tr>
  <tr>
    <td>
      Besoins - Scores bruts<br/>(12 colonnes)
</td>
    <td>
      need_liberty_raw<br/>need_ideal_raw<br/>
      need_love_raw<br/>need_practicality_raw<br/>
      need_self_expression_raw<br/>need_stability_raw<br/>
      need_structure_raw<br/>need_challenge_raw<br/>
      need_closeness_raw<br/>need_curiosity_raw<br/>
      need_excitement_raw<br/>need_harmony_raw
    </td>
  </tr>
  <tr>
    <td>
      Valeurs - Scores bruts<br/>(5 colonnes)
</td>
    <td>
      value_conservation_raw<br/>value_hedonism_raw<br/>
      value_openness_to_change_raw<br/>value_self_enhancement_raw<br/>
      value_self_transcendence_raw
    </td>
  </tr>
</table>

## Signification
{: #significantCSV}

Les colonnes suivantes sont toujours présentes dans la sortie CSV pour toutes les demandes. Dans tous les cas, la colonne est une valeur booléenne qui indique si la dimension, la facette, le besoin ou la valeur est significatif pour la langue d'entrée traitée. 

<table>
  <caption>Tableau 3. Colonnes CSV pour la signification</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Groupement<br/>(nombre de colonnes)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Libellés facultatifs</th>
  </tr>
  <tr>
    <td>
      Amabilité Big Five<br/>Signification<br/>(7 colonnes)
</td>
    <td>
      big5_agreeableness_significant<br/>facet_altruism_significant<br/>
      facet_cooperation_significant<br/>facet_modesty_significant<br/>
      facet_morality_significant<br/>facet_sympathy_significant<br/>
      facet_trust_significant
    </td>
  </tr>
  <tr>
    <td>
      Tempérament consciencieux Big Five<br/>Signification<br/>(7 colonnes)
</td>
    <td>
      big5_conscientiousness_significant<br/>
      facet_achievement_striving_significant<br/>
      facet_cautiousness_significant<br/>facet_dutifulness_significant<br/>
      facet_orderliness_significant<br/>facet_self_discipline_significant<br/>
      facet_self_efficacy_significant
    </td>
  </tr>
  <tr>
    <td>
      Extraversion Big Five<br/>Signification<br/>(7 colonnes)
</td>
    <td>
      big5_extraversion_significant<br/>facet_activity_level_significant<br/>
      facet_assertiveness_significant<br/>facet_cheerfulness_significant<br/>
      facet_excitement_seeking_significant<br/>
      facet_friendliness_significant<br/>facet_gregariousness_significant
    </td>
  </tr>
  <tr>
    <td>
      Portée émotionnelle Big Five<br/>Signification<br/>(7 colonnes)
</td>
    <td>
      big5_neuroticism_significant<br/>facet_anger_significant<br/>
      facet_anxiety_significant<br/>facet_depression_significant<br/>
      facet_immoderation_significant<br/>
      facet_self_consciousness_significant<br/>facet_vulnerability_significant
    </td>
  </tr>
  <tr>
    <td>
      Ouverture Big Five<br/>Signification<br/>(7 colonnes)
</td>
    <td>
      big5_openness_significant<br/>facet_adventurousness_significant<br/>
      facet_artistic_interests_significant<br/>
      facet_emotionality_significant<br/>facet_imagination_significant<br/>
      facet_intellect_significant<br/>facet_liberalism_significant
    </td>
  </tr>
  <tr>
    <td>
      Besoins - Signification<br/>(12 colonnes)
</td>
    <td>
      need_liberty_significant<br/>need_ideal_significant<br/>
      need_love_significant<br/>need_practicality_significant<br/>
      need_self_expression_significant<br/>need_stability_significant<br/>
      need_structure_significant<br/>need_challenge_significant<br/>
      need_closeness_significant<br/>need_curiosity_significant<br/>
      need_excitement_significant<br/>need_harmony_significant
    </td>
  </tr>
  <tr>
    <td>
      Valeurs - Signification<br/>(5 colonnes)
</td>
    <td>
      value_conservation_significant<br/>value_hedonism_significant<br/>
      value_openness_to_change_significant<br/>
      value_self_enhancement_significant<br/>
      value_self_transcendence_significant
    </td>
  </tr>
</table>

## Préférences de consommation
{: #preferenceCSV}

Les colonnes suivantes sont présentes uniquement si vous demandez des préférences de consommation en affectant au paramètre de requête `consumption_preferences` la valeur `true`. Dans tous les cas, la colonne est une valeur double précision qui renvoie la propension de l'auteur à préférer la rubrique de consommation nommée. 

<table style="width:90%">
  <caption>Tableau 4. Colonnes CSV pour les préférences de consommation</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Groupement<br/>(nombre de colonnes)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Libellés facultatifs</th>
  </tr>
  <tr>
    <td>
      Préférences en matière d'achat<br/>Scores des catégories<br/>(12 colonnes)
</td>
    <td>
      consumption_preferences_spur_of_moment<br/>
      consumption_preferences_credit_card_payment<br/>
      consumption_preferences_influence_brand_name<br/>
      consumption_preferences_influence_utility<br/>
      consumption_preferences_online_ads<br/>
      consumption_preferences_social_media<br/>
      consumption_preferences_family_members<br/>
      consumption_preferences_clothes_quality<br/>
      consumption_preferences_clothes_style<br/>
      consumption_preferences_clothes_comfort<br/>
      consumption_preferences_automobile_ownership_cost<br/>
      consumption_preferences_automobile_safety
    </td>
  </tr>
  <tr>
    <td>
      Préférences en matière de musique<br/>Scores des catégories<br/>(9 colonnes)
    </td>
    <td>
      consumption_preferences_music_rap<br/>
      consumption_preferences_music_country<br/>
      consumption_preferences_music_r_b<br/>
      consumption_preferences_music_hip_hop<br/>
      consumption_preferences_music_live_event<br/>
      consumption_preferences_music_playing<br/>
      consumption_preferences_music_latin<br/>
      consumption_preferences_music_rock<br/>
      consumption_preferences_music_classical
    </td>
  </tr>
  <tr>
    <td>
      Préférences en matière de santé et d'activité<br/>Scores des catégories<br/>(3 colonnes)
    </td>
    <td>
      consumption_preferences_gym_membership<br/>
      consumption_preferences_outdoor<br/>
      consumption_preferences_eat_out
    </td>
  </tr>
  <tr>
    <td>
      Préférences en matière de films<br/>Scores des catégories<br/>(10 colonnes)
    </td>
    <td>
      consumption_preferences_movie_romance<br/>
      consumption_preferences_movie_adventure<br/>
      consumption_preferences_movie_horror<br/>
      consumption_preferences_movie_musical<br/>
      consumption_preferences_movie_historical<br/>
      consumption_preferences_movie_science_fiction<br/>
      consumption_preferences_movie_war<br/>
      consumption_preferences_movie_drama<br/>
      consumption_preferences_movie_action<br/>
      consumption_preferences_movie_documentary
    </td>
  </tr>
  <tr>
    <td>
      Préférences en matière de lecture<br/>Scores des catégories<br/>(5 colonnes)
</td>
    <td>
      consumption_preferences_read_frequency<br/>
      consumption_preferences_books_entertainment_magazines<br/>
      consumption_preferences_books_non_fiction<br/>
      consumption_preferences_books_financial_investing<br/>
      consumption_preferences_books_autobiographies
    </td>
  </tr>
  <tr>
    <td>
      Préférences en matière de bénévolat<br/>Scores des catégories<br/>(1 colonne)
</td>
    <td>
      consumption_preferences_volunteer
    </td>
  </tr>
  <tr>
    <td>
      Préférences en matière d'écologie<br/>Scores des catégories<br/>(1 colonne)
</td>
    <td>
      consumption_preferences_concerned_environment
    </td>
  </tr>
  <tr>
    <td>
      Préférences en matière d'esprit d'entreprise<br/>Scores des catégories<br/>(1 colonne)
</td>
    <td>
      consumption_preferences_start_business
    </td>
  </tr>
</table>
