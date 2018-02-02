---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-18"

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
{:download: .download}

# 入门教程

{{site.data.keyword.personalityinsightsfull}} 服务用于从社交媒体、企业数据或其他数字通信提炼有关个性特征的洞见。本教程可帮助您快速开始使用 {{site.data.keyword.personalityinsightsshort}} 服务。示例显示如何针对不同类型的输入来调用服务的 `POST /v3/profile` 方法，以及如何请求不同类型的输出和输出格式。
{: shortdesc}

## 开始之前
{: #before-you-begin}

- 创建服务的实例：
    - {: download} 如果您看到此信息，说明已创建服务实例。现在，请获取凭证。
    - 通过服务创建项目：
        1.  转至 {{site.data.keyword.watson}} 开发者控制台 [服务 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://console.{DomainName}/developer/watson/services){: new_window} 页面。
        1.  选择 {{site.data.keyword.personalityinsightsshort}}，单击**添加服务**，然后注册免费 {{site.data.keyword.Bluemix_notm}} 帐户或登录。
        1.  输入 `personality-tutorial` 作为项目名称，然后单击**创建项目**。
- 复制凭证以向服务实例进行认证：
    - {: download} 在服务仪表板中（您正在查看的内容）：
        1.  单击**服务凭证**选项卡。
        1.  单击**操作**下的**查看凭证**。
        1.  复制 `username`、`password` 和 `url` 值。
        {: download}
    - 在开发者控制台中的 **personality-tutorial** 项目中，复制**凭证**部分中“`personality_insights`”的 `username`、`password` 和 `url` 值。
- 确保您有 cURL：
    - 示例使用 cURL 来调用 HTTP 接口的方法。通过 [curl.haxx.se ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://curl.haxx.se/){: new_window} 安装与您的操作系统对应的版本。安装支持安全套接字层 (SSL) 协议的版本。确保在 `PATH` 环境变量中包括已安装的二进制文件。

<!-- Remove this text after dedicated instances have the Developer Console: begin -->

如果使用的是 {{site.data.keyword.Bluemix_dedicated_notm}}，请在“目录”的 [{{site.data.keyword.personalityinsightsshort}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://console.{DomainName}/catalog/services/personality-insights/){: new_window} 页面中创建服务实例。有关如何查找服务凭证的详细信息，请参阅 [Watson 服务的服务凭证 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](/docs/services/watson/getting-started-credentials.html#getting-credentials-manually){: new_window}。

<!-- Remove this text after dedicated instances have the Developer Console: end -->

## 步骤 1：发送纯文本输入并接收基本 JSON 输出
{: #example1}

第一个示例将纯文本文件 `profile.txt` 传递给 `POST /v3/profile` 方法，并隐式请求缺省 JSON 响应。

1.  下载样本文件 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="外部链接图标" title="外部链接图标" class="style-scope doc-content"></a>。
1.  发出以下命令将该文件发送到 `/v3/profile` 方法，并请求缺省 JSON 响应。`Content-Type` 头中包含的 `charset` 参数用于指定输入文本的字符编码。
    -   将 `{username}` 和 `{password}` 替换为先前步骤中的服务凭证。
    -   修改 `{path_to_file}` 以指定 `profile.txt` 文件的位置。

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --data-binary "@{path_to_file}profile.txt" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
    ```
    {: pre}

服务会返回 JSON `Profile` 对象，该对象包含基本元数据，例如，输入中的字数、用于处理输入的语言模型以及与输入关联的任何警告。有关更多信息，请参阅 [Profile 对象](/docs/services/personality-insights/output.html#outputJSON)。

概要文件包含根据输入文本推断出的有关作者的“大五类人格”个性、“需求”和“价值观”特征的信息。服务会报告每个特征的 `percentile`（百分位数），即规范化得分。服务会通过将作者的结果与样本群体的结果进行比较来计算出百分位数。有关更多信息，请参阅[个性特征输出](/docs/services/personality-insights/output.html#traitJSON)。

## 步骤 2：发送 JSON 输入并接收详细的 JSON 输出
{: #example2}

第二个示例将 JSON 文件 `profile.json` 传递给 `/v3/profile` 方法，并同样接受缺省 JSON 响应。此示例请求消费偏好和原始评分以对输入进行更详细的分析。

1.  下载样本文件 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="外部链接图标" title="外部链接图标" class="style-scope doc-content"></a>，其中包含推特消息的集合。
1.  发出以下命令将该文件发送到 `/v3/profile` 方法。此示例为 `Content-Type` 头指定了 `application/json`；对于 JSON 输入，不需要 `charset` 参数。此示例将 `consump_sorpreferences` 和 `raw_scores` 查询参数设置为 `true`。

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --data-binary "@{path_to_file}profile.json" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"
    ```
    {: pre}

服务会返回 JSON 概要文件，其中包含先前示例返回的元数据和特征。对于每个特征，服务还包含 `raw_score`，用于表示作者仅基于输入文本的特征得分，而不将结果与样本群体进行比较。

由于输入内容包含时间戳记，因此服务还会报告行为特征。这些是时间特征，用于指示在一周的每天和一天的每个小时所创建内容项的 `percentage`（百分比）。有关更多信息，请参阅[行为输出](/docs/services/personality-insights/output.html#behaviorJSON)。

服务还会报告其消费偏好集合的得分。这些得分根据推断的特征指示作者偏好不同产品、服务和活动的可能性。有关更多信息，请参阅[消费偏好输出](/docs/services/personality-insights/output.html#preferenceJSON)。

## 步骤 3：发送 JSON 输入并接收详细的 CSV 输出
{: #example3}

第三个示例与第二个示例类似：传递相同的 JSON 内容并请求相同的结果。但是，此示例为 `Accept` 头指定了 `text/csv`，以请求采用逗号分隔值 (CSV) 格式的响应。它使用 cURL 命令的 `--output` 选项将结果定向到名为 `profile.csv` 的文件。此示例将 `csv_headers` 查询参数设置为 `true`，以请求将列标题与输出一起返回。

1.  发出以下命令将该 JSON 文件发送到 `/v3/profile` 方法。

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary "@{path_to_file}profile.json" \
    --output profile.csv \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"
    ```
    {: pre}

有关 CSV 响应和标题的详细描述，请参阅[了解 CSV 概要文件](/docs/services/personality-insights/output-csv.html)。

## 后续步骤

-   了解有关[请求概要文件](/docs/services/personality-insights/input.html)、[了解 JSON 概要文件](/docs/services/personality-insights/output.html)和[了解 CSV 概要文件](/docs/services/personality-insights/output-csv.html)的更多信息。
-   了解有关“大五类人格”、“需求”和“价值观”[个性模型](/docs/services/personality-insights/models.html)的信息。
-   在 [API 参考 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window} 中了解有关 API 的更多信息。
-   在 [API Explorer ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v3){: new_window} 中与 API 进行交互。
-   浏览 [Node.js 样本应用程序 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window}，以了解有关使用服务开发应用程序的更多信息。
