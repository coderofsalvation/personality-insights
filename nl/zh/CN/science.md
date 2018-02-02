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

# 服务背后的科学
{: #science}

在心理学、市场营销和其他领域中，广为接受的一个理论是，人类的语言反映了个性、思维方式、社会关系和情绪状态。根据我们使用特定类别字词的频率，可以找出这些特征的线索。一些研究人员发现，根据在写作（例如，博客、短文和推文）中用词的变化，可以预测多种个性方面（[Fast 和 Funder，2008 年](/docs/services/personality-insights/references.html#fast2008)；[Gill 等人，2009 年](/docs/services/personality-insights/references.html#gill2009)；[Golbeck 等人，2011 年](/docs/services/personality-insights/references.html#golbeck2011)；[Hirsh 和 Peterson，2009 年](/docs/services/personality-insights/references.html#hirsh2009)；以及 [Yarkoni，2010 年](/docs/services/personality-insights/references.html#yarkoni2010)）。
{: shortdesc}

{{site.data.keyword.IBM_notm}} 开展了一组研究，以了解根据社交媒体数据推断出的个性特征是否能预测人们的行为和偏好。{{site.data.keyword.IBM_notm}} 发现，具有特定个性特征的人对信息收集和信息传播任务的响应和推文转发数量更高。例如，在“寻求刺激”上得分高的人响应的可能性较高，而在“谨慎”上得分高的人响应的可能性较低（[Mahmud 等人，2013 年](/docs/services/personality-insights/references.html#mahmud2013)）。与此类似，在“谦虚”、“开放性”和“友善”上得分高的人传播信息的可能性较高（[Lee 等人，2014 年](/docs/services/personality-insights/references.html#lee2014)）。

{{site.data.keyword.IBM_notm}} 还发现，根据社交媒体语言推断出的“开放性”得分高而“情绪程度”（情绪不稳定性）得分低的人更愿意积极响应（例如，通过点击广告链接或关注帐户），这些结果已通过基于调查的参考标准检查得到证实。例如，瞄准“开放性”得分高和“情绪程度”得分低的前 10% 的用户可将点击率从 6.8% 增加到 11.3%，并将关注率从 4.7% 提高到 8.8%。

对于根据社交媒体数据计算出的特征，最近的多项研究揭示了类似的结果。最近对零售店数据开展的一项研究发现，在“条理性”、“自律性”和“谨慎”上得分高而在“无节制”上得分低的人，响应优惠券的可能性比随机群体高出 40%。第二项研究发现，具有特定价值观的人表现出特定的阅读兴趣（[Hsieh 等人，2014 年](/docs/services/personality-insights/references.html#hsieh2014)）。例如，在“自我超越”价值观上得分更高的人表现出对阅读环保相关文章感兴趣，在“自我提升”价值观上得分更高的人表现出对阅读工作相关文章感兴趣。第三项对超过 600 个推特用户开展的研究发现，可以根据个人的个性特征来预测其品牌偏好，准确性为 65%。

以下各部分在这些高级别的发现结果基础上进一步扩展，描述了 {{site.data.keyword.personalityinsightsshort}} 服务背后的研究和开发工作。有关将该服务应用于实际场景的研究的更多信息，请参阅[服务实战](/docs/services/personality-insights/applied.html)。

## 了解个性模型
{: #researchModels}

针对 {{site.data.keyword.personalityinsightsshort}} 服务，{{site.data.keyword.IBM_notm}} 开发了多个模型，用于根据文本信息推断“大五类人格”维度和构面、“需求”和“价值观”的得分。服务所报告的模型基于心理学、心理语言学和市场营销领域的研究：

-   [大五类人格](/docs/services/personality-insights/models.html)是心理学家开发的个性模型中，研究最为成功的一种个性模型（[Costa 和 McCra，1992 年](/docs/services/personality-insights/references.html#costa1992)以及 [Norman，1963 年](/docs/services/personality-insights/references.html#norman1963)）。这也是用于描述个人通常如何参与社会生活的一种使用最广泛的个性模型。服务将计算模型的 5 个维度和 30 个构面。维度通常用助记符 *OCEAN* 表示，其中 *O* 表示“开放性”、*C* 表示“尽责性”、*E* 表示“外倾性”、*A* 表示“随和性”、*N* 表示“情绪不稳定性”。（因为术语“情绪不稳定性”可能具有特定的临床意义，所以服务将此类洞见放在更普遍适用的标题“情绪程度”下。）
-   [需求](/docs/services/personality-insights/needs.html)是人类行为的一个重要方面。研究文献表明，有多种类型的人类需求是普遍存在的，并且直接影响消费者行为（[Kotler 和 Armstrong，2013 年](/docs/services/personality-insights/references.html#kotler2013)以及 [Ford，2005 年](/docs/services/personality-insights/references.html#ford2005)）。在市场营销文献中，服务所报告的 12 个需求类别描述为，人们在考虑产品或服务时希望满足的欲望。
-   [价值观](/docs/services/personality-insights/values.html)传达的是对个人最重要的东西。这些东西是“值得向往、超越情境的目标，有着不同的重要性，是人们生活的指导原则”（[Schwartz，2006 年](/docs/services/personality-insights/references.html#schwartz2006)）。Schwartz 概括了所有价值观共有的五个特征：(1) 价值观是信念；(2) 价值观是动机性构想；(3) 价值观超越具体行动和情境；(4) 价值观指导对行动、策略、人员和事件的选择或评估；以及 (5) 价值观的相对重要性各不相同，因此可以相应地进行排名。服务将计算由 Schwartz 提出，并在超过 20 个国家或地区得到证实的五个基本人类价值观（[Schwartz，1992 年](/docs/services/personality-insights/references.html#schwartz1992)）。

## 如何推断个性特征
{: #researchInfer}

{{site.data.keyword.personalityinsightsshort}} 服务基于开放式词汇表方法从文本信息推断个性特征。此方法反映了有关个性推断的最新研究趋势（[Arnox 等人，2017 年](/docs/services/personality-insights/references.html#arnoux2017)、[Schwartz 等人，2013 年](/docs/services/personality-insights/references.html#schwartz2013)以及 [Plank 和 Hovy，2015 年](/docs/services/personality-insights/references.html#plank2015)）。

服务首先对输入文本进行记号化，以在 *n* 维空间中开发一种表示法。服务使用名为 [GloVe ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](http://nlp.stanford.edu/projects/glove/){: new_window} 的开放式源代码字嵌入技术来获取输入文本中字词的向量表示法（[Pennington 等人，2014 年](/docs/services/personality-insights/references.html#pennington2014)）。然后，服务将此表示法提供给机器学习算法，此算法将推断出具有“大五类人格”、“需求”和“价值观”特征的个性概要文件。为了培训此算法，服务使用了从对数千个用户开展的调查中获取的得分，以及来自这些用户推特订阅源中的数据。

{{site.data.keyword.IBM_notm}} 以相同方式为所有支持的语言开发了模型。这些模型的开发独立于用户人口统计信息，例如年龄、性别或文化。未来，{{site.data.keyword.IBM_notm}} 可能会开发特定于不同人口统计信息类别的模型。

较早版本的服务对其机器学习模型使用的是《语言查询与字词计数》(LIWC) 心理语言学字典。但是，刚才描述的开放式词汇表方法的性能优于基于 LIWC 的模型。有关服务对每种语言的平均“平均绝对误差”(MAE) 和相关性方面精度的更多信息，请参阅[服务精确程度](#researchPrecise)。有关提供输入文本以获取最准确结果的指导信息，请参阅[提供足够的输入](/docs/services/personality-insights/input.html#sufficient)。

## 服务精确程度
{: #researchPrecise}

{{site.data.keyword.IBM_notm}} 开展了验证研究，以了解服务的个性概要文件推断方法的准确性。{{site.data.keyword.IBM_notm}} 针对所有特征和语言，收集了 1500 到 2000 个参与者的调查响应和推特订阅源。为了建立*参考标准*，参与者参加了四组标准心理测量测试：

-   50 项“大五类人格”，来源于“国际个性项目库”(IPIP)
-   120 项“构面”，来源于 IPIP“情绪不稳定性”、“外倾性”和“开放性”(IPIP-NEO)
-   52 项基本“需求”，由 {{site.data.keyword.IBM_notm}} 开发
-   26 项基本“价值观”，由 Schwartz 开发

然后，{{site.data.keyword.IBM_notm}} 将其模型派生的得分与推特用户的基于调查的得分进行了比较。根据这些结果，{{site.data.keyword.IBM_notm}} 确定了不同类别个性特征的推断得分与实际得分之间的[平均“平均绝对误差”](#preciseMAE)和[平均相关性](#preciseCorrelation)。[每个语言的平均 MAE 和相关性](#precisePerLanguage)提供了每种受支持语言的统计值。

### 平均“平均绝对误差”
{: #preciseMAE}

*平均“平均绝对误差”(MAE)* 是用于测量实际值与预测值之间差值的度量值。对于 {{site.data.keyword.personalityinsightsshort}} 服务，实际值（即参考标准）是通过管理个性调查获取的个性得分。预测值是服务的模型所生成的得分。

{{site.data.keyword.IBM_notm}} 通过利用实际得分与预测得分之间绝对差值的平均值计算出 MAE。{{site.data.keyword.IBM_notm}} 之所以使用绝对值，是因为对实际值的预测略有偏差是无关紧要的；只要存在差异，就会根据误差量级对模型执行惩罚。MAE 越低，模型的性能越好。对于 MAE，{{site.data.keyword.IBM_notm}} 使用的量表为 0 到 1，其中 0 表示无误差（预测值与实际值完全相同），1 表示最大误差。

### 平均相关性
{: #preciseCorrelation}

*平均相关性*是测量两个变量相互依赖关系的统计术语。{{site.data.keyword.IBM_notm}} 使用此度量值测量了不同类别个性特征的推断得分与实际得分之间的相关性。如果预测得分与实际结果密切相关，那么相关性得分就高，否则就低。

{{site.data.keyword.IBM_notm}} 测量相关性的量表为 -1 到 1：1 表示完美的直接（上升）线性关系，-1 表示完美的逆（下降）线性关系。在其他所有情况下，值都位于这两个极值之间。如果变量是独立的（即完全没有任何关系），那么相关性为 0。

{{site.data.keyword.IBM_notm}} 会寻找接近 1 的数字，从而获得最佳预测。但是，个性很难仅根据文本进行预测，并且对于这些类型的心理模型，也很少看到相关性超过 0.4。在此领域的研究文献中，高于 0.2 的相关性即视为可接受。

### 每种语言的平均 MAE 和相关性
{: #precisePerLanguage}

下表显示了 {{site.data.keyword.personalityinsightsshort}} 服务的每种语言的平均 MAE 和相关性结果。这些结果证明该服务在根据文本数据推断个性方面处在最前沿，如 [Schwartz 等人（2013 年）](/docs/services/personality-insights/references.html#schwartz2013)以及 [Plank 和 Hovy（2015 年）](/docs/services/personality-insights/references.html#plank2015)所指示。

<table>
  <caption>表 1. 按语言列出的平均 MAE 和相关性</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      语言
    </th>
    <th style="text-align:center; vertical-align:bottom">
      大五类人格维度
    </th>
    <th style="text-align:center; vertical-align:bottom">
      大五类人格构面
    </th>
    <th style="text-align:center; vertical-align:bottom">
      需求
    </th>
    <th style="text-align:center; vertical-align:bottom">
      价值观
    </th>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **英语**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      平均 MAE
    </td>
    <td style="text-align:center">
      0.12
    </td>
    <td style="text-align:center">
      0.12
    </td>
    <td style="text-align:center">
      0.11
    </td>
    <td style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      平均相关性
    </td>
    <td style="text-align:center">
      0.33
    </td>
    <td style="text-align:center">
      0.28
    </td>
    <td style="text-align:center">
      0.22
    </td>
    <td style="text-align:center">
      0.24
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **西班牙语**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      平均 MAE
    </td>
    <td style="text-align:center">
      0.10
    </td>
    <td style="text-align:center">
      0.12
    </td>
    <td style="text-align:center">
      0.12
    </td>
    <td style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      平均相关性
    </td>
    <td style="text-align:center">
      0.35
    </td>
    <td style="text-align:center">
      0.21
    </td>
    <td style="text-align:center">
      0.24
    </td>
    <td style="text-align:center">
      0.19
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **日语**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      平均 MAE
    </td>
    <td style="text-align:center">
      0.11
    </td>
    <td style="text-align:center">
      0.12
    </td>
    <td style="text-align:center">
      0.11
    </td>
    <td style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      平均相关性
    </td>
    <td style="text-align:center">
      0.27
    </td>
    <td style="text-align:center">
      0.22
    </td>
    <td style="text-align:center">
      0.25
    </td>
    <td style="text-align:center">
      0.19
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **阿拉伯语**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      平均 MAE
    </td>
    <td style="text-align:center">
      0.09
    </td>
    <td style="text-align:center">
      0.12
    </td>
    <td style="text-align:center">
      0.11
    </td>
    <td style="text-align:center">
      0.10
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      平均相关性
    </td>
    <td style="text-align:center">
      0.17
    </td>
    <td style="text-align:center">
      0.14
    </td>
    <td style="text-align:center">
      0.13
    </td>
    <td style="text-align:center">
      0.14
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **韩语**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      平均 MAE
    </td>
    <td style="text-align:center">
      0.11
    </td>
    <td style="text-align:center">
      0.12
    </td>
    <td style="text-align:center">
      0.11
    </td>
    <td style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      平均相关性
    </td>
    <td style="text-align:center">
      0.21
    </td>
    <td style="text-align:center">
      0.21
    </td>
    <td style="text-align:center">
      0.13
    </td>
    <td style="text-align:center">
      0.12
    </td>
  </tr>
</table>

为了计算百分位数得分，{{site.data.keyword.IBM_notm}} 收集了推特用户的超大数据集（对于英语，为 100 万个用户；对于韩语，为 200,000 个用户；对于阿拉伯语和日语，分别为 100,000 个用户；对于西班牙语，为 80,000 个用户），并计算了他们的个性特质。然后，{{site.data.keyword.IBM_notm}} 将每个已计算概要文件的原始评分与根据这些数据集确定的概要文件分布进行比较，以确定百分位数。

> **注：**对于阿拉伯语和韩语输入，服务无法为某些个性特征生成有意义的百分位数和原始评分。有关更多信息，请参阅[阿拉伯语和韩语输入的限制](/docs/services/personality-insights/numeric.html#limitations)。

## 了解消费偏好
{: #researchPrefs}

针对各种产品和服务，开展了个性与购买行为之间关系的研究：

-   [Chen（2007 年）](/docs/services/personality-insights/references.html#chen2007)在测试有机食品相关的偏好后指出，个人的个性特征在建立个人食品选择标准方面扮演着重要的角色。
-   [Schlegelmilch 等人（1996 年）](/docs/services/personality-insights/references.html#schlegelmilch1996)研究了个性变量与支持环保的购买行为之间的关系。作者表明，消费者的总体环保意识对绿色购买决定有着积极影响。
-   [Hymbaugh 和 Garrett（2007 年）](/docs/services/personality-insights/references.html#hymbaugh1974)调查了个性与跳伞运动之间的关系，发现在“冒险性”和“寻求刺激”上得分高的人通常会热爱跳伞运动。（有关更多信息，请参阅[风险情况分析](/docs/services/personality-insights/applied.html#otherRisk)。）

应用消费行为与个性之间的这些已知关系比较困难：其中大部分工作使用的是来源于调查的个性数据，并且其模型并非公开可用。因此，{{site.data.keyword.IBM_notm}} 决定直接学习这些消费偏好模型。培训模型时，{{site.data.keyword.IBM_notm}} 使用了从 {{site.data.keyword.personalityinsightsshort}} 服务作为特征返回的个性得分。因此，通过该服务应用这些模型来计算用户的个性特征时，预测可能更为准确。

## 如何推断消费偏好
{: #researchInferPrefs}

{{site.data.keyword.personalityinsightsshort}} 服务根据其个性概要文件的结果，推断输入文本作者的消费偏好。在现有文献中，{{site.data.keyword.IBM_notm}} 确定了 104 项消费偏好，这些偏好均已证明与个性相关，其中包括与购物、电影、音乐和其他类别相关的偏好。然后，{{site.data.keyword.IBM_notm}} 创建了一个心理测量调查来评估个人针对每种消费行为的倾向性。

{{site.data.keyword.IBM_notm}} 从其调查获得了大约 600 人的响应，并且还获得了这些人的推特数据（每个用户自己编写的推文超过 200 条）。{{site.data.keyword.IBM_notm}} 向服务提交了这些推文，以收集每个人的个性概要文件。然后，IBM 为每项消费偏好构建了一个分类器，其中输入特征集是个性信息。

为了包含在服务中，{{site.data.keyword.IBM_notm}} 仅选择了基于个性的分类至少比随机分类好 9% 的那些消费偏好。在最初的 104 项偏好中，有 42 项满足此标准，因此由服务公开为消费偏好。

<!--
COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016

## How media influence inferred characteristics

{{site.data.keyword.IBM_notm}} conducted a validation study to understand the effect of media on inferred characteristics. To determine the accuracy of the service's approach to estimating characteristics, {{site.data.keyword.IBM_notm}} compared scores that were derived by its models with survey-based scores for Twitter users (for instance, approximately 500 users for English and more than 600 for Spanish).

To establish ground truth, participants took three sets of standard psychometric tests: 50-item Big Five (derived from the International Personality Item Pool, or IPIP), 52-item fundamental Needs (developed by {{site.data.keyword.IBM_notm}}), and 26-item basic Values (developed by Schwartz). {{site.data.keyword.IBM_notm}} conducted the study in two phases:

-   For the first study, conducted in 2013, {{site.data.keyword.IBM_notm}} recruited 256 Twitter users ([Gou et al., 2014](/docs/services/personality-insights/references.html#gou2014)). Although the models were learned from different sources, {{site.data.keyword.IBM_notm}} found that for more than 80 percent of the Twitter users, scores for characteristics that were inferred for all three models correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80). Specifically, scores that were derived by the service correlated with survey-based scores as follows:
    -   For 80.8 percent of participants' Big Five scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.75)
    -   For 86.6 percent of participants' Needs scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80)
    -   For 98.21 percent of participants' Values scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.55)
-   For the second study, conducted in 2015, {{site.data.keyword.IBM_notm}} recruited another set of 237 Twitter users. The study found that for Big Five and Values, scores for inferred characteristics correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.07 and 0.21) for every Twitter user. For needs, such significant correlation was observed for 90 percent of the users (p value &lt; 0.05 and correlation coefficient between 0.01 and 0.20).

In both studies, participants also rated on a five-point scale how well each derived characteristic matched their perceptions of themselves. Their ratings suggest that the inferred characteristics largely matched their self-perceptions. Specifically, means of all ratings were above 3 ("somewhat") out of 5 ("perfect").

-   For the 256 Twitter users of the first study, means were 3.4 (with a standard deviation of 1.14) for Big Five, 3.39 (with a standard deviation of 1.34) for Needs, and 3.13 (with a standard deviation of 1.17) for Values.
-   For the 237 Twitter users of the second study, means were 3.31 (with a standard deviation of 1.18) for Big Five, 3.37 (with a standard deviation of 1.22) for Needs, and 3.36 (with a standard deviation of 1.18) for Values.

COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016
-->

## 有关个性调查的说明
{: #researchSurveys}

在开发 {{site.data.keyword.personalityinsightsshort}} 服务时，{{site.data.keyword.IBM_notm}} 依赖个性调查来确定用于个性推断的参考标准数据。参考标准是指通过直接观察获取的真实数据，而不是通过推断获取的数据。对于任何机器学习模型，典型的准确性度量方法是将模型推断的得分与参考标准数据进行比较；先前各部分描述了 {{site.data.keyword.IBM_notm}} 如何使用调查来验证服务的准确性。

以下说明阐明了如何使用个性调查和基于调查的个性估算：

-   完成个性调查需要很长时间。因此，结果会受到愿意并可参与 {{site.data.keyword.IBM_notm}} 研究的推特用户数的制约。{{site.data.keyword.IBM_notm}} 计划对更多推特用户及其他在线媒体（例如，电子邮件、博客和论坛）的用户开展验证研究。
-   基于调查的个性估算基于自我报告，这可能并不总是会真实反映出一个人的个性：某些用户可能会对此类调查提供干扰回答。为了减少干扰，{{site.data.keyword.IBM_notm}} 通过包含检查注意力的问题并舍弃填写速度过快的调查，从而过滤调查响应。
-   虽然推断的得分和基于调查的得分之间的相关性都是积极且有意义的，但结果隐含推断的得分可能并不总是与基于调查的结果相关。{{site.data.keyword.IBM_notm}} 外部的研究人员也开展了试验，以比较推断的得分与从调查获取的得分的匹配程度，但没有任何人报告了完全一致的匹配度：
    -   [Golbeck 等人（2011 年）](/docs/services/personality-insights/references.html#golbeck2011)报告称，将推断的得分与基于调查的得分匹配时，误差率为 10% 到 18%。
    -   [Sumner 等人（2012 年）](/docs/services/personality-insights/references.html#sumner2012)报告称，个性预测准确性约为 65%。
    -   [Maesresse 和 Walker（2006 年）](/docs/services/personality-insights/references.html#mairesse2006)报告称，“大五类人格”个性预测的准确性为 60% 到 70%。

通常，在研究文献中广为接受的一点是，个性调查中的自我报告得分并不总是与根据文本推断出的得分完全匹配。但是，更重要的是，{{site.data.keyword.IBM_notm}} 发现根据文本推断的特征能够可靠地预测各种现实世界的行为。
