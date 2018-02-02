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

# JSON プロファイルの解釈
{: #output}

コンテンツを分析するために `POST /v3/profile` メソッドを使用すると、要求の `Accept` ヘッダーで `application/json` が指定されている場合、またはデフォルトで、本サービスは分析結果を JSON `Profile` オブジェクトとして返します。JSON 出力のスコープは、要求で指定されたパラメーターと、入力テキストがタイム・スタンプ付きデータ (例えば、Twitter フィードに関連付けられたテキスト) を表しているかどうかに基づきます。
{: shortdesc}

以降のセクションで、JSON フォーマットの応答のコンテンツを説明します。すべての出力例は、[入門チュートリアル](/docs/services/personality-insights/getting-started.html)で使用されているサンプル JSON ファイル <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="外部リンク・アイコン" title="外部リンク・アイコン" class="style-scope doc-content"></a> によって生成されたものです。CSV 出力について詳しくは、『[CSV プロファイルの解釈](/docs/services/personality-insights/output-csv.html)』を参照してください。

## Profile オブジェクト
{: #outputJSON}

`Profile` オブジェクトは、本サービスによって返される最上位の JSON オブジェクトです。このオブジェクトには以下のフィールドがあります。

-   `word_count` (integer) は、入力コンテンツのうち、プロファイルを生成するために使用された単語の数を示します。要求が大量のコンテンツを送信した場合、この数は入力の単語数を下回ることがあります。単語数が最小しきい値に満たない場合、出力には追加ガイダンスを提供する `word_count_message` フィールドも含まれます。
-   `processed language` (string) は、入力を処理するために本サービスが使用した言語モデルを示します。`ar` (アラビア語)、`en` (英語)、`es` (スペイン語)、`ja` (日本語)、または `ko` (韓国語) のいずれかです。
-   `personality` は、入力テキストから推論されたビッグ・ファイブのディメンションおよびファセットを記述する `Trait` オブジェクトの再帰的配列です。
-   `needs` は、入力テキストから推論されたニーズを記述する `Trait` オブジェクトの配列です。
-   `values` は、入力テキストから推論された価値を記述する `Trait` オブジェクトの配列です。
-   `behavior` は、コンテンツが曜日および時刻にどのように分布しているのかを記述する `Behavior` オブジェクトの配列です。JSON 入力にタイム・スタンプが付いている場合のみ、本サービスはこのフィールドを返します。
-   `consumption_preferences` は、各消費嗜好性カテゴリーの結果を提供する `ConsumptionPreferencesCategory` オブジェクトの配列です。この配列の要素は、そのカテゴリーの個々の消費嗜好性の情報を提供します。要求の `consumption_preferences` 照会パラメーターが `true` に設定されている場合のみ、本サービスはこのフィールドを返します。
-   `warnings` は、入力テキストに関連するメッセージを提供する `Warning` オブジェクトの配列です。入力が警告を生成しなかった場合、この配列は空です。

### 応答例
{: #JSONExample}

以下の出力例は、`Profile` オブジェクトの上位の構造を示します。出力には、`personality` フィールド、`needs` フィールド、および `values` フィールドが必ず含まれます。入力がタイム・スタンプ付き JSON の場合、応答には `behavior` フィールドが含まれます。また、要求で消費嗜好性が要求された場合、応答には `consumption_preferences` フィールドが含まれます。この例では、入力は警告を生成しません。

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

## パーソナリティー特性の出力
{: #traitJSON}

すべてのタイプの入力に対して、`Profile` オブジェクトには、`personality` フィールド、`needs` フィールド、および `values` フィールドが必ず含まれます。これらのフィールドには、それぞれ、特性のタイプに応じた属性についてのパーソナリティー特性を記述する `Trait` オブジェクトの配列が含まれます。ニーズおよび価値の特性の場合、配列は特性を記述する単一レベルからなります。ビッグ・ファイブの特性の場合、第 1 レベルの配列がディメンションを記述し、第 2 レベルの配列が各ディメンションのファセットを記述します。

-   `trait_id` (string) は、特性の固有 ID であり、結果がどの特性に関連したものなのかを示します。
    -   `big5_characteristic`: ビッグ・ファイブのパーソナリティーのディメンション
    -   `facet_characteristic`: ビッグ・ファイブのパーソナリティーのファセット
    -   `need_characteristic`: ニーズ
    -   `value_characteristic`: 価値
-   `name` (string) は、ユーザーに表示される、特性の名前です。
-   `category` (string) は特性のカテゴリーです。
    -   `personality`: ビッグ・ファイブのパーソナリティー特性
    -   `needs`: ニーズ
    -   `values`: 価値
-   `percentile` (double) は、特性の正規化済み百分位数スコアです。詳しくは、『[パーソナリティー特性の百分位数](/docs/services/personality-insights/numeric.html#percentiles)』を参照してください。
-   `raw_score` (double) は、特性のロー・スコアです。このフィールドが返されるのは、`raw_scores` 照会パラメーターを `true` に設定することでロー・スコアを要求した場合のみです。詳しくは、『[パーソナリティー特性のロー・スコア](/docs/services/personality-insights/numeric.html#rawScores)』を参照してください。
-   `significant` (boolean) は、入力言語で特性が有意かどうかを示します。英語、スペイン語、および日本語の入力では、すべての特性でこのフィールドは常に `true` です。このフィールドは、アラビア語および韓国語の入力に対して本サービスのモデルが意味のある結果を生成できないような一部の特性では `false` です。詳しくは、『[アラビア語および韓国語の入力の制限事項](/docs/services/personality-insights/numeric.html#limitations)』を参照してください。
-   `children` は、入力テキストから推論されたビッグ・ファイブの各ディメンションのファセットに関する詳しい結果を提供する `Trait` オブジェクトの配列です。この配列は、ビッグ・ファイブのディメンションに対してのみ返されます。

### 応答例
{: #traitExample}

以下の出力例は、ビッグ・ファイブ、ニーズ、および価値の特性に関する出力の断片を示します。説明したように、ビッグ・ファイブの特性は、それぞれのファセットに対して `children` の配列を持ちます。

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

## 行動出力
{: #behaviorJSON}

本サービスへの入力が、個々のコンテンツ・アイテムにタイム・スタンプが付いた JSON である場合、`Profile` オブジェクトに `behavior` フィールドが含まれます。このフィールドは、曜日および時刻ごとに 1 つの `Behavior` オブジェクトを含みます。

-   `trait_id` (string) は、特性の固有 ID であり、結果がどの特性に関連したものなのかを示します。
    -   `behavior_day` は、曜日を表します (例: `behavior_sunday`)。
    -   `behavior_hour` は、時刻を表します (例: `behavior_0000`)。
-   `name` (string) は、ユーザーに表示される、特性の名前です。
-   `category` (string) は、特性のカテゴリーであり、常に `behavior` です。
-   `percentage` (double) は、その曜日または時刻に発生したコンテンツ・アイテムのパーセンテージです。詳しくは、『[行動特性のパーセンテージ](/docs/services/personality-insights/numeric.html#percentages)』を参照してください。

### 応答例
{: #behaviorExample}

以下の出力は、時間特性の行動出力の断片を示します。

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

## 消費嗜好性の出力
{: #preferenceJSON}

`consumption_preferences` 照会パラメーターが `true` に設定されている場合、`Profile` オブジェクトには `consumption_preferences` フィールドが含まれます。このフィールドには、消費嗜好性カテゴリーごとに 1 つの `ConsumptionPreferencesCategory` オブジェクトが含まれます。

-   `consumption_preference_category_id` (string) は、消費嗜好性カテゴリーの固有 ID であり、結果がどのカテゴリーに関連したものなのかを示します。形式は `consumption_preferences_{category}` です。
-   `name` (string) は、ユーザーに表示される、消費嗜好性カテゴリーの名前です。
-   `consumption_preferences` は、カテゴリーの個々の消費嗜好性の結果を提供する `ConsumptionPreferences` オブジェクトの配列です。

カテゴリーの個々の消費嗜好性が、それぞれ 1 つの `ConsumptionPreferences` オブジェクトによって記述されます。消費嗜好性が 1 つしかないカテゴリーや、多くあるカテゴリーがあります。

-   `consumption_preference_id` (string) は、消費嗜好性の固有 ID であり、結果がどの消費嗜好性に関連したものなのかを示します。形式は `consumption_preferences_preference` です。
-   `name` (string) は、ユーザーに表示される、消費嗜好性の名前です。
-   `score` (double) は、筆者がそのアイテムを好む可能性を示すスコアです。詳しくは、『[消費嗜好性のスコア](/docs/services/personality-insights/numeric.html#scores)』を参照してください。

### 応答例
{: #preferenceExample}

以下の出力は、消費嗜好性の出力の断片を示します。

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
