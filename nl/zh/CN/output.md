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

# 了解 JSON 概要文件
{: #output}

使用 `POST /v3/profile` 方法来分析内容时，为请求的 `Accept` 头指定 `application/json` 时，服务会将其分析的结果作为 JSON `Profile` 对象返回。JSON 输出的作用域取决于为请求指定的参数。还取决于输入文本是否表示带时间戳记的数据，例如与推特订阅源关联的文本。
{: shortdesc}

以下各部分描述了 JSON 格式的响应内容。所有示例输出均由[入门教程](/docs/services/personality-insights?topic=personality-insights-gettingStarted)中使用的样本 JSON 文件 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="外部链接图标" title="外部链接图标"></a> 生成。有关 CSV 输出的信息，请参阅[了解 CSV 概要文件](/docs/services/personality-insights?topic=personality-insights-outputCSV)。

## Profile 对象
{: #outputJSON}

`Profile` 对象是服务返回的顶级 JSON 对象。该对象具有以下字段：

-   `word_count`（整数）提供输入内容中用于生成概要文件的字数。如果请求提交了大量内容，那么此数字可能小于输入中的字数。如果字数未达到最小阈值，那么输出包含 `word_count_message` 字段，以提供进一步的指导信息。
-   `processed language`（字符串）描述服务用于处理输入的语言模型：`ar`（阿拉伯语）、`en`（英语）、`es`（西班牙语）、`ja`（日语）或 `ko`（韩语）。
-   `personality` 是 `Trait` 对象的递归数组，用于描述根据输入文本推断出的“大五类人格”维度和构面。
-   `needs` 是 `Trait` 对象的数组，用于描述根据输入文本推断出的“需求”。
-   `values` 是 `Trait` 对象的数组，用于描述根据输入文本推断出的“价值观”。
-   `behavior` 是 `Behavior` 对象的数组，用于描述内容在一周的各天和一天的各小时内的分布。服务仅对带时间戳记的 JSON 输入返回此字段。
-   `consumption_preferences` 是 `ConsumptionPreferencesCategory` 对象的数组，用于为每个类别的消费偏好提供结果。该数组的元素提供该类别的各个偏好的信息。仅当请求的 `consumption_preferences` 查询参数设置为 `true` 时，服务才会返回此字段。
-   `warnings` 是 `Warning` 对象的数组，用于提供与输入文本相关的消息。如果输入未生成任何警告，那么该数组为空。

### 示例响应
{: #JSONExample}

以下示例输出显示了 `Profile` 对象的高级别结构。输出始终包含 `personality`、`needs` 和 `values` 字段。如果输入是带时间戳记的 JSON，那么响应会包含 `behavior` 字段。此外，如果请求还要求提供消费偏好，那么响应会包含 `consumption_preferences` 字段。在此示例中，输入不会生成警告。

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

## 个性特征输出
{: #traitJSON}

对于所有类型的输入，`Profile` 对象始终包含 `personality`、`needs` 和 `values` 字段。其中每个字段都包含 `Trait` 对象的数组，用于描述该类型特征的属性的个性特征。对于“需求”和“价值观”特征，该数组具有单个级别用于描述特征。对于“大五类人格”特征，顶级数组描述维度，第二级数组描述每个维度的构面。

-   `trait_id`（字符串）是与结果相关的特征的唯一标识：
    -   `big5_{characteristic}` 表示“大五类人格”个性维度
    -   `facet_{characteristic}` 表示“大五类人格”个性构面
    -   `need_{characteristic}` 表示“需求”
    -   `value_{characteristic}` 表示“价值观”
-   `name`（字符串）是向用户显示的特征名称。
-   `category`（字符串）是特征的类别：
    -   `personality` 表示“大五类人格”个性特征
    -   `needs` 表示“需求”
    -   `values` 表示“价值观”
-   `percentile`（双精度值）是特征的规范化百分位数得分。有关更多信息，请参阅[个性特征的百分位数](/docs/services/personality-insights?topic=personality-insights-numeric#percentiles)。
-   `raw_score`（双精度值）是特征的原始评分。仅当通过将 `raw_scores` 查询参数设置为 `true` 来请求原始评分时，才会返回此字段。有关更多信息，请参阅[个性特征的原始评分](/docs/services/personality-insights?topic=personality-insights-numeric#rawScores-numeric)。
-   `significant`（布尔值）指示特征是否对输入语言有意义。对于英语、西班牙语和日语输入的所有特征，此字段都始终为 `true`。对于阿拉伯语和韩语输入中，服务的模型无法为其生成有意义结果的部分特征，此字段为 `false`。有关更多信息，请参阅[阿拉伯语和韩语输入的限制](/docs/services/personality-insights?topic=personality-insights-numeric#limitations)。
-   `children` 是 `Trait` 对象的数组，用于为根据输入文本推断出的每个“大五类人格”维度的构面提供更详细的结果。仅对于“大五类人格”维度返回此数组。

### 示例响应
{: #traitExample}

以下示例输出显示了“大五类人格”、“需求”和“价值观”特征的输出片段。如上所述，仅“大五类人格”特征具有 `children` 数组来表示其各自的构面。

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

## 行为输出
{: #behaviorJSON}

如果服务的输入是具有各个内容项的时间戳记的 JSON，那么 `Profile` 对象会包含 `behavior` 字段。该字段针对一周的每天和一天的每个小时包含一个 `Behavior` 对象。

-   `trait_id`（字符串）是与结果相关的特征的唯一标识：
    -   `behavior_{day}` 表示一周的星期几（例如，`behavior_sunday`）。
    -   `behavior_{hour}`，表示一天的时间（例如，`behavior_0000`）。
-   `name`（字符串）是向用户显示的特征名称。
-   `category`（字符串）是特征的类别，始终为 `behavior`。
-   `percentage`（双精度值）是在一周的该天或一天的该小时内发生的内容项的百分比。有关更多信息，请参阅[行为特征的百分比](/docs/services/personality-insights?topic=personality-insights-numeric#percentages)。

### 示例响应
{: #behaviorExample}

以下输出显示了时间特征的行为输出片段。

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

## 消费偏好输出
{: #preferenceJSON}

如果 `consumption_preferences` 查询参数设置为 `true`，那么 `Profile` 对象会包含 `consumption_preferences` 字段。此字段针对每个类别的偏好包含一个 `ConsumptionPreferencesCategory` 对象。

-   `consumption_preference_category_id`（字符串）是与结果相关的消费偏好类别的唯一标识，格式为 `consumption_preferences_{category}`。
-   `name`（字符串）是向用户显示的消费偏好类别名称。
-   `consumption_preferences` 是 `ConsumptionPreferences` 对象的数组，用于为该类别的各个偏好提供结果。

一个类别的各个偏好通过 `ConsumptionPreferences` 对象来描述。一些类别只有一个偏好；另一些类别有许多偏好。

-   `consumption_preference_id`（字符串）是与结果相关的消费偏好的唯一标识，格式为 `consumption_preferences_{preference}`。
-   `name`（字符串）是向用户显示的消费偏好名称。
-   `score`（双精度值）是用于指示作者偏好该项的可能性的得分。有关更多信息，请参阅[消费偏好的得分](/docs/services/personality-insights?topic=personality-insights-numeric#scores)。

### 示例响应
{: #preferenceExample}

以下输出显示了消费偏好的输出片段。

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
