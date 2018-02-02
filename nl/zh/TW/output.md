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

# 瞭解 JSON 設定檔
{: #output}

當您使用 `POST /v3/profile` 方法來分析內容時，依預設，或是您以要求的 `Accept` 標頭來指定 `application/json` 時，服務會將其分析結果傳回作為 JSON `Profile` 物件。JSON 輸出的範圍取決於您在要求中指定的參數，以及輸入文字是否代表時間戳記資料，例如與 Twitter 資訊來源相關聯的文字。
{: shortdesc}

下列各節說明 JSON 格式的回應內容。所有範例輸出都是由[入門指導教學](/docs/services/personality-insights/getting-started.html)中使用的範例 JSON 檔案 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json<img src="../../icons/launch-glyph.svg" alt="外部鏈結圖示" title="外部鏈結圖示" class="style-scope doc-content"></a> 所產生。如需 CSV 輸出的相關資訊，請參閱[瞭解 CSV 設定檔](/docs/services/personality-insights/output-csv.html)。

## 設定檔物件
{: #outputJSON}

`Profile` 物件是服務傳回的最上層 JSON 物件。此物件具有下列欄位：

-   `word_count`（整數）提供用來產生設定檔之輸入內容中的字數。如果要求提交大量內容，則此數會小於輸入中的字數。如果字數未達臨界值下限，則輸出也會包括 `word_count_message` 欄位，以提供其他指引。
-   `processed language`（字串）說明服務用來處理輸入的語言模型：`ar`（阿拉伯文）、`en`（英文）、`es`（西班牙文）、`ja`（日文）或 `ko`（韓文）。
-   `personality` 是 `Trait` 物件的遞迴陣列，說明從輸入文字推斷的「五大性格特質」維度和面向。
-   `needs` 是 `Trait` 物件的陣列，說明從輸入文字推斷的「需求」。
-   `values` 是 `Trait` 物件的陣列，說明從輸入文字推斷的「價值觀」。
-   `behavior` 是 `Behavior` 物件的陣列，說明在星期幾和幾點的內容分佈狀況。服務只會針對具有時間戳記的 JSON 輸入傳回此欄位。
-   `consumption_preferences` 是 `ConsumptionPreferencesCategory` 物件的陣列，提供每一種消費喜好的結果。陣列的元素可提供該種類個別喜好的資訊。只有在要求的 `consumption_preferences` 查詢參數設為 `true` 時，服務才會傳回此欄位。
-   `warnings` 是 `Warning` 物件的陣列，提供與輸入文字相關聯的訊息。如果輸入未產生任何警告，則陣列會是空的。

### 回應範例
{: #JSONExample}

下列範例輸出顯示 `Profile` 物件的高階結構。輸出一律包括 `personality`、`needs` 和 `values` 欄位。如果輸入是含時間戳記的 JSON，則回應會包括 `behavior` 欄位。如果要求也有要求消費喜好，則回應會包括 `consumption_preferences` 欄位。在這個範例中，輸入不會產生任何警告。

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

## 性格特質輸出
{: #traitJSON}

`Profile` 物件一律包括所有類型輸入的 `personality`、`needs` 和 `values` 欄位。其中每一個欄位都會包含 `Trait` 物件的陣列，用於說明該特質類型屬性的性格特質。對於「需求」和「價值觀」特質，陣列有單一層次用於說明那些特質。對於「五大性格特質」，最上層陣列會說明維度，而第二層陣列會說明每一個維度的面向。

-   `travit_id`（字串）是結果所屬特質的唯一 ID：
    -   `big5_characteristic` 代表「五大性格特質」維度
    -   `facet_characteristic` 代表「五大性格特質」面向
    -   `need_characteristic` 代表「需求」
    -   `value_characteristic` 代表「價值觀」
-   `name`（字串）是使用者可看見的特質名稱。
-   `category`（字串）是特質的種類：
    -   `personality` 代表「五大性格特質」
    -   `needs` 代表「需求」
    -   `values` 代表「價值觀」
-   `percentile`（倍精準數）是特質的正規化百分位數評分。如需相關資訊，請參閱[性格特質的百分位數](/docs/services/personality-insights/numeric.html#percentiles)。
-   `raw_score`（倍精準數）是特質的原始評分。只有在您將 `raw_scores` 查詢參數設為 `true` 以要求原始評分時，才會傳回此欄位。如需相關資訊，請參閱[性格特質的原始評分](/docs/services/personality-insights/numeric.html#rawScores)。
-   `significant`（布林）指出特質對輸入語言是否有意義。對於英文、西班牙文和日文輸入的所有特質，此欄位一律為 `true`。對於服務模型無法為其產生有意義結果的阿拉伯文和韓文輸入的部分特質，此欄位為 `false`。如需相關資訊，請參閱[阿拉伯文和韓文輸入的限制](/docs/services/personality-insights/numeric.html#limitations)。
-   `children` 是 `Trait` 物件的陣列，可為從輸入文字推斷之每一個「五大性格特質」維度的面向，提供更詳細的結果。只有針對「五大性格特質」維度，才會傳回此陣列。

### 回應範例
{: #traitExample}

下列範例輸出顯示「五大性格特質」、「需求」和「價值觀」特質的輸出 Snippet。如前述，只有「五大性格特質」才會有其各個面向的 `children` 陣列。

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

## 行為輸出
{: #behaviorJSON}

如果服務的輸入是 JSON，其中有個別內容項目的時間戳記，則 `Profile` 物件會包括 `behavior` 欄位。此欄位包括指出在星期幾和幾點的 `Behavior` 物件。

-   `travit_id`（字串）是結果所屬特質的唯一 ID：
    -   `behavior_day` 代表星期幾（例如，`behavior_sunday`）。
    -   `behavior_hour` 代表幾點（例如，`behavior_0000`）。
-   `name`（字串）是使用者可看見的特質名稱。
-   `category`（字串）是特質的種類，一律為 `behavior`。
-   `percentage`（倍精準數）是星期幾或幾點期間出現的內容項目百分比。如需相關資訊，請參閱[行為特質的百分比](/docs/services/personality-insights/numeric.html#percentages)。

### 回應範例
{: #behaviorExample}

下列輸出顯示時間特質的行為輸出 Snippet。

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

## 消費喜好輸出
{: #preferenceJSON}

如果 `consumption_preferences` 查詢參數設為 `true`，則 `Profile` 物件會包括 `consumpation_preferences` 欄位。此欄位包括每一種喜好的 `ConsumptionPreferencesCategory` 物件。

-   `consumption_preference_category_id`（字串）是結果所屬之消費喜好種類的唯一 ID，格式為 `consumption_preferences_{category}`。
-   `name`（字串）是使用者可看見的消費喜好種類名稱。
-   `consumption_preferences` 是 `ConsumptionPreferences` 物件的陣列，針對種類的個別喜好提供結果。

種類的每一個個別喜好都是透過 `ConsumptionPreferences` 物件來說明。部分種類只有單一喜好，而其他種類則有許多喜好。

-   `consumption_preference_id`（字串）是結果所屬之消費喜好的唯一 ID，格式為 `consumption_preferences_preference`。
-   `name`（字串）是使用者可看見的消費喜好名稱。
-   `score`（倍精準數）是一項評分，指出作者喜好該項目的可能性。如需相關資訊，請參閱[消費喜好的評分](/docs/services/personality-insights/numeric.html#scores)。

### 回應範例
{: #preferenceExample}

下列輸出顯示消費喜好的輸出 Snippet。

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
