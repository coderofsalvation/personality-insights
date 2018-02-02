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

# 开发者概述
{: #overviewDevelopers}

可以通过 HTTP 具象状态传输 (REST) API 来使用 {{site.data.keyword.personalityinsightsshort}} 服务。此外，还有多种软件开发包 (SDK) 可用于简化各种语言和环境中的应用程序开发。
{: shortdesc}

## 使用服务进行编程
{: #programming}

要生成个性概要文件，请将文本发送到服务的 HTTP `POST /v3/profile` 方法。可以提交纯文本、HTML 或 JSON 内容。服务返回的分析可以是 JSON 或 CSV 格式。

对于每种个性特征，服务会报告*百分位数*，这是一种规范化得分，用于描述作者的书写内容表现出样本群体中某种特征的程度高低。如果请求，服务还会返回*原始评分*，这是未对样本群体进行规范化的绝对值。如果输入带有时间戳记，那么服务会提供摘要，以说明作者在一周的星期几和一天的时间方面的写作习惯。此外，如果请求，服务还会返回其每项可用消费偏好的可能性得分。

有关使用服务的更多信息，请参阅

-   [请求概要文件](/docs/services/personality-insights/input.html)
-   [了解 JSON 概要文件](/docs/services/personality-insights/output.html)
-   [了解 CSV 概要文件](/docs/services/personality-insights/output-csv.html)

### 可视化概要文件
{: #visualize}

服务提供了用于支持概要文件图形可视化的 JavaScript 文件的集合。通过这些脚本，可更方便地将服务用于高速缓存和内容分发网络。这些脚本依赖于具有数据驱动的文档 (`D3.js`) 库的 JavaScript、jQuery、HTML 和 SVG 来描述结果。有关这些客户机端文件的信息，请参阅[使用软件开发包](#sdks)中引用的样本应用程序；有关 `D3.js` 的更多信息，请参阅 [d3js.org ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://d3js.org/){: new_window}。

### CORS 支持
{: #CORS}

服务支持跨源资源共享 (CORS)，以允许基于浏览器的客户机直接通过前端脚本向服务发出异步请求。CORS 支持客户机向发起请求的域之外的域请求资源；它还支持 Web 应用程序绕过同源安全策略，否则该策略会阻止此类请求。有关更多信息，请参阅 [enable-cors.org ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://enable-cors.org/){: new_window}。

## 使用软件开发包
{: #sdks}

{{site.data.keyword.personalityinsightsshort}} 服务支持用于简化应用程序开发的若干 SDK。这些 SDK 可用于许多热门的编程语言和平台，包括 Node.js、Java、Python 和 Apple&reg; iOS。有关 SDK 的完整列表以及使用 SDK 的信息，请参阅 [{{site.data.keyword.watson}} SDK](/docs/services/watson/getting-started-sdks.html)。所有 SDK 都可从 GitHub 上的 [watson-developer-cloud 名称空间 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://github.com/watson-developer-cloud){: new_window} 获取。

服务还提供了以下样本应用程序来帮助您入门：

-   可以在 [person-Insights-nodejs 存储库 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} 中访问使用 Node.js SDK 的应用程序。
-   可以在 [personality-insights-java 存储库 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://github.com/watson-developer-cloud/personality-insights-java){: new_window} 中访问使用 Java SDK 的应用程序。

对于移动开发，请参阅 [{{site.data.keyword.watson}} Developer Cloud Swift SDK ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://github.com/watson-developer-cloud/swift-sdk){: new_window}。所有 SDK 都支持使用服务凭证或认证令牌进行认证。

## 了解有关应用程序开发的更多信息
{: #learn}

{{site.data.keyword.personalityinsightsshort}} 服务支持两种典型的编程模型：*直接交互*和*通过代理中继*。在第一个模型中，客户机直接与服务进行通信；在第二个模型中，客户机和服务通过位于 {{site.data.keyword.Bluemix_short}} 中的代理应用程序来交换所有数据（请求和结果）。

有关使用 {{site.data.keyword.watson}} Developer Cloud 服务和 {{site.data.keyword.Bluemix_notm}} 的更多信息，请参阅以下内容：

-   有关使用 {{site.data.keyword.watson}} 服务和 {{site.data.keyword.Bluemix_notm}} 的简介，请参阅 [{{site.data.keyword.watson}} 和 {{site.data.keyword.Bluemix_notm}} 入门](/docs/services/watson/index.html)。
-   有关在 {{site.data.keyword.Bluemix_notm}} 中开发 {{site.data.keyword.watson}} 服务应用程序的独立于语言的简介，请参阅 [{{site.data.keyword.Bluemix_notm}} 开发方法](/docs/services/watson/getting-started-bluemix.html)。
-   有关可用于开发 {{site.data.keyword.watson}} 应用程序的两种编程模型的信息，请参阅 [{{site.data.keyword.watson}} 服务的编程模型](/docs/services/watson/getting-started-develop.html)：
    -   使用“通过代理中继”时，客户机依赖于位于 {{site.data.keyword.Bluemix_notm}} 中的代理服务器来与服务进行通信；客户机通过代理应用程序传递所有请求。通过代理中继请求仅依赖于服务凭证向服务进行认证；请参阅 [{{site.data.keyword.watson}} 服务的服务凭证](/docs/services/watson/getting-started-credentials.html)。
    -   使用“直接交互”时，客户机仅使用 {{site.data.keyword.Bluemix_notm}} 中的代理应用程序来获取服务的认证令牌，在此之后客户机直接与服务进行通信。直接交互仅使用服务凭证来获取令牌；请参阅[用于认证的令牌](/docs/services/watson/getting-started-tokens.html)。
-   有关控制对所有 {{site.data.keyword.watson}} 服务执行的缺省请求日志记录的信息，请参阅[控制对 {{site.data.keyword.watson}} 服务的请求日志记录](/docs/services/watson/getting-started-logging.html)。
