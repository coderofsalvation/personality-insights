---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-28"

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

# JSON 프로파일 이해하기
{: #output}

`POST /v3/profile` 메소드를 사용하여 컨텐츠를 분석하는 경우, 서비스는
요청의 `Accept` 헤더에서 `application/json`을 지정할 때
또는 기본적으로 JSON `Profile` 오브젝트로서 자체 분석의 결과를 리턴합니다. 
JSON 결과의 범위는 요청에서 지정된 매개변수에 따라, 그리고 입력 텍스트가
시간소인이 있는 데이터(예: Twitter 피드와 연관된 텍스트)를 표시하는지 여부에 따라 다릅니다.
{: shortdesc}

다음 절에서는 JSON 형식으로 응답의 컨텐츠를 설명합니다. 모든 예제 결과는 [시작하기 튜토리얼](/docs/services/personality-insights/getting-started.html)에서 사용된 샘플 JSON 파일
<a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="외부 링크 아이콘" title="외부 링크 아이콘" class="style-scope doc-content"></a>에 의해 생성됩니다. 
CSV 결과에 대한 정보는 [CSV 프로파일 이해하기](/docs/services/personality-insights/output-csv.html)를 참조하십시오. 

## 프로파일 오브젝트
{: #outputJSON}

`Profile` 오브젝트는 서비스에서 리턴하는 최상위 레벨 JSON 오브젝트입니다. 오브젝트에는 다음 필드가 있습니다. 

-   `word_count`(정수)는 프로파일을 생성하는 데 사용된 입력 컨텐츠의 단어 수를 제공합니다. 
요청이 대용량의 컨텐츠를 제출할 경우, 이는 입력의 단어 수보다 적을 수 있습니다. 단어 수가 최소 임계값을 충족하지 못하는 경우,
결과에는 추가적인 안내를 제공하는 `word_count_message` 필드도 포함됩니다. 
-   `processed language`(문자열)는 서비스가 입력을 처리하는 데 사용한 언어 모델(`ar`(아랍어),
`en`(영어), `es`(스페인어), `ja`(일본어) 또는 `ko`(한국어))을 기술합니다. 
-   `personality`는 입력 텍스트에서 추론된 빅 파이브 특질과 성향을 기술하는 `Trait` 오브젝트의 반복 배열입니다. 
-   `needs`는 입력 텍스트에서 추론된 욕구를 기술하는 `Trait` 오브젝트의 배열입니다. 
-   `values`는 입력 텍스트에서 추론된 가치를 기술하는 `Trait` 오브젝트의 배열입니다. 
-   `behavior`는 요일 및 일중 시간 중에 컨텐츠의 배포를 기술하는 `Behavior` 오브젝트의 배열입니다. 
서비스는 시간소인이 있는 JSON 입력에 대해서만 필드를 리턴합니다. 
-   `consumption_preferences`는 소비 성향의 각 범주에 대한 결과를 제공하는
`ConsumptionPreferencesCategory` 오브젝트의 배열입니다. 배열의 요소는 해당 범주의 개별 성향에 대한 정보를 제공합니다. 
서비스는 요청의 `consumption_preferences` 조회 매개변수가 `true`로 설정된 경우에만 필드를 리턴합니다. 
-   `warnings`는 입력 텍스트와 연관된 메시지를 제공하는 `Warning` 오브젝트의 배열입니다. 
입력이 경고를 생성하지 않으면 배열은 비어 있습니다. 

### 예제 응답
{: #JSONExample}

다음 예제 결과는 `Profile` 오브젝트의 상위 레벨 구조를 보여줍니다. 결과에는 항상
`personality`, `needs` 및 `values` 필드가 포함되어 있습니다. 
입력이 시간소인이 있는 JSON인 경우에는 응답에 `behavior` 필드가 포함됩니다. 그리고 요청이 소비 성향도 요청하는 경우에는
응답에 `consumption_preferences` 필드가 포함됩니다. 이 예제에서 입력은 경고를 생성하지 않습니다. 

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

## 성격 특성 결과
{: #traitJSON}

`Profile` 오브젝트에는 항상 모든 유형의 입력에 대해
`personality`, `needs` 및 `values` 필드가 포함되어 있습니다. 
이러한 각 필드에는 해당 특성 유형의 속성에 대한 성격 특성을 기술하는 `Trait` 오브젝트의 배열이 포함되어 있습니다. 
욕구 및 가치 특성의 경우, 배열에는 특성을 기술하는 단일 레벨이 있습니다. 
빅 파이브 특성의 경우, 최상위 레벨 배열은 특질을 기술하며 2차 레벨 배열은 각 특질의 성향을 기술합니다. 

-   `trait_id`(문자열)는 결과가 관련된 특성의 고유 ID입니다. 
    -   `big5_characteristic`: 빅 파이브 성격 특질의 경우
    -   `facet_characteristic`: 빅 파이브 성격 성향의 경우
    -   `need_characteristic`: 욕구의 경우
    -   `value_characteristic`: 가치의 경우
-   `name`(문자열)은 사용자에게 보이는 특성의 이름입니다. 
-   `category`(문자열)는 특성의 범주입니다. 
    -   `personality`: 빅 파이브 성격 특성의 경우
    -   `needs`: 욕구의 경우
    -   `values`: 가치의 경우
-   `percentile`(double)은 특성에 대한 정규화된 백분위수 점수입니다. 자세한 정보는
[성격 특성에 대한 백분위수](/docs/services/personality-insights/numeric.html#percentiles)를 참조하십시오. 
-   `raw_score`(double)는 특성에 대한 원 점수입니다. 이 필드는 `raw_scores` 조회 매개변수를
`true`로 설정하여 원 점수를 요청하는 경우에만 리턴됩니다. 자세한 정보는
[성격 특성에 대한 원 점수](/docs/services/personality-insights/numeric.html#rawScores)를 참조하십시오. 
-   `significant`(부울)는 특성이 입력 언어에 대해 의미가 있는지 여부를 표시합니다. 
영어, 스페인어 및 일본어 입력의 모든 특성에 대해 이 필드는 항상 `true`입니다. 
이 필드는 서비스의 모델이 의미 있는 결과를 생성할 수 없는 아랍어와 한국어 입력의 특성의 서브세트에 대해 `false`입니다. 
자세한 정보는 [아랍어와 한국어 입력에 대한 제한사항](/docs/services/personality-insights/numeric.html#limitations)을 참조하십시오. 
-   `children`은 입력 텍스트에서 추론된 각각의 빅 파이브 특질의 성향에 대한
보다 자세한 결과를 제공하는 `Trait` 오브젝트의 배열입니다. 배열은 빅 파이브 특질에 대해서만 리턴됩니다. 

### 예제 응답
{: #traitExample}

다음 예제 결과는 빅 파이브, 욕구 및 가치 특성에 대한 결과의 스니펫을 보여줍니다. 
설명한 대로, 빅 파이브 특성에만 개별 성향에 대한 `children`의 배열이 있습니다. 

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
      "significant": true,
      "children": [
        {
          "trait_id": "facet_adventurousness",
          "name": "Adventurousness",
          "category": "personality",
          "percentile": 0.89755869047319,
          "raw_score": 0.54990704031219,
          "significant": true
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
      "significant": true,
      "children": [
        {
          "trait_id": "facet_achievement_striving",
          "name": "Achievement striving",
          "category": "personality",
          "percentile": 0.84613299226628,
          "raw_score": 0.74240118454888,
          "significant": true
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
      "significant": true,
      "children": [
        {
          "trait_id": "facet_activity_level",
          "name": "Activity level",
          "category": "personality",
          "percentile": 0.88220584913965,
          "raw_score": 0.60106995926143,
          "significant": true
        },
      ]
    },
    {
      "trait_id": "big5_agreeableness",
      "name": "Agreeableness",
      "category": "personality",
      "percentile": 0.94786124793821,
      "raw_score": 0.80677815631809,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_altruism",
          "name": "Altruism",
          "category": "personality",
          "percentile": 0.99241983824205,
          "raw_score": 0.79028406290747,
          "significant": true
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
      "significant": true,
      "children": [
        {
          "trait_id": "facet_anger",
          "name": "Fiery",
          "category": "personality",
          "percentile": 0.17640022058508,
          "raw_score": 0.48490315691802,
          "significant": true
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
      "raw_score": 0.75196348037675,
      "significant": true
    },
    . . .
  ],
  "values": [
    {
      "trait_id": "value_conservation",
      "name": "Conservation",
      "category": "values",
      "percentile": 0.89268222856139,
      "raw_score": 0.72135308187423,
      "significant": true
    },
    . . .
  ],
  . . .
}
```
{: codeblock}

## 행동 결과
{: #behaviorJSON}

서비스에 대한 입력이 개별 컨텐츠 항목에 대한 시간소인이 있는 JSON인 경우,
`Profile` 오브젝트에는 `behavior` 필드가 포함되어 있습니다. 
이 필드에는 각 요일 및 일중 시간에 대한 `Behavior` 오브젝트가 포함되어 있습니다. 

-   `trait_id`(문자열)는 결과가 관련된 특성의 고유 ID입니다. 
    -   `behavior_day`: 요일의 경우(예: `behavior_sunday`).
    -   `behavior_hour`: 일중 시간의 경우(예: `behavior_0000`).
-   `name`(문자열)은 사용자에게 보이는 특성의 이름입니다. 
-   `category`(문자열)는 특성의 범주이며, 이는 항상 `behavior`입니다. 
-   `percentage`(double)는 해당 요일 또는 일중 시간 중에 발생한 컨텐츠 항목의 백분율입니다. 자세한 정보는
[행동 특성에 대한 백분율](/docs/services/personality-insights/numeric.html#percentages)을 참조하십시오. 

### 예제 응답
{: #behaviorExample}

다음 결과는 시간 특성에 대한 행동 결과의 스니펫을 보여줍니다. 

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

## 소비 성향 결과
{: #preferenceJSON}

`consumption_preferences` 조회 매개변수가 `true`로 설정된 경우,
`Profile` 오브젝트에는 `consumption_preferences` 필드가 포함되어 있습니다. 
이 필드에는 성향의 각 범주에 대한 `ConsumptionPreferencesCategory` 오브젝트가 포함되어 있습니다. 

-   `consumption_preference_category_id`(문자열)는
`consumption_preferences_{category}` 양식으로 결과가 관련되는 소비 성향 범주의 고유 ID입니다. 
-   `name`(문자열)은 사용자에게 보이는 소비 성향 범주의 이름입니다. 
-   `consumption_preferences`는
범주의 개별 성향에 대한 결과를 제공하는 `ConsumptionPreferences` 오브젝트의 배열입니다. 

범주의 각 개별 성향은 `ConsumptionPreferences` 오브젝트를 통해 기술됩니다. 
일부 범주에는 단일 성향만 있으며, 기타 범주에는 다수의 성향이 있습니다. 

-   `consumption_preference_id`(문자열)는
`consumption_preferences_preference` 양식으로 결과가 관련되는 소비 성향의 고유 ID입니다. 
-   `name`(문자열)은 사용자에게 보이는 소비 성향의 이름입니다. 
-   `score`(double)는 작성자가 항목을 선호할 가능성을 표시하는 점수입니다. 자세한 정보는
[소비 성향에 대한 점수](/docs/services/personality-insights/numeric.html#scores)를 참조하십시오. 

### 예제 응답
{: #preferenceExample}

다음 결과는 소비 성향에 대한 결과의 스니펫을 보여줍니다. 

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
          "name": "Likely to be sensitive to ownership cost when buying automobiles",
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
          "name": "Likely to eat out frequently",
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
          "name": "Likely to volunteer for social causes",
          "score": 0
        }
      ]
    }
  ],
  . . .
}
```
{: codeblock}
