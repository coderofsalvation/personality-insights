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

# 解读数字结果
{: #numeric}

{{site.data.keyword.personalityinsightsshort}} 服务会为每个个性特征和行为特征以及每个消费偏好返回数字结果。这些值提供的信息各不相同。
{: shortdesc}

对于阿拉伯语和韩语输入，服务无法为一些个性特征生成有意义的百分位数和原始评分。有关更多信息，请参阅[阿拉伯语和韩语输入的限制](#limitations)。
{: note}

## 个性特征的百分位数
{: #percentiles}

对于每个请求，服务始终会将规范化得分报告为每个“大五类人格”、“价值观”和“需求”个性特征的 `percentile`（百分位数）。规范化得分表示基于服务从输入文本所推断特质的每个特征的百分位数排名。服务通过将作者文本的原始评分与样本群体的结果进行比较来计算规范化得分。服务将每个百分位数报告为范围在 0 到 1 之间的双精度值。

例如，个性特征 `big5_extraversion` 的百分位数 `0.64980796071382` 指示作者在该特征的得分排在第 65 位百分位数。作者的写作内容表明倾向程度大于 64% 且小于样本群体的 34%。百分位数的精度取决于作为输入随请求提交的字数。有关更多信息，请参阅[提供足够的输入](/docs/services/personality-insights?topic=personality-insights-input#sufficient)。


为“大五类人格”维度和构面报告的百分位数之间不存在数学关系。服务会根据调查参与者对相应维度或构面的评分以及所使用字数之间的相关性，独立地计算每个维度和构面的规范化百分位数。因此，尽管构面提供了维度的更细颗粒度描述，但为维度的六个构面添加得分并不一定会生成该维度的百分位数。对于原始评分也一样。
{: note}

## 个性特征的原始评分
{: #rawScores-numeric}

如果对请求的 `raw_scores` 查询参数指定 `true`，那么服务会为每个个性特征报告 `raw_score`。原始评分表示仅基于作者文本和该特征的模型的特征得分。在生成原始评分时，服务不将结果与样本群体进行比较。原始评分可以解读为作者参加个性测试会获取的得分。

服务将每个原始评分报告为范围在 0 到 1 之间的双精度值。通常得分越高，表示作者具有该特征的可能性越大。但是，原始评分必须作为总体进行考虑：实际的值范围可能比 0 到 1 要小得多，因此必须在总体得分及其范围的上下文中考虑各个得分。但是通常情况下，个性特征 `big5_extraversion` 的原始评分（例如，`0.56817738781166`）指示作者很可能会在个性测试上获取此得分。将此原始评分与前一部分中针对同一作者和特征所报告的规范化百分位数进行比较。

服务将原始评分提供给希望针对特定场景应用定制规范化的用户，或者不需要与样本群体进行比较的用户。希望了解如何将作者特征与大型样本群体进行比较的用户，可以使用规范化得分。希望从原始数据得出其自己的规范化百分位数得分的用户，可以将原始评分与其他样本群体进行比较，并将其他方法应用于规范化。

要将原始评分规范化为特定特征的百分位数，请将原始评分与已知该特征的平均值和标准差的样本群体进行比较。例如，{{site.data.keyword.IBM_notm}} 开展了多项研究，以收集来自大型推特用户样本群体的数据。{{site.data.keyword.IBM_notm}} 计算了用户在每个个性特征上的得分，然后确定了每个特征的平均值和标准差。为了计算根据其输入文本分析而推断出的原始评分的百分位数得分，服务使用从其样本推特群体得出的针对该特征的平均值和标准差。

## 行为特征的百分比
{: #percentages}

如果提交其内容项具有时间戳记的 JSON 数据，那么服务将为每个行为特征报告 `percentage`（百分比）。行为特征用于确定输入的时间分布。百分比指示在一周的每天和一天的各时间中发生的内容项的比例。例如，行为特征 `behavior_0000` 的百分比 `0.456109445005` 表示，大约有 46% 的内容项是在午夜到凌晨 1:00 之间创建的。

## 消费偏好的得分
{: #scores}

如果对请求的 `consumption_preferences` 查询参数指定 `true`，那么服务在报告消费偏好时，会包含每个偏好的 `score`（得分）。服务从根据输入文本推断出的个性特征来得出该得分。得分是双精度值，指示文本的作者偏好该项的可能性。这指示的是偏好，而不是规范化百分比。

对于某些偏好，得分为以下三个值之一：

-   `0.0`：作者偏好该项的可能性非常小。对于某些偏好，可以将此值解读为作者的兴趣水平较低。
-   `0.5`：作者对于该项是中性的。对于某些偏好，此值可能表示作者的兴趣水平为中等。
-   `1.0`：作者偏好该项的可能性非常大。对于某些偏好，此值指示兴趣水平很高。

对于其他偏好，此得分表示二进制值。输入文本的作者不可能 (`0.0`) 或很可能 (`1.0`) 对该项感兴趣，或者作者的兴趣水平较低或较高。在某些情况下，得分可以表示简单的“是”或“否”响应（例如，用户是否可能有参加社会事业的志愿活动经验）。

有关按类别及其结果范围列出的所有偏好的完整列表，请参阅[消费偏好](/docs/services/personality-insights?topic=personality-insights-preferences)。

## 阿拉伯语和韩语输入的限制
{: #limitations}

对于阿拉伯语和韩语输入，服务的模型无法为部分个性特征生成有意义的结果。对于以下特征，规范化百分位数得分始终为 `0.5`，原始评分始终为原始分布的平均值。其中每个特征的 `significant` 字段始终为 `false`。*不要*依赖于这些特征的结果作为作者个性概要文件的一部分。

<table>
  <caption>表 1. 其结果没有意义的特征</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      特征
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      没有意义的<br/>阿拉伯语结果
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      没有意义的<br/>韩语结果
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      大五类人格维度
    </td>
    <td style="text-align:left; vertical-align:top">
      情绪程度
    </td>
    <td style="text-align:left; vertical-align:top">
      无
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      大五类人格构面
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; line-height:110%; padding:0px">
          *随和性*：利他主义、合作、谦逊和信任
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *尽责性*：追求成就和有责任心
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *外倾性*：开朗和友善（外向）
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *情绪程度*：愤怒（易怒）、易焦虑、无节制和自我意识
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *开放性*：冒险性、想像力和才智
        </li>
      </ul>
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; padding:0px">
          *外倾性*：寻求刺激
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      需求
    </td>
    <td style="text-align:left; vertical-align:top">
      理想、自由、爱、实际和结构
    </td>
    <td style="text-align:left; vertical-align:top">
      自由和稳定
    </td>
  </tr>
  </tr>
    <td style="text-align:left; vertical-align:top">
      价值观
    </td>
    <td style="text-align:left; vertical-align:top">
      自我提升
    </td>
    <td style="text-align:left; vertical-align:top">
      保守
    </td>
  </tr>
</table>
