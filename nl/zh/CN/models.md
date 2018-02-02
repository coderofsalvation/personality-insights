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

# 个性模型
{: #models}

{{site.data.keyword.personalityinsightsshort}} 服务是根据语言心理学并采用数据分析算法开发的。该服务可分析您发送的内容，然后返回输入作者的个性概要文件。服务基于三个模型来推断个性特征：
{: shortdesc}

-   *大五类人格*个性特征表示通常用于描述个人如何参与社会生活的一种使用最广泛的模型。该模型包含五个主要维度：
    -   [*随和性*](/docs/services/personality-insights/agreeableness.html)是指个人对待他人是否具有同情心、是否乐于合作方面的倾向。
    -   [*尽责性*](/docs/services/personality-insights/conscientiousness.html)是指个人的行为方式是否有条理、是否思虑周全方面的倾向。
    -   [*外倾性*](/docs/services/personality-insights/extraversion.html)是指个人在寻求通过他人陪伴获得激励方面的倾向。
    -   [*情绪程度*](/docs/services/personality-insights/emotional-range.html)，也称为*情绪不稳定性*或*自然反应*，是指个人情绪对其周围环境敏感的程度高低。

    -   [*开放性*](/docs/services/personality-insights/openness.html)是指个人对体验各种活动所持开放态度的程度高低。

    上述每个顶级维度都有六个构面，用于根据该维度进一步描绘个人的特征。
-   [需求](/docs/services/personality-insights/needs.html)用于描述产品的哪些方面能够引起个人的共鸣。该模型包含 12 个特征需求。
-   [价值观](/docs/services/personality-insights/values.html)描述了会影响个人决策的激励因素。该模型包含五个值。

有关这些模型是如何开发的以及服务如何使用这些模型的更多信息，请参阅[服务背后的科学](/docs/services/personality-insights/science.html)。

## 大五类人格个性特征描述
{: #bigFive}

每个“大五类人格”维度通过三个表进行描述：

-   *构面*介绍维度的构面并描述在每个构面中得分高的个人。
-   *特征范围*提供了可能适用于其得分或多或少证实了该维度每个构面的个人的一般描述，以及可能描述了此类个人的术语。要获取方便阅读的单页表（其中汇总了所有五个维度的各构面的*特征范围*表），请参阅 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Facet-Characteristics.pdf" download="Personality-Insights-Facet-Characteristics.pdf">Personal-Insights-Facet-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="外部链接图标" title="外部链接图标" class="style-scope doc-content"></a>。
-   *主维度和辅助维度*提供了表达该维度与其他维度的关系的信息，描述了个性特征的组合。该表深入说明主特征和辅助特征之间可能如何相互关联，以表示个人的综合个性。要获取方便阅读的单页表（其中汇总了所有五个维度的*主特征和辅助特征*表），请参阅 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Dimension-Characteristics.pdf" download="Personality-Insights-Dimension-Characteristics.pdf">Personality-Insights-Dimension-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="外部链接图标" title="外部链接图标" class="style-scope doc-content"></a>。
