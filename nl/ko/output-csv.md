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

# CSV 프로파일 이해하기
{: #outputCSV}

요청의 `Accept` 헤더에 `text/csv`를 지정하는 경우, 서비스는 CSV(Comma-Separated Values)
형식으로 분석의 결과를 리턴합니다. CSV 결과는 JSON 결과에서 제공하는 정보와 유사한 정보를 제공합니다. JSON에서와 마찬가지로,
CSV 결과의 정보는 입력 데이터에 시간소인이 있는지 및 사용자가 원 점수와 소비 성향을 요청하는지 여부에 따라 다릅니다.
{: shortdesc}

JSON과는 달리, CSV 결과는 고정된 열 수로서 리턴됩니다. 결과의 첫 번째 행은 선택적 열 레이블로 구성되며,
이는 요청의 `csv_headers` 조회 매개변수가 `true`로 설정되는 경우에만 포함됩니다. 
항상 존재하는 결과의 두 번째 행에는 분석 결과가 포함되어 있습니다.

다음 절에서는 결과에 나타나는 순서와 동일하게 CSV 결과의 모든 열을 나열하고 간략하게 설명합니다. 
표에서는 각 그룹의 열 수와 선택적 레이블을 포함하여 논리 그룹화별로 열을 설명합니다. 단어 수 외의 모든 숫자 데이터는 double 값으로 리턴됩니다. 

CSV 열의 의미에 대한 자세한 정보는 [JSON 프로파일
이해하기](/docs/services/personality-insights?topic=personality-insights-output) 및 [숫자 결과 해석](/docs/services/personality-insights?topic=personality-insights-numeric)을 참조하십시오.

## 기본 특성 및 메타데이터
{: #basicCSV}

다음 열이 항상 모든 요청에 대한 CSV 결과에 존재합니다.

<table>
  <caption>표 1. 기본 특성 및 메타데이터에 대한 CSV 열</caption>
  <tr>
    <th style="width:25%; text-align:left; vertical-align:bottom">그룹화<br/>(열 수)</th>
    <th style="width:25%; text-align:left; vertical-align:bottom">선택적 레이블</th>
    <th style="text-align:left; vertical-align:bottom">설명</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      빅 파이브 친화성 백분위수<br/>(7개 열)
    </td>
    <td style="vertical-align:top">
      big5_agreeableness<br/>facet_altruism<br/>
      facet_cooperation<br/>facet_modesty<br/>
      facet_morality<br/>facet_sympathy<br/>
      facet_trust
    </td>
    <td style="vertical-align:top">
      이름 지정된 특질 또는 성향에 대해 텍스트 작성자의 정규화된 백분위수 점수.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      빅 파이브 성실성 백분위수<br/>(7개 열)
    </td>
    <td style="vertical-align:top">
      big5_conscientiousness<br/>facet_achievement_striving
      <br/>facet_cautiousness<br/>facet_dutifulness<br/>
      facet_orderliness<br/>facet_self_discipline<br/>
      facet_self_efficacy
    </td>
    <td style="vertical-align:top">
      이름 지정된 특질 또는 성향에 대해 텍스트 작성자의 정규화된 백분위수 점수.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      빅 파이브 외향성 백분위수<br/>(7개 열)
    </td>
    <td style="vertical-align:top">
      big5_extraversion<br/>facet_activity_level
      <br/>facet_assertiveness<br/>facet_cheerfulness<br/>
      facet_excitement_seeking<br/>facet_friendliness<br/>
      facet_gregariousness
    </td>
    <td style="vertical-align:top">
      이름 지정된 특질 또는 성향에 대해 텍스트 작성자의 정규화된 백분위수 점수.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      빅 파이브 감정 범위 백분위수<br/>(7개 열)
    </td>
    <td style="vertical-align:top">
      big5_neuroticism<br/>facet_anger<br/>
      facet_anxiety<br/>facet_depression<br/>
      facet_immoderation<br/>facet_self_consciousness<br/>
      facet_vulnerability
    </td>
    <td style="vertical-align:top">
      이름 지정된 특질 또는 성향에 대해 텍스트 작성자의 정규화된 백분위수 점수.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      빅 파이브 개방성 백분위수<br/>(7개 열)
    </td>
    <td style="vertical-align:top">
      big5_openness<br/>facet_adventurousness<br/>
      facet_artistic_interests<br/>facet_emotionality<br/>
      facet_imagination<br/>facet_intellect<br/>
      facet_liberalism
    </td>
    <td style="vertical-align:top">
      이름 지정된 특질 또는 성향에 대해 텍스트 작성자의 정규화된 백분위수 점수.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      욕구 백분위수<br/>(12개 열)
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
      이름 지정된 욕구에 대해 텍스트 작성자의 정규화된 백분위수 점수.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      가치 백분위수<br/>(5개 열)
    </td>
    <td style="vertical-align:top">
      value_conservation<br/>value_hedonism<br/>
      value_openness_to_change<br/>value_self_enhancement<br/>
      value_self_transcendence
    </td>
    <td style="vertical-align:top">
      이름 지정된 가치에 대해 텍스트 작성자의 정규화된 백분위수 점수.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      요일 백분율<br/>(7개 열)
    </td>
    <td style="vertical-align:top">
      behavior_sunday<br/>behavior_monday<br/>
      behavior_tuesday<br/>behavior_wednesday<br/>
      behavior_thursday<br/>behavior_friday<br/>
      behavior_saturday
    </td>
    <td style="vertical-align:top">
      <em>입력 텍스트에 시간소인이 있는 경우,</em> 각 요일과 연관된 입력의 백분율. 그렇지 않으면 모든 백분율은 <code>0.0</code>입니다.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      일중 시간 백분율<br/>(24개 열)
    </td>
    <td style="vertical-align:top">
      behavior_0000 <em>through</em> behavior_2300
    </td>
    <td style="vertical-align:top">
      <em>입력 텍스트에 시간소인이 있는 경우,</em> 각 일 중 시간과 연관된 입력의 백분율. 그렇지 않으면 모든 백분율은 <code>0.0</code>입니다.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      단어 개수 및 언어<br/>(2개 열)
    </td>
    <td style="vertical-align:top">
      word_count<br/>processed_language
    </td>
    <td style="vertical-align:top">
      입력 텍스트에 존재하는 단어의 수를 표시하는 정수이며,
      텍스트 분석을 위해 서비스가 사용한 언어 모델의 두 문자 ID입니다.
    </td>
  </tr>
</table>

## 원 점수
{: #rawCSV}

다음 열은 `raw_scores` 조회 매개변수를 `true`로 설정하여 원 점수를 요청하는 경우에만 존재합니다. 모든 경우, 열은 특질, 성향, 욕구 또는 가치에 대한 작성자의 원 점수를 제공하는 double 값입니다.

<table>
  <caption>표 2. 원 점수의 CSV 열</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">그룹화<br/>(열 수)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">선택적 레이블</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      빅 파이브 친화성 원 점수<br/>(7개 열)
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
      빅 파이브 성실성 원 점수<br/>(7개 열)
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
      빅 파이브 외향성 원 점수<br/>(7개 열)
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
      빅 파이브 감정 범위 원 점수<br/>(7개 열)
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
      빅 파이브 개방성 원 점수<br/>(7개 열)
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
      욕구 원 점수<br/>(12개 열)
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
      가치 원 점수<br/>(5개 열)
    </td>
    <td>
      value_conservation_raw<br/>value_hedonism_raw<br/>
      value_openness_to_change_raw<br/>value_self_enhancement_raw<br/>
      value_self_transcendence_raw
    </td>
  </tr>
</table>

## 중요도
{: #significantCSV}

다음 열이 항상 모든 요청에 대한 CSV 결과에 존재합니다. 
모든 경우, 열은 특질, 성향, 욕구 또는 가치가 처리된 입력 언어에 대해 의미가 있는지 여부를 표시하는 부울 값입니다.

<table>
  <caption>표 3. 중요도의 CSV 열</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">그룹화<br/>(열 수)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">선택적 레이블</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      빅 파이브 친화성 중요도<br/>(7개 열)
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
      빅 파이브 성실성 중요도<br/>(7개 열)
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
      빅 파이브 외향성 중요도<br/>(7개 열)
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
      빅 파이브 감정 범위 중요도<br/>(7개 열)
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
      빅 파이브 개방성 중요도<br/>(7개 열)
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
      욕구 원 중요도<br/>(12개 열)
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
      가치 중요성<br/>(5개 열)
    </td>
    <td>
      value_conservation_significant<br/>value_hedonism_significant<br/>
      value_openness_to_change_significant<br/>
      value_self_enhancement_significant<br/>
      value_self_transcendence_significant
    </td>
  </tr>
</table>

## 소비 성향
{: #preferenceCSV}

다음 열은 `consumption_preferences` 조회 매개변수를 `true`로 설정하여 소비 성향을
요청하는 경우에만 존재합니다. 모든 경우, 열은 작성자가 이름 지정된 소비 주제를 선호할 가능성을 보고하는 double 값입니다.

<table style="width:90%">
  <caption>표 4. 소비 성향의 CSV 열</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">그룹화<br/>(열 수)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">선택적 레이블</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      구매 성향 범주 점수<br/>(12개 열)
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
      음악 취향 범주 점수<br/>(9개 열)
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
      건강 및 활동 성향 범주 점수<br/>(3개 열)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_gym_membership<br/>
      consumption_preferences_outdoor<br/>
      consumption_preferences_eat_out
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      영화 취향 범주 점수<br/>(10개 열)
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
      독서 취향 범주 점수<br/>(5개 열)
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
      자원 봉사 성향 범주 점수<br/>(1개 열)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_volunteer
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      환경 관심도 성향 범주 점수<br/>(1개 열)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_concerned_environment
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      기업가 정신 성향 범주 점수<br/>(1개 열)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_start_business
    </td>
  </tr>
</table>
