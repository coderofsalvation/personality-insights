---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-27"

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

# 关于
{: #about}

> **服务更新：***{{site.data.keyword.personalityinsightsshort}} 服务已于 2018 年 11 月 18 日更新。现在，在 {{site.data.keyword.cloud}} 伦敦位置提供了服务。有关更多信息，请参阅发行说明中的 [2018 年 11 月 18 日服务更新](/docs/services/personality-insights?topic=personality-insights-release-notes#November2018b)。*

{{site.data.keyword.personalityinsightsfull}} 服务提供了用于从社交媒体、企业数据或其他数字通信提炼洞察的应用程序编程接口 (API)。该服务使用语言分析从数字通信（例如，电子邮件、文本消息、推文和论坛帖子）推断个人的固有个性特征。
{: shortdesc}

服务可以从有潜在噪声的社交媒体中，推断出反映个人个性特征的特质。此外，还可以确定个人的消费偏好，这指示个人偏好各种产品、服务和活动的可能性。

## 个性特征
{: #models-index}

{{site.data.keyword.personalityinsightsshort}} 服务基于三个主要模型来推断个性特征：

-   **大五类人格**个性特征表示通常用于描述个人如何参与社会生活的一种使用最广泛的模型。该模型包含五个主要维度：*随和性*、*尽责性*、*外倾性*、*情绪程度*和*开放性*。每个维度有六个构面，用于根据该维度进一步描绘个人的特征。
-   **需求**用于描述产品的哪些方面可能引起个人的共鸣。该模型包含十二种性格需求：*兴奋*、*和谐*、*好奇*、*理想*、*接近*、*自我表达*、*自由*、*爱*、*实际*、*稳定*、*挑战*和*结构*。
-   **价值观**描述了会影响个人决策的激励因素。该模型包含五个价值观：*自我超越/帮助他人*、*保守/传统*、*享乐主义/享受生活*、*自我提升/取得成功*和*乐于接受改变/激动*。

有关更多信息，请参阅[个性模型](/docs/services/personality-insights?topic=personality-insights-models)。

## 消费偏好
{: #preferences-index}

根据从输入文本推断出的个性特征，服务还可以返回指示作者消费偏好的信息。消费偏好指示作者采用不同产品、服务和活动的可能性。服务将各个偏好分组为八个类别：*购物*、*音乐*、*电影*、*阅读和学习*、*健康和活动*、*志愿活动*、*关注环保*和*创业*。每个类别包含一到十几个不同的偏好。

有关更多信息，请参阅[消费偏好](/docs/services/personality-insights?topic=personality-insights-preferences)。

## 服务的优点
{: #benefits}

{{site.data.keyword.personalityinsightsshort}} 服务是 {{site.data.keyword.ibmwatson}} 平台的核心服务，可以提供多种洞察来帮助企业实现：

-   通过了解客户的偏好、改善客户满意度以及巩固客户关系，从而更深入地了解客户。
-   改善客户获取、保留和参与。
-   指导高度个性化的参与和互动，以更好地针对不同客户来定制产品、服务、营销活动和沟通。

有关可从服务获得哪些益处的更多信息，请参阅[用例](/docs/services/personality-insights?topic=personality-insights-usecases)。

## 语言支持
{: #languages-index}

服务支持以下语言。可以对请求和响应使用受支持语言的任何组合，但所有输入文本必须使用同一语言。有关更多信息，请参阅[指定请求和响应语言](/docs/services/personality-insights?topic=personality-insights-input#languages-input)。

<table style="width:75%">
  <caption>表 1. 支持的语言</caption>
  <tr>
    <th style="width:50%; text-align:center">
      请求语言
    </th>
    <th style="width:50%; text-align:center">
      响应语言
    </th>
  </tr>
  <tr>
    <td style="text-align:center; vertical-align:top">
      阿位伯语<br/>
      英语<br/>
      日语<br/>
      韩语<br/>
      西班牙语
    </td>
    <td style="text-align:center; vertical-align:top">
      阿位伯语<br/>
      英语<br/>
      日语<br/>
      韩语<br/>
      西班牙语<br/>
      巴西葡萄牙语<br/>
      法语<br/>
      德语<br/>
      意大利语<br/>
      简体中文<br/>
      繁体中文
    </td>
  </tr>
</table>

## HIPAA
{: hipaa}

美国健康保险可移植性和责任法案 (HIPAA) 支持不适用于 {{site.data.keyword.personalityinsightsshort}} 服务。服务无状态。它不在 {{site.data.keyword.cloud_notm}} 上存储任何用户数据。

## 了解有关服务的更多信息
{: #learn-index}

-   {{site.data.keyword.personalityinsightsshort}} 服务的[快速演示 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://personality-insights-demo.ng.bluemix.net/){: new_window} 分析输入文本，以阐明包含作者的消费偏好的个性特质。
-   {{site.data.keyword.watson}} [Starter Kits ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](http://www.ibm.com/watson/developercloud/starter-kits.html){: new_window} 中的应用程序演示了此服务。
-   [服务实战](/docs/services/personality-insights?topic=personality-insights-applied)和[服务背后的科学](/docs/services/personality-insights?topic=personality-insights-science)提供了有关服务所基于的研究的信息。
-   [{{site.data.keyword.cloud_notm}} 目录中的 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/catalog/services/personality-insights/){: new_window} {{site.data.keyword.personalityinsightsshort}} 服务描述了服务可用的价格套餐。
