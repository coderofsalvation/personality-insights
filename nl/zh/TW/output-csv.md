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

# 瞭解 CSV 設定檔
{: #outputCSV}

當您以要求的 `Accept` 標頭來指定 `text/csv` 時，服務會以逗點區隔值 (CSV) 格式傳回其分析的結果。CSV 輸出提供的資訊與 JSON 輸出所提供的資訊類似。如同 JSON 一樣，CSV 輸出中的資訊取決於輸入資料是否為時間戳記，以及您是否要求原始評分和消費喜好。
{: shortdesc}

與 JSON 不同的是，CSV 輸出是以固定數目的直欄傳回。輸出的第一列是由選用的直欄標籤組成，只有在您將要求的 `csv_headers` 查詢參數設為 `true` 時，才會包括這些直欄標籤。輸出的第二列一律會呈現，其中包含分析的結果。

下列各節會列出並簡短說明 CSV 輸出的所有直欄，並依其出現在結果中的精確順序排列。這些表格會依邏輯分組來說明直欄，包括每一個群組中的直欄數及其選用標籤。除了字數之外，所有數值資料都會以倍精準數值傳回。

如需 CSV 直欄意義的相關資訊，請參閱[瞭解 JSON 設定檔](/docs/services/personality-insights?topic=personality-insights-output)和[解譯數值結果](/docs/services/personality-insights?topic=personality-insights-numeric)。

## 基本特質和 meta 資料
{: #basicCSV}

針對所有要求，下列直欄一律都是以 CSV 輸出呈現。

<table>
  <caption>表 1. 基本特質和 meta 資料的 CSV 直欄</caption>
  <tr>
    <th style="width:25%; text-align:left; vertical-align:bottom">分組<br/>（欄數）</th>
    <th style="width:25%; text-align:left; vertical-align:bottom">選用標籤</th>
    <th style="text-align:left; vertical-align:bottom">說明</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      五大性格特質隨和百分位數<br/>（7 個直欄）
    </td>
    <td style="vertical-align:top">
      big5_agreeableness<br/>facet_altruism<br/>
      facet_cooperation<br/>facet_modesty<br/>
      facet_morality<br/>facet_sympathy<br/>
      facet_trust
    </td>
    <td style="vertical-align:top">
      針對已指名維度或面向之文字作者的正規化百分位數評分。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      五大性格特質責任感百分位數<br/>（7 個直欄）
    </td>
    <td style="vertical-align:top">
      big5_conscientiousness<br/>facet_achievement_striving
      <br/>facet_cautiousness<br/>facet_dutifulness<br/>
      facet_orderliness<br/>facet_self_discipline<br/>
      facet_self_efficacy
    </td>
    <td style="vertical-align:top">
      針對已指名維度或面向之文字作者的正規化百分位數評分。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      五大性格特質外向百分位數<br/>（7 個直欄）
    </td>
    <td style="vertical-align:top">
      big5_extraversion<br/>facet_activity_level
      <br/>facet_assertiveness<br/>facet_cheerfulness<br/>
      facet_excitement_seeking<br/>facet_friendliness<br/>
      facet_gregariousness
    </td>
    <td style="vertical-align:top">
      針對已指名維度或面向之文字作者的正規化百分位數評分。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      五大性格特質情緒表達幅度百分位數<br/>（7 個直欄）
    </td>
    <td style="vertical-align:top">
      big5_neuroticism<br/>facet_anger<br/>
      facet_anxiety<br/>facet_depression<br/>
      facet_immoderation<br/>facet_self_consciousness<br/>
      facet_vulnerability
    </td>
    <td style="vertical-align:top">
      針對已指名維度或面向之文字作者的正規化百分位數評分。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      五大性格特質開放性百分位數<br/>（7 個直欄）
    </td>
    <td style="vertical-align:top">
      big5_openness<br/>facet_adventurousness<br/>
      facet_artistic_interests<br/>facet_emotionality<br/>
      facet_imagination<br/>facet_intellect<br/>
      facet_liberalism
    </td>
    <td style="vertical-align:top">
      針對已指名維度或面向之文字作者的正規化百分位數評分。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      需求百分位數<br/>（12 個直欄）
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
      針對已指名需求之文字作者的正規化百分位數評分。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      價值觀百分位數<br/>（5 個直欄）
    </td>
    <td style="vertical-align:top">
      value_conservation<br/>value_hedonism<br/>
      value_openness_to_change<br/>value_self_enhancement<br/>
      value_self_transcendence
    </td>
    <td style="vertical-align:top">
      針對已指名價值觀之文字作者的正規化百分位數評分。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      星期幾百分比<br/>（7 個直欄）
    </td>
    <td style="vertical-align:top">
      behavior_sunday<br/>behavior_monday<br/>
      behavior_tuesday<br/>behavior_wednesday<br/>
      behavior_thursday<br/>behavior_friday<br/>
      behavior_saturday
    </td>
    <td style="vertical-align:top">
      <em>如果輸入文字有時間戳記，</em>則為與星期幾相關聯的輸入百分比。否則百分比全部為 <code>0.0</code>。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      幾點百分比<br/>（24 個直欄）
    </td>
    <td style="vertical-align:top">
      behavior_0000 <em>到</em> behavior_2300
    </td>
    <td style="vertical-align:top">
      <em>如果輸入文字有時間戳記，</em>則為與幾點相關聯的輸入百分比。否則百分比全部為 <code>0.0</code>。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      字數和語言<br/>（2 個直欄）
    </td>
    <td style="vertical-align:top">
      word_count<br/>processed_language
    </td>
    <td style="vertical-align:top">
      一個整數，指出輸入文字中的字數；以及一個雙字母 ID，代表服務用來分析文字的語言模型。
    </td>
  </tr>
</table>

## 原始評分
{: #rawCSV}

只有在您將 `raw_scores` 查詢參數設為 `true` 以要求原始評分時，才會呈現下列直欄。無論如何，直欄都是倍精準數值，針對維度、面向、需求或價值觀，提供作者的原始評分。

<table>
  <caption>表 2. 原始評分的 CSV 直欄</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">分組<br/>（欄數）</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">選用標籤</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      五大性格特質隨和原始評分<br/>（7 個直欄）
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
      五大性格特質責任感原始評分<br/>（7 個直欄）
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
      五大性格特質外向原始評分<br/>（7 個直欄）
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
      五大性格特質情緒表達幅度原始評分<br/>（7 個直欄）
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
      五大性格特質開放性原始評分<br/>（7 個直欄）
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
      需求原始評分<br/>（12 個直欄）
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
      價值觀原始評分<br/>（5 個直欄）
    </td>
    <td>
      value_conservation_raw<br/>value_hedonism_raw<br/>
      value_openness_to_change_raw<br/>value_self_enhancement_raw<br/>
      value_self_transcendence_raw
    </td>
  </tr>
</table>

## 重要性
{: #significantCSV}

針對所有要求，下列直欄一律都是以 CSV 輸出呈現。無論如何，直欄都是布林值，指出維度、面向、需求或價值觀對所處理的輸入語言是否有意義。

<table>
  <caption>表 3. 重要性的 CSV 直欄</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">分組<br/>（欄數）</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">選用標籤</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      五大性格特質隨和重要性<br/>（7 個直欄）
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
      五大性格特質責任感重要性<br/>（7 個直欄）
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
      五大性格特質外向重要性<br/>（7 個直欄）
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
      五大性格特質情緒表達幅度重要性<br/>（7 個直欄）
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
      五大性格特質開放性重要性<br/>（7 個直欄）
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
      需求原始重要性<br/>（12 個直欄）
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
      價值觀重要性<br/>（5 個直欄）
    </td>
    <td>
      value_conservation_significant<br/>value_hedonism_significant<br/>
      value_openness_to_change_significant<br/>
      value_self_enhancement_significant<br/>
      value_self_transcendence_significant
    </td>
  </tr>
</table>

## 消費喜好
{: #preferenceCSV}

只有在您將 `consumption_preferences` 查詢參數設為 `true` 以要求消費喜好時，才會呈現下列直欄。無論如何，直欄都是倍精準數值，報告作者喜好已指名消費主題的可能性。

<table style="width:90%">
  <caption>表 4. 消費喜好的 CSV 直欄</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">分組<br/>（欄數）</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">選用標籤</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      採購喜好種類評分<br/>（12 個直欄）
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
      音樂喜好種類評分<br/>（9 個直欄）
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
      健康和活動喜好種類評分<br/>（3 個直欄）
    </td>
    <td style="vertical-align:top">
      consumption_preferences_gym_membership<br/>
      consumption_preferences_outdoor<br/>
      consumption_preferences_eat_out
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      電影喜好種類評分<br/>（10 個直欄）
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
      閱讀喜好種類評分<br/>（5 個直欄）
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
      志願服務喜好種類評分<br/>（1 個直欄）
    </td>
    <td style="vertical-align:top">
      consumption_preferences_volunteer
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      環境關懷喜好種類評分<br/>（1 個直欄）
    </td>
    <td style="vertical-align:top">
      consumption_preferences_concerned_environment
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      企業家精神喜好種類評分<br/>（1 個直欄）
    </td>
    <td style="vertical-align:top">
      consumption_preferences_start_business
    </td>
  </tr>
</table>
