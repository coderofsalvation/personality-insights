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
{:go: .ph data-hd-programlang='go'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}
{:download: .download}
{:apikey: data-credential-placeholder='apikey'}
{:url: data-credential-placeholder='url'}
{:hide-dashboard: .hide-dashboard}

# 入门教程
{: #gettingStarted}

{{site.data.keyword.personalityinsightsfull}} 服务用于从社交媒体、企业数据或其他数字通信中获取有关个性特征的洞察。本教程可帮助您快速开始使用 {{site.data.keyword.personalityinsightsshort}} 服务。示例显示如何针对不同类型的输入来调用服务的 `POST /v3/profile` 方法，以及如何请求不同类型的输出和输出格式。
{: shortdesc}

本教程使用 {{site.data.keyword.cloud}} Identity and Access Management (IAM) API 密钥进行认证。较旧的服务实例可能继续使用来自现有 Cloud Foundry 服务凭证的 `{username}` 和 `{password}` 进行认证。使用适合您的服务实例的方法进行认证。有关服务使用 IAM 认证的更多信息，请参阅发行说明中的 [2018 年 10 月 30 日服务更新](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018)。
{: important}

## 开始之前
{: #before-you-begin}

-   {: hide-dashboard}创建服务的实例：
    1.  {: hide-dashboard}转至 {{site.data.keyword.cloud_notm}}“目录”中的 [{{site.data.keyword.personalityinsightsshort}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/catalog/services/personality-insights){: new_window} 页面。
    1.  {: hide-dashboard}注册免费的 {{site.data.keyword.cloud_notm}} 帐户或登录。
    1.  {: hide-dashboard}单击**创建**。
-   复制凭证以向服务实例进行认证：
    1.  {: hide-dashboard}从 [{{site.data.keyword.cloud_notm}} 仪表板 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/dashboard/apps){: new_window}，单击 {{site.data.keyword.personalityinsightsshort}} 服务实例以转至 {{site.data.keyword.personalityinsightsshort}} 服务仪表板页面。
    1.  在**管理**页面上，单击**显示**以查看凭证。
    1.  复制 `API Key` 和 `URL` 值。
-   确保您具有 `curl` 命令。
    -   示例使用 `curl` 来调用 HTTP 接口的方法。通过 [curl.haxx.se ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://curl.haxx.se/){: new_window} 安装与您的操作系统对应的版本。安装支持安全套接字层 (SSL) 协议的版本。确保在 `PATH` 环境变量中包括已安装的二进制文件。

输入命令时，将 `{apikey}` 和 `{url}` 替换为您的实际 API 密钥和 URL。省略命令中指示变量值的花括号。实际值类似于以下示例：
{: hide-dashboard}

```bash
curl -X POST -u "apikey:L_HALhLVIksh1b73l97LSs6R_3gLo4xkujAaxm7i-b9x"
. . .
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{:pre}
{: hide-dashboard}

## 步骤 1：发送纯文本输入并接收基本 JSON 输出
{: #example1}

第一个示例将纯文本文件 `profile.txt` 传递给 `POST /v3/profile` 方法，并请求 JSON 响应。

1.  下载样本文件 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="外部链接图标" title="外部链接图标"></a>。
1.  发出以下命令将该文件发送到 `/v3/profile` 方法，并请求 JSON 响应。
    -   `Content-Type` 头指定输入为纯文本，即 `text/plain`。头中包含的 `charset` 参数用于标识输入文本的字符编码。
    -   `Accept` 头指定 `application/json` 以指示请求了 JSON 输出。
    -   {: hide-dashboard}将 `{apikey}` 和 `{url}` 替换为您的信息。
    -   修改 `{path_to_file}` 以指定 `profile.txt` 文件的位置。

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.txt \
    "{url}/v3/profile?version=2017-10-13"{: url}
    ```
    {: pre}

服务会返回 JSON `Profile` 对象，该对象包含基本元数据，例如，输入中的字数、用于处理输入的语言模型以及与输入关联的任何警告。有关更多信息，请参阅 [Profile 对象](/docs/services/personality-insights?topic=personality-insights-output#outputJSON)。

概要文件包含根据输入文本推断出的有关作者的“大五类人格”个性、“需求”和“价值观”特征的信息。服务会报告每个特征的 `percentile`（百分位数），即规范化得分。服务会通过将作者的结果与样本群体的结果进行比较来计算出百分位数。有关更多信息，请参阅[个性特征输出](/docs/services/personality-insights?topic=personality-insights-output#traitJSON)。

## 步骤 2：发送 JSON 输入并接收详细的 JSON 输出
{: #example2}

第二个示例将 JSON 文件 `profile.json` 传递给 `/v3/profile` 方法，并同样请求 JSON 响应。此示例请求消费偏好和原始评分以对输入进行更详细的分析。

1.  下载样本文件 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="外部链接图标" title="外部链接图标"></a>，其中包含推特消息的集合。
1.  发出以下命令将该文件发送到 `/v3/profile` 方法。此示例为 `Content-Type` 和 `Accept` 头指定了 `application/json`；对于 JSON 输入，不需要 `charset` 参数。此示例将 `consump_sorpreferences` 和 `raw_scores` 查询参数设置为 `true`。

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.json \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"{: url}
    ```
    {: pre}

服务会返回 JSON 概要文件，其中包含先前示例返回的元数据和特征。对于每个特征，服务还包含 `raw_score`，用于表示作者仅基于输入文本的特征得分，而不将结果与样本群体进行比较。

由于输入内容包含时间戳记，因此服务还会报告行为特征。这些是时间特征，用于指示在一周的每天和一天的每个小时所创建内容项的 `percentage`（百分比）。有关更多信息，请参阅[行为输出](/docs/services/personality-insights?topic=personality-insights-output#behaviorJSON)。

服务还会报告其消费偏好集合的得分。这些得分根据推断的特征指示作者偏好不同产品、服务和活动的可能性。有关更多信息，请参阅[消费偏好输出](/docs/services/personality-insights?topic=personality-insights-output#preferenceJSON)。

## 步骤 3：发送 JSON 输入并接收详细的 CSV 输出
{: #example3}

第三个示例与第二个示例类似：传递相同的 JSON 内容并请求相同的结果。但是，此示例为 `Accept` 头指定了 `text/csv`，以请求采用逗号分隔值 (CSV) 格式的响应。它使用 `curl` 命令的 `--output` 选项将结果定向到名为 `profile.csv` 的文件。此示例将 `csv_headers` 查询参数设置为 `true`，以请求将列标题与输出一起返回。

1.  发出以下命令将该 JSON 文件发送到 `/v3/profile` 方法。`Content-Type` 头将输入内容标识为 `application/json`，并且 `Accept` 头请求 CSV 输出 `text/csv`。

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary @{path_to_file}profile.json \
    --output profile.csv \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"{: url}
    ```
    {: pre}

有关 CSV 响应和标题的详细描述，请参阅[了解 CSV 概要文件](/docs/services/personality-insights?topic=personality-insights-outputCSV)。

## 后续步骤
{: #gsns}

-   了解有关[请求概要文件](/docs/services/personality-insights?topic=personality-insights-input)、[了解 JSON 概要文件](/docs/services/personality-insights?topic=personality-insights-output)和[了解 CSV 概要文件](/docs/services/personality-insights?topic=personality-insights-outputCSV)的更多信息。
-   了解有关“大五类人格”、“需求”和“价值观”[个性模型](/docs/services/personality-insights?topic=personality-insights-models)的信息。
-   在 [API 参考 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/apidocs/personality-insights){: new_window} 中了解有关 API 的更多信息。
-   浏览 [Node.js 样本应用程序 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window}，以了解有关使用服务开发应用程序的更多信息。
