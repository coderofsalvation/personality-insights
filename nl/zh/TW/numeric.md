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

# 解譯數值結果
{: #numeric}

{{site.data.keyword.personalityinsightsshort}} 服務會針對每一種性格和行為特質，以及每一種消費喜好，傳回數值結果。這些值在其提供的資訊中各不相同。
{: shortdesc}

若為阿拉伯文和韓文輸入，服務無法為一些性格特質產生有意義的百分位數和原始評分。如需相關資訊，請參閱[阿拉伯文和韓文輸入的限制](#limitations)。
{: note}

## 性格特質的百分位數
{: #percentiles}

對於每一個要求，服務一律會針對每一個「五大性格特質」、「價值觀」和「需求」性格特質，以 `percentile` 來報告的正規化評分。正規化評分代表每一個特質的百分位數等級（根據服務從輸入文字推斷的品質）。服務會將作者文字的原始評分與樣本母體的結果做比較，以計算正規化評分。服務會以範圍 0 到 1 的倍精準數來報告每一個百分位數。

例如，性格特質 `big5_extraversion` 的百分位數為 `0.64980796071382`，表示作者針對特質的評分落在第 65 個百分位數。作者的書寫內容顯現出的傾向程度，在樣本母體中大於百分之 64，小於百分之 34。百分位數的精準度，取決於在要求中提交作為輸入的字數。如需相關資訊，請參閱[提供足夠的輸入](/docs/services/personality-insights?topic=personality-insights-input#sufficient)。


針對「五大性格特質」維度和面向所報告的百分位數之間，不存在任何數學關係。服務會根據意見調查參與者在該維度和面向的評分與用字之間的相關性，分別計算每一個維度和面向的正規化百分位數。因此，即使面向提供更精細的維度說明，但針對維度的六個面向增加評分並不一定會產生該維度的百分位數。原始評分也是如此。
{: note}

## 性格特質的原始評分
{: #rawScores-numeric}

如果您為要求的 `raw_scores` 查詢參數指定 `true`，則服務會報告每一個性格特質的 `raw_score`。原始評分代表僅根據作者文字和特質模型的特質評分。當它產生原始評分時，服務不會將結果與樣本母體比較。原始評分可解譯為作者將從性格測試獲得的評分。

服務會以範圍 0 到 1 的倍精準數來報告每一個原始評分。評分愈高通常表示作者具有該特質的可能性愈大。不過，原始評分必須以總數來考量：實際的值範圍可能遠小於 0 到 1，因此個別評分必須在整體評分及其範圍的背景下考量。但是一般而言，性格特質 `big5_extraversion` 的原始評分（例如`0.56817738781166`）表示作者可能在某個性格測試上已達到此評分。請將這個原始評分與針對前一節相同作者和特質所報告的正規化百分位數做比較。

針對想要為特定實務範例套用自訂正規化，或是不需要與樣本母體進行比較的使用者，服務可提供原始評分。使用者如果想要知道作者特質與大型樣本母體比較的結果，可以使用正規化評分。使用者如果想要從原始資料衍生衍生自己的正規化百分位數評分，可以將原始評分與不同的樣本母體做比較，並套用不同的方法來進行正規化。

若要將原始評分正規化為特定特質的百分位數，請將原始評分與已知特質之平均值和標準差的樣本母體做比較。例如，{{site.data.keyword.IBM_notm}} 曾做過研究，從 Twitter 使用者的大型樣本母體收集資料。{{site.data.keyword.IBM_notm}} 針對每一個性格特質來計算使用者的評分，然後再針對每一個特質來建立平均值和標準差。若要針對從輸入文字分析推斷的原始評分來計算百分位數評分，服務會將衍生自其 Twitter 樣本母體的平均值和標準差用於該特質。

## 行為特質的百分比
{: #percentages}

如果您提交內容項目含有時間戳記的 JSON 資料，則服務會針對每一個行為特質報告 `percentage`。行為特質會識別輸入的時間分佈。此百分比會指出在星期幾和幾點出現多少內容項目。例如，行為特質 `behavior_0000` 的百分比為 `0.4561049445005`，表示大約有百分之 46 的內容項目是在午夜到 1:00 a.m. 之間建立。

## 消費喜好的評分
{: #scores}

如果您為要求的 `consumption_preferences` 查詢參數指定 `true`，則服務會報告包括每一項喜好 `score` 的消費喜好。服務會依據其從輸入文字推斷的性格特質來衍生評分。此評分是倍精準數，指出文字作者有多喜歡該項目。這是喜好的表示，而不是正規化的百分比。

針對某些喜好，評分為三個值之一：

-   `0.0`：作者不太可能喜歡該項目。針對某些喜好，您可以將此值解譯為作者感興趣的程度低。
-   `0.5`：作者對該項目保持中立態度。針對某些喜好，此值可能表示作者感興趣的程度為中等。
-   `1.0`：作者很可能喜歡該項目。針對某些喜好，此值表示高度感興趣。

針對其他喜好，此評分代表二進位值。輸入文字的作者不太可能 (`0.0`) 或可能 (`1.0`) 對該項目感興趣，或是作者有低度或高度的興趣。在某些情況下，評分可以代表簡單的「是」或「無回應」（例如，作者可能有因為社交原因而志願參加的經驗）。

[消費喜好](/docs/services/personality-insights?topic=personality-insights-preferences)中有提供依種類排列的所有喜好及其結果範圍的完整清單。

## 阿拉伯文和韓文輸入的限制
{: #limitations}

若為阿拉伯文和韓文輸入，服務的模型無法為部分性格特質產生有意義的結果。針對下列特質，正規化百分位數評分一律為 `0.5`，而原始評分一律為原始分佈的平均值。這些特質的 `significant` 欄位一律為 `false`。*請不要* 採信這些特質的結果作為作者特質設定檔的一部分。

<table>
  <caption>表 1. 結果不重要的特質</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      特質
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      無意義的<br/>阿拉伯文結果
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      無意義的<br/>韓文結果
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      五大性格特質維度
    </td>
    <td style="text-align:left; vertical-align:top">
      情緒表達幅度
    </td>
    <td style="text-align:left; vertical-align:top">
      無
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      五大性格特質面向
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; line-height:110%; padding:0px">
          *隨和*：利他主義、合作、謙遜和信任
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *責任感*：為成就而奮鬥和忠於職守
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *外向*：愉快和友善（直率）
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *情緒表達幅度*：憤怒（暴躁）、容易擔心、無節制和自我意識
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *開放性*：愛冒險、想像力、思維能力
        </li>
      </ul>
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; padding:0px">
          *外向*：追求刺激
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      需求
    </td>
    <td style="text-align:left; vertical-align:top">
      理想、自由、愛、實際和結構
    </td>
    <td style="text-align:left; vertical-align:top">
      自由和穩定
    </td>
  </tr>
  </tr>
    <td style="text-align:left; vertical-align:top">
      價值觀
    </td>
    <td style="text-align:left; vertical-align:top">
      自我提升
    </td>
    <td style="text-align:left; vertical-align:top">
      保守
    </td>
  </tr>
</table>
