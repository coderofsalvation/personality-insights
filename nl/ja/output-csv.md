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

# CSV プロファイルの解釈
{: #outputCSV}

要求の `Accept` ヘッダーで `text/csv` を指定すると、本サービスは分析結果を CSV (コンマ区切り値) 形式で返します。 CSV 出力が提供する情報は、JSON 出力で提供される情報に似ています。 JSON の場合と同様に、CSV 出力に含まれる情報は、入力データにタイム・スタンプが付いているかどうかと、ロー・スコアおよび消費嗜好性を要求しているかどうかに基づきます。
{: shortdesc}

CSV 出力は JSON とは異なり、固定数の列として返されます。出力の先頭行は、要求の `csv_headers` 照会パラメーターが `true` に設定されている場合のみ組み込まれる、オプションの列ラベルからなります。 出力の第 2 行は常に存在し、分析結果を含みます。

以降のセクションでは、CSV 出力のすべての列を結果に含まれるとおりの順序でリストし、簡単に説明します。 以降の表では、列を論理的なグループに分けて説明し、各グループ内の列の数と、オプションの列ラベルも示します。 単語数以外は、すべての数値データは倍精度の値として返されます。

CSV 列の意味について詳しくは、『[JSON プロファイルの解釈](/docs/services/personality-insights?topic=personality-insights-output)』および『[数値結果の解釈](/docs/services/personality-insights?topic=personality-insights-numeric)』を参照してください。

## 基本的な特性およびメタデータ
{: #basicCSV}

以下の列は、すべての要求の CSV 出力に常に含まれます。

<table>
  <caption>表 1. 基本的な特性およびメタデータの CSV 列</caption>
  <tr>
    <th style="width:25%; text-align:left; vertical-align:bottom">グループ<br/>(列の数)</th>
    <th style="width:25%; text-align:left; vertical-align:bottom">オプションのラベル</th>
    <th style="text-align:left; vertical-align:bottom">説明</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      ビッグ・ファイブの協調性の百分位数<br/>(7 列)
    </td>
    <td style="vertical-align:top">
      big5_agreeableness<br/>facet_altruism<br/>
      facet_cooperation<br/>facet_modesty<br/>
      facet_morality<br/>facet_sympathy<br/>
      facet_trust
    </td>
    <td style="vertical-align:top">
      指定されたディメンションまたはファセットに関する、テキスト筆者の正規化済み百分位数スコア。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      ビッグ・ファイブの誠実性の百分位数<br/>(7 列)
    </td>
    <td style="vertical-align:top">
      big5_conscientiousness<br/>facet_achievement_striving
      <br/>facet_cautiousness<br/>facet_dutifulness<br/>
      facet_orderliness<br/>facet_self_discipline<br/>
      facet_self_efficacy
    </td>
    <td style="vertical-align:top">
      指定されたディメンションまたはファセットに関する、テキスト筆者の正規化済み百分位数スコア。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      ビッグ・ファイブの外向性の百分位数<br/>(7 列)
    </td>
    <td style="vertical-align:top">
      big5_extraversion<br/>facet_activity_level
      <br/>facet_assertiveness<br/>facet_cheerfulness<br/>
      facet_excitement_seeking<br/>facet_friendliness<br/>
      facet_gregariousness
    </td>
    <td style="vertical-align:top">
      指定されたディメンションまたはファセットに関する、テキスト筆者の正規化済み百分位数スコア。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      ビッグ・ファイブの情緒不安定性の百分位数<br/>(7 列)
    </td>
    <td style="vertical-align:top">
      big5_neuroticism<br/>facet_anger<br/>
      facet_anxiety<br/>facet_depression<br/>
      facet_immoderation<br/>facet_self_consciousness<br/>
      facet_vulnerability
    </td>
    <td style="vertical-align:top">
      指定されたディメンションまたはファセットに関する、テキスト筆者の正規化済み百分位数スコア。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      ビッグ・ファイブの開放性の百分位数<br/>(7 列)
    </td>
    <td style="vertical-align:top">
      big5_openness<br/>facet_adventurousness<br/>
      facet_artistic_interests<br/>facet_emotionality<br/>
      facet_imagination<br/>facet_intellect<br/>
      facet_liberalism
    </td>
    <td style="vertical-align:top">
      指定されたディメンションまたはファセットに関する、テキスト筆者の正規化済み百分位数スコア。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      ニーズの百分位数<br/>(12 列)
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
      指定されたニーズに関する、テキスト筆者の正規化済み百分位数スコア。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      価値の百分位数<br/>(5 列)
    </td>
    <td style="vertical-align:top">
      value_conservation<br/>value_hedonism<br/>
      value_openness_to_change<br/>value_self_enhancement<br/>
      value_self_transcendence
    </td>
    <td style="vertical-align:top">
      指定された価値に関する、テキスト筆者の正規化済み百分位数スコア。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      曜日のパーセンテージ<br/>(7 列)
    </td>
    <td style="vertical-align:top">
      behavior_sunday<br/>behavior_monday<br/>
      behavior_tuesday<br/>behavior_wednesday<br/>
      behavior_thursday<br/>behavior_friday<br/>
      behavior_saturday
    </td>
    <td style="vertical-align:top">
      <em>入力テキストがタイム・スタンプ付きの場合</em>、各曜日に関連付けられている入力のパーセンテージ。 タイム・スタンプが付いていない場合、すべてのパーセンテージは <code>0.0</code> になります。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      時刻のパーセンテージ<br/>(24 列)
    </td>
    <td style="vertical-align:top">
      behavior_0000 <em>から</em> behavior_2300
    </td>
    <td style="vertical-align:top">
      <em>入力テキストがタイム・スタンプ付きの場合</em>、1 日のうちの各時刻に関連付けられている入力のパーセンテージ。 タイム・スタンプが付いていない場合、すべてのパーセンテージは <code>0.0</code> になります。
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      単語数および言語<br/>(2 列)
    </td>
    <td style="vertical-align:top">
      word_count<br/>processed_language
    </td>
    <td style="vertical-align:top">
      入力テキスト内にある単語の数を示す整数と、本サービスがテキストを分析するために使用した言語モデルを表す 2 文字の識別子。
    </td>
  </tr>
</table>

## ロー・スコア
{: #rawCSV}

以下の列は、`raw_scores` 照会パラメーターを `true` に設定することでロー・スコアを要求した場合にのみ存在します。 すべてのケースで、列は、ディメンション、ファセット、ニーズ、または価値に関する筆者のロー・スコアを提供する倍精度値です。

<table>
  <caption>表 2. ロー・スコアの CSV 列</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">グループ<br/>(列の数)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">オプションのラベル</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      ビッグ・ファイブの協調性のロー・スコア<br/>(7 列)
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
      ビッグ・ファイブの誠実性のロー・スコア<br/>(7 列)
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
      ビッグ・ファイブの外向性のロー・スコア<br/>(7 列)
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
      ビッグ・ファイブの情緒不安定性のロー・スコア<br/>(7 列)
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
      ビッグ・ファイブの開放性のロー・スコア<br/>(7 列)
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
      ニーズのロー・スコア<br/>(12 列)
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
      価値のロー・スコア<br/>(5 列)
    </td>
    <td>
      value_conservation_raw<br/>value_hedonism_raw<br/>
      value_openness_to_change_raw<br/>value_self_enhancement_raw<br/>
      value_self_transcendence_raw
    </td>
  </tr>
</table>

## 有意性
{: #significantCSV}

以下の列は、すべての要求の CSV 出力に常に含まれます。 すべてのケースで、列は、ディメンション、ファセット、ニーズ、または価値が、処理される入力言語で意味があるかどうかを示すブール値です。

<table>
  <caption>表 3. 有意性の CSV 列</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">グループ<br/>(列の数)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">オプションのラベル</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      ビッグ・ファイブの協調性の有意性<br/>(7 列)
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
      ビッグ・ファイブの誠実性の有意性<br/>(7 列)
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
      ビッグ・ファイブの外向性の有意性<br/>(7 列)
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
      ビッグ・ファイブの情緒不安定性の有意性<br/>(7 列)
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
      ビッグ・ファイブの開放性の有意性<br/>(7 列)
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
      ニーズのロー有意性<br/>(12 列)
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
      価値の有意性<br/>(5 列)
    </td>
    <td>
      value_conservation_significant<br/>value_hedonism_significant<br/>
      value_openness_to_change_significant<br/>
      value_self_enhancement_significant<br/>
      value_self_transcendence_significant
    </td>
  </tr>
</table>

## 消費嗜好性
{: #preferenceCSV}

以下の列は、`consumption_preferences` 照会パラメーターを `true` に設定することで消費嗜好性を要求した場合にのみ存在します。 すべてのケースで、列は、指定された消費トピックを筆者が好む可能性を報告する倍精度値です。

<table style="width:90%">
  <caption>表 4. 消費嗜好性の CSV 列</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">グループ<br/>(列の数)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">オプションのラベル</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      購入の嗜好性カテゴリーのスコア<br/>(12 列)
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
      音楽の嗜好性カテゴリーのスコア<br/>(9 列)
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
      健康および活動の嗜好性カテゴリーのスコア<br/>(3 列)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_gym_membership<br/>
      consumption_preferences_outdoor<br/>
      consumption_preferences_eat_out
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      映画の嗜好性カテゴリーのスコア<br/>(10 列)
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
      読書の嗜好性カテゴリーのスコア<br/>(5 列)
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
      ボランティア活動の嗜好性カテゴリーのスコア<br/>(1 列)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_volunteer
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      環境への関心の嗜好性カテゴリーのスコア<br/>(1 列)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_concerned_environment
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      起業家精神の嗜好性カテゴリーのスコア<br/>(1 列)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_start_business
    </td>
  </tr>
</table>
