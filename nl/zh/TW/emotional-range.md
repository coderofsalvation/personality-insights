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

# 五大性格特質 - 情緒表達幅度
{: #emotionalRange}

*情緒表達幅度*，也稱為*神經質* 或*自然反應*，是個人的情緒對個別環境的敏感程度。
下列表格符合*高*或*低*特質的結果：
{: shortdesc}

-   任何大於 0.5 的平均值的評分，表示特質的平均趨勢為大於平均值。若評分等於或大於 0.75 ，表示特質在辨識方面較容易；這類評分被視為*高*。
-   相反的陳述式是低於 0.50 和 0.25 的評分，這將會被視為*低*。

如需相關資訊，請參閱[性格特質的百分位數](/docs/services/personality-insights?topic=personality-insights-numeric#percentiles)。

## 面向
{: #facets-emote}

簡要說明維度的面向，以及在各面向獲得高評分的個人。

<table>
  <caption>表 1. 面向（情緒表達幅度）</caption>
  <tr>
    <th style="text-align:left">面向</th>
    <th style="text-align:left">評分高的個人...</th>
  </tr>
  <tr>
    <td><strong>憤怒 / 暴躁</strong></td>
    <td>有生氣的傾向。</td>
  </tr>
  <tr>
    <td><strong>焦慮 / 容易擔心</strong></td>
    <td>常常覺得快要發生不愉快、具威脅性或危險的事。他們大腦中的「戰或逃」系統太容易且太常引動。</td>
  </tr>
  <tr>
    <td><strong>沮喪 / 憂鬱 / 悶悶不樂</strong></td>
    <td>對於人生的起伏比較易感。</td>
  </tr>
  <tr>
    <td><strong>無節制 / 自我放縱</strong></td>
    <td>感覺到強烈的渴望和衝動，即使知道以後可能會後悔，還是難以抵抗。他們往往偏向於短期的快樂和回報，而不是長期的後果。</td>
  </tr>
  <tr>
    <td><strong>自我意識</strong></td>
    <td>對於他人如何看待自己很敏感。他們對拒絕和嘲笑的擔憂，使他們在人群中感到害羞和不自在；容易覺得尷尬。</td>
  </tr>
  <tr>
    <td><strong>脆弱  / 抗壓性低 / 對壓力敏感</strong></td>
    <td>難以應付壓力。在壓力下或遇到緊急情況時，他們會感到恐慌、困惑和無助。</td>
  </tr>
</table>

## 特質範圍
{: #range-emote}

針對評分或多或少可證明維度各面向的個人，提供一般性說明，以及可以形容這些個人的詞彙。

<table summary="針對每一列中間直欄所列出的面向，前兩個直欄會提供低面向評分的個人說明及詞彙，而最後兩個直欄會提供高面向評分的個人說明及詞彙。">
<caption>表 2. 特質範圍（情緒表達幅度）</caption>
  <tr>
    <th id="lowValue" colspan="2" style="text-align:center">
低值的說明</th>
    <th id="blank"></th>
    <th id="highValue" colspan="2" style="text-align:center">
高值的說明</th>
  </tr>
  <tr>
    <th id="lowDescription" headers="lowValue" style="text-align:left; width: 23%">
說明</th>
    <th id="lowTerm" headers="lowValue" style="text-align:center; width: 16%">
詞彙</th>
    <th id="facet" headers="blank" style="text-align:center; width: 16%">
面向</th>
    <th id="highTerm" headers="highValue" style="text-align:center; width: 16%">
詞彙</th>
    <th id="highDescription" headers="highValue" style="text-align:right">
說明</th>
  </tr>
  <tr>
    <td headers="lowValue lowDescription" style="text-align:left">
很難讓您生氣。</td>
    <td headers="lowValue lowTerm" style="text-align:center">
脾氣溫和</td>
    <td headers="blank facet" style="text-align:center">
      <strong>憤怒</strong>
    </td>
    <td headers="highValue highTerm" style="text-align:center">
暴躁</td>
    <td headers="highValue highDescription" style="text-align:right">
您的脾氣暴躁，尤其是當事情不按照您的方式進行時。</td>
  </tr>
  <tr>
    <td headers="lowValue lowDescription" style="text-align:left">
您經常感覺平靜和自信。</td>
    <td headers="lowValue lowTerm" style="text-align:center">
自信</td>
    <td headers="blank facet" style="text-align:center">
      <strong>焦慮</strong>
    </td>
    <td headers="highValue highTerm" style="text-align:center">
容易擔心</td>
    <td headers="highValue highDescription" style="text-align:right">
您經常擔心可能會發生的事情。</td>
  </tr>
  <tr>
    <td headers="lowValue lowDescription" style="text-align:left">
您通常對於做自己感到很自在。</td>
    <td headers="lowValue lowTerm" style="text-align:center">
滿足</td>
    <td headers="blank facet" style="text-align:center">
      <strong>沮喪</strong>
    </td>
    <td headers="highValue highTerm" style="text-align:center">
憂鬱</td>
    <td headers="highValue highDescription" style="text-align:right">
您經常想到讓您不開心的事。</td>
  </tr>
  <tr>
    <td headers="lowValue lowDescription" style="text-align:left">
對於不是特別熱切的慾望，您都可以控制得很好。</td>
    <td headers="lowValue lowTerm" style="text-align:center">
自我控制</td>
    <td headers="blank facet" style="text-align:center">
      <strong>無節制</strong>
    </td>
    <td headers="highValue highTerm" style="text-align:center">
享樂主義</td>
    <td headers="highValue highDescription" style="text-align:right">
您會感受到強烈的慾望，且容易被慾望誘惑。</td>
  </tr>
  <tr>
    <td headers="lowValue lowDescription" style="text-align:left">
您不太會尷尬，大部分時候都很有自信。</td>
    <td headers="lowValue lowTerm" style="text-align:center">
自信</td>
    <td headers="blank facet" style="text-align:center">
      <strong>自我意識</strong>
    </td>
    <td headers="highValue highTerm" style="text-align:center">
忸怩不自在</td>
    <td headers="highValue highDescription" style="text-align:right">
對於他人可能對您的想法很敏感。</td>
  </tr>
  <tr>
    <td headers="lowValue lowDescription" style="text-align:left">
您可以平靜而有效地處理突發事件。</td>
    <td headers="lowValue lowTerm" style="text-align:center">
在壓力下保持平靜</td>
    <td headers="blank facet" style="text-align:center">
      <strong>脆弱</strong>
    </td>
    <td headers="highValue highTerm" style="text-align:center">
抗壓性低</td>
    <td headers="highValue highDescription" style="text-align:right">
在有壓力的情況下，很容易被擊垮。</td>
  </tr>
</table>

## 主要和次要維度
{: #dimensions-emote}

在不同維度之間建立關聯的資訊，說明性格特質的組合。提供主要與次要特質如何相互關聯的洞察分析，以呈現個人的綜合性格。

<table>
  <caption>表 3. 主要和次要維度（情緒表達幅度）</caption>
  <tr>
    <th colspan="2" style="width:30%">維度</th>
    <th style="width:35%">高情緒表達幅度</th>
    <th style="width:35%">低情緒表達幅度</th>
  </tr>
  <tr>
    <td style="text-align:left"><strong>隨和</strong></td>
    <td style="text-align:center"><em>高</em></td>
    <td>易動情、易受騙、深情、敏感、溫柔</td>
    <td>耐心、放鬆、不苛求、務實</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>低</em></td>
    <td>喜怒無常、易怒、好爭辯、急躁、乖戾</td>
    <td>沒有感情、冷漠、無動於衷、沒有熱情</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>責任感</strong></td>
    <td style="text-align:center"><em>高</em></td>
    <td>過分講究、高度緊張</td>
    <td>理性、客觀、穩定、合乎邏輯、果斷</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>低</em></td>
    <td>難以控制、愛管閒事、自我放縱、健忘、衝動</td>
    <td>不拘禮節、低調</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>外向</strong></td>
    <td style="text-align:center"><em>高</em></td>
    <td>易激動、囉唆、輕浮、暴躁、揮霍</td>
    <td>自然大方、孜孜不倦、不屈不撓</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>低</em></td>
    <td>防衛、煩躁、不安、悲觀、遮遮掩掩</td>
    <td>謙虛、不易激動、溫和、平靜</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>開放性</strong></td>
    <td style="text-align:center"><em>高</em></td>
    <td>易激動、熱情、喜愛感官享受</td>
    <td>真誠、隨機應變、有創意、有智慧、有洞察力</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>低</em></td>
    <td>易慌亂、易惱怒、憂慮</td>
    <td>冷靜、冷漠</td>
  </tr>
</table>
