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

# 开发者概述
{: #overviewDevelopers}

可以通过 HTTP 具象状态传输 (REST) API 来使用 {{site.data.keyword.personalityinsightsshort}} 服务。此外，还有多种软件开发包 (SDK) 可用于简化各种语言中的应用程序开发。
{: shortdesc}

## 使用服务进行编程
{: #programming}

要生成个性概要文件，请将文本发送到服务的 HTTP `POST /v3/profile` 方法。可以提交纯文本、HTML 或 JSON 内容。服务返回的分析可以是 JSON 或 CSV 格式。

对于每种个性特征，服务会报告*百分位数*。百分位数是一种规范化得分，用于描述作者的书写内容表现出样本群体中某种特征的程度高低。如果请求，服务还会返回*原始评分*，这是未对样本群体进行规范化的绝对值。如果输入带有时间戳记，那么服务会提供摘要，以说明作者在一周的星期几和一天的时间的写作习惯。此外，如果请求，服务还会返回其每项可用消费偏好的可能性得分。

有关使用服务的更多信息，请参阅

-   [请求概要文件](/docs/services/personality-insights?topic=personality-insights-input)
-   [了解 JSON 概要文件](/docs/services/personality-insights?topic=personality-insights-output)
-   [了解 CSV 概要文件](/docs/services/personality-insights?topic=personality-insights-outputCSV)

### 可视化概要文件
{: #visualize}

服务提供了用于支持概要文件图形可视化的 JavaScript 文件的集合。通过这些脚本，可更方便地将服务用于高速缓存和内容分发网络。这些脚本依赖于具有数据驱动的文档 (`D3.js`) 库的 JavaScript、jQuery、HTML 和 SVG 来描述结果。有关 `D3.js` 的更多信息，请访问 [d3js.org ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://d3js.org/){: new_window}。

### CORS 支持
{: #CORS}

服务支持跨源资源共享 (CORS)。CORS 允许基于浏览器的客户机从前端脚本直接对服务发出异步请求。CORS 会绕过同源安全策略，否则该策略会阻止此类请求。

通过使用 CORS，Web 页面可以请求来自外部域的资源，该域位于发起请求的域之外。有关更多信息，请参阅 [enable-cors.org ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://enable-cors.org/){: new_window}。

## 使用软件开发包
{: #sdks}

SDK 可供 {{site.data.keyword.personalityinsightsshort}} 服务用于简化应用程序开发。{{site.data.keyword.ibmwatson}} SDK 可用于许多热门编程语言和平台。

-   有关 SDK 的完整列表以及到 GitHub 上 SDK 的链接，请参阅[使用 SDK](/docs/services/watson?topic=watson-using-sdks)。
-   有关用于 {{site.data.keyword.personalityinsightsshort}} 服务的 Node、Java、Python、Ruby 和 Go SDK 的所有方法的详细信息，请参阅 [API 参考 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/apidocs/personality-insights){: new_window}。

## 了解有关应用程序开发的更多信息
{: #learn-overview}

有关使用 {{site.data.keyword.watson}} 服务和 {{site.data.keyword.cloud}} 的更多信息，请参阅以下部分：

-   有关使用 {{site.data.keyword.watson}} 服务和 {{site.data.keyword.cloud_notm}} 的简介，请参阅 [{{site.data.keyword.watson}} 和 {{site.data.keyword.cloud_notm}} 入门](/docs/services/watson?topic=watson-about)。
-   所有新服务实例都使用 {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) 进行认证。较旧的服务实例可能继续使用来自现有 Cloud Foundry 服务凭证的 `{username}` 和 `{password}` 进行认证。有关向服务进行认证的更多信息，请参阅发行说明中的 [2018 年 10 月 30 日服务更新](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018)。
-   针对 {{site.data.keyword.personalityinsightsshort}} 服务禁用了请求日志记录。服务不记录或保留来自请求和响应的数据，而无论是否设置 `X-Watson-Learning-Opt-Out` 请求头。
