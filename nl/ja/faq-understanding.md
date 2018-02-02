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

# プロファイルについて
{: #output}

1.  <span style="color:#003F69">サービスから戻されたスコアをどう解釈するのですか?</span>

    -   [数値結果の解釈 (Interpreting the numeric results)](/docs/services/personality-insights/numeric.html) に、サービスから戻された百分位数をどう解釈するかに関する説明があります。また、サービスから戻される動向パーセンテージ、オプションのロー・スコアと消費嗜好性に関する情報もあります。

1.  <span style="color:#003F69">特定ディメンションのファセットのスコアを加算しても、そのディメンションのスコアにならないのはなぜですか?</span>

    -   [パーソナリティー特性の百分位数 (Percentiles for personality characteristics)](/docs/services/personality-insights/numeric.html#percentiles) に、この質問に対する回答があります。要約すると、サービスは、それぞれのディメンションとファセットの正規化百分位数を独立して算出します。ディメンションとそのファセットの間に、数学的関係はありません。

1.  <span style="color:#003F69">百分位数スコアの代わりにロー・スコアを使用するのは、どんな場合ですか?</span>

    -   [パーソナリティー特性のロー・スコア (Raw scores for personality characteristics)](/docs/services/personality-insights/numeric.html#rawScores) に、ロー・スコアを使用した場合の詳しい説明があります。簡単に言うと、特定シナリオのカスタム正規化を作成したい場合や、サンプル母集団との比較が不要な場合にロー・スコアを使用できます。筆者の結果をサンプル母集団と照らし合わせた状況を知りたい場合は、百分位数スコアを使用します。

1.  <span style="color:#003F69">ロー・スコアを百分位数スコアにどのようにして正規化するのですか?</span>

    -   [パーソナリティー特性のロー・スコア (Raw scores for personality characteristics)](/docs/services/personality-insights/numeric.html#rawScores) に、ロー・スコアの正規化に関する概要ガイダンスと、{{site.data.keyword.IBM_notm}} による正規化アプローチの説明があります。

1.  <span style="color:#003F69">{{site.data.keyword.personalityinsightsshort}} の可視化された結果はどのように解釈するのですか?</span>

    -   [数値結果の解釈 (Interpreting the numeric results)](/docs/services/personality-insights/numeric.html) に、可視化で示された数値結果の解釈方法に関する説明があります。
