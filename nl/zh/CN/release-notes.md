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

# 发行说明
{: #release-notes}

以下各部分记录了 {{site.data.keyword.personalityinsightsshort}} 服务的每个发行版包含的新功能和更改。除非另有说明，否则所有更改均兼容先前发行版并且自动且透明地可供所有新应用程序和现有应用程序使用。
{: shortdesc}

发行说明记录了针对所有最近更新的*服务版本*和*接口版本*。使用 `version` 查询参数指定*接口版本*，可使用该更新提供的新功能部件和功能。此服务将使用 `X-Service-Api-Version` 响应头返回这两个版本。
{: note}

## 2018 年 12 月 21 日
{: #December2018}

**服务版本** - `3.4.5`<br/> **接口版本** - `2017-10-13`

已从服务中除去 {{site.data.keyword.personalityinsightsshort}} API V2。2016 年 10 月 19 日发布了服务 V3。此时，强烈建议用户尽快从 V2 迁移。

## 2018 年 11 月 18 日
{: #November2018b}

**服务版本** - `3.4.5`<br/> **接口版本** - `2017-10-13`

现在，在 {{site.data.keyword.cloud}} 伦敦位置 (**eu-gb**) 提供了 {{site.data.keyword.personalityinsightsshort}} 服务。与所有位置一样，伦敦使用基于令牌的 Identity and Access Management (IAM) 认证。在此位置中创建的所有新服务实例都使用 IAM 认证。

## 2018 年 11 月 7 日
{: #November2018a}

**服务版本** - `3.4.5`<br/> **接口版本** - `2017-10-13`

现在，在 {{site.data.keyword.cloud_notm}} 东京位置 (**jp-tok**) 中提供了 {{site.data.keyword.personalityinsightsshort}} 服务。与所有位置一样，东京使用基于令牌的 Identity and Access Management (IAM) 认证。在此位置中创建的所有新服务实例都使用 IAM 认证。

## 旧发行版
{: #older}

-   [2018 年 10 月 30 日](#October2018)
-   [2018 年 6 月 11 日](#June2018b)
-   [2018 年 6 月 4 日](#June2018a)
-   [2018 年 3 月 23 日](#March2018)
-   [2017 年 10 月 13 日](#October2017)
-   [2017 年 9 月 18 日](#September2017)
-   [2017 年 4 月 10 日](#April2017)
-   [2017 年 3 月 1 日](#March2017)
-   [2017 年 2 月 20 日](#February2017b)
-   [2017 年 2 月 13 日](#February2017)
-   [2017 年 1 月 13 日](#January2017)
-   [2016 年 12 月 15 日](#December2016)
-   [2016 年 11 月 15 日](#November2016)
-   [2016 年 10 月 20 日](#October2016b)
-   [2016 年 10 月 12 日](#October2016a)
-   [2016 年 8 月 31 日](#August2016)
-   [2016 年 7 月 14 日](#July2016b)
-   [2016 年 7 月 1 日](#July2016a)
-   [2016 年 6 月 7 日](#June2016b)
-   [2016 年 6 月 1 日](#June2016a)
-   [2016 年 5 月 17 日](#May2016)
-   [2016 年 3 月 18 日](#March2016)
-   [2015 年 7 月 9 日](#July2015)
-   [2015 年 2 月 23 日](#February2015)

### 2018 年 10 月 30 日
{: #October2018}

**服务版本** - `3.4.5`<br/> **接口版本** - `2017-10-13`

对于所有位置，{{site.data.keyword.personalityinsightsshort}} 服务已迁移至基于令牌的 Identity and Access Management (IAM) 认证。所有 {{site.data.keyword.cloud_notm}} 服务现在都使用 IAM 认证。每个位置中的 {{site.data.keyword.personalityinsightsshort}} 服务已于以下日期迁移：

-   达拉斯 (**us-south**)：2018 年 10 月 30 日
-   法兰克福 (**eu-de**)：2018 年 10 月 30 日
-   华盛顿特区 (**us-east**)：2018 年 6 月 11 日
-   悉尼 (**au-syd**)：2018 年 6 月 4 日

迁移至 IAM 认证会以不同方式影响新的服务实例和现有服务实例：

-   *在任何位置创建的所有新服务实例*现在都使用 IAM 认证来访问服务。您可以传递不记名令牌或 API 密钥：令牌支持已认证的请求，而无需在每个调用中嵌入服务凭证；API 密钥使用 HTTP 基本认证。使用任何 {{site.data.keyword.watson}} SDK 时，都可以传递 API 密钥，并让 SDK 管理令牌的生命周期。
-   *在指示的迁移日期之前在位置中创建的现有服务实例*继续使用来自先前 Cloud Foundry 服务凭证的 `{username}` 和 `{password}` 进行认证，直至将其更新为使用 IAM 认证。因为 {{site.data.keyword.personalityinsightsshort}} 服务无状态，所以可以执行以下步骤以将现有服务实例转换为使用 IAM 认证：

    1.  删除并重新创建服务实例。
    1.  修改应用程序代码以使用 IAM 认证。

有关更多信息，请参阅以下文档：

-   要了解服务实例使用的认证机制，请通过单击 [{{site.data.keyword.cloud_notm}} 仪表板 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/dashboard/apps){: new_window} 上的实例以查看服务凭证。
-   有关将 IAM 令牌与 Watson 服务配合使用的更多信息，请参阅[使用 IAM 令牌进行认证](/docs/services/watson?topic=watson-iam)。
-   有关将 IAM API 密钥与 Watson 服务配合使用的更多信息，请参阅 [IAM 服务 API 密钥](/docs/services/watson?topic=watson-api-key-bp)。
-   有关使用 IAM 认证的示例，请参阅 [API 参考 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/apidocs/personality-insights){: new_window}。


### 2018 年 6 月 11 日
{: #June2018b}

**服务版本** - `3.4.5`<br/> **接口版本** - `2017-10-13`

对于在华盛顿特区 (**us-east**) 中托管的服务实例和应用程序，服务现在支持新的 API 认证过程。有关更多信息，请参阅 [2018 年 10 月 30 日服务更新](#October2018)。

### 2018 年 6 月 4 日
{: #June2018a}

**服务版本** - `3.4.5`<br/> **接口版本** - `2017-10-13`

对于在悉尼 (**au-syd**) 中托管的服务实例和应用程序，服务现在支持新的 API 认证过程。有关更多信息，请参阅 [2018 年 10 月 30 日服务更新](#October2018)。

### 2018 年 3 月 23 日
{: #March2018}

**服务版本** - `3.4.4`<br/> **接口版本** - `2017-10-13`

-   使用小的缺陷修订更新了服务。这些更改特定于阿拉伯语、日语和韩语。
-   `POST /v3/profile` 方法现在需要 `Accept` 请求头。您必须指定 `application/json` 或 `text/csv`。

### 2017 年 10 月 13 日
{: #October2017}

**服务版本** - `3.4.0`<br/> **接口版本** - `2017-10-13`

-   现在，个性概要文件的 `Trait` 对象包含 `significant` 字段。单独的 `Trait` 对象会报告每个“大五类人格”维度、“大五类人格”构面、“需求”和“价值观”的结果。该对象的每个实例的 `significant` 字段确定特征的结果对于请求的输入语言 (`Content-Language`) 是否有意义：

    -   对于英语、西班牙语和日语，所有个性特征的该字段都始终为 `true`。
    -   对于阿拉伯语和韩语，对于大多数个性特征，该字段为 `true`，但对于服务的模型无法为其生成有意义结果的特征，该字段为 `false`。对于一组不变的特征，该字段为 `false`。有关完整列表，请参阅[阿拉伯语和韩语输入的限制](/docs/services/personality-insights?topic=personality-insights-numeric#limitations)。不要依赖于该字段为 `false` 的任何特征的结果。

有关服务的 JSON 响应内容的更多信息，请参阅[了解 JSON 概要文件](/docs/services/personality-insights?topic=personality-insights-output)。
-   现在，CSV 输出还包括标题名为 `*_significant` 的列。每列提供一个布尔值，用于指示特征是否有意义。有关服务的 CSV 响应内容的更多信息，请参阅[了解 CSV 概要文件](/docs/services/personality-insights?topic=personality-insights-outputCSV)。
-   要使用此最新版本的接口，请使用 `version` 参数指定接口版本 `2017-10-13`。

### 2017 年 9 月 18 日
{: #September2017}

**服务版本** - `3.3.0`<br/> **接口版本** - `2016-10-19`

现在，服务支持韩语 (`ko`) 输入内容。有关韩语输入的平均“平均绝对误差”(MAE) 和平均相关性的更多信息，请参阅[每种语言的平均 MAE 和相关性](/docs/services/personality-insights?topic=personality-insights-science#precisePerLanguage)。

对于韩语输入的一些个性特征，服务的模型无法生成有意义的百分位数和原始评分。有关这些特征的结果的更多信息，请参阅[阿拉伯语和韩语输入的限制](/docs/services/personality-insights?topic=personality-insights-numeric#limitations)。

### 2017 年 4 月 10 日
{: #April2017}

**服务版本** - `3.1.7`<br/> **接口版本** - `2016-10-19`

-   服务更改了处理具有大量输入内容的请求的方式。服务可接受的最大内容为 20 MB。但是，对于基于 *GloVe* 的模型，准确性大约在 3000 字的输入时趋于稳定。此行为与旧模型不同，在旧模型中，文本越多，准确性越高。通常，服务不再需要这么多的内容即可生成准确的概要文件。但是，内容越多，需要的处理时间越长，这可能会导致请求在完成之前超时。

    因此，服务现在仅从大型请求中抽取并使用前 250 KB 的内容（不算任何 HTML 或 JSON 标记）。此数字并不对应于确切的字数，确切的字数根据文本的语言和性质而变化。例如，英语的平均字长为 4 到 5 个字符，所以 250 KB 约含 50,000 字，这至少是服务所需字数的 15 倍。响应 JSON 的 `word_count` 字段指示服务用于请求的字数，这可能小于输入中的字数。

    由于服务仍会使概要文件基于的字数远多于满足最大准确性严格所需的字数，因此服务会生成准确性与过去一样的概要文件。然而，服务的响应速度要比以前快得多。对于服务仅为其使用部分输入内容的请求，服务会返回以下 `CONTENT_TRUNCATED` 警告消息，以使用户了解这一事实：

    `为了实现最高准确性，同时优化处理时间，仅分析了前 250 KB 的输入文本（不包括标记）。准确性大约在 3000 字时趋于稳定，因此这不会影响概要文件的准确性。`

有关更多信息，请参阅[提供足够的输入](/docs/services/personality-insights?topic=personality-insights-input#sufficient)。
-   使用小的安全修订更新了服务。

### 2017 年 3 月 1 日
{: #March2017}

**服务版本** - `3.1.6`<br/> **接口版本** - `2016-10-19`

通过对日志记录的小型增强功能，更新了服务。

### 2017 年 2 月 20 日
{: #February2017b}

**服务版本** - `3.1.5.1`<br/> **接口版本** - `2016-10-19`

通过小型的安全修订和缺陷修订更新了服务，以改进 API 调用的测量。

### 2017 年 2 月 13 日
{: #February2017}

**服务版本** - `3.1.4`<br/> **接口版本** - `2016-10-19`

-   优化了消费偏好列表。此列表现在仅包含对于了解个人主要生活习惯和消费者特征最重要的偏好。消费偏好列表已从 51 个减少为为 42 个。剩余的偏好以更简洁的方式表达了作者偏好不同产品、服务和活动的可能性，从而更加容易根据结果采取行动。

    服务不再返回以下 9 个消费偏好：

    -   <code>consumption_preferences_shopping</code> 类别不再包含：
        -   <code>consumption_preferences_automobile_resale_value</code>
              -   <code>consumption_preferences_reading</code> 类别不再包含：
        -   <code>consumption_preferences_read_motive_enjoyment</code><br/>
        -   <code>consumption_preferences_read_motive_information</code><br/>
        -   <code>consumption_preferences_read_motive_mandatory</code><br/>
        -   <code>consumption_preferences_read_motive_relaxation</code>
    -   <code>consumption_preferences_health_and_activity</code> 类别不再包含：
        -   <code>consumption_preferences_adventurous_sports</code>
        -   <code>consumption_preferences_fast_food_frequency</code>
    -   <code>consumption_preferences_volunteering</code> 类别不再包含：
        -   <code>consumption_preferences_volunteering_time</code>
        -   <code>consumption_preferences_volunteer_learning</code>

    有关剩余偏好的更多信息，请参阅[消费偏好](/docs/services/personality-insights?topic=personality-insights-preferences)。
-   现在，*对于阿拉伯语输入*，有关平均“平均绝对误差”(MAE) 和平均相关性的信息在[每种语言的平均 MAE 和相关性](/docs/services/personality-insights?topic=personality-insights-science#precisePerLanguage)中提供。此外，对于一些个性特征，服务的模型无法生成有意义的百分位数和原始评分。有关这些特征的结果的更多信息，请参阅[阿拉伯语和韩语输入的限制](/docs/services/personality-insights?topic=personality-insights-numeric#limitations)。

### 2017 年 1 月 13 日
{: #January2017}

**服务版本** - `3.1.2.1`<br/> **接口版本** - `2016-10-19`

通过一些小型的缺陷修订更新了 Personality Insights 服务。

### 2016 年 12 月 15 日
{: #December2016}

**服务版本** - `3.1.1`<br/> **接口版本** - `2016-10-19`

现在，对于阿拉伯语输入文本，{{site.data.keyword.personalityinsightsshort}} 服务使用 *GloVe* 来开发个性概要文件。对于任何语言，服务都不再使用《语言查询与字词计数》(LIWC) 心理语言学字典。有关服务如何开发个性特质的更多信息，请参阅[如何推断个性特征](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)。

### 2016 年 11 月 15 日
{: #November2016}

**服务版本** - `3.1.0`<br/> **接口版本** - `2016-10-19`

-   现在，对于日语输入文本，{{site.data.keyword.personalityinsightsshort}} 服务使用 *GloVe* 来开发个性概要文件。对于日语输入，服务都不再使用《语言查询与字词计数》(LIWC) 心理语言学字典。有关更多信息，请参阅[如何推断个性特征](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)。
-   现在，`ConsumptionPreferencesCategory` 和 `ConsumptionPreferences` 对象的所返回 `name` 字段包含使用 `Accept-Language` 请求头中所指定语言的本地化字符串。
-   更新包含一些小型的缺陷修订。

### 2016 年 10 月 20 日
{: #October2016b}

**服务版本** - `3.0.0`<br/> **接口版本** - `2016-10-19`

对 {{site.data.keyword.personalityinsightsshort}} 服务及其 API 进行了重大更新。API 的版本从 V2 递增到 V3，并提供了新功能。此发行说明的其余部分详细描述了这些更改。

V3 不兼容 V2。建议您迁移到 V3 以利用新功能和更改。迁移到 V3 仅包括更新和重新部署应用程序，以使用新版本的这些发行说明中描述的更改。无需在 {{site.data.keyword.cloud_notm}} 中创建服务的新实例；只需要调用 `v3` API。

将很快从服务中除去 {{site.data.keyword.personalityinsightsshort}} API V2。因此，强烈建议您尽快迁移到 V3。
{: note}

#### 有关 V3 的更多信息

现在，本文档描述的是 {{site.data.keyword.personalityinsightsshort}} API V3。以下各部分概括了新版本接口的更改：

-   有关调用 `/v3/profile` 方法的更多信息，请参阅[请求概要文件](/docs/services/personality-insights?topic=personality-insights-input)。
-   有关 `/v3/profile` 方法的响应的更多信息，请参阅[了解 JSON 概要文件](/docs/services/personality-insights?topic=personality-insights-output)和[了解 CSV 概要文件](/docs/services/personality-insights?topic=personality-insights-outputCSV)。
-   有关 V3 接口的更多信息，请参阅 [API 参考 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/apidocs/personality-insights){: new_window}。

#### 更改了 <code>/v3/profile</code> 方法的参数

`/v3/profile` 方法的参数已更改：

-   现在，API 提供有名为 `consumption_preferences` 的可选查询参数。此参数接受布尔值，用于指示是否要在结果中返回有关消费偏好的推断信息。缺省情况下，响应中不包含这些信息。有关更多信息，请参阅[新增消费偏好功能](#cp)。
-   现在，API 包含必需的 `version` 查询参数。此参数接受一个字符串，用于将 API 的请求版本和响应格式识别为 `YYYY-MM-DD` 格式的日期；例如，对于 2016 年 10 月 19 日，请指定 `2016-10-19`。此参数允许服务在不中断现有客户机的情况下，针对新版本更新其 API 或响应格式。API V3 的初始字符串为 `2016-10-19`。

    指定的日期不需要与服务的版本完全匹配。服务使用的版本不晚于您提供的日期。如果指定的日期早于 V3 发行日期，那么服务将使用 API V3。如果指定的是将来的日期，或者指定的日期晚于最新版本，那么服务将使用最新版本。
-   现在，`include_raw` 查询参数的名称为 `raw_scores`。
-   现在，`headers` 查询参数的名称为 `csv_headers`。

#### 新增消费偏好功能
{: #cp}

消费偏好功能指示作者倾向于展示不同的消费者倾向。将值为 `true` 的 `consumption_preferences` 查询参数传递给 `/v3/profile` 方法后，服务会返回具有 `Profile` 对象的更多结果：

-   `consumption_preferences` 字段，用于提供 `ConsumptionPreferencesCategory` 对象的数组。
-   每个 `ConsumptionPreferencesCategory` 对象都包含以下字段：
    -   `consumption_preference_category_id`：其中一个消费偏好类别的标识
    -   `name`：向用户显示的类别名称。
    -   `consumption_preferences`：`ConsumptionPreferences` 对象数组，用于为该类别的各个偏好提供根据输入文本推断的结果
-   每个 `ConsumptionPreferences` 对象都包含以下字段：
    -   `consumption_preference_id`：其中一个消费偏好的标识。
    -   `name`：向用户显示的消费偏好名称。
    -   `score`：消费偏好的得分：

        -   `0.0` 指示不可能
        -   `0.5` 指示中性
        -   `1.0` 指示可能

        某些偏好的得分为二进制，不允许使用中性值。此得分是基于从输入文本推断的结果（而不是标准化百分位数）来指示偏好。

有关消费偏好的更多信息，请参阅[消费偏好](/docs/services/personality-insights?topic=personality-insights-preferences)。

两个消费偏好对象的 `name` 字段始终返回英语值，与使用 `Accept-Language` 请求头指定的语言无关。
{: note}

#### 更改了 JSON 对象和字段

JSON 输入和输出对象及其字段已经过简化和澄清：

-   以下字段已从可以通过请求传递到 `/v3/profile` 方法的 JSON `ContentItem` 对象中除去：
    -   `userid`
    -   `sourceid`
    -   `charset`（先前已不推荐使用）

    您在 JSON 请求主体中将这些对象作为 `Content` 对象的 `contentItems` 数组元素进行传递。
-   更改了 `/v3/profile` 方法返回的 JSON `Profile` 对象的以下字段：
    -   除去了以下字段：
        -   `id`
        -   `source`
    -   除去了 `tree` 字段。取而代之的是四个新字段：
        -   `personality`，用于“大五类人格”个性特征。
        -   `needs`，用于“需求”特征。
        -   `values`，用于“价值观”特征。
        -   `behavior`，用于有关在一周的星期几和一天的时间内分发内容的时间结果。仅对带有时间戳记的 JSON 输入返回此字段。

    此更改实际上将结果在 JSON `Profile` 对象中上移了一个级别，从而消除了一个递归级别。
    -   现在，`processed_lang` 字段的名称改为 `processed_language`。
-   重命名了 `/v3/profile` 方法返回的 JSON `Trait` 对象的以下字段：
    -   现在，JSON `Trait` 对象的 `id` 字段的名称改为 `tratr_id`。
    -   现在，JSON `Trait` 对象的 `percentage` 字段的名称改为 `percentile`。
-   除去了 `/v3/profile` 方法返回的 JSON `Trait` 对象的以下字段：
    -   `sampling_error`
    -   `raw_sampling_error`

    现在，服务会报告用于限定其结果精度的平均“平均绝对误差”(MAE)。有关不同输入文本量的 MAE 的更多信息，请参阅[提供足够的输入](/docs/services/personality-insights?topic=personality-insights-input#sufficient)。
-   对于 `Profile` 对象的 `personality`、`needs` 和 `values` 字段，仍然会返回 JSON `Trait` 对象。但是，`behavior` 字段会返回名为 `Behavior` 的 JSON 对象数组，这些对象具有以下字段：
    -   `trait_id`
    -   `name`
    -   `category`
    -   `percentage`

    此外，行为信息不再作为值的树返回。输出包含列出所有时间特征（一周的星期几和一天的时间）的单个数组。
-   现在，`v/v3/profile` 方法可以返回的 JSON `Warnings` 对象的 `id` 字段的名称改为 `warnings_id`。

#### 更改了 JSON 标识
{: #ids}

服务为 `Trait` 和新 `Behavior` 对象的 `traitm_id`（以前为 `id`）字段返回的 JSON 标识已更改：

-   现在，“大五类人格”维度的标识以字符串 `big5_` 开头。
-   现在，“大五类人格”构面的标识以字符串 `facet_` 开头。
-   现在，“需求”的标识以字符串 `need_` 开头。
-   现在，“价值观”的标识以字符串 `value_` 开头。
-   现在，所有时间特征的标识以字符串 `behavior_` 开头。
-   现在，与一天的时间相关的时间特征的标识使用 4 位数的 24 小时制时间（例如，`behavior_0000`），而不是 12 小时制时间（例如，`0:00 am`）。
-   现在，所有字符均为小写。
-   现在，空格和连字符均改为下划线。

#### 更改了 CSV 头
{: #headers}

更改了服务可以对 CSV 输出返回的可选列标题：

-   对 JSON 输出的 `tratry_id` 描述的所有更改也适用于 CSV 头。
-   现在，“大五类人格”维度的原始评分的头以字符串 `big5_` 开头。
-   现在，“大五类人格”构面的原始评分的头以字符串 `facet_` 开头。
-   现在，“需求”的原始评分的头以字符串 `need_` 开头。
-   现在，“价值观”的原始评分的头以字符串 `value_` 开头。
-   现在，已处理的语言列的头为 `processed_language`，而不是 `processed_lang`。
-   不再返回 `user` 和 `source_id` 列。
-   现在，所有字符均为小写。
-   现在，空格和连字符均改为下划线。

#### 除去了 <code>visualize</code> 方法

服务的 API V2 包含了已不推荐使用的 `visualize` 方法，此方法在较早的发行版中用于可视化对 `/v3/profile` 方法的调用的结果。现在，已从服务的 API 中除去了 `visualize` 方法。服务继续提供用于支持概要文件图形可视化的 JavaScript 文件的集合。有关更多信息，请参阅[可视化概要文件](/docs/services/personality-insights?topic=personality-insights-overviewDevelopers#visualize)。

### 2016 年 10 月 12 日
{: #October2016a}

现在，对于西班牙语输入文本，{{site.data.keyword.personalityinsightsshort}} 服务使用 *GloVe* 来开发个性概要文件。对于西班牙语输入，服务都不再使用《语言查询与字词计数》(LIWC) 心理语言学字典。此服务从 8 月 31 日开始将新模型用于英语输入文本。计划很快将新模型应用于其余输入语言。有关新模型的更多信息，请参阅[如何推断个性特征](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)。

### 2016 年 8 月 31 日
{: #August2016}

现在，服务使用 *GloVe* 来开发个性概要文件。*GloVe* 是一种开放式源代码字嵌入技术。有关更多信息，请参阅[如何推断个性特征](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)。服务仅将新方法用于英语输入文本。对于其他语言，服务仍将继续使用《语言查询与字词计数》(LIWC) 心理语言学字典。服务计划未来将开放式词汇表方法用于所有语言。

对于用于英语输入的新模型，服务会报告所培训模型的结果的平均“平均绝对误差”(MAE)。有关不同输入文本量的 MAE 如何变化的更多信息，请参阅[提供足够的输入](/docs/services/personality-insights?topic=personality-insights-input#sufficient)。


{{site.data.keyword.IBM_notm}} 计划在未来报告非英语模型的 MAE。{{site.data.keyword.IBM_notm}} 计划使用 MAE（而不是采样错误）以根据所提供的输入文本量来确定服务精度如何变化。

### 2016 年 7 月 14 日
{: #July2016b}

-   现在，对于阿拉伯语输入，服务可以出于性能原因而削减输入文本量。达到特定阈值后，阿拉伯语结果的准确性不会随着提供更多字词而提升。如果服务削减阿拉伯语输入文本，那么将返回包含以下消息的 `PARTIAL_TEXT_USED` 警告：

    `出于性能原因，削减了提供用于计算概要文件的文本。此操作不会影响输出的准确性，因为并不是所有输入文本都是必需的。`
-   更新包括缺陷修订和内部改进。

### 2016 年 7 月 1 日
{: #July2016a}

-   服务的价格套餐现在向 {{site.data.keyword.personalityinsightsshort}} 用户提供更低价格。有关更多信息，请参阅 [{{site.data.keyword.cloud_notm}} 目录中的 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/catalog/services/personality-insights/){: new_window} {{site.data.keyword.personalityinsightsshort}} 服务。
-   现在，可以使用 `Accept-Language` 头指定的受支持响应语言列表包含：
    -   `ar`（阿拉伯语）
    -   `de`（德语）
    -   `en`（英语，缺省值）
    -   `es`（西班牙语）
    -   `fr`（法语）
    -   `it`（意大利语）
    -   `ja`（日语）
    -   `ko`（韩语）
    -   `pt-br`（巴西葡萄牙语）
    -   `zh-cn`（简体中文）
    -   `zh-tw`（繁体中文）

有关更多信息，请参阅[指定请求和响应语言](/docs/services/personality-insights?topic=personality-insights-input#languages-input)。
-   现在，`/v2/profile` 方法可以返回以下 HTTP 状态码：
    -   429 *请求太多*：服务正在处理的针对内容语言的请求太多。请稍候，然后重试请求。如果要提交针对该语言的大量请求，请考虑调节提交请求的速率。
    -   504 *网关超时*：请求已超时或处理用时太长。请稍候，然后重试请求。如果输入包含太多字词（例如，超过 20,000 字），请考虑减少字数，但是遵循有意义输入的准则。

    该方法不再返回 503 *服务不可用*。有关可能的响应代码的更多信息，请参阅 [API 参考 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/apidocs/personality-insights){: new_window}。
-   更新包括缺陷修订和内部改进。

### 2016 年 6 月 7 日
{: #June2016b}

-   现在，服务支持跨源资源共享 (CORS)，以允许基于浏览器的客户机直接调用服务。有关更多信息，请参阅 [CORS 支持](/docs/services/personality-insights?topic=personality-insights-overviewDevelopers#CORS)。
-   显著提高了服务的日语文本性能。
-   更新包括缺陷修订和内部改进。

### 2016 年 6 月 1 日
{: #June2016a}

通过缺陷修订和内部改进更新了服务。还会将新的顶级字段 `warnings` 添加到服务返回的 JSON 结果。有关更多信息，请参阅 [API 参考 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/apidocs/personality-insights){: new_window}。


### 2016 年 5 月 17 日
{: #May2016}

通过缺陷修订和内部改进更新了服务。

### 2016 年 3 月 18 日
{: #March2016}

现在，服务支持以下语言：

-   服务支持用于其输入文本的四种语言：阿拉伯语 (`ar`)、英语 (`en`)、西班牙语 (`es`) 和日语 (`ja`)。要指定语言，请使用 HTTP `Content-Language` 头（对于纯文本和 HTML 输入）或使用 `ContentItem` 对象的 `language` 属性（对于 JSON 输入）。
-   服务支持用于其响应的相同四种语言。要指定响应的语言，请使用 `Accept-Language` 头。

可以对输入和响应使用任何语言组合。如果不指明语言，那么服务缺省使用英语。有关更多信息，请参阅[指定请求和响应语言](/docs/services/personality-insights?topic=personality-insights-input#languages-input)。您还可以参阅博客帖子 [Arabic and Japanese support is now available for {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.personalityinsightsshort}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/blogs/watson/2016/04/arabic-japanese-support-now-available-ibm-watson-personality-insights/){: new_window}。

由于分析阿拉伯语内容所需的计算周期显著多于其他语言，因此阿拉伯语内容的处理时间也明显长得多。尽管服务对于所有语言的输入文本量都支持相同的 20 MB 限制，但阿拉伯语内容的合理限制可以更低，以避免超时。日语内容也需要更长的处理时间，但延迟产生的影响比阿拉伯语小得多。
{: note}

### 2015 年 7 月 9 日
{: #July2015}

-   *语言支持。*您可以分析英语和西班牙语内容。使用 `/v2/profile` 方法的 `Content-Language` 头可指示输入文本的语言。有关指定语言的更多信息，请参阅[指定请求和响应语言](/docs/services/personality-insights?topic=personality-insights-input#languages-input)。
-   *原始评分。*您可以请求根据输入文本和服务模型计算出的原始评分和原始采样错误数。这些值未进行规范化，也未与样本群体进行比较。对于希望针对特定场景应用定制规范化的客户，或者不需要与样本群体进行比较的客户，原始评分非常有用。通过将 `/v2/profile` 方法的 `include_raw` 查询参数设置为 `true`，可请求原始评分。有关更多信息，请参阅[解读数字结果](/docs/services/personality-insights?topic=personality-insights-numeric)。
-   *模型增强功能。*{{site.data.keyword.IBM_notm}} 根据自己的最新研究，进一步改进了一些推断个性特征的方法。这些更改对于服务的用户是透明的；它们不会使先前从服务获得的任何结果失效。有关这些研究以及服务推断方法的更多信息，请参阅[如何推断个性特征](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)。

### 2015 年 2 月 23 日
{: #February2015}

从 2015 年 2 月 23 日开始，{{site.data.keyword.personalityinsightsshort}} 服务成为前 User Modeling 服务的一般可用 (GA) 版本，原先该服务作为 Beta 发行版提供。GA 发行版需要用户迁移到新服务的实例。Beta 版本和 GA 版本的服务之间存在以下差异。

-   {{site.data.keyword.personalityinsightsshort}} 服务兼容 User Modeling 服务。描述的差异提高了灵活性并改进了结果，而并不影响当前应用程序。
-   更改了用于在 {{site.data.keyword.cloud_notm}} 中创建服务的参数。现在，使用的服务名称是 `personality_insights`（而不是 `user_modeling`），服务套餐是“`IBM Watson Personality Insights Monthly Plan`”（而不是 `user_modeling_free_plan`）。
-   `/v2/profile` 方法接受两种新的输入格式。现在，`Content-Type` 头除了接受 JSON (`application/json`) 外，还接受纯文本（`text/plain`，这是缺省值）和 HTML (`text/html`) 输入格式。
-   现在，`/v2/profile` 方法返回新的输出格式。`Accept` 头现在除了接受 JSON（`text/json`，这是缺省值）外，还接受 CSV (`text/csv`) 输出格式。
-   现在，对于要为其报告百分比值的每个特征，`/v2/profile` 方法包含新的输出元素 `sampling_error`。采样错误将作为双精度值返回，用于指示服务根据输入文本对作者百分位数的置信度级别。
-   “需求”模型应用改进的记号化和处理，以更好地规范化其特征值的分布。建议您重新计算先前由 User Modeling API 生成的所有结果。
-   现在，不推荐使用 `visualize` 方法，未来的发行版中将完全除去该方法。可以使用样本应用程序随附的 `personality.js` JavaScript 文件来从客户机获取类似结果。`textsummary.js` JavaScript 文件为服务结果提供了额外的格式设置。
