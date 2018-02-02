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

# 關於
{: #about}

> **服務程式更新：***{{site.data.keyword.personalityinsightsshort}} 服務程式更新於 2017 年 10 月 13 日。現在性格設定檔的每一個 `Trait` 物件都包括一個 `significant` 欄位，以指出性格特質對於輸入語言而言是否有意義。此欄位會識別服務模型無法為阿拉伯文和韓文輸入產生有意義結果的那些特質。此版次的介面版本為 `2017-10-13`。如需此服務及其所有更新項目的相關資訊，請參閱[版本注意事項](/docs/services/personality-insights/release-notes.html)。*

{{site.data.keyword.personalityinsightsfull}} 服務提供「應用程式設計介面 (API)」，可從社交媒體、企業資料或其他數位通訊中衍生洞察分析。服務使用語言分析，從數位通訊（例如電子郵件、文字訊息、推文和討論區貼文）來推斷個人固有的性格特質。
{: shortdesc}

服務會從可能很吵雜的社交媒體，推斷反映個人性格特質的性格側寫。它也會判斷個人的消費喜好，進而指出其偏好各種產品、服務和活動的可能性。

## 性格特質
{: #models}

{{site.data.keyword.personalityinsightsshort}} 服務會根據三個主要模型來推斷性格特質：

-   **五大性格特質**代表在概括描述一個人如何與世界互動時最廣泛使用的模型。此模型包括五個主要維度：*隨和*、*責任感*、*外向*、*情緒表達幅度* 和*開放性*。每一個維度各有六個面向，以根據該維度進一步描述一個人。
-   **需求**描述產品的哪些方面會與一個人產生共鳴。此模型包括 12 項特質需求：*興奮*、*和諧*、*好奇心*、*理想*、*親密*、*自我表達*、*自由*、*愛*、*實際*、*穩定*、*挑戰* 和*結構*。
-   **價值觀**描述影響一個人決策的激勵因素。此模型包括五個值：*自我超越 / 幫助他人*、*保守 / 傳統*、*享樂主義 / 享受生活*、*自我提升 / 達到成功* 和*接受改變 / 興奮*。

如需相關資訊，請參閱[性格模型](/docs/services/personality-insights/models.html)。

## 消費喜好
{: #preferences}

服務也可以根據從輸入文字推斷的性格特質，傳回作者消費喜好的指示。消費喜好會指出作者喜好不同產品、服務和活動的可能性。服務將個人喜好分組成八個種類：*購物*、*音樂*、*電影*、*閱讀和學習*、*健康和活動*、*志願服務*、*環境關懷*，以及*企業家精神*。每一個種類各包含一到數十項個人喜好。

如需相關資訊，請參閱[消費喜好](/docs/services/personality-insights/preferences.html)。

## 服務的好處
{: #benefits}

作為 {{site.data.keyword.IBM_notm}}{{site.data.keyword.watson}} 平台的核心服務，{{site.data.keyword.personalityinsightsshort}} 服務可提供協助企業的洞察分析

-   獲悉其客戶的喜好、提升客戶滿意度，並加強客戶關係，以更深入地瞭解其客戶。
-   提升來客率、留客率與客戶參與率。
-   指導高度個人化的參與和互動，以針對個別客戶量身打造更適合他們的產品、服務、行銷活動和其他通訊。

如需如何善用服務功能的相關資訊，請參閱[使用案例](/docs/services/personality-insights/usecases.html)。

## 語言支援
{: #languages}

服務支援下列語言。您可以將任何組合的支援語言用於要求和回應，但所有輸入文字都必須使用相同的語言。如需相關資訊，請參閱[指定要求和回應語言](/docs/services/personality-insights/input.html#languages)。

<table style="width:75%">
  <caption>表 1. 支援的語言</caption>
  <tr>
    <th style="width:50%; text-align:center">
      要求語言
    </th>
    <th style="width:50%; text-align:center">
      回應語言
    </th>
  </tr>
  <tr>
    <td style="text-align:center; vertical-align:top">
      阿拉伯文<br/>
      英文<br/>
      日文<br/>
      韓文<br/>
      西班牙文
    </td>
    <td style="text-align:center; vertical-align:top">
      阿拉伯文<br/>
      英文<br/>
      日文<br/>
      韓文<br/>
      西班牙文<br/>
      巴西葡萄牙文<br/>
      法文<br/>
      德文<br/>
      義大利文<br/>
      簡體中文<br/>
      繁體中文
    </td>
  </tr>
</table>

## 進一步瞭解服務
{: #learn}

-   {{site.data.keyword.personalityinsightsshort}} 服務的[快速示範 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://personality-insights-demo.ng.bluemix.net/){: new_window} 可讓您分析輸入文字，以開發包括作者消費喜好的性格側寫。
-   {{site.data.keyword.watson}} Developer Cloud [Starter Kits ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://www.ibm.com/watson/developercloud/starter-kits.html){: new_window} 中的應用程式會示範此服務。
-   [運作中的服務](/docs/services/personality-insights/applied.html)和[服務背後的科學](/docs/services/personality-insights/science.html)提供此服務基礎研究的相關資訊。
-   [{{site.data.keyword.Bluemix_short}} 型錄中的 {{site.data.keyword.personalityinsightsshort}} 服務 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://console.ng.bluemix.net/catalog/services/personality-insights/){: new_window} 說明此服務適用的定價方案。
