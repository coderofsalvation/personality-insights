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

# 性格模型
{: #models}

{{site.data.keyword.personalityinsightsshort}} 服務是根據語言心理學並結合資料分析演算法而開發。服務會分析您傳送的內容，並針對該輸入的作者傳回性格設定檔。服務會根據三個模型來推斷性格特質：
{: shortdesc}

-   *五大性格特質* 代表在概括描述一個人如何與世界互動時最廣泛使用的模型。此模型包括五項主要維度：
    -   [*隨和*](/docs/services/personality-insights?topic=personality-insights-agreeableness) 是一個人對其他人具有同情心且願意合作的傾向。
    -   [*自律*](/docs/services/personality-insights?topic=personality-insights-conscientiousness) 是一個人舉止經過組織或深思的傾向。
    -   [*外向*](/docs/services/personality-insights?topic=personality-insights-extraversion) 是一個人在他人陪伴下尋求刺激的傾向。
    -   [*情緒表達幅度*](/docs/services/personality-insights?topic=personality-insights-emotionalRange)，也稱為*神經質* 或*自然反應*，是個人的情緒對其環境的敏感程度。
    -   [*開放性*](/docs/services/personality-insights?topic=personality-insights-openness) 是一個人樂於體驗不同活動的程度。

    這些頂層維度各有六個面向，以根據該維度進一步描述一個人。
-   [需求](/docs/services/personality-insights?topic=personality-insights-needs)描述產品的哪些方面會與一個人產生共鳴。此模型包括十二項特質需求。
-   [價值觀](/docs/services/personality-insights?topic=personality-insights-values)描述影響一個人決策的激勵因素。此模型包括五種價值。

如需模型開發方式以及服務如何使用這些模型的相關資訊，請參閱[服務背後的科學](/docs/services/personality-insights?topic=personality-insights-science)。

## 五大性格特質的說明
{: #bigFive}

每一個「五大性格特質」維度各以三個表格來說明：

-   *面向* 表格引進維度的面向，以及說明在各面向獲得高評分的個人。
-   *特質範圍* 表格針對評分或多或少可證明維度各面向的個人，提供一般性說明，以及可以形容這些個人的詞彙。<a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Facet-Characteristics.pdf" download="Personality-Insights-Facet-Characteristics.pdf">Personality-Insights-Facet-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="外部鏈結圖示" title="外部鏈結圖示"></a> 中有一個便利的單頁表格，針對所有五個維度的面向來彙總*特質範圍* 表格。
-   *主要和次要維度* 表格代表在不同維度之間建立關聯的資訊，說明性格特質的組合。此表格提供主要與次要特質如何相互關聯的洞察分析，以呈現個人的綜合性格。<a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Dimension-Characteristics.pdf" download="Personality-Insights-Dimension-Characteristics.pdf">Personality-Insights-Dimension-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="外部鏈結圖示" title="外部鏈結圖示"></a> 中有一個便利的單頁表格，針對所有五個維度來彙總*主要和次要維度* 表格。
