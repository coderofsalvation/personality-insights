---

copyright:
  years: 2015, 2017
lastupdated: "2017-09-13"

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

# 了解概要文件
{: #output}

1.  <span style="color:#003F69">如何解读服务返回的评分？</span>

    -   [解读数字结果](/docs/services/personality-insights/numeric.html)描述了如何解读服务返回的百分位数。它还包含有关服务可能返回的行为百分比以及可选的原始评分和消费偏好的信息。

1.  <span style="color:#003F69">为什么向维度的构面添加评分不会生成该维度的评分？</span>

    -   [个性特征的百分位数](/docs/services/personality-insights/numeric.html#percentiles)回答了此问题。总的来说，服务会独立地计算每个维度和构面的规范化百分位数。维度与其构面之间不存在数学关系。

1.  <span style="color:#003F69">何时使用原始评分而不使用百分比评分？</span>

    -   [个性特征的原始评分](/docs/services/personality-insights/numeric.html#rawScores)提供了对此选项的深入说明。简而言之，如果要为特定场景开发定制规范化，或者不需要与样本群体进行比较，那么可以使用原始评分。如果需要了解如何将作者的结果与样本群体进行比较，请使用百分位数评分。

1.  <span style="color:#003F69">如何将原始评分规范化为百分位数评分？</span>

    -   [个性特征的原始评分](/docs/services/personality-insights/numeric.html#rawScores)提供了用于规范化原始评分的高级指导信息，并讨论了 {{site.data.keyword.IBM_notm}} 的规范化方法。

1.  <span style="color:#003F69">如何解读 {{site.data.keyword.personalityinsightsshort}} 可视化？</span>

    -   [解读数字结果](/docs/services/personality-insights/numeric.html)描述了如何解读可视化中显示的数字结果。
