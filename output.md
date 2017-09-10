---

copyright:
  years: 2015, 2017
lastupdated: "2017-09-10"

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

# Understanding a profile
{: #output}

When you use the `profile` method to analyze content, you can select the format of the profile that the service sends in response: JSON or Comma-Separated Values (CSV). Both formats return the same requested data based on the parameters of the call.
{: shortdesc}

The following sections describe the content of a response in both formats. All example output is produced by the sample JSON file <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a> that is used in the [Getting started tutorial](/docs/services/personality-insights/getting-started.html). For more information about calling the `profile` method, see [Requesting a profile](/docs/services/personality-insights/input.html). For complete details about the method, see the [API reference ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

## JSON response content
{: #outputJSON}

The service returns the results of its analysis as a JSON `Profile` object by default or when you specify `application/json` with the `Accept` header of a request. The scope of the JSON output depends on the parameters you specified with the request and on whether the input text represents timestamped data, such as the text associated with a Twitter feed. The `Profile` object has the following fields:

-   `word_count` (integer) provides the number of words from the input content that were used to generate the profile. This can be less than the number of words in the input if the request submitted a large amount of content. If the number of words fails to meet a minimum threshold, the output also includes a `word_count_message` field that provides additional guidance.
-   `processed language` (string) describes the language model that the service used to process the input: `ar` (Arabic), `en` (English), `es` (Spanish), or `ja` (Japanese).
-   `personality` is a recursive array of `Trait` objects that describes the Big Five dimensions and facets inferred from the input text.
-   `needs` is an array of `Trait` objects that describes the Needs inferred from the input text.
-   `values` is an array of `Trait` objects that describes the Values inferred from the input text.
-   `behavior` is an array of `Behavior` objects that describes the distribution of the content over the days of the week and the hours of the day. The service returns the field only for JSON input that is timestamped.
-   `consumption_preferences` is an array of `ConsumptionPreferencesCategory` objects that provides results for each category of consumption preferences. The elements of the array provide information for the individual preferences of that category. The service returns the field only if the `consumption_preferences` query parameter of the request is set to `true`.
-   `warnings` is an array of `Warning` objects that provides messages associated with the input text. The array is empty if the input generated no warnings.

### Example response
{: #JSONExample}

The following example output shows the high-level structure of a `Profile` object. The output always includes the `personality`, `needs`, and `values` fields. If the input is timestamped JSON, the response includes the `behavior` field. And if the request also asks for consumption preferences, the response includes the `consumption_preferences` field. In this example, the input generates no warnings.

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

## Personality characteristics output
{: #traitJSON}

The `Profile` object always includes `personality`, `needs`, and `values` fields for all types of input. Each of these fields contains an array of `Trait` objects that describes the personality characteristics for the attributes of that type of characteristic. For Needs and Values characteristics, the array has a single level that describes the characteristics. For Big Five characteristics, a top-level array describes the dimensions, and second-level arrays describe the facets of each dimension.

-   `trait_id` (string) is the unique ID of the characteristic to which the results pertain:
    -   `big5_characteristic` for Big Five personality dimensions
    -   `facet_characteristic` for Big Five personality facets
    -   `need_characteristic` for Needs
    -   `value_characteristic` for Values
-   `name` (string) is the user-visible name of the characteristic.
-   `category` (string) is the category of the characteristic:
    -   `personality` for Big Five personality characteristics
    -   `needs` for Needs
    -   `values` for Values
-   `percentile` (double) is the normalized percentile score for the characteristic. For more information, see [Percentiles for personality characteristics](#percentiles).
-   `raw_score` (double) is the raw score for the characteristic. The field is returned only if you request raw scores by setting the `raw_scores` query parameter to `true`. For more information, see [Raw scores for personality characteristics](#rawScores).
-   `children` is an array of `Trait` objects that provides more detailed results for the facets of each Big Five dimension as inferred from the input text. The array is returned only for Big Five dimensions.

### Example response
{: #traitExample}

The following example output shows snippets of the output for the Big Five, Needs, and Values characteristics. As described, only the Big Five characteristics have an array of `children` for their respective facets.

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
      "children": [
        {
          "trait_id": "facet_adventurousness",
          "name": "Adventurousness",
          "category": "personality",
          "percentile": 0.89755869047319,
          "raw_score": 0.54990704031219
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
      "children": [
        {
          "trait_id": "facet_achievement_striving",
          "name": "Achievement striving",
          "category": "personality",
          "percentile": 0.84613299226628,
          "raw_score": 0.74240118454888
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
      "children": [
        {
          "trait_id": "facet_activity_level",
          "name": "Activity level",
          "category": "personality",
          "percentile": 0.88220584913965,
          "raw_score": 0.60106995926143
        },
      ]
    },
    {
      "trait_id": "big5_agreeableness",
      "name": "Agreeableness",
      "category": "personality",
      "percentile": 0.94786124793821,
      "raw_score": 0.80677815631809,
      "children": [
        {
          "trait_id": "facet_altruism",
          "name": "Altruism",
          "category": "personality",
          "percentile": 0.99241983824205,
          "raw_score": 0.79028406290747
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
      "children": [
        {
          "trait_id": "facet_anger",
          "name": "Fiery",
          "category": "personality",
          "percentile": 0.17640022058508,
          "raw_score": 0.48490315691802
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
      "raw_score": 0.75196348037675
    },
    . . .
  ],
  "values": [
    {
      "trait_id": "value_conservation",
      "name": "Conservation",
      "category": "values",
      "percentile": 0.89268222856139,
      "raw_score": 0.72135308187423
    },
    . . .
  ],
  . . .
}
```
{: codeblock}

## Behavioral output
{: #behaviorJSON}

If the input to the service is JSON that has timestamps for the individual content items, the `Profile` object includes a `behavior` field. The field includes a `Behavior` object for each day of the week and hour of the day.

-   `trait_id` (string) is the unique ID of the characteristic to which the results pertain:
    -   `behavior_day` for days of the week (for example, `behavior_sunday`).
    -   `behavior_hour` for hours of the day (for example, `behavior_0000`).
-   `name` (string) is the user-visible name of the characteristic.
-   `category` (string) is the category of the characteristic, which is always `behavior`.
-   `percentage` (double) is the percentage of content items that occurred during that day of the week or hour of the day. For more information, see [Percentages for behavioral characteristics](#percentages).

### Example response
{: #behaviorExample}

The following output shows snippets of the behavioral output for temporal characteristics.

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

## Consumption preferences output
{: #preferenceJSON}

If the `consumption_preferences` query parameter is set to `true`, the `Profile` object includes a `consumption_preferences` field. The field includes a `ConsumptionPreferencesCategory` object for each category of preferences.

-   `consumption_preference_category_id` (string) is the unique ID of the consumption preferences category to which the results pertain in the form `consumption_preferences_category`.
-   `name` (string) is the user-visible name of the consumption preferences category.
-   `consumption_preferences` is an array of `ConsumptionPreferences` objects that provides results for the individual preferences of the category.

Each individual preference for a category is described via a `ConsumptionPreferences` object. Some categories have only a single preference, others have many more.

-   `consumption_preference_id` (string) is the unique ID of the consumption preference to which the results pertain in the form `consumption_preferences_preference`.
-   `name` (string) is the user-visible name of the consumption preference.
-   `score` (double) is a score that indicates the author's likelihood of preferring the item. For more information, see [Scores for consumption preferences](#scores).

### Example response
{: #preferenceExample}

The following output shows snippets of the output for consumption preferences.

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
          "name": "Prefers automobile ownership cost",
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
          "name": "Prefers to eat out",
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
          "name": "Have volunteering experience",
          "score": 0
        }
      ]
    }
  ],
  . . .
}
```
{: codeblock}

## CSV response content
{: #outputCSV}

The service returns the results of its analysis in CSV format when you specify `text/csv` with the `Accept` header of the request. CSV output provides information that is similar to the information provided by JSON output. As with JSON, the information in the CSV output depends on whether the input represents timestamped data and whether the user requests raw scores and consumption preferences.

Unlike JSON, however, CSV output is returned as a fixed number of columns. The first row of the output consists of optional column labels, which are included only if you set the `csv_headers` query parameter of the request to `true`. The second row of the output, which is always present, contains the results of the analysis.

The following sections list and briefly describe all columns of the CSV output in the exact order in which they appear in the results. To make the information easier to follow, the tables describe the columns by logical grouping, including the number of columns in each group and their optional labels. Other than the word count, all numeric data are returned as double values.

### Basic characteristics and metadata
{: #basicCSV}

The following columns are always present in the CSV output for all requests.

<table>
  <caption>Table 1. CSV columns for basic characteristics and
    metadata</caption>
  <tr>
    <th style="width:25%; text-align:left; vertical-align:bottom">Grouping<br/>(number of columns)</th>
    <th style="width:25%; text-align:left; vertical-align:bottom">Optional labels</th>
    <th style="text-align:left; vertical-align:bottom">Description</th>
  </tr>
  <tr>
    <td>
      Big Five Agreeableness<br/>percentiles<br/>(7 columns)
    </td>
    <td>
      big5_agreeableness<br/>facet_altruism<br/>
      facet_cooperation<br/>facet_modesty<br/>
      facet_morality<br/>facet_sympathy<br/>
      facet_trust
    </td>
    <td>
      Normalized percentile score for the author of the text with respect
      to the named dimension or facet.
    </td>
  </tr>
  <tr>
    <td>
      Big Five Conscientiousness<br/>percentiles<br/>(7 columns)
    </td>
    <td>
      big5_conscientiousness<br/>facet_achievement_striving
      <br/>facet_cautiousness<br/>facet_dutifulness<br/>
      facet_orderliness<br/>facet_self_discipline<br/>
      facet_self_efficacy
    </td>
    <td>
      Normalized percentile score for the author of the text with respect
      to the named dimension or facet.
    </td>
  </tr>
  <tr>
    <td>
      Big Five Extraversion<br/>percentiles<br/>(7 columns)
    </td>
    <td>
      big5_extraversion<br/>facet_activity_level
      <br/>facet_assertiveness<br/>facet_cheerfulness<br/>
      facet_excitement_seeking<br/>facet_friendliness<br/>
      facet_gregariousness
    </td>
    <td>
      Normalized percentile score for the author of the text with respect
      to the named dimension or facet.
    </td>
  </tr>
  <tr>
    <td>
      Big Five Emotional range<br/>percentiles<br/>(7 columns)
    </td>
    <td>
      big5_neuroticism<br/>facet_anger<br/>
      facet_anxiety<br/>facet_depression<br/>
      facet_immoderation<br/>facet_self_consciousness<br/>
      facet_vulnerability
    </td>
    <td>
      Normalized percentile score for the author of the text with respect
      to the named dimension or facet.
    </td>
  </tr>
  <tr>
    <td>
      Big Five Openness<br/>percentiles<br/>(7 columns)
    </td>
    <td>
      big5_openness<br/>facet_adventurousness<br/>
      facet_artistic_interests<br/>facet_emotionality<br/>
      facet_imagination<br/>facet_intellect<br/>
      facet_liberalism
    </td>
    <td>
      Normalized percentile score for the author of the text with respect
      to the named dimension or facet.
    </td>
  </tr>
  <tr>
    <td>
      Needs percentiles<br/>(12 columns)
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
      Normalized percentile score for the author of the text with respect
      to the named need.
    </td>
  </tr>
  <tr>
    <td>
      Values percentiles<br/>(5 columns)
    </td>
    <td>
      value_conservation<br/>value_hedonism<br/>
      value_openness_to_change<br/>value_self_enhancement<br/>
      value_self_transcendence
    </td>
    <td>
      Normalized percentile score for the author of the text with respect
      to the named value.
    </td>
  </tr>
  <tr>
    <td>
      Days of the week<br/>percentages<br/>(7 columns)
    </td>
    <td>
      behavior_sunday<br/>behavior_monday<br/>
      behavior_tuesday<br/>behavior_wednesday<br/>
      behavior_thursday<br/>behavior_friday<br/>
      behavior_saturday
    </td>
    <td>
      If the input text is timestamped, the percentage of the input
      associated with each day of the week; if the input is not
      timestamped, the percentages are all <code>0.0</code>.
    </td>
  </tr>
  <tr>
    <td>
      Hours of the day<br/>percentages<br/>(24 columns)
    </td>
    <td>
      behavior_0000<br/><em>through</em><br/>behavior_2300
    </td>
    <td>
      If the input text is timestamped, the percentage of the input
      associated with each hour of the day; if the input is not
      timestamped, the percentages are all <code>0.0</code>.
    </td>
  </tr>
  <tr>
    <td>
      Word count and<br/>language<br/>(2 columns)
    </td>
    <td>
      word_count<br/>processed_language
    </td>
    <td>
      An integer that indicates the number of words present in the input
      text, and a two-letter identifier for the language model that the
      service used to analyze the text.
    </td>
  </tr>
</table>

### Raw scores
{: #rawCSV}

The following columns are present only if you request raw scores by setting the `raw_scores` query parameter to `true`.

<table>
  <caption>Table 2. CSV columns for raw scores</caption>
  <tr>
    <th style="width:25%; text-align:left; vertical-align:bottom">Grouping<br/>(number of columns)</th>
    <th style="width:25%; text-align:left; vertical-align:bottom">Optional labels</th>
    <th style="text-align:left; vertical-align:bottom">Description</th>
  </tr>
  <tr>
    <td>
      Big Five Agreeableness<br/>raw scores<br/>(7 columns)
    </td>
    <td>
      big5_agreeableness_raw<br/>facet_altruism_raw<br/>
      facet_cooperation_raw<br/>facet_modesty_raw<br/>
      facet_morality_raw<br/>facet_sympathy_raw<br/>
      facet_trust_raw
    </td>
    <td>
      Raw score for the author of the text with respect to the named
      dimension or facet.
    </td>
  </tr>
  <tr>
    <td>
      Big Five Conscientiousness<br/>raw scores<br/>(7 columns)
    </td>
    <td>
      big5_conscientiousness_raw<br/>facet_achievement_striving_raw<br/>
      facet_cautiousness_raw<br/>facet_dutifulness_raw<br/>
      facet_orderliness_raw<br/>facet_self_discipline_raw<br/>
      facet_self_efficacy_raw
    </td>
    <td>
      Raw score for the author of the text with respect to the named
      dimension or facet.
    </td>
  </tr>
  <tr>
    <td>
      Big Five Extraversion<br/>raw scores<br/>(7 columns)
    </td>
    <td>
      big5_extraversion_raw<br/>facet_activity_level_raw<br/>
      facet_assertiveness_raw<br/>facet_cheerfulness_raw<br/>
      facet_excitement_seeking_raw<br/>facet_friendliness_raw<br/>
      facet_gregariousness_raw
    </td>
    <td>
      Raw score for the author of the text with respect to the named
      dimension or facet.
    </td>
  </tr>
  <tr>
    <td>
      Big Five Emotional range<br/>raw scores<br/>(7 columns)
    </td>
    <td>
      big5_neuroticism_raw<br/>facet_anger_raw<br/>
      facet_anxiety_raw<br/>facet_depression_raw<br/>
      facet_immoderation_raw<br/>facet_self_consciousness_raw<br/>
      facet_vulnerability_raw
    </td>
    <td>
      Raw score for the author of the text with respect to the named
      dimension or facet.
    </td>
  </tr>
  <tr>
    <td>
      Big Five Openness<br/>raw scores<br/>(7 columns)
    </td>
    <td>
      big5_openness_raw<br/>facet_adventurousness_raw<br/>
      facet_artistic_interests_raw<br/>facet_emotionality_raw<br/>
      facet_imagination_raw<br/>facet_intellect_raw<br/>
      facet_liberalism_raw
    </td>
    <td>
      Raw score for the author of the text with respect to the dimension
      or facet.
    </td>
  </tr>
  <tr>
    <td>
      Needs raw scores<br/>(12 columns)
    </td>
    <td>
      need_liberty_raw<br/>need_ideal_raw<br/>
      need_love_raw<br/>need_practicality_raw<br/>
      need_self_expression_raw<br/>need_stability_raw<br/>
      need_structure_raw<br/>need_challenge_raw<br/>
      need_closeness_raw<br/>need_curiosity_raw<br/>
      need_excitement_raw<br/>need_harmony_raw
    </td>
    <td>
      Raw score for the author of the text with respect to the named need.
    </td>
  </tr>
  <tr>
    <td>
      Values raw scores<br/>(5 columns)
    </td>
    <td>
      value_conservation_raw<br/>value_hedonism_raw<br/>
      value_openness_to_change_raw<br/>value_self_enhancement_raw<br/>
      value_self_transcendence_raw
    </td>
    <td>
      Raw score for the author of the text with respect to the named value.
    </td>
  </tr>
</table>

### Consumption preferences
{: #preferenceCSV}

The following columns are present only if you request consumption preferences by setting the `consumption_preferences` query parameter to `true`. In all cases, the column reports the likelihood that the author of the text prefers the named consumption topic.

<table style="width:90%">
  <caption>Table 3. CSV columns for consumption preferences</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Grouping<br/>(number of columns)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Optional labels</th>
  </tr>
  <tr>
    <td>
      Purchasing preferences<br/>category scores<br/>(12 columns)
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
      Music preferences<br/>category scores<br/>(9 columns)
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
      Health and activity preferences<br/>category scores<br/>(3 columns)
    </td>
    <td>
      consumption_preferences_gym_membership<br/>
      consumption_preferences_outdoor<br/>
      consumption_preferences_eat_out
    </td>
  </tr>
  <tr>
    <td>
      Movie preferences<br/>category scores<br/>(10 columns)
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
      Reading preferences<br/>category scores<br/>(5 columns)
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
      Volunteering preferences<br/>category scores<br/>(1 column)
    </td>
    <td>
      consumption_preferences_volunteer
    </td>
  </tr>
  <tr>
    <td>
      Environmental concern preferences<br/>category scores<br/>(1 column)
    </td>
    <td>
      consumption_preferences_concerned_environment
    </td>
  </tr>
  <tr>
    <td>
      Entrepreneurship preferences<br/>category scores<br/>(1 column)
    </td>
    <td>
      consumption_preferences_start_business
    </td>
  </tr>
</table>

## Interpreting the numeric results
{: #numeric}

The {{site.data.keyword.personalityinsightsshort}} service returns numeric results for each of the personality and behavioral characteristics and for each consumption preference. The values differ in the information they provide, as described in the following sections.

> **Note:** For Arabic input, the service is unable to produce meaningful percentiles and raw scores for a number of personality characteristics. For more information, see [Limitations for Arabic input](#arabic).

### Percentiles for personality characteristics
{: #percentiles}

For each request, the service always reports a normalized score as a `percentile` for each Big Five, Values, and Needs personality characteristic. Normalized scores represent a percentile ranking for each characteristic based on qualities inferred from the input text. The service computes normalized scores by comparing the raw score for the author's text with results from a sample population. The service reports each percentile as a double in the range of 0 to 1.

For example, a percentile of `0.64980796071382` for the personality characteristic `big5_extraversion` indicates that the author of the text scored in the 65th percentile for that characteristic. The author's writing exhibits the tendency to an extent that is greater than 64 percent and less than 34 percent of the sample population. The precision of the percentile depends on the number of words that were submitted as input with the request; for more information, see [Guidelines for providing sufficient input](/docs/services/personality-insights/user-overview.html#overviewGuidelines).

> **Note:** No mathematical relationship exists between the percentiles reported for Big Five dimensions and facets. The service calculates the normalized percentile for each dimension and facet independently based on correlations between survey participants' scores for that dimension or facet and the words they use. Therefore, even though facets provide finer-grained descriptions of dimensions, adding the scores for the six facets of a dimension does not necessarily yield the percentile for that dimension. The same is true of raw scores.

### Raw scores for personality characteristics
{: #rawScores}

If you specify `true` for the `raw_scores` query parameter of the request, the service reports a `raw_score` for each personality characteristic. Raw scores represent the score for the specific characteristic based solely on the author's text and the model for that characteristic, without comparing the results to a sample population. Raw scores can be interpreted as the scores the author would receive from taking a personality test.

The service reports each raw score as a double in the range of 0 to 1. A higher score generally indicates a greater likelihood that the author has that characteristic. However, raw scores must be considered in aggregate: The range of values in practice might be much smaller than 0 to 1, so an individual score must be considered in the context of the overall scores and their range. But in general, a raw score, for instance, of `0.56817738781166` for the personality characteristic `big5_extraversion` indicates that the author would likely have achieved this score on a personality test. Compare this raw score with the normalized percentile reported for the same author and characteristic in the previous section.

The service makes raw scores available for users who want to apply a custom normalization for a specific scenario or who do not require a comparison with a sample population. Users who want to know how the author's characteristics compare with a large sample population can use the normalized scores. Users who want to derive their own normalized percentile scores from the raw data can compare the raw scores against a different sample population and apply a different approach to normalization.

To normalize a raw score to a percentile for a specific characteristic, compare the raw score with a sample population for which the mean and the standard deviation for the characteristic are known. For example, {{site.data.keyword.IBM_notm}} conducted studies to gather data from a large sample population of Twitter users. {{site.data.keyword.IBM_notm}} computed the users' scores for each of the personality characteristics and then established the mean and standard deviation for each characteristic. To compute the percentile score for a raw score inferred from its analysis of input text, the service uses the mean and standard deviation derived from its sample Twitter population for that characteristic.

### Percentages for behavioral characteristics
{: #percentages}

If you submit JSON data whose content items have timestamps, the service reports a `percentage` for each behavioral characteristic. Behavioral characteristics identify the temporal distribution of the input. The percentage indicates how many of the content items occurred during each day of the week and time of day. For example, a percentage of `0.4561049445005` for the behavioral characteristic `behavior_0000` means that roughly 46 percent of the content items were created between the hours of midnight and 1:00 a.m.

### Scores for consumption preferences
{: #scores}

If you specify `true` for the `consumption_preferences` query parameter of the request, the service reports consumption preferences that include a `score` for each preference. The service derives the score from the personality characteristics that it infers from the input text. The score is a double that indicates how likely the author of the text is to prefer the item. It is an indication of preference, not a normalized percentage.

For some preferences, the score is one of the following three values:

-   `0.0`: The author is very unlikely to prefer the item. For some preferences, you can interpret the value as meaning that the author has a very low level of interest.
-   `0.5`: The author is neutral with respect to the item. For some preferences, the value can mean that the author has a medium level of interest.
-   `1.0`: The author is very likely to prefer the item. For some preferences, the value indicates a high level of interest.

For other preferences, the score represents a binary value. The author of the input text is either unlikely (`0.0`) or likely (`1.0`) to have an interest in the item, or the author has either a low or high level of interest. In some cases, the score can represent a simple yes or no response (for instance, is the author likely to have experience volunteering for social causes).

For a complete list of all preferences by category and the range of their results, see [Consumption preferences](/docs/services/personality-insights/preferences.html).

### Limitations for Arabic input
{: #arabic}

For Arabic input, the service's models are unable to produce meaningful results for a subset of personality characteristics. For the following characteristics, normalized percentile scores are always `0.5` and raw scores are always the mean of the original distribution. Do not rely on the results for these characteristics as part of the personality profile of the author.

-   **Big Five dimensions:** *Emotional range*
-   **Big Five facets:**
    -   **Agreeableness**: *Altruism*, *Cooperation*, *Modesty*, and *Trust*
    -   **Conscientiousness**: *Achievement striving* and *Dutifulness*
    -   **Extraversion**: *Cheerfulness* and *Friendliness* (*Outgoing*)
    -   **Emotional range**: *Anger* (*Fiery*), *Prone to worry*, *Immoderation*, and *Self-consciousness*
    -   **Openness**: *Adventurousness*, *Imagination*, and *Intellect*
-   **Needs:** *Ideal*, *Liberty*, *Love*, *Practicality*, and *Structure*
-   **Values:** *Self-enhancement*
