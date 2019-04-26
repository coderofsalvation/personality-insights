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

# 使用指南
{: #guidance}

{{site.data.keyword.personalityinsightsshort}} 服务被用户应用于越来越多的用例。用户应用该服务通过店内多媒体终端向客户提供个性化的产品推荐。用户根据美国总统的国情咨文推断出总统个性，并对各位总统的个性差异进行研究和分析。此外，用户还将该服务与 {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} 产品服务组合中的另一个产品 {{site.data.keyword.watson}} Explorer 相集成，以展示投资顾问可如何根据投资者的个性特质提供适当的投资方案。（有关更多信息，请参阅[用例](/docs/services/personality-insights?topic=personality-insights-usecases)。）
{: shortdesc}

在这些用例及其他预期用例的整个开发过程中，{{site.data.keyword.IBM_notm}} 已经与银行、医疗保健提供者、客户体验管理公司和联邦机构进行了对话。这些对话通常会产生有关适用的使用方案的问题。

-   哪种类型的文本最适合用于推断个人的个性？文本是否必须具备反映性的本质？如果是，那么反映程度如何，以及如何测量反映程度？请参阅[哪种类型的文本最适合用于推断个性？](#optimal)
-   如何解读某个人写的有关另一个人的文本？可以从作者的虚构作品中推断出作者的个性吗？可以组合多人编写的文本来获取个性特质吗？请参阅[解读从不同类型文本中获取的结果](#interpreting)。
-   可以从转录或翻译服务生成的文本中推断出个性特质吗？请参阅[从生成的文本中推断个性](#inferring)。
-   个性特质可以应用于匹配个人、监视和预测心理健康，以及通过社交媒体监视激进和恶意元素等应用吗？请参阅[将个性特质用于特定应用](#applying)。
-   个人的个性会随年龄而变化吗？请参阅[个人的个性会随时间而变化吗？](#evolve)

## 哪种类型的文本最适合用于推断个性？
{: #optimal}

哪种类型的文本最适合用于推断个性？文本需要具备反映性、自我反映性、正式性还是非正式性？如何测量日常生活中的用词？此类用词是否具备反映性的本质？这些问题的答案可以帮助您选择最合适的输入来最有效地应用服务。

{{site.data.keyword.IBM_notm}} 对 {{site.data.keyword.personalityinsightsshort}} 服务开展的工作基于这样一个基本假设：一个人在日常生活中的用词可揭示其个性（[Pennebaker 等人，2001 年](/docs/services/personality-insights?topic=personality-insights-references#pennebaker2001)和 [Pennebaker 等人，2007 年](/docs/services/personality-insights?topic=personality-insights-references#pennebaker2007)）。该服务可以分析个人编写的有关其自身或任何主题的用词。要使服务生成准确的个性特质，个人必须选择并编写用词。

{{site.data.keyword.IBM_notm}} 认为，用于推断个人个性的文本最好需要具备反映性。反映性的写作会透露出作者的个人体验和响应。它要求作者在所选用词中表达一定的思想。例如，文本可以包含作者关于某人或某事的意见、态度、情绪和观察。也可以表达作者的好恶。但必须反映出作者选择的用词。

{{site.data.keyword.IBM_notm}} 在语言心理学文献中并未发现有明确的参考资料表明在用于推断个性的文本中需要具备反映性。但是，{{site.data.keyword.IBM_notm}} 确实发现一些研究使用了实验室环境中所收集文本的用词，在此环境中，要求人们围绕特定主题写出短文。此类型写作隐含要求具备一定程度的反映性。另一些研究使用了自然样本中的文本，例如各种主题的博客、推文、电子邮件，甚至是从游戏《*魔兽世界*》中提取的交流内容。所有这类研究均假设日常生活中的用词透露了个性，因为用词倾向于反映出作者的想法。

其他研究表明，感性写作、控制型写作、博客和语音转录都非常适合用于推断个性。相反，科学性文章在很大程度上并不适合用于推断个性。此外，文献表明，对于以下特点的文本，很难据以准确测量个性：

-   缺乏真实性，例如，反话、讽刺、密集编辑或多位作者
-   包含拼写错误、技术用语、多义词、否定语言，以及短语（而非单独的词语）
-   包含不合适的比较组，如专业写作与私人写作相比较，技术写作与感性写作相比较

## 解读从不同类型文本中获取的结果
{: #interpreting}

要分析的文本类型会对 {{site.data.keyword.personalityinsightsshort}} 服务结果的质量有很大的影响。以下各部分讨论如何解读从不同来源获取的结果：

-   [解读从有关他人的文本中获取的结果](#writingaboutothers)
-   [解读从虚构作品中获取的结果](#fictionalworks)
-   [解读从多人文本中获取的结果](#multipleindividuals)

### 解读从有关他人的文本中获取的结果
{: #writingaboutothers}

为了可靠地推断个人的个性，文本是必须*由*此人编写，还是可以是其他人编写的*有关*此人的文本？当一个人编写关于另一个人的文本时，从文本推断出的是谁的个性？

{{site.data.keyword.IBM_notm}} 的直觉是，写作始终会反映出作者的个性，不管主题是什么。例如，如果个人 A 编写有关个人 B 的文本，那么对该文本分析后，可推断出个人 A 的个性。虽然个人 A 编写的是有关个人 B 的内容，但选择用词来表达个人 B 相关内容的是个人 A。不过，{{site.data.keyword.IBM_notm}} 并未明确测试过此场景。

### 解读从虚构作品中获取的结果
{: #fictionalworks}

{{site.data.keyword.IBM_notm}} 建议不要根据虚构作品来推断作者的个性。作者在编写虚构作品时，会有意以不同方式描写每个人物，构造反映人物个性的对话，以及在脑海中预先设定每个人物的个性。

使用旨在反映个性化虚构人物个性的文本来推断该人物的创作者的个性，是不大靠得住的。虽然每个作者都有独特的风格，但这些人物仍然是有意预先编排的。不过，作者的个性可以从其非虚构类文章、访谈记录或其他作品（例如，简介、前言、致谢或题献）中推断出来。

### 解读从多人文本中获取的结果
{: #multipleindividuals}

{{site.data.keyword.personalityinsightsshort}} 服务的常见用例是分析品牌或公司的关注者。关注者定义为在推特或公共 Facebook 页面上关注公司的人。在此场景中，目标是提炼出公司关注者的总体个性。首选方法是收集由一个组的各个成员编写的足够文本，以计算每个个体成员的个性。然后，将这些个性群集成不同的组。这些组代表了关注公司且具有独特个性特征的角色。

如果组成员提供的文本不充分，那么可以将许多成员编写的文本组合在一起进行分析，从而为组生成平均或综合个性特质。此方法可以反映出该组的主导特性，但是这种方法的准确性会随着群体的多样性而下降。在解读通过汇总多人文本而获得的特质时，请务必谨慎。{{site.data.keyword.IBM_notm}} 在此领域的工作仍处于初始阶段；{{site.data.keyword.IBM_notm}} 在发现了令人信服的结果后会进行报告。

## 根据生成的文本推断个性
{: #inferring}

分析由转录或翻译服务生成的文本可能会影响 {{site.data.keyword.personalityinsightsshort}} 服务结果的可靠性。以下各部分讨论根据生成的文本推断个性的影响：

-   [根据语音转录推断个性](#transcription)
-   [根据翻译的文本推断个性](#translation)

### 根据语音转录推断个性
{: #transcription}

语音转录引擎（例如，{{site.data.keyword.IBM_notm}} {{site.data.keyword.speechtotextshort}} 服务）可从口头用词生成书面文本。不同的转录引擎具有不同的准确性范围。客户若要将语音转录成文本以用作 {{site.data.keyword.personalityinsightsshort}} 服务输入，就需要意识到这些结果可能因引擎性能而有很大差异。具体而言，{{site.data.keyword.IBM_notm}} 建议客户和业务合作伙伴针对以下两种类型的错误来确定转录质量：

-   *丢弃：*在转录中省略了口头用词。
-   *替代：*错误地转录了口头用词。

替代可能是更严重的问题，因为可能会引入讲话中不存在，但与用于确定个性的用词相匹配的用词。所以在使用转录的文本之前，请考虑手动更正测试文集内的文本，并统计找到的错误数。然后，将自动生成的文本的结果与手动更正的版本进行比较，以确定因转录错误而导致的结果差异。

### 根据翻译的文本推断个性
{: #translation}

语言翻译服务用于将以一种语言编写的文本翻译成另一种语言。与语音转录一样，问题是翻译的文本可否用作 {{site.data.keyword.personalityinsightsshort}} 服务的输入。{{site.data.keyword.IBM_notm}} 建议不要使用通过翻译服务获取的文本作为 {{site.data.keyword.personalityinsightsshort}} 服务的输入。根据翻译服务的不同，翻译和个性推断的结果都可能会有很大差异。用词及其含义和文化敏感性往往会在翻译中丧失，从而生成无效的结果。

{{site.data.keyword.IBM_notm}} 建议仅将以支持 {{site.data.keyword.personalityinsightsshort}} 服务的语言编写的文本用作输入。语言支持的服务版本：

-   以本机语言解析输入文本。
-   使用本机语言字典来识别个性特征。
-   使用针对本机语言校准的模型来生成统计结果。

如果必须分析翻译的文本，{{site.data.keyword.IBM_notm}} 建议您首先请一位语言专家人工翻译一些样本文本。然后，可以将 {{site.data.keyword.personalityinsightsshort}} 服务从人工翻译和机器翻译的文本中获取的结果进行比较，以了解结果中的差异。

随着业务需求的增加，{{site.data.keyword.IBM_notm}} 将继续添加更多语言。{{site.data.keyword.IBM_notm}} 了解 {{site.data.keyword.personalityinsightsshort}} 服务可能支持您本机语言的速度不够快，无法满足您的用途。{{site.data.keyword.IBM_notm}} 正在开展测试，将来自本机语言支持的结果与来自语言翻译服务的结果进行比较，并在研究结果可用时进行报告。

## 将个性特质用于特定应用
{: #applying}

{{site.data.keyword.personalityinsightsshort}} 服务可应用于无数用例。以下各部分描述如何使用个性特质来实现一些具体目的：

-   [匹配个人](#matching)
-   [监视和预测心理健康](#mentalhealth)
-   [通过社交媒体监视激进和恶意元素](#monitoring)

### 匹配个人
{: #matching}

在个人之间建立良好匹配可以改善关系中的互动和结果。此概念也适用于公司内的团队组建，以及在各行各业与客户进行的互动。在一项有关医患匹配的研究中，研究人员发现患者偏好选择与自己类似的医生。有效匹配医生和患者有助于患者树立信心，鼓励医患沟通，从而可以提高患者的顺从性，实现更成功的治疗（[Godager，2012 年](/docs/services/personality-insights?topic=personality-insights-references#godager2012)）。

个性还会影响专业人员和客户之间的互动偏好。例如，“尽责性”和“开放性”水平高的患者倾向于积极参与治疗过程的决策。“随和性”或“情绪不稳定性”水平高的患者倾向于以医生为主导来做出重要的健康决策（[Flynn 和 Smith，2007 年](/docs/services/personality-insights?topic=personality-insights-references#flynn2007)）。

### 监视和预测心理健康
{: #mentalhealth}

{{site.data.keyword.IBM_notm}} 认为疾病诊断最好由训练有素的医疗专业人员来执行。有可能能够通过个人的用词来检测出此人的一些心理状态迹象。但是，{{site.data.keyword.IBM_notm}} 尚未开展可作为参考标准的研究，或探索为此类工作建立科学基础的可能性。

对于有兴趣使用 {{site.data.keyword.personalityinsightsshort}} 服务进行心理健康诊断的客户和业务合作伙伴，欢迎针对此类用例设计并开展可作为参考标准的试验。此领域的积极和持续研究包括将个性与健康结果相关联的工作（[Israel 等人，2014 年](/docs/services/personality-insights?topic=personality-insights-references#israel2014)）。还包含旨在通过社交媒体预测产后抑郁和其他形式抑郁的工作（[DeChoudhury 等人，2013a](/docs/services/personality-insights?topic=personality-insights-references#dechoudhury2013a) 和 [De Choudhury 等人，2013b](/docs/services/personality-insights?topic=personality-insights-references#dechoudhury2013b)）。

### 通过社交媒体监视激进和恶意元素
{: #monitoring}

世界各地的政府机构一直在寻找各种方法，用于通过社交媒体渠道来检测个人或群体激进行为的早期信号。从个人的写作中推断个性是 {{site.data.keyword.personalityinsightsshort}} 服务的一项传统应用。因此，使用该服务通过社交媒体来推断激进和恶意元素是一种可行的用例，这也就不足为奇了。可靠的推断不仅需要个性特征，还需要其他大量属性（例如，性别、年龄和地理位置）。{{site.data.keyword.IBM_notm}} 尚未开展任何研究来证实或证伪此用例。欢迎客户和业务合作伙伴开展研究，以根据自己的具体目标和需求来探索此用例。

## 个人的个性会随时间而变化吗？
{: #evolve}

个人的个性会随时间而变化吗？如果会，应该多久使用一次 {{site.data.keyword.personalityinsightsshort}} 服务来推断个人的个性？对于个性在成年后即稳定不变的理论，各种不同的研究报告了支持和反对这一理论的证据。哈佛心理学家 William James 在其 1890 年出版的关于测量个性稳定性的重要著作*《心理学原理》(The Principles of Psychology)* 中指出：“大多数人年届 30 时，性格已然像坚硬成型的石膏一样，再也不会变软，再也不可能重塑了。”但更近期的研究报告称，个性确实能随时间而变化：

-   [Helson 等人（2002 年）](/docs/services/personality-insights?topic=personality-insights-references#helson2002)报告称，“个性变化在 30 岁以前最为明显，随后会进入平台期的这一想法并有没任何依据。”作者针对两个群组开展了一项跨越 40 年的纵向研究。他们指出，年龄段和社会大环境是影响成年人个性变化的重要因素。他们评论说：“这两个群组在中年时‘支配性’和‘独立性’得分最高，在个人主义文化达到巅峰的年代，‘责任感’得分最低。”
-   [Scollon 和 Diener（2006 年）](/docs/services/personality-insights?topic=personality-insights-references#scollon2006)着手检查了外倾性、情绪不稳定性、工作和关系满意度随时间变化的个体差异。作者指出，随着时间推移，工作和关系满意度提升与情绪不稳定性下降和外倾性上升相关联。
-   [Roberts 和 Mroczek（2008 年）](/docs/services/personality-insights?topic=personality-insights-references#roberts2008)评论说，存在“个性特质平均水平变化，以及在整个寿命内个体差异”的证据。作者指出，随着年龄的增长，人们在自信、同情心、自我控制和情绪稳定性方面都有所提升。这些变化在成年早期（20 到 40 岁）占主导地位。此外，个性特征的平均水平变化发生在中年和老年，这反映出个性特征可能在任何年龄发生变化。

根据这些研究，{{site.data.keyword.IBM_notm}} 建议 {{site.data.keyword.personalityinsightsshort}} 服务的用户始终使用最新的数据，并使用尽可能多的可用数据。此外，{{site.data.keyword.IBM_notm}} 进一步建议用户定期刷新个性特质，以捕获个人不断变化的个性。虽然 {{site.data.keyword.IBM_notm}} 倾向于认为个性是在一定界限内变化，但并没有开展相关研究来检查这一变化范围的上下限。

人们可能会问应该多久刷新一次个人的个性特质。{{site.data.keyword.IBM_notm}} 给出的指导意见是查找个人的新数据和文本是否可用。如果自获取某个人的个性特质以来，此人又创作了大量的新文本，那么可能值得刷新特质。如果人们选择接受个性会变化的观点，那么这种方法会捕获个性不断变化的本质。这还会使 {{site.data.keyword.personalityinsightsshort}} 服务受益于可处理更多用词，进而可提高服务结果的准确性。
