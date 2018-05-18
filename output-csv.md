---

copyright:
  years: 2015, 2018
lastupdated: "2018-05-18"

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

# Understanding a CSV profile
{: #outputCSV}

The service returns the results of its analysis in comma-separated values (CSV) format when you specify `text/csv` with the `Accept` header of a request. CSV output provides information that is similar to the information provided by JSON output. As with JSON, the information in the CSV output depends on whether the input data is timestamped and whether you request raw scores and consumption preferences.
{: shortdesc}

CSV output, unlike JSON, is returned as a fixed number of columns. The first row of the output consists of optional column labels, which are included only if you set the `csv_headers` query parameter of the request to `true`. The second row of the output, which is always present, contains the results of the analysis.

The following sections list and briefly describe all columns of the CSV output in the exact order in which they appear in the results. The tables describe the columns by logical grouping, including the number of columns in each group and their optional labels. Other than the word count, all numeric data is returned as double values.

For more information about the meaning of the CSV columns, see [Understanding a JSON profile](/docs/services/personality-insights/output.html) and [Interpreting the numeric results](/docs/services/personality-insights/numeric.html).

## Basic characteristics and metadata
{: #basicCSV}

The following columns are always present in the CSV output for all requests.

<table>
  <caption>Table 1. CSV columns for basic characteristics and
    metadata</caption>
  <tr>
    <th style="width:25%; text-align:left; vertical-align:bottom">Grouping<br/>(Number of columns)</th>
    <th style="width:25%; text-align:left; vertical-align:bottom">Optional labels</th>
    <th style="text-align:left; vertical-align:bottom">Description</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five Agreeableness percentiles<br/>(Seven columns)
    </td>
    <td style="vertical-align:top">
      big5_agreeableness<br/>facet_altruism<br/>
      facet_cooperation<br/>facet_modesty<br/>
      facet_morality<br/>facet_sympathy<br/>
      facet_trust
    </td>
    <td style="vertical-align:top">
      Normalized percentile score for the author of the text for the
      named dimension or facet.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five Conscientiousness percentiles<br/>(Seven columns)
    </td>
    <td style="vertical-align:top">
      big5_conscientiousness<br/>facet_achievement_striving
      <br/>facet_cautiousness<br/>facet_dutifulness<br/>
      facet_orderliness<br/>facet_self_discipline<br/>
      facet_self_efficacy
    </td>
    <td style="vertical-align:top">
      Normalized percentile score for the author of the text for the
      named dimension or facet.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five Extraversion percentiles<br/>(Seven columns)
    </td>
    <td style="vertical-align:top">
      big5_extraversion<br/>facet_activity_level
      <br/>facet_assertiveness<br/>facet_cheerfulness<br/>
      facet_excitement_seeking<br/>facet_friendliness<br/>
      facet_gregariousness
    </td>
    <td style="vertical-align:top">
      Normalized percentile score for the author of the text for the
      named dimension or facet.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five Emotional range percentiles<br/>(Seven columns)
    </td>
    <td style="vertical-align:top">
      big5_neuroticism<br/>facet_anger<br/>
      facet_anxiety<br/>facet_depression<br/>
      facet_immoderation<br/>facet_self_consciousness<br/>
      facet_vulnerability
    </td>
    <td style="vertical-align:top">
      Normalized percentile score for the author of the text for the
      named dimension or facet.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five Openness percentiles<br/>(Seven columns)
    </td>
    <td style="vertical-align:top">
      big5_openness<br/>facet_adventurousness<br/>
      facet_artistic_interests<br/>facet_emotionality<br/>
      facet_imagination<br/>facet_intellect<br/>
      facet_liberalism
    </td>
    <td style="vertical-align:top">
      Normalized percentile score for the author of the text for the
      named dimension or facet.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Needs percentiles<br/>(Twelve columns)
    </td>
    <td style="vertical-align:top">
      need_liberty<br/>need_ideal<br/>
      need_love<br/>need_practicality<br/>
      need_self_expression<br/>need_stability<br/>
      need_structure<br/>need_challenge<br/>
      need_closeness<br/>need_curiosity<br/>
      need_excitement<br/>need_harmony
    </td>
    <td style="vertical-align:top">
      Normalized percentile score for the author of the text for the
      named need.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Values percentiles<br/>(Five columns)
    </td>
    <td style="vertical-align:top">
      value_conservation<br/>value_hedonism<br/>
      value_openness_to_change<br/>value_self_enhancement<br/>
      value_self_transcendence
    </td>
    <td style="vertical-align:top">
      Normalized percentile score for the author of the text for the
      named value.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Days of the week percentages<br/>(Seven columns)
    </td>
    <td style="vertical-align:top">
      behavior_sunday<br/>behavior_monday<br/>
      behavior_tuesday<br/>behavior_wednesday<br/>
      behavior_thursday<br/>behavior_friday<br/>
      behavior_saturday
    </td>
    <td style="vertical-align:top">
      <em>If the input text is timestamped,</em> the percentage of the
      input that is associated with each day of the week. Otherwise,
      all percentages are <code>0.0</code>.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Hours of the day percentages<br/>(Twenty-four columns)
    </td>
    <td style="vertical-align:top">
      behavior_0000 <em>through</em> behavior_2300
    </td>
    <td style="vertical-align:top">
      <em>If the input text is timestamped,</em> the percentage of the
      input that is associated with each hour of the day. Otherwise,
      all percentages are <code>0.0</code>.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Word count and language<br/>(Two columns)
    </td>
    <td style="vertical-align:top">
      word_count<br/>processed_language
    </td>
    <td style="vertical-align:top">
      An integer that indicates the number of words present in the input
      text, and a two-letter identifier for the language model that the
      service used to analyze the text.
    </td>
  </tr>
</table>

## Raw scores
{: #rawCSV}

The following columns are present only if you request raw scores by setting the `raw_scores` query parameter to `true`. In all cases, the column is a double value that provides the author's raw score for the dimension, facet, need, or value.

<table>
  <caption>Table 2. CSV columns for raw scores</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Grouping<br/>(Number of columns)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Optional labels</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five Agreeableness raw scores<br/>(Seven columns)
    </td>
    <td>
      big5_agreeableness_raw<br/>facet_altruism_raw<br/>
      facet_cooperation_raw<br/>facet_modesty_raw<br/>
      facet_morality_raw<br/>facet_sympathy_raw<br/>
      facet_trust_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five Conscientiousness raw scores<br/>(Seven columns)
    </td>
    <td>
      big5_conscientiousness_raw<br/>facet_achievement_striving_raw<br/>
      facet_cautiousness_raw<br/>facet_dutifulness_raw<br/>
      facet_orderliness_raw<br/>facet_self_discipline_raw<br/>
      facet_self_efficacy_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five Extraversion raw scores<br/>(Seven columns)
    </td>
    <td>
      big5_extraversion_raw<br/>facet_activity_level_raw<br/>
      facet_assertiveness_raw<br/>facet_cheerfulness_raw<br/>
      facet_excitement_seeking_raw<br/>facet_friendliness_raw<br/>
      facet_gregariousness_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five Emotional range raw scores<br/>(Seven columns)
    </td>
    <td>
      big5_neuroticism_raw<br/>facet_anger_raw<br/>
      facet_anxiety_raw<br/>facet_depression_raw<br/>
      facet_immoderation_raw<br/>facet_self_consciousness_raw<br/>
      facet_vulnerability_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five Openness raw scores<br/>(Seven columns)
    </td>
    <td>
      big5_openness_raw<br/>facet_adventurousness_raw<br/>
      facet_artistic_interests_raw<br/>facet_emotionality_raw<br/>
      facet_imagination_raw<br/>facet_intellect_raw<br/>
      facet_liberalism_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Needs raw scores<br/>(Twelve columns)
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
    <td style="vertical-align:top">
      Values raw scores<br/>(Five columns)
    </td>
    <td>
      value_conservation_raw<br/>value_hedonism_raw<br/>
      value_openness_to_change_raw<br/>value_self_enhancement_raw<br/>
      value_self_transcendence_raw
    </td>
  </tr>
</table>

## Significance
{: #significantCSV}

The following columns are always present in the CSV output for all requests. In all cases, the column is a boolean value that indicates whether the dimension, facet, need, or value is meaningful for the processed input language.

<table>
  <caption>Table 3. CSV columns for significance</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Grouping<br/>(Number of columns)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Optional labels</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five Agreeableness significance<br/>(Seven columns)
    </td>
    <td>
      big5_agreeableness_significant<br/>facet_altruism_significant<br/>
      facet_cooperation_significant<br/>facet_modesty_significant<br/>
      facet_morality_significant<br/>facet_sympathy_significant<br/>
      facet_trust_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five Conscientiousness significance<br/>(Seven columns)
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
    <td style="vertical-align:top">
      Big Five Extraversion significance<br/>(Seven columns)
    </td>
    <td>
      big5_extraversion_significant<br/>facet_activity_level_significant<br/>
      facet_assertiveness_significant<br/>facet_cheerfulness_significant<br/>
      facet_excitement_seeking_significant<br/>
      facet_friendliness_significant<br/>facet_gregariousness_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five Emotional range significance<br/>(Seven columns)
    </td>
    <td>
      big5_neuroticism_significant<br/>facet_anger_significant<br/>
      facet_anxiety_significant<br/>facet_depression_significant<br/>
      facet_immoderation_significant<br/>
      facet_self_consciousness_significant<br/>facet_vulnerability_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five Openness significance<br/>(Seven columns)
    </td>
    <td>
      big5_openness_significant<br/>facet_adventurousness_significant<br/>
      facet_artistic_interests_significant<br/>
      facet_emotionality_significant<br/>facet_imagination_significant<br/>
      facet_intellect_significant<br/>facet_liberalism_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Needs raw significance<br/>(Twelve columns)
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
    <td style="vertical-align:top">
      Values significance<br/>(Five columns)
    </td>
    <td>
      value_conservation_significant<br/>value_hedonism_significant<br/>
      value_openness_to_change_significant<br/>
      value_self_enhancement_significant<br/>
      value_self_transcendence_significant
    </td>
  </tr>
</table>

## Consumption preferences
{: #preferenceCSV}

The following columns are present only if you request consumption preferences by setting the `consumption_preferences` query parameter to `true`. In all cases, the column is a double value that reports the likelihood that the author prefers the named consumption topic.

<table style="width:90%">
  <caption>Table 4. CSV columns for consumption preferences</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Grouping<br/>(Number of columns)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Optional labels</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Purchasing preferences category scores<br/>(Twelve columns)
    </td>
    <td style="vertical-align:top">
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
    <td style="vertical-align:top">
      Music preferences category scores<br/>(Nine columns)
    </td>
    <td style="vertical-align:top">
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
    <td style="vertical-align:top">
      Health and activity preferences category scores<br/>(Three columns)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_gym_membership<br/>
      consumption_preferences_outdoor<br/>
      consumption_preferences_eat_out
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Movie preferences category scores<br/>(Ten columns)
    </td>
    <td style="vertical-align:top">
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
    <td style="vertical-align:top">
      Reading preferences category scores<br/>(Five columns)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_read_frequency<br/>
      consumption_preferences_books_entertainment_magazines<br/>
      consumption_preferences_books_non_fiction<br/>
      consumption_preferences_books_financial_investing<br/>
      consumption_preferences_books_autobiographies
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Volunteering preferences category scores<br/>(One column)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_volunteer
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Environmental concern preferences category scores<br/>(One column)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_concerned_environment
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Entrepreneurship preferences category scores<br/>(One column)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_start_business
    </td>
  </tr>
</table>
