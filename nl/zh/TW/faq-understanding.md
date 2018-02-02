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

# 瞭解設定檔
{: #output}

1.  <span style="color:#003F69">我要如何解譯服務傳回的評分？</span>

    -   [解譯數字結果](/docs/services/personality-insights/numeric.html)說明如何解譯服務所傳回的百分位數。其中也包含行為百分比，以及服務可傳回之選用原始評分和消費喜好的相關資訊。

1.  <span style="color:#003F69">為什麼針對維度的面向新增評分，不會產生該維度的評分？</span>

    -   [性格特質的百分位數](/docs/services/personality-insights/numeric.html#percentiles)會回答這個問題。總結來說，服務會分別計算每一個維度和面向的正規化百分位數。維度與其面向之間不存在數學關係。

1.  <span style="color:#003F69">我什麼時候要使用原始評分，而非百分位數評分？</span>

    -   [性格特質的原始評分](/docs/services/personality-insights/numeric.html#rawScores)提供此選擇的洞察資訊。簡單說，當您想要為特定實務範例開發自訂正規化，或不需要與樣本母體進行比較時，您可以使用原始評分。如果您需要關於作者的結果如何與樣本母體比較的知識，請使用百分位數評分。

1.  <span style="color:#003F69">如何將原始評分正規化為百分位數評分？</span>

    -   [性格特質的原始評分](/docs/services/personality-insights/numeric.html#rawScores)提供正規化原始評分的高階指引，並討論 {{site.data.keyword.IBM_notm}} 的正規化方式。

1.  <span style="color:#003F69">如何解譯 {{site.data.keyword.personalityinsightsshort}} 視覺效果？</span>

    -   [解譯數字結果](/docs/services/personality-insights/numeric.html)說明如何解譯視覺化中所顯示的數字結果。
