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

# 소비 성향
{: #preferences}

{{site.data.keyword.personalityinsightsshort}} 서비스는 3개 모델(빅 파이브, 욕구 및 가치)에 대해 작성자의
성격 특성을 추론합니다. 이러한 모델의 결과를 기반으로 하여, 서비스는 입력 텍스트 작성자의 소비 성향을 생성할 수도 있습니다. 
소비 성향을 가져오려면 요청에 대해 `consumption_preferences` 조회 매개변수를 `true`로 설정하십시오.
{: shortdesc}

8개의 상위 레벨 범주로 그룹화된 40개가 넘는 소비 성향은 작성자가 다양한 제품, 서비스 및 활동을 선호할 가능성을 표시합니다. 
예를 들어, 무엇보다도 서비스는 옷(착용감 대 패션)과 자동차(비용 대 안전성)를 구매할 때 작성자의 성향,
다양한 장르의 음악, 영화 및 독서에 대한 성향, 그리고 환경과 자원 봉사에 대한 이들의 태도를 식별할 수 있습니다. 

비즈니스는 서비스의 성격 모델을 사용하여 고객을 보다 잘 파악할 수 있으며 보다 개인화되고 대상화된 캠페인, 제품 및
서비스를 디자인하고 개발할 수 있습니다. 소비 성향을 이용하면 서비스의 결과에 따라 조치를 취하기가 훨씬 더 쉬워집니다. 
비즈니스는 손쉽게 개인의 두드러진 특성과 연관된 성향의 목록을 가져와서 이에 알맞게 대응할 수 있습니다. 소비 성향의 가능한
응용 분야에 대한 자세한 정보는 [유스 케이스](/docs/services/personality-insights/usecases.html) 및
[제공 중인 서비스](/docs/services/personality-insights/applied.html)를 참조하십시오. 

다음 절에서는 서비스가 리턴할 수 있는 소비 성향을 나열하고 설명합니다. 숫자 성향의 해석에 대한 자세한 정보는
[소비 성향에 대한 점수](/docs/services/personality-insights/numeric.html#scores)를 참조하십시오. 
{{site.data.keyword.IBM_notm}}이 성향을 개발한 방법에 대한 정보는
[서비스를 뒷받침하는 과학](/docs/services/personality-insights/science.html)을 참조하십시오. 

## 쇼핑 성향
{: #shopping}

쇼핑 성향은 다양한 구매 유형에서 작성자의 관심도, 작성자의 구매 습관이 다양한 외부 소스에 의해 영향을 받는
정도 및 작성자의 지출 습관을 표시합니다. 범주 ID 및 이름은 `consumption_preferences_shopping` 및
`Purchasing Preferences`입니다. 범주에는 12개의 성향이 있습니다. 

<table>
  <caption>표 1. 쇼핑 성향</caption>
  <tr>
    <th style="width:45%; text-align:left">
      소비 성향 ID
    </th>
    <th style="width:30%; text-align:left">
      이름
    </th>
    <th style="text-align:center">
      점수
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_ownership_cost</code>
    </td>
    <td style="text-align:left">
      자동차를 구매할 때 유지비에 민감할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_safety</code>
    </td>
    <td style="text-align:left">
      자동차를 구매할 때 안전성을 선호할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_quality</code>
    </td>
    <td style="text-align:left">
      옷을 구매할 때 품질을 선호할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_style</code>
    </td>
    <td style="text-align:left">
      옷을 구매할 때 스타일을 선호할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_comfort</code>
    </td>
    <td style="text-align:left">
      옷을 구매할 때 착용감을 선호할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_brand_name</code>
    </td>
    <td style="text-align:left">
      제품을 구매할 때 브랜드명의 영향을 받을 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_utility</code>
    </td>
    <td style="text-align:left">
      제품을 구매할 때 제품 유용성의 영향을 받을 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_online_ads</code>
    </td>
    <td style="text-align:left">
      제품을 구매할 때 온라인 광고의 영향을 받을 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_social_media</code>
    </td>
    <td style="text-align:left">
      제품을 구매할 때 소셜 미디어의 영향을 받을 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_family_members</code>
    </td>
    <td style="text-align:left">
      제품을 구매할 때 가족의 영향을 받을 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_spur_of_moment</code>
    </td>
    <td style="text-align:left">
      충동 구매의 유혹에 빠질 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_credit_card_payment</code>
    </td>
    <td style="text-align:left">
      쇼핑에 신용카드 사용을 선호할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
</table>

## 영화 성향
{: #movie}

영화 성향은 서로 다른 종류의 영화에 대한 작성자의 관심도를 표시합니다. 범주 ID 및 이름은
`consumption_preferences_movie` 및 `Movie Preferences`입니다. 범주에는 10개의 성향이 있습니다. 

<table>
  <caption>표 2. 영화 성향</caption>
  <tr>
    <th style="width:45%; text-align:left">
      소비 성향 ID
    </th>
    <th style="width:30%; text-align:left">
      이름
    </th>
    <th style="text-align:center">
      점수
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_romance</code>
    </td>
    <td style="text-align:left">
      로맨스 영화를 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_adventure</code>
    </td>
    <td style="text-align:left">
      모험 영화를 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_horror</code>
    </td>
    <td style="text-align:left">
      공포 영화를 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_musical</code>
    </td>
    <td style="text-align:left">
      뮤지컬 영화를 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_historical</code>
    </td>
    <td style="text-align:left">
      사극 영화를 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_science_fiction</code>
    </td>
    <td style="text-align:left">
      공상과학 영화를 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_war</code>
    </td>
    <td style="text-align:left">
      전쟁 영화를 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_drama</code>
    </td>
    <td style="text-align:left">
      드라마 영화를 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_action</code>
    </td>
    <td style="text-align:left">
      액션 영화를 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_documentary</code>
    </td>
    <td style="text-align:left">
      다큐멘터리 영화를 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
</table>

## 음악 성향
{: #music}

음악 성향은 서로 다른 유형의 음악에서 작성자의 관심도와 작성자가 음악 연주를 즐기는지 여부를 표시합니다. 
범주 ID 및 이름은 `consumption_preferences_music` 및 `Music Preferences`입니다. 범주에는 9개의 성향이 있습니다. 

<table>
  <caption>표 3. 음악 성향</caption>
  <tr>
    <th style="width:45%; text-align:left">
      소비 성향 ID
    </th>
    <th style="width:30%; text-align:left">
      이름
    </th>
    <th style="text-align:center">
      점수
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rap</code>
    </td>
    <td style="text-align:left">
      랩 음악을 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_country</code>
    </td>
    <td style="text-align:left">
      컨트리 음악을 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_r_b</code>
    </td>
    <td style="text-align:left">
      R&amp;B 음악을 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_hip_hop</code>
    </td>
    <td style="text-align:left">
      힙합 음악을 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_live_event</code>
    </td>
    <td style="text-align:left">
      라이브 음악 공연에 참여할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_playing</code>
    </td>
    <td style="text-align:left">
      음악을 연주해 본 경험이 있을 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_latin</code>
    </td>
    <td style="text-align:left">
      라틴 음악을 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rock</code>
    </td>
    <td style="text-align:left">
      록 음악을 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_classical</code>
    </td>
    <td style="text-align:left">
      클래식 음악을 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
</table>

## 독서 및 학습 성향
{: #reading}

독서 및 학습 성향은 작성자가 독서할 가능성, 작성자가 독서하는 동기, 그리고 작성자가 독서를 즐기는 컨텐츠의 유형을 표시합니다. 
범주 ID 및 이름은 `consumption_preferences_reading` 및 `Reading Preferences`입니다. 범주에는 5개의 성향이 있습니다. 

<table>
  <caption>표 4. 독서 및 학습 성향</caption>
  <tr>
    <th style="width:45%; text-align:left">
      소비 성향 ID
    </th>
    <th style="width:30%; text-align:left">
      이름
    </th>
    <th style="text-align:center">
      점수
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_read_frequency</code>
    </td>
    <td style="text-align:left">
      자주 독서할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_entertainment_magazines</code>
    </td>
    <td style="text-align:left">
      연예 잡지를 읽을 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_non_fiction</code>
    </td>
    <td style="text-align:left">
      논픽션 서적을 읽을 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_financial_investing</code>
    </td>
    <td style="text-align:left">
      금융 투자 서적을 읽을 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_autobiographies</code>
    </td>
    <td style="text-align:left">
      자서전을 읽을 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
</table>

## 건강 및 활동 성향
{: #health}

건강 및 활동 성향은 건강 식품과 신체 활동에 대한 작성자의 관심도를 표시합니다. 
범주 ID 및 이름은 `consumption_preferences_health_and_activity` 및
`Health & Activity Preferences`입니다. 범주에는 3개의 성향이 있습니다. 

<table>
  <caption>표 5. 건강 및 활동 성향</caption>
  <tr>
    <th style="width:45%; text-align:left">
      소비 성향 ID
    </th>
    <th style="width:30%; text-align:left">
      이름
    </th>
    <th style="text-align:center">
      점수
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_eat_out</code>
    </td>
    <td style="text-align:left">
      자주 외식할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_gym_membership</code>
    </td>
    <td style="text-align:left">
      헬스클럽 멤버십을 보유할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_outdoor</code>
    </td>
    <td style="text-align:left">
      야외 활동을 좋아할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
</table>

## 기업가 정신 성향
{: #entrepreneur}

기업가 정신 성향은 사업을 시작하는 데 대한 작성자의 관심도를 표시합니다. 
범주 ID 및 이름은 `consumption_preferences_entrepreneurship` 및
`Entrepreneurship Preferences`입니다. 범주에는 1개의 성향이 있습니다. 

<table>
  <caption>표 6. 기업가 정신 성향</caption>
  <tr>
    <th style="width:45%; text-align:left">
      소비 성향 ID
    </th>
    <th style="width:30%; text-align:left">
      이름
    </th>
    <th style="text-align:center">
      점수
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_start_business</code>
    </td>
    <td style="text-align:left">
      몇 년 안에 사업 시작을 고려할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
</table>

## 환경 관심도 성향
{: #environment}

환경 관심도 성향은 작성자의 환경에 대한 관심도를 표시합니다. 
범주 ID 및 이름은 `consumption_preferences_environmental_concern` 및
`Environmental Concern Preferences`입니다. 범주에는 1개의 성향이 있습니다. 

<table>
  <caption>표 7. 환경 관심도 성향</caption>
  <tr>
    <th style="width:45%; text-align:left">
      소비 성향 ID
    </th>
    <th style="width:30%; text-align:left">
      이름
    </th>
    <th style="text-align:center">
      점수
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_concerned_environment</code>
    </td>
    <td style="text-align:left">
      환경에 대한 관심도가 높을 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>0.5</code>(중립)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
</table>

## 자원 봉사 성향
{: #volunteer}

자원 봉사 성향은 사회적 대의명분을 위한 자원 봉사에서 작성자의 관심도를 표시합니다. 범주 ID 및 이름은
`consumption_preferences_volunteering` 및 `Volunteering Preferences`입니다. 범주에는 1개의 성향이 있습니다. 

<table>
  <caption>표 8. 자원 봉사 성향</caption>
  <tr>
    <th style="width:45%; text-align:left">
      소비 성향 ID
    </th>
    <th style="width:30%; text-align:left">
      이름
    </th>
    <th style="text-align:center">
      점수
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_volunteer</code>
    </td>
    <td style="text-align:left">
      사회적 대의명분을 위해 자원 봉사할 가능성이 많음
    </td>
    <td style="text-align:center">
      <code>0.0</code>(가능성 없음)<br/>
      <code>1.0</code>(가능성 많음)
    </td>
  </tr>
</table>
