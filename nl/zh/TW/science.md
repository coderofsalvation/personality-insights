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

# 服務背後的科學
{: #science}

有一個在心理學、行銷學和其他領域都公認的理論是，人類的語言會反映性格、思維方式、社交關係和情緒狀態。我們使用某些字詞種類的頻率，可以提供這些特質的線索。有幾位研究人員發現，在部落格、散文和推文等書寫中的用字變化，可以預測性格的層面（[Fast &amp;Funder, 2008](/docs/services/personality-insights/references.html#fast2008)；[Gill 等人 (2009)](/docs/services/personality-insights/references.html#gill2009)；[Golbeck 等人 (2011)](/docs/services/personality-insights/references.html#golbeck2011)；[Hirsh &amp; Peterson, 2009](/docs/services/personality-insights/references.html#hirsh2009)；和 [Yarkoni, 2010](/docs/services/personality-insights/references.html#yarkoni2010)）。
{: shortdesc}

{{site.data.keyword.IBM_notm}} 進行一組研究，以瞭解從社交媒體資料推斷的性格特質是否可以預測個人的行為和喜好。{{site.data.keyword.IBM_notm}} 發現，具有特定性格特質的人對於資訊收集與資訊傳播的回應及轉發推文的人數較高。例如，在追求刺激方面評分較高的人，比較可能會回應，而在謹慎方面評分較高的人，比較不可能這麼做（[Mahmud 等人 (2013)](/docs/services/personality-insights/references.html#mahmud2013)）。同樣地，在謙遜、開放性和友善方面評分較高的人，比較有可能會傳播資訊（[Lee 等人 (2014)](/docs/services/personality-insights/references.html#lee2014)）。

{{site.data.keyword.IBM_notm}} 也發現，從社交媒體語言推斷出開放性高而情緒表達幅度（神經質）低的人，比較會有贊同的回應（例如，點擊廣告鏈結或追蹤某帳戶），這個結果已經過意見調查型的基準檢查證實。例如，將目標設定在前百分之 10 開放性高和情緒表達幅度低的使用者，會讓點擊率從百分之 6.8 增加到百分之 11.3，而追蹤率從百分之 4.7 增加到百分之 8.8。

針對從社交媒體資料計算而來的特質，多項最新的研究也顯示類似的結果。最近一項針對零售商店資料的研究發現，在有條理、自律和謹慎方面評分較高，而在無節制方面評分較低的人，回應優惠券的可能性比隨機母體高出百分之 40。第二項研究發現，具有特定價值觀的人會顯示特定的閱讀興趣（([Hsieh 等人 (2014)](/docs/services/personality-insights/references.html#hsieh2014)）。例如，自我超越價值觀較高的人，會對於閱讀環境相關文章展現興趣，而自我提升價值觀較高的人，會對於閱讀工作相關文章展現興趣。第三項對超過 600 位 Twitter 使用者所做的研究發現，個人的性格特質可以預測其品牌喜好，精確度達百分之 65。

下列各節就這些高階發現結果加以詳述，以說明 {{site.data.keyword.personalityinsightsshort}} 服務背後的研究和開發。如需將服務套用至實際情境研究的相關資訊，請參閱[運作中的服務](/docs/services/personality-insights/applied.html)。

## 瞭解性格模型
{: #researchModels}

對於 {{site.data.keyword.personalityinsightsshort}} 服務，{{site.data.keyword.IBM_notm}} 已開發從文字資訊來推斷「五大性格特質」維度和面向、「需求」和「價值觀」評分的模型。服務所報告的模型是以心理學、心理語言學和行銷學領域的研究為依據。

-   [五大性格特質](/docs/services/personality-insights/models.html)是心理學家開發的性格模型中研究得最深入的項目之一（[Costa &amp; McCrae, 1992](/docs/services/personality-insights/references.html#costa1992) 和 [Norman, 1963](/docs/services/personality-insights/references.html#norman1963)）。這是在描述一個人通常如何與世界互動時，最廣泛使用的性格模型。服務會計算此模型的 5 個維度和 30 個面向。維度常會以助記詞 *OCEAN* 來表示，其中 *O* 代表開放性 (Openness)，*C* 代表責任感 (Conscientiousness)、*E* 代表外向 (Extraversion)、*A* 代表隨和 (Agreeableness)，而 *N* 代表神經質 (Neuroticism)。（因為「神經質」這個詞可能有特定的臨床意義，所以服務會將這類洞察分析呈現在比較適合一般使用的標題「情緒表達幅度」之下。）
-   [需求](/docs/services/personality-insights/needs.html)是人類行為的重要層面。研究文獻顯示，有幾種人類需求類型是全體性的，並且會直接影響消費者的行為（[Kotler&amp; Armstrong, 2013](/docs/services/personality-insights/references.html#kotler2013) 和 [Ford, 2005](/docs/services/personality-insights/references.html#ford2005)）。服務所報告的 12 個需求種類，在行銷文獻中被形容成一個人在考慮產品或服務時所希望滿足的慾望。
-   [價值觀](/docs/services/personality-insights/values.html)傳達對個人最重要的東西。其為「令人嚮往、跨情境的目標，重要性各不相同，是為個人的人生指導原則 ([Schwartz, 2006](/docs/services/personality-insights/references.html#schwartz2006))。Schwartz 彙總所有價值觀共同的 5 項特性：(1) 價值觀是信仰；(2) 價值觀是動機建構；(3) 價值觀超越特定的行動和情況；(4) 價值觀會引導行動、政策、個人和事件的選擇或評估；以及 (5) 價值觀會因相對重要性而不同，並可據以排序。服務計算 Schwartz 所提出的五項基本人類價值觀，並且在超過二十個國家獲得驗證 ([Schwartz, 1992](/docs/services/personality-insights/references.html#schwartz1992))。

## 推斷性格特質的方式
{: #researchInfer}

{{site.data.keyword.personalityinsightsshort}} 服務根據開放字彙方式，從文字資訊推斷出性格特質。此方法會反映研究中關於性格推斷的最新趨勢（[Arnoux 等人 (2017)](/docs/services/personality-insights/references.html#arnoux2017)、[Schwartz 等人 (2013)](/docs/services/personality-insights/references.html#schwartz2013) 和 [Plank &amp; Hovy, 2015](/docs/services/personality-insights/references.html#plank2015)）。

服務會先將輸入文字記號化，以在 *n* 維度空間中開發表示法。服務使用一項稱為 [GloVe ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://nlp.stanford.edu/projects/glove/){: new_window} 的開放程式碼字詞內嵌技術，以針對輸入文字中的字詞來取得向量表示法（[Pennington 等人 (2014)](/docs/services/personality-insights/references.html#pennington2014)），然後將此表示法提供至機器學習演算法，以使用「五大性格特質」、「需求」和「價值觀」特質來推斷性格設定檔。服務針對數千個使用者及其 Twitter 資訊來源中的資料進行意見調查，並使用所取得的評分來訓練演算法。

{{site.data.keyword.IBM_notm}} 以相同的方式為所有支援的語言開發模型。這些模型的開發未納入使用者個人背景資訊（例如年齡、性別或文化）。在未來，{{site.data.keyword.IBM_notm}} 可能會針對不同的個人背景資訊種類，開發特定的模型。

舊版服務使用「語言查詢和字詞計數 (LIWC)」心理語言學詞典來搭配其機器學習模型。不過，剛剛提到的開放字彙方式的效能勝過 LIWC 模型。如需就平均「平均絕對誤差 (MAE)」和相關性方面，將服務用於各種語言的精準度的相關資訊，請參閱[服務的精準度](#researchPrecise)。如需提供輸入文字以達到最佳精確結果的相關指引，請參閱[提供足夠的輸入](/docs/services/personality-insights/input.html#sufficient)。

## 服務的精準度
{: #researchPrecise}

{{site.data.keyword.IBM_notm}} 進行了一項驗證研究，以瞭解服務用來推斷性格設定檔的方法的精確度。{{site.data.keyword.IBM_notm}} 針對所有特質和語言，收集了 1500 到 2000 位參與者的意見調查回應和 Twitter 資訊來源。為了建立*基準*，參與者進行了四組標準心理測試：

-   50 項從 International Personality Item Pool (IPIP) 衍生而來的「五大性格特質」
-   120 項從 IPIP「神經質、外向和開放性」(IPIP-NEO) 衍生而來的面向
-   52 項由 {{site.data.keyword.IBM_notm}} 所開發的基礎「需求」
-   26 項由 Schwartz 所開發的基本「價值觀」

然後，{{site.data.keyword.IBM_notm}} 會將由其模型衍生而來的評分與針對 Twitter 使用者進行意見調查所得到評分做比較。{{site.data.keyword.IBM_notm}} 根據這些結果，在不同種類性格特質的推斷與實際評分之間，判斷出[平均「平均絕對誤差」](#preciseMAE)和[平均相關性](#preciseCorrelation)。[每種語言的平均 MAE 和相關性](#precisePerLanguage)提供每一種支援語言的統計值。

### 平均「平均絕對誤差」
{: #preciseMAE}

*平均絕對誤差 (MAE)* 是用來測量實際值與預測值之間差異的度量值。對 {{site.data.keyword.personalityinsightsshort}} 服務而言，實際值（或基準）是藉由管理性格調查所得到性格評分。預測值是服務模型所產生的評分。

{{site.data.keyword.IBM_notm}} 採用實際與預測評分差的平均絕對值來計算 MAE。{{site.data.keyword.IBM_notm}} 使用絕對值是因為預測較多或較少實際值並無關聯；只要有差異，模型就會因誤差大小而受損。MAE 愈低，模型的效能愈好。{{site.data.keyword.IBM_notm}} 為 MAE 使用 0 到 1 的等級，其中 0 表示沒有誤差（預測值與實際值完全相同），而 1 表示最大誤差。

### 平均相關性
{: #preciseCorrelation}

*平均相關性* 是測量兩個變數相依性的統計術語。使用此度量值，{{site.data.keyword.IBM_notm}} 可以測量不同種類性格特質的推斷與實際評分之間的相關性。如果預測的評分與實際結果非常接近，則相關性評分為高；否則，評分為低。

{{site.data.keyword.IBM_notm}} 測量等級 -1 到 1 的相關性：1 表示完全直接（遞增）線性關係，而 -1 表示完全反向（遞減）線性關係。在所有其他情況下，該值都介於這兩個極端值之間。如果變數是獨立的（它們完全沒有關係），則相關性為 0。

{{site.data.keyword.IBM_notm}} 期待有較接近 1 的數字以作為最佳預測。但是，單靠文字很難預測性格，而且就這些類型的心理模型而言，很少看到相關性超過 0.4。在這個領域的研究獻中，相關性高於 0.2 是可接受的。

### 每種語言的平均 MAE 和相關性
{: #precisePerLanguage}

下表顯示 {{site.data.keyword.personalityinsightsshort}} 服務的每種語言平均 MAE 和相關性結果。如 [Schwartz 等人 (2013)](/docs/services/personality-insights/references.html#schwartz2013) 和 [Plank 與 Hovy (2015)](/docs/services/personality-insights/references.html#plank2015) 所指出的，這些結果將服務放在從文字資料推斷性格的最重要位置。

<table>
  <caption>表 1. 依語言列出的平均 MAE 和相關性</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      語言
    </th>
    <th style="text-align:center; vertical-align:bottom">
      五大性格特質維度
    </th>
    <th style="text-align:center; vertical-align:bottom">
      五大性格特質面向
    </th>
    <th style="text-align:center; vertical-align:bottom">
      需求
    </th>
    <th style="text-align:center; vertical-align:bottom">
      價值觀
    </th>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **英文**
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
      平均相關性
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
      **西班牙文**
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
      平均相關性
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
      **日文**
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
      平均相關性
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
      **阿拉伯文**
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
      平均相關性
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
      **韓文**
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
      平均相關性
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

為了計算百分位數評分，{{site.data.keyword.IBM_notm}} 收集了非常大量的 Twitter 使用者資料集（一百萬位英文使用者，200,000 位韓文使用者，阿拉伯文和日文使用者各 100,000 位，以及 80,000 位西班牙文使用者），並計算其性格側寫。然後，{{site.data.keyword.IBM_notm}} 會將每一個計算設定檔的原始評分與那些資料集產生的設定檔分佈相比較，以判斷百分位數。

> **附註：**若為阿拉伯文和韓文輸入，服務無法為部分性格特質產生有意義的百分位數和原始評分。如需相關資訊，請參閱[阿拉伯文和韓文輸入的限制](/docs/services/personality-insights/numeric.html#limitations)。

## 瞭解消費喜好
{: #researchPrefs}

性格與採購行為之間的關係已經在各種產品和服務之間進行研究：

-   [Chen (2007)](/docs/services/personality-insights/references.html#chen2007) 在測試關於有機食品的喜好時，指出個人的性格特質在建立個人食物選擇的準則中，扮演著重要的角色。
-   [Schlegelmilch 等人 (1996)](/docs/services/personality-insights/references.html#schlegelmilch1996) 探討了性格變數與友善環境採購行為之間的關係。作者表示消費者的整體環境意識對綠色採購決策具有正面影響。
-   [Hymbaugh 與 Garrett (2007)](/docs/services/personality-insights/references.html#hymbaugh1974) 調查了性格與跳傘之間的關係，發現在愛冒險和追求刺激方面評分較高的人，通常對跳傘都很著迷。（如需相關資訊，請參閱[建立風險設定檔](/docs/services/personality-insights/applied.html#otherRisk)。）

套用消費行為與性格之間的這些已知關係很有挑戰性：這些研究大部分都是使用從意見調查衍生而來的性格資料，且無法公開取得其模型。因此，{{site.data.keyword.IBM_notm}} 決定直接學習這些消費喜好模型。在訓練模型時，{{site.data.keyword.IBM_notm}} 使用從 {{site.data.keyword.personalityinsightsshort}} 服務傳回的性格評分作為特性。因此，當您套用這些模型，使用服務來計算使用者的性格特質時，預測可能會更準確。

## 推斷消費喜好的方式
{: #researchInferPrefs}

{{site.data.keyword.personalityinsightsshort}} 服務會根據其性格設定檔的結果，針對輸入文字的作者推斷消費喜好。{{site.data.keyword.IBM_notm}} 已從現有的文獻中，識別出 104 種證實與性格相關聯的消費喜好。其中包括與購物、電影、音樂和其他種類相關的喜好。然後，{{site.data.keyword.IBM_notm}} 會建立心理測量的調查，以評量個人對每一種消費行為的傾向。

{{site.data.keyword.IBM_notm}} 從大約 600 位同時擁有其 Twitter 資料（每一位使用者有 200 個以上自行編寫的推文）的個人，取得對意見調查的回應。{{site.data.keyword.IBM_notm}} 提交推文至服務，以收集每一個人的性格設定檔。然後，它針對每一個消費喜好各建置一個分類器，其中輸入特性集是性格資訊。

為了併在服務中，{{site.data.keyword.IBM_notm}} 僅選取性格型分類效能至少高於隨機分類百分之 9 的消費喜好。在原始 104 項喜好中，有 42 項符合此準則，且服務會將其顯示為消費喜好。

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

## 性格調查注意事項
{: #researchSurveys}

在開發 {{site.data.keyword.personalityinsightsshort}} 服務時，{{site.data.keyword.IBM_notm}} 是根據性格調查來為性格推斷建立基準資料。基準是指透過直接觀察，而不是透過推斷所取得的事實資料。任何機器學習模型的一般精確度測量，是將由模型所推斷的評分與基準資料做比較；前幾節有說明 {{site.data.keyword.IBM_notm}} 如何使用意見調查來驗證服務的精確度。

下列注意事項說明性格調查以及意見調查型性格評估的用法：

-   性格調查需耗費很長的時間才能完成。因此，結果會受限於有願意且有空參與 {{site.data.keyword.IBM_notm}} 研究的 Twitter 使用者人數。{{site.data.keyword.IBM_notm}} 計劃讓更多使用者以及其他線上媒體（例如電子郵件、部落格和討論區）的使用者來參與驗證研究。
-   意見調查型性格評估是根據自我報告，這不一定能真正反射一個人的性格：部分使用者可能會對這類意見調查發出喧鬧的答案。為了減少這些干擾，{{site.data.keyword.IBM_notm}} 納入了注意力檢查問題，並捨棄太快完成的意見調查，藉以過濾意見調查的回應。
-   雖然推斷與意見調查型評分之間的相關性是正面且有意義的評分，但結果暗示推斷的評分與意見調查型結果不一定有關聯。{{site.data.keyword.IBM_notm}} 外部的研究人員也進行了實驗來比較推斷的評分與從意見調查取得的評分的相符程度，而沒有任何研究人員報告完全一致的相符項：
    -   [Golbeck 等人 (2011)](/docs/services/personality-insights/references.html#golbeck2011) 報告，將推斷的評分與意見調查型評分比對時，誤差率為百分之 10 到 18。
    -   [Sumner 等人 (2012)](/docs/services/personality-insights/references.html#sumner2012) 報告性格預測的精確度大約為百分之 65。
    -   [Mairesse 與 Walker (2006)](/docs/services/personality-insights/references.html#mairesse2006) 報告「五大性格特質」預測的精確度為百分之 60 到 70。

一般而言，研究文獻中普遍接受性格調查所產生的自我報告評分，並不一定完全符合從文字所推斷的評分。不過，更重要的是，{{site.data.keyword.IBM_notm}} 發現從文字推斷的特質確實能夠預測各種真實世界的行為。
