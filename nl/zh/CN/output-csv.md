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

# 了解 CSV 概要文件
{: #outputCSV}

为请求的 `Accept` 头指定 `text/csv` 时，服务会以逗号分隔值 (CSV) 格式返回其分析的结果。CSV 输出提供的信息类似于 JSON 输出提供的信息。与 JSON 一样，CSV 输出中的信息也取决于输入是否表示带时间戳记的数据以及用户是否请求原始评分和消费偏好。
{: shortdesc}

但是，与 JSON 不同的是，CSV 输出将作为固定列数返回。输出的第一行由可选的列标签组成，仅当将请求的 `csv_headers` 查询参数设置为 `true` 时，才会包含这些标签。输出的第二行（始终存在）包含分析的结果。

以下各部分完全按结果中显示的顺序列出 CSV 输出的所有列，并简要描述这些列。这些表按逻辑分组来描述列，包括每个组中的列数以及列的可选标签。除了字数外，所有数字数据都作为双精度值返回。

有关 CSV 列的含义的更多信息，请参阅[了解 JSON 概要文件](/docs/services/personality-insights/output.html)和[解读数字结果](/docs/services/personality-insights/numeric.html)。

## 基本特征和元数据
{: #basicCSV}

以下各列始终显示在所有请求的 CSV 输出中。

<table>
  <caption>表 1. 基本特征和元数据的 CSV 列</caption>
  <tr>
    <th style="width:25%; text-align:left; vertical-align:bottom">分组<br/>（列数）</th>
    <th style="width:25%; text-align:left; vertical-align:bottom">可选标签</th>
    <th style="text-align:left; vertical-align:bottom">描述</th>
  </tr>
  <tr>
    <td>
      大五类人格 - 随和性<br/>百分位数<br/>（7 列）
    </td>
    <td>
      big5_agreeableness<br/>facet_altruism<br/>
      facet_cooperation<br/>facet_modesty<br/>
      facet_morality<br/>facet_sympathy<br/>
      facet_trust
    </td>
    <td>
      文本作者在指定维度或构面上的规范化百分位数得分。
    </td>
  </tr>
  <tr>
    <td>
      大五类人格 - 尽责性<br/>百分位数<br/>（7 列）
    </td>
    <td>
      big5_conscientiousness<br/>facet_achievement_striving
      <br/>facet_cautiousness<br/>facet_dutifulness<br/>
      facet_orderliness<br/>facet_self_discipline<br/>
      facet_self_efficacy
    </td>
    <td>
      文本作者在指定维度或构面上的规范化百分位数得分。
    </td>
  </tr>
  <tr>
    <td>
      大五类人格 - 外倾性<br/>百分位数<br/>（7 列）
    </td>
    <td>
      big5_extraversion<br/>facet_activity_level
      <br/>facet_assertiveness<br/>facet_cheerfulness<br/>
      facet_excitement_seeking<br/>facet_friendliness<br/>
      facet_gregariousness
    </td>
    <td>
      文本作者在指定维度或构面上的规范化百分位数得分。
    </td>
  </tr>
  <tr>
    <td>
      大五类人格 - 情绪程度<br/>百分位数<br/>（7 列）
    </td>
    <td>
      big5_neuroticism<br/>facet_anger<br/>
      facet_anxiety<br/>facet_depression<br/>
      facet_immoderation<br/>facet_self_consciousness<br/>
      facet_vulnerability
    </td>
    <td>
      文本作者在指定维度或构面上的规范化百分位数得分。
    </td>
  </tr>
  <tr>
    <td>
      大五类人格 - 开放性<br/>百分位数<br/>（7 列）
    </td>
    <td>
      big5_openness<br/>facet_adventurousness<br/>
      facet_artistic_interests<br/>facet_emotionality<br/>
      facet_imagination<br/>facet_intellect<br/>
      facet_liberalism
    </td>
    <td>
      文本作者在指定维度或构面上的规范化百分位数得分。
    </td>
  </tr>
  <tr>
    <td>
      需求百分位数<br/>（12 列）
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
      文本作者在指定需求上的规范化百分位数得分。
    </td>
  </tr>
  <tr>
    <td>
      价值观百分位数<br/>（5 列）
    </td>
    <td>
      value_conservation<br/>value_hedonism<br/>
      value_openness_to_change<br/>value_self_enhancement<br/>
      value_self_transcendence
    </td>
    <td>
      文本作者在指定价值观上的规范化百分位数得分。
    </td>
  </tr>
  <tr>
    <td>
      一周的各天<br/>百分比<br/>（7 列）
    </td>
    <td>
      behavior_sunday<br/>behavior_monday<br/>
      behavior_tuesday<br/>behavior_wednesday<br/>
      behavior_thursday<br/>behavior_friday<br/>
      behavior_saturday
    </td>
    <td>
      如果输入文本带时间戳记，那么为与一周的每天关联的输入的百分比；如果输入不带时间戳记，那么百分比均为 <code>0.0</code>。
    </td>
  </tr>
  <tr>
    <td>
      一天的各小时<br/>百分比<br/>（24 列）
    </td>
    <td>
      behavior_0000<br/><em>到</em><br/>behavior_2300
    </td>
    <td>
      如果输入文本带时间戳记，那么为与一天的每个小时关联的输入的百分比；如果输入不带时间戳记，那么百分比均为 <code>0.0</code>。
    </td>
  </tr>
  <tr>
    <td>
      字数和<br/>语言<br/>（2 列）
    </td>
    <td>
      word_count<br/>processed_language
    </td>
    <td>
      用于指示输入文本中所提供字数的整数，以及服务用于分析文本的语言模型的双字母标识。
    </td>
  </tr>
</table>

## 原始评分
{: #rawCSV}

仅当通过将 `raw_scores` 查询参数设置为 `true` 来请求原始评分时，才会提供以下各列。在所有情况下，列都为双精度值，用于提供作者的在相应维度、构面、需求或价值观上的原始评分。

<table>
  <caption>表 2. 原始评分的 CSV 列</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">分组<br/>（列数）</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">可选标签</th>
  </tr>
  <tr>
    <td>
      大五类人格 - 随和性<br/>原始评分<br/>（7 列）
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
      大五类人格 - 尽责性<br/>原始评分<br/>（7 列）
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
      大五类人格 - 外倾性<br/>原始评分<br/>（7 列）
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
      大五类人格 - 情绪程度<br/>原始评分<br/>（7 列）
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
      大五类人格 - 开放性<br/>原始评分<br/>（7 列）
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
      需求原始评分<br/>（12 列）
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
      价值观原始评分<br/>（5 列）
    </td>
    <td>
      value_conservation_raw<br/>value_hedonism_raw<br/>
      value_openness_to_change_raw<br/>value_self_enhancement_raw<br/>
      value_self_transcendence_raw
    </td>
  </tr>
</table>

## 意义
{: #significantCSV}

以下各列始终显示在所有请求的 CSV 输出中。在所有情况下，列都为布尔值，用于指示相应维度、构面、需求或价值观对于所处理的输入语言是否有意义。

<table>
  <caption>表 3. 意义的 CSV 列</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">分组<br/>（列数）</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">可选标签</th>
  </tr>
  <tr>
    <td>
      大五类人格 - 随和性<br/>意义<br/>（7 列）
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
      大五类人格 - 尽责性<br/>意义<br/>（7 列）
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
      大五类人格 - 外倾性<br/>意义<br/>（7 列）
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
      大五类人格 - 情绪程度<br/>意义<br/>（7 列）
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
      大五类人格 - 开放性<br/>意义<br/>（7 列）
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
      需求意义<br/>（12 列）
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
      价值观意义<br/>（5 列）
    </td>
    <td>
      value_conservation_significant<br/>value_hedonism_significant<br/>
      value_openness_to_change_significant<br/>
      value_self_enhancement_significant<br/>
      value_self_transcendence_significant
    </td>
  </tr>
</table>

## 消费偏好
{: #preferenceCSV}

仅当通过将 `consumption_preferences` 查询参数设置为 `true` 来请求消费偏好时，才会提供以下各列。在所有情况下，列都为双精度值，用于报告作者偏好指定消费主题的可能性。

<table style="width:90%">
  <caption>表 4. 消费偏好的 CSV 列</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">分组<br/>（列数）</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">可选标签</th>
  </tr>
  <tr>
    <td>
      购买偏好<br/>类别得分<br/>（12 列）
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
      音乐偏好<br/>类别得分<br/>（9 列）
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
      健康和活动偏好<br/>类别得分<br/>（3 列）
    </td>
    <td>
      consumption_preferences_gym_membership<br/>
      consumption_preferences_outdoor<br/>
      consumption_preferences_eat_out
    </td>
  </tr>
  <tr>
    <td>
      电影偏好<br/>类别得分<br/>（10 列）
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
      阅读偏好<br/>类别得分<br/>（5 列）
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
      志愿活动偏好<br/>类别得分<br/>（1 列）
    </td>
    <td>
      consumption_preferences_volunteer
    </td>
  </tr>
  <tr>
    <td>
      关注环保偏好<br/>类别得分<br/>（1 列）
    </td>
    <td>
      consumption_preferences_concerned_environment
    </td>
  </tr>
  <tr>
    <td>
      创业偏好<br/>类别得分<br/>（1 列）
    </td>
    <td>
      consumption_preferences_start_business
    </td>
  </tr>
</table>
