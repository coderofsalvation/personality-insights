---

copyright:
  years: 2015, 2017
lastupdated: "2017-08-08"

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

# Consumption preferences
{: #preferences}

The {{site.data.keyword.personalityinsightsshort}} service infers an author's personality characteristics for three models: Big Five, Needs, and Values. Based on its results for these models, the service can also produce consumption preferences for the author of the input text.
{: shortdesc}

Grouped into eight high-level categories, the more than 40 consumption preferences indicate the author's likelihood to prefer different products, services, and activities. For instance, the service can identify the author's inclinations when shopping for clothing (comfort versus fashion) and automobiles (cost versus safety); their leanings toward different genres of music, movies, and reading; and their attitudes toward the environment and volunteering, among other things.

Businesses have already been using the service's personality models to better understand their customers and to design and develop more personalized and targeted campaigns, products, and services. Consumption preferences make it even easier to take action based on the service's results. Users can now easily obtain a list of preferences that are associated with an individual's dominant characteristics and respond accordingly. For more information about possible applications of the consumption preferences, see [Use cases](/docs/services/personality-insights/usecases.html) and [The service in action](/docs/services/personality-insights/applied.html).

The following sections list and describe the consumption preferences that the service can return. For more information about interpreting the numeric preferences, see [Scores for consumption preferences](/docs/services/personality-insights/output.html#scores). For information about how {{site.data.keyword.IBM_notm}} developed the preferences, see [The science behind the service](/docs/services/personality-insights/science.html).

## Shopping preferences
{: #shopping}

Shopping preferences indicate the author's interest in different types of purchases, the extent to which the author's purchasing habits are influenced by different external sources, and the author's spending habits. The category ID and name are `consumption_preferences_shopping` and `Purchasing Preferences`. The category has 12 preferences.

<table>
  <caption>Table 1. Shopping preferences</caption>
  <tr>
    <th style="width:45%; text-align:left">
      Consumption preference ID
    </th>
    <th style="width:30%; text-align:left">
      Name
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
      Likely to be sensitive to ownership cost when buying automobiles
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_safety</code>
    </td>
    <td style="text-align:left">
      Likely to prefer safety when buying automobiles
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_quality</code>
    </td>
    <td style="text-align:left">
      Likely to prefer quality when buying clothes
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_style</code>
    </td>
    <td style="text-align:left">
      Likely to prefer style when buying clothes
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_comfort</code>
    </td>
    <td style="text-align:left">
      Likely to prefer comfort when buying clothes
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_brand_name</code>
    </td>
    <td style="text-align:left">
      Likely to be influenced by brand name when making product purchases
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_utility</code>
    </td>
    <td style="text-align:left">
      Likely to be influenced by product utility when making product
      purchases
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_online_ads</code>
    </td>
    <td style="text-align:left">
      Likely to be influenced by online ads when making product purchases
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_social_media</code>
    </td>
    <td style="text-align:left">
      Likely to be influenced by social media when making product
      purchases
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_family_members</code>
    </td>
    <td style="text-align:left">
      Likely to be influenced by family when making product purchases
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_spur_of_moment</code>
    </td>
    <td style="text-align:left">
      Likely to indulge in spur of the moment purchases
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_credit_card_payment</code>
    </td>
    <td style="text-align:left">
      Likely to prefer using credit cards for shopping
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
</table>

## Movie preferences
{: #movie}

Movie preferences indicate the author's interest in different types of movies. The category ID and name are `consumption_preferences_movie` and `Movie Preferences`. The category has 10 preferences.

<table>
  <caption>Table 2. Movie preferences</caption>
  <tr>
    <th style="width:45%; text-align:left">
      Consumption preference ID
    </th>
    <th style="width:30%; text-align:left">
      Name
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
      Likely to like romance movies
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_adventure</code>
    </td>
    <td style="text-align:left">
      Likely to like adventure movies
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_horror</code>
    </td>
    <td style="text-align:left">
      Likely to like horror movies
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_musical</code>
    </td>
    <td style="text-align:left">
      Likely to like musical movies
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_historical</code>
    </td>
    <td style="text-align:left">
      Likely to like historical movies
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_science_fiction</code>
    </td>
    <td style="text-align:left">
      Likely to like science-fiction movies
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_war</code>
    </td>
    <td style="text-align:left">
      Likely to like war movies
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_drama</code>
    </td>
    <td style="text-align:left">
      Likely to like drama movies
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_action</code>
    </td>
    <td style="text-align:left">
      Likely to like action movies
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_documentary</code>
    </td>
    <td style="text-align:left">
      Likely to like documentary movies
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
</table>

## Music preferences
{: #music}

Music preferences indicate the author's interest in different types of music and whether the author enjoys playing music. The category ID and name are `consumption_preferences_music` and `Music Preferences`. The category has nine preferences.

<table>
  <caption>Table 3. Music preferences</caption>
  <tr>
    <th style="width:45%; text-align:left">
      Consumption preference ID
    </th>
    <th style="width:30%; text-align:left">
      Name
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
      Likely to like rap music
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_country</code>
    </td>
    <td style="text-align:left">
      Likely to like country music
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_r_b</code>
    </td>
    <td style="text-align:left">
      Likely to like R&amp;B music
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_hip_hop</code>
    </td>
    <td style="text-align:left">
      Likely to like hip hop music
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_live_event</code>
    </td>
    <td style="text-align:left">
      Likely to attend live musical events
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_playing</code>
    </td>
    <td style="text-align:left">
      Likely to have experience playing music
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_latin</code>
    </td>
    <td style="text-align:left">
      Likely to like Latin music
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rock</code>
    </td>
    <td style="text-align:left">
      Likely to like rock music
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_classical</code>
    </td>
    <td style="text-align:left">
      Likely to like classical music
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
</table>

## Reading and learning preferences
{: #reading}

Reading and learning preferences indicate the author's likelihood to read, the author's motivation for reading, and the types of content the author enjoys reading. The category ID and name are `consumption_preferences_reading` and `Reading Preferences`. The category has five preferences.

<table>
  <caption>Table 4. Reading and learning preferences</caption>
  <tr>
    <th style="width:45%; text-align:left">
      Consumption preference ID
    </th>
    <th style="width:30%; text-align:left">
      Name
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
      Likely to read often
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_entertainment_magazines</code>
    </td>
    <td style="text-align:left">
      Likely to read entertainment magazines
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_non_fiction</code>
    </td>
    <td style="text-align:left">
      Likely to read non-fiction books
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_financial_investing</code>
    </td>
    <td style="text-align:left">
      Likely to read financial investment books
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_autobiographies</code>
    </td>
    <td style="text-align:left">
      Likely to read autobiographical books
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
</table>

## Health and activity preferences
{: #health}

Health and activity preferences indicate the author's interest in healthy foods and physical activity. The category ID and name are `consumption_preferences_health_and_activity` and `Health & Activity Preferences`. The category has three preferences.

<table>
  <caption>Table 5. Health and activity preferences</caption>
  <tr>
    <th style="width:45%; text-align:left">
      Consumption preference ID
    </th>
    <th style="width:30%; text-align:left">
      Name
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
      Likely to eat out frequently
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_gym_membership</code>
    </td>
    <td style="text-align:left">
      Likely to have a gym membership
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_outdoor</code>
    </td>
    <td style="text-align:left">
      Likely to like outdoor activities
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
</table>

## Entrepreneurship preferences
{: #entrepreneur}

Entrepreneurship preferences indicate the author's interest in starting a business. The category ID and name are `consumption_preferences_entrepreneurship` and `Entrepreneurship Preferences`. The category has one preference.

<table>
  <caption>Table 6. Entreprenuership preferences</caption>
  <tr>
    <th style="width:45%; text-align:left">
      Consumption preference ID
    </th>
    <th style="width:30%; text-align:left">
      Name
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
      Likely to consider starting a business in next few years
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
</table>

## Environmental concern preferences
{: #environment}

Environmental concern preferences indicate the author's interest in the environment. The category ID and name are `consumption_preferences_environmental_concern` and `Environmental Concern Preferences`. The category has one preference.

<table>
  <caption>Table 7. Environmental concern preferences</caption>
  <tr>
    <th style="width:45%; text-align:left">
      Consumption preference ID
    </th>
    <th style="width:30%; text-align:left">
      Name
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
      Likely to be concerned about the environment
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
</table>

## Volunteering preferences
{: #volunteer}

Volunteering preferences indicate the author's interest in volunteering for social causes. The category ID and name are `consumption_preferences_volunteering` and `Volunteering Preferences`. The category has one preference.

<table>
  <caption>Table 8. Volunteering preferences</caption>
  <tr>
    <th style="width:45%; text-align:left">
      Consumption preference ID
    </th>
    <th style="width:30%; text-align:left">
      Name
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
      Likely to volunteer for social causes
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unlikely)<br/>
      <code>1.0</code> (likely)
    </td>
  </tr>
</table>
