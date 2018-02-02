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

# Préférences de consommation
{: #preferences}

Le service {{site.data.keyword.personalityinsightsshort}} déduit les caractéristiques de personnalité d'un auteur pour trois modèles : Big Five, Besoins et Valeurs. En fonction des résultats qu'il obtient pour ces modèles, le service peuvent également produire des préférences de consommation pour l'auteur du texte d'entrée. Affectez au paramètre de requête `consumption_preferences` la valeur `true` pour une demande de préférences de consommation.
{: shortdesc}

Regroupées dans huit catégories de haut niveau, plus de 40 préférences de consommation indiquent la propension de l'auteur à préférer différents produits et services et différentes activités. Par exemple, le service peut identifier les aspirations de l'auteur lorsqu'il effectue des achats de vêtements (le confort par rapport à la mode) et d'automobiles (le coût par rapport à la sécurité) ; ses penchants pour différents styles de musique, différents types de films et différentes lectures et ses attitudes en faveur de l'environnement et du bénévolat, entre autres. 

Les entreprises utilisent les modèles de personnalité du service pour mieux comprendre leurs clients et pour concevoir et développer des campagnes, des produits et des services plus personnalisés et ciblés. Les préférences de consommation permettent de prendre des mesures plus facilement en fonction des résultats du service. Les entreprises peuvent facilement obtenir une liste de préférences associées aux caractéristiques dominantes d'un individu et y répondre de manière appropriée. Pour plus d'informations sur les applications possibles des préférences de consommation, voir [Cas d'utilisation](/docs/services/personality-insights/usecases.html) et [Le service en action](/docs/services/personality-insights/applied.html).

Les sections suivantes répertorient et décrivent les préférences de consommation que le service peut renvoyer. Pour plus d'informations sur l'interprétation des préférences numériques, voir [Scores des préférences de consommation](/docs/services/personality-insights/numeric.html#scores). Pour plus d'informations sur la manière dont {{site.data.keyword.IBM_notm}} a développé les préférences, voir [L'aspect scientifique du service](/docs/services/personality-insights/science.html).

## Préférences en matière d'achat
{: #shopping}

Les préférences en matière d'achat indiquent l'intérêt de l'auteur pour différents types d'achats, dans quelle mesure les habitudes d'achat de l'auteur sont influencées par différentes sources externes, et les habitudes de dépenses de l'auteur. L'ID et le nom de catégorie sont `consumption_preferences_shopping` et `Purchasing Preferences`. La catégorie comprend 12 préférences. 

<table>
  <caption>Tableau 1. Préférences en matière d'achats</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de préférence de consommation
</th>
    <th style="width:30%; text-align:left">
Nom
</th>
    <th style="text-align:center">
      Scores
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_ownership_cost</code>
    </td>
    <td style="text-align:left">
Susceptible d'être sensible au coût de possession lors de l'achat d'automobiles
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_safety</code>
    </td>
    <td style="text-align:left">
Susceptible de préférer la sécurité lors de l'achat d'automobiles
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_quality</code>
    </td>
    <td style="text-align:left">
Susceptible de préférer la qualité lors de l'achat de vêtements
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_style</code>
    </td>
    <td style="text-align:left">
Susceptible de préférer le style lors de l'achat de vêtements
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_comfort</code>
    </td>
    <td style="text-align:left">
Susceptible de préférer le confort lors de l'achat de vêtements
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_brand_name</code>
    </td>
    <td style="text-align:left">
Susceptible d'être influencé par la marque lors de l'achat de produits
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_utility</code>
    </td>
    <td style="text-align:left">
Susceptible d'être influencé par l'utilité du produit lors de l'achat de produits
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_online_ads</code>
    </td>
    <td style="text-align:left">
Susceptible d'être influencé par la publicité en ligne lors de l'achat de produits
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_social_media</code>
    </td>
    <td style="text-align:left">
Susceptible d'être influencé par les médias sociaux lors de l'achat de produits
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_family_members</code>
    </td>
    <td style="text-align:left">
Susceptible d'être influencé par sa famille lors de l'achat de produits
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_spur_of_moment</code>
    </td>
    <td style="text-align:left">
Susceptible d'acheter sur un coup de tête
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_credit_card_payment</code>
    </td>
    <td style="text-align:left">
Susceptible de préférer utiliser des cartes de crédit pour ses achats
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
</table>

## Préférences en matière de films
{: #movie}

Les préférences en matière de films indiquent l'intérêt de l'auteur pour différents types de films. L'ID et le nom de catégorie sont `consumption_preferences_movie` et `Movie Preferences`. La catégorie comprend 10 préférences. 

<table>
  <caption>Tableau 2. Préférences en matière de films</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de préférence de consommation
</th>
    <th style="width:30%; text-align:left">
Nom
</th>
    <th style="text-align:center">
      Scores
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_romance</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer les films romantiques
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_adventure</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer les films d'aventure
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_horror</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer les films d'horreur
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_musical</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer les comédies musicales
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_historical</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer les films historiques
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_science_fiction</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer les films de science-fiction
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_war</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer les films de guerre
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_drama</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer les films dramatiques
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_action</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer les films d'action
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_documentary</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer les films documentaires
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
</table>

## Préférences en matière de musique
{: #music}

Les préférences en matière de musique indiquent l'intérêt de l'auteur pour différents types de musique et s'il aime jouer de la musique. L'ID et le nom de catégorie sont `consumption_preferences_music` et `Music Preferences`. La catégorie comprend neuf préférences. 

<table>
  <caption>Tableau 3. Préférences en matière de musique</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de préférence de consommation
</th>
    <th style="width:30%; text-align:left">
Nom
</th>
    <th style="text-align:center">
      Scores
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rap</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer le rap
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_country</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer la country
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_r_b</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer le R & B
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_hip_hop</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer le hip hop
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_live_event</code>
    </td>
    <td style="text-align:left">
Susceptible d'assister à des concerts
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_playing</code>
    </td>
    <td style="text-align:left">
Susceptible d'avoir essayé de jouer d'un instrument
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_latin</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer la musique latine
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rock</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer le rock
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_classical</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer le classique
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
</table>

## Préférences en matière de lecture et d'apprentissage
{: #reading}

Les préférences en matière de lecture et d'apprentissage indiquent la propension de l'auteur à lire, sa motivation pour la lecture, et les types de contenu qu'il aime lire. L'ID et le nom de catégorie sont `consumption_preferences_reading` et `Reading Preferences`. La catégorie comprend cinq préférences. 

<table>
  <caption>Tableau 4. Préférences en matière de lecture et d'apprentissage</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de préférence de consommation
</th>
    <th style="width:30%; text-align:left">
Nom
</th>
    <th style="text-align:center">
      Scores
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_read_frequency</code>
    </td>
    <td style="text-align:left">
Susceptible de lire souvent
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_entertainment_magazines</code>
    </td>
    <td style="text-align:left">
Susceptible de lire des magasines de divertissement
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_non_fiction</code>
    </td>
    <td style="text-align:left">
Susceptible de lire des essais
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_financial_investing</code>
    </td>
    <td style="text-align:left">
Susceptible de lire des livres sur les investissements financiers
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_autobiographies</code>
    </td>
    <td style="text-align:left">
Susceptible de lire des livres autobiographiques
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
</table>

## Préférences en matière de santé et d'activité
{: #health}

Les préférences en matière de santé et d'activité indiquent l'intérêt de l'auteur pour la nourriture saine et l'activité physique. L'ID et le nom de catégorie sont `consumption_preferences_health_and_activity` et `Reading & Activity Preferences`. La catégorie comprend trois préférences. 

<table>
  <caption>Tableau 5. Préférences en matière de santé et d'activité</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de préférence de consommation
</th>
    <th style="width:30%; text-align:left">
Nom
</th>
    <th style="text-align:center">
      Scores
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_eat_out</code>
    </td>
    <td style="text-align:left">
Susceptible de manger souvent à l'extérieur
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_gym_membership</code>
    </td>
    <td style="text-align:left">
Susceptible d'être abonné à une salle de sport
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_outdoor</code>
    </td>
    <td style="text-align:left">
Susceptible d'aimer les activités à l'extérieur
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
</table>

## Préférences en matière d'esprit d'entreprise
{: #entrepreneur}

Les préférences en matière d'esprit d'entreprise indiquent l'intérêt de l'auteur pour la création d'entreprise. L'ID et le nom de catégorie sont`consumption_preferences_entrepreneurship` et `Entrepreneurship Preferences`. La catégorie comprend une préférence. 

<table>
  <caption>Tableau 6. Préférences en matière d'esprit d'entreprise</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de préférence de consommation
</th>
    <th style="width:30%; text-align:left">
Nom
</th>
    <th style="text-align:center">
      Scores
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_start_business</code>
    </td>
    <td style="text-align:left">
Susceptible d'envisager de créer une entreprise dans les années à venir
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
</table>

## Préférences en matière d'écologie
{: #environment}

Les préférences en matière d'écologie indiquent l'intérêt de l'auteur pour l'environnement. L'ID et de nom de catégorie sont `consumption_preferences_environmental_concern` et `Environmental Concern Preferences`. La catégorie comprend une préférence. 

<table>
  <caption>Tableau 7. Préférences en matière d'écologie</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de préférence de consommation
</th>
    <th style="width:30%; text-align:left">
Nom
</th>
    <th style="text-align:center">
      Scores
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_concerned_environment</code>
    </td>
    <td style="text-align:left">
Susceptible de s'inquiéter pour l'environnement
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>0.5</code> (neutre)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
</table>

## Préférences en matière de bénévolat
{: #volunteer}

Les préférences en matière de bénévolat indiquent l'intérêt de l'auteur pour le bénévolat pour des causes sociales. L'ID et le nom de catégorie sont`consumption_preferences_volunteering` et `Volunteering Preferences`. La catégorie comprend une préférence. 

<table>
  <caption>Tableau 8. Préférences en matière de bénévolat</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de préférence de consommation
</th>
    <th style="width:30%; text-align:left">
Nom
</th>
    <th style="text-align:center">
      Scores
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_volunteer</code>
    </td>
    <td style="text-align:left">
Susceptible de se porter volontaire pour des causes sociales
</td>
    <td style="text-align:center">
      <code>0.0</code> (peu probable)<br/>
      <code>1.0</code> (probable)
</td>
  </tr>
</table>
