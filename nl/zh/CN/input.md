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

# 请求概要文件
{: #input}

要分析内容，请使用 HTTP `POST` 请求方法来调用 {{site.data.keyword.personalityinsightsshort}} 服务的 `/v3/profile` 方法。可以通过请求的主体向服务传递最多 20 MB 内容进行分析，但服务生成准确个性概要文件所需的输入实际上要少得多；有关更多信息，请参阅[提供足够的输入](#sufficient)。
{: shortdesc}

`/v3/profile` 方法包含多个参数，通过这些参数，可以指定要向服务传递并由服务返回的内容类型，以及每种内容类型的语言。服务始终会返回一个概要文件，其中提供对输入文本作者的个性特征的洞见。此外，还可以请求服务返回原始评分和消费偏好。

以下部分描述 `/v3/profile` 方法的参数。有关请求结果的信息，请参阅[了解 JSON 概要文件](/docs/services/personality-insights/output.html)和[了解 CSV 概要文件](/docs/services/personality-insights/output-csv.html)。有关 `/v3/profile` 方法的详细信息，请参阅 [API 参考 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}。

## 指定请求和响应格式
{: #formats}

可以使用 `Content-Type` 和 `Accept` 头参数来指示要传递给方法的内容的格式以及服务响应的格式。可以对请求和响应使用受支持格式的任何组合。

<table>
  <caption>表 1. 指定请求和响应格式</caption>
  <tr>
    <th style="width:10%; text-align:left; vertical-align:bottom">
      格式
    </th>
    <th style="width:26%; text-align:center; vertical-align:bottom">
      自变量
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      受 <code>Content-Type</code><br/>
      支持
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      受 <code>Accept</code><br/>
      支持
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      纯文本
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/plain</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      是（缺省值）<br/><br/>
      服务将处理纯文本而不进行修改。
    </td>
    <td style="text-align:center; vertical-align:top">
      否
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      HTML
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/html</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      是<br/><br/>
      服务会先从内容中除去标记，然后再对其进行处理。
    </td>
    <td style="text-align:center; vertical-align:top">
      否
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      JSON
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>application/json</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      是<br/><br/>
      内容必须符合 <code>Content</code> 对象定义的模型，该对象是 <code>ContentItem</code> 对象的数组。
    </td>
    <td style="text-align:center; vertical-align:top">
      是（缺省值）<br/><br/>
      服务会将结果作为 <code>Profile</code> 对象返回。
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      CSV
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/csv</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      否
    </td>
    <td style="text-align:center; vertical-align:top">
      是<br/><br/>
      缺省情况下，服务会返回单行数字结果。将可选的 <code>csv_headers</code> 查询参数设置为 <code>true</code>，以请求输出中每列的标题。
    </td>
  </tr>
</table>

### 指定字符集
{: #charset}

缺省情况下，服务将以下字符集用于输入内容：

-   *对于纯文本和 HTML 内容*，服务会根据 HTTP V1.1 规范，使用国际标准组织 (ISO) 的 ISO-8859-1 字符集（实际上是 ASCII 字符集）。
-   *对于 JSON 内容*，服务实际上会始终使用国际工程任务小组 (IETF) [请求评论 (RFC) 7159 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://tools.ietf.org/html/rfc7159#section-8.1){: new_window} 第 8.1 节中规定的 Unicode 转换格式 (UTF)-8 字符集。

提交纯文本或 HTML 内容时，请在 `Content-Type` 头中包含 `charset` 参数，以指示输入文本的字符编码。以下示例为纯文本输入指定了 UTF-8 字符编码：

```
Content-Type: text/plain;charset=utf-8
```
{: codeblock}

通过使用 `charset` 参数，可以避免与非 ASCII 或不可打印字符相关联的潜在问题。如果在未指定字符集的情况下传递 UTF-8 数据，那么特殊字符可能会导致不正确的结果，或者生成 HTTP 4*nn* 或 5*nn* 错误。

### 使用 cURL
{: #charsetCurl}

要避免使用 cURL 时发生错误，请始终通过 `curl` 命令的 `--data-binary` 选项传递内容，以保留内容的任何 UTF-8 编码。如果使用 `--data` 选项将内容作为 ASCII 传递，该命令可以处理输入，但这可能会导致以 UTF-8 编码的数据出现问题。

例如，以下 `curl` 命令正确使用 `--data-binary` 选项来发布指定 *filename* 的内容，而无需其他处理。此命令还将 `charset` 参数与 `Content-Type` 头配合使用，并且显式请求缺省 JSON 响应格式。

```bash
curl -X POST --user {username}:{password}
--header "Content-Type: text/plain;charset=utf-8"
--header "Accept: application/json"
--data-binary @{filename}
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{: pre}

有关使用不同请求和响应格式来调用服务的其他示例，请参阅[入门教程](/docs/services/personality-insights/getting-started.html)。

## 指定 JSON 输入
{: #json}

要传递 JSON 输入，请使用 `Content` 对象。该对象包含 `ContentItem` 对象的数组，其中每个对象都包含内容的一个元素。该对象唯一的必填字段是 `content`，用于提供要分析的文本。其他字段均为可选，您可用于指定以下内容：

-   `id`（字符串）是内容项的唯一标识。
-   `created`（整数）是表示内容项创建时间的 UNIX 时间戳记。
-   `updated`（整数）是表示内容项上次更新时间的 UNIX 时间戳记。
-   `contenttype`（字符串）指示内容项的类型：`text/plain` 或 `text/html`。
-   `language`（字符串）指示内容项的语言：`ar`（阿拉伯语）、`en`（英语）、`es`（西班牙语）、`ja`（日语）或 `ko`（韩语）。请参阅[指定请求和响应语言](#languages)。
-   `parentid`（字符串）是内容项的父项的 `id`。
-   `reply`（布尔值）指示内容项是否为对另一项的回复。
-   `forward`（布尔值）指示内容项是否为对另一项的转发或复制。

JSON 输入非常适合用于来自推特或其他由多个对话或帖子组成的社交网络的内容。您可以使用 JSON 按原样提交数据，而不将作者的所有文本并置到单个字符串中。这样做还有一个优点是，可以让服务知道文本哪些部分是相关的。

### 示例 JSON 输入
{: jsonExample}

[入门教程](/docs/services/personality-insights/getting-started.html)中的示例使用的是样本 JSON 文件 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="外部链接图标" title="外部链接图标" class="style-scope doc-content"></a>。该文件包含一系列推特消息。以下示例显示该文件中的前几条推文。

```javascript
{
  "contentItems": [
    {
      "content": "Wow, I liked @TheRock before, now I really SEE how special he is. The daughter story was IT for me. So great! #MasterClass",
      "contenttype": "text/plain",
      "created": 1447639154000,
      "id": "666073008692314113",
      "language": "en"
    },
    {
      "content": ".@TheRock how did you Know to listen to your gut and Not go back to football? #Masterclass",
      "contenttype": "text/plain",
      "created": 1447638226000,
      "id": "666069114889179136",
      "language": "en"
    },
    . . .
  ]
}
```
{: codeblock}

## 指定请求和响应语言
{: #languages}

可以使用 `Content-Language` 和 `Accept-Language` 头参数来指示输入内容的语言和服务响应的语言。可以对请求和响应使用受支持语言的任何组合。如果不指明语言，那么服务会使用其英语培训的模型来进行分析，并将英语用于其结果。下表列出了受支持的输入和输出语言，并标识了可与语言相关参数配合使用的参数。

<table style="width:90%">
  <caption>表 2. 指定请求和响应语言</caption>
  <tr>
    <th style="width:28%; text-align:left; vertical-align:bottom">
      语言
    </th>
    <th style="width:12%; text-align:center; vertical-align:bottom">
      自变量
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      受 <code>Content-Language</code><br/>
      支持
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      受 <code>Accept-Language</code><br/>
      支持
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      阿位伯语
    </td>
    <td style="text-align:center">
      <code>ar</code>
    </td>
    <td style="text-align:center">
      是
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      英语
    </td>
    <td style="text-align:center">
      <code>en</code>
    </td>
    <td style="text-align:center">
      是
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      日语
    </td>
    <td style="text-align:center">
      <code>ja</code>
    </td>
    <td style="text-align:center">
      是
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      韩语
    </td>
    <td style="text-align:center">
      <code>ko</code>
    </td>
    <td style="text-align:center">
      是
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      西班牙语
    </td>
    <td style="text-align:center">
      <code>es</code>
    </td>
    <td style="text-align:center">
      是
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      巴西葡萄牙语
    </td>
    <td style="text-align:center">
      <code>pt-br</code>
    </td>
    <td style="text-align:center">
      否
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      法语
    </td>
    <td style="text-align:center">
      <code>fr</code>
    </td>
    <td style="text-align:center">
      否
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      德语
    </td>
    <td style="text-align:center">
      <code>de</code>
    </td>
    <td style="text-align:center">
      否
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      意大利语
    </td>
    <td style="text-align:center">
      <code>it</code>
    </td>
    <td style="text-align:center">
      否
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      简体中文
    </td>
    <td style="text-align:center">
      <code>zh-cn</code>
    </td>
    <td style="text-align:center">
      否
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      繁体中文
    </td>
    <td style="text-align:center">
      <code>zh-tw</code>
    </td>
    <td style="text-align:center">
      否
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
</table>

以相同语言提交所有文本；请勿在同一请求中混用多种语言。对于两个字符的语言参数，服务会将区域变体视为其父语言；例如，服务将 `en-US` 解释为 `en`。

### 指定 JSON 内容的语言
{: #languageJSON}

对于纯文本和 HTML 输入，`Content-Language` 头是指定语言的唯一方法。对于 JSON 输入，还可以使用 `ContentItem` 对象的 `language` 参数来指定每个内容项的语言。但是，使用 `Content-Language` 头指定的语言会覆盖为内容项指定的语言；服务会忽略指定其他语言的内容项。

省略 `Content-Type` 头可使语言仅基于内容项的规范。服务会使用内容项中最普遍的语言，从而尽可能生成最佳结果。服务还会统计每种语言的内容项数并选择频率最高的语言。如果多种语言具有相同的最高频率，那么服务会使用最先达到该值的语言。同样，服务会忽略指定其他语言的内容项。

### 语言注意事项
{: #languageNotes}

提交输入文本时，请考虑以下内容：

-   *对于英语*，结果基于美国文化标准。如果分析来自其他文化的英语文本，可能需要相应调整结果。
-   *对于阿拉伯语*，服务可以出于性能原因而削减输入文本量。达到特定阈值后，阿拉伯语结果的准确性不会随着提供更多字数而提升。如果服务削减阿拉伯语输入，那么将返回警告消息，通知您服务已减少用于概要文件的输入文本量。
-   *对于阿拉伯语和韩语*，服务无法为部分特征返回有意义的结果。有关更多信息，请参阅[阿拉伯语和韩语输入的限制](/docs/services/personality-insights/numeric.html#limitations)。

有关使用翻译文本的常规信息，请参阅[根据翻译的文本推断个性](/docs/services/personality-insights/guidance.html#translation)。

## 提供足够的输入
{: #sufficient}

只有在提供适当数量和质量的充足数据的情况下，才能创建有意义的个性概要文件。由于语言的使用自然会因文档的不同、时间的不同而有所不同，因此文本的一小部分样本可能并不能代表个人的总体语言模式。此外，不同特征和不同媒体的汇聚速率略有不同。

在一定程度上，字数越多，可能生成的结果越好，从而通过减少预测的结果与用户实际得分之间的偏差来提高服务的精度。可以向服务发送最多 20 MB 的输入内容，但准确性大约在 3000 字的输入时趋于稳定；多于此字数的内容不会进一步提高概要文件的准确性。因此，服务仅从大型请求中抽取并使用前 250 KB 的内容（不算任何 HTML 或 JSON 标记）。

此数字并不对应于确切的字数，确切的字数根据文本的语言和性质而变化。例如，英语的平均字长为 4 到 5 个字符，所以 250 KB 约含 50,000 字，这至少是服务生成准确概要文件所需字数的 15 倍。通过截断较长的输入，服务可缩短响应时间而不会牺牲精度。响应 JSON 的 `word_count` 字段指示服务实际用于请求的字数，这可能小于提交的字数。

### 准则和建议
{: #sufficientGuidelines}

下表针对不同数量的输入文本报告两个值：

-   基于作为输入提供的字数而对所有特征计算的*平均“平均绝对误差”(MAE)*。MAE 越小，服务的结果越接近作者参加实际个性测试会获取的得分。
-   所有特征的推断得分与实际得分之间的*平均相关性*。相关性越接近 1，预测准确性越高，但高于 0.2 的相关性即视为可接受，高于 0.4 的相关性很少见。

这些信息基于英语数据，但一般准则适用于所有语言。有关平均 MAE 和相关性的更多信息（包括特定于语言的统计信息），请参阅[服务精确程度](/docs/services/personality-insights/science.html#researchPrecise)。

<table style="width:80%">
  <caption>表 3. 平均 MAE 和相关性</caption>
  <tr>
    <th style="text-align:center; vertical-align:bottom; width:24%">字数</th>
    <th style="text-align:center; width:38%">所有特征的<br/>平均 MAE</th>
    <th style="text-align:center; width:38%">所有特征的<br/>平均相关性</th>
  </tr>
  <tr>
    <td style="text-align:center">3000</td>
    <td style="text-align:center">12.1%</td>
    <td style="text-align:center">0.257</td>
  </tr>
  <tr>
    <td style="text-align:center">1200</td>
    <td style="text-align:center">12.2%</td>
    <td style="text-align:center">0.237</td>
  </tr>
  <tr>
    <td style="text-align:center">600</td>
    <td style="text-align:center">12.3%</td>
    <td style="text-align:center">0.212</td>
  </tr>
  <tr>
    <td style="text-align:center">300</td>
    <td style="text-align:center">12.5%</td>
    <td style="text-align:center">0.175</td>
  </tr>
  <tr>
    <td style="text-align:center">100</td>
    <td style="text-align:center">12.7%</td>
    <td style="text-align:center">0.095</td>
  </tr>
</table>

如以下准则所示，{{site.data.keyword.IBM_notm}} 建议至少提供 1200 字，但提供至少 600 字也会生成可接受的结果：

-   3000 字足以达到服务的最大精度。
-   至少提供 1200 字可将 MAE 控制在服务能返回的最佳 MAE 的 2% 范围内。
-   提供 600 到 1200 字可将 MAE 控制在服务能返回的最佳 MAE 的 3% 范围内。
-   少于 600 字会生成警告，但服务仍会分析输入。
-   少于 100 字会生成错误。

这些准则可帮助您使结果的可靠性适合您的应用。例如，对于推荐电影的休闲应用，您可能认为较低精度也可接受；对于提供更重要推荐的应用，您可能需要更精确的结果。有关服务如何推断个性特征的更多信息，请参阅[如何推断个性特征](/docs/services/personality-insights/science.html#researchInfer)。

## 请求原始评分
{: #rawScores}

服务始终会将每个个性特征（“大五类人格”维度和构面、“需求”和“价值观”）的规范化得分作为其响应的一部分返回。如果将 `raw_score` 查询参数设置为 `true`，那么服务还可以报告每个特征的 `raw_score`。原始评分表示仅基于作者文本和该特征的模型的特征得分，而不将结果与样本群体进行比较。有关使用原始评分的更多信息，请参阅[个性特征的原始评分](/docs/services/personality-insights/numeric.html#rawScores)。

## 请求消费偏好
{: #preferences}

服务始终会返回个性模型的结果。将 `consump_sorpreferences` 查询参数设置为 `true` 时，服务还会基于根据输入文本推断出的个性特征，返回各种消费偏好的 `score`（得分）。这些结果指示作者偏好不同产品、服务和活动的倾向性。企业可以使用这些结果来更好地了解作者的倾向，并针对作者对沟通和优惠进行个性化。

有关不同消费偏好的更多信息，请参阅[消费偏好](/docs/services/personality-insights/preferences.html)。有关解读偏好的数字结果的信息，请参阅[消费偏好的得分](/docs/services/personality-insights/numeric.html#scores)。

## 指定接口版本
{: #version}

对 `/v3/profile` 方法的所有调用都必须包含 `version` 查询参数，以指示要使用的服务 API 版本和响应格式。您将 version 指定为 `YYYY-MM-DD` 格式的日期；例如，指定 `2017-10-13` 以表示 2017 年 10 月 13 日。此参数允许服务在不中断现有客户机的情况下，针对新版本更新其 API 和响应格式。

指定的日期不需要与服务的版本完全匹配；服务使用的版本不晚于您提供的日期。如果指定的日期早于 V3 的初始发行版，那么服务将使用 API V3。如果指定的是将来的日期，或者指定的日期晚于最新版本，那么服务将使用最新版本。
