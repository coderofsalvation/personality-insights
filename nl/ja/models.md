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

# パーソナリティー・モデル
{: #models}

{{site.data.keyword.personalityinsightsshort}} サービスは、言語心理学とデータ分析アルゴリズムを組み合わせたものがベースになっています。本サービスは、ユーザーが送信したコンテンツを分析して、その入力の筆者のパーソナリティー・プロファイルを返します。本サービスは、次の 3 つのモデルに基づいてパーソナリティー特性を推論します。
{: shortdesc}

-   *ビッグ・ファイブ* のパーソナリティー特性は、個人が世界とどのように関与しているかを一般的に記述するために最も広く使用されるモデルを表します。このモデルには、次の 5 つの主要ディメンションが含まれます。
    -   [*協調性*](/docs/services/personality-insights/agreeableness.html) は、他人に対して思いやりを持ち協力的になる個人の傾向です。
            
    -   [*誠実性*](/docs/services/personality-insights/conscientiousness.html) は、組織的な思慮深い方法で行動する個人の傾向です。
            
    -   [*外向性*](/docs/services/personality-insights/extraversion.html) は、他人との付き合いで刺激を求める個人の傾向です。
            
    -   [*情緒不安定性*](/docs/services/personality-insights/emotional-range.html) は、*神経症的傾向* または*自然な反応* とも呼ばれ、個人の感情が環境に左右される程度です。
    -   [*開放性*](/docs/services/personality-insights/openness.html) は、個人がさまざまな活動の経験に対してオープンである程度です。

    これらの最上位ディメンションのそれぞれに、そのディメンションに応じて個人をさらに特徴付ける 6 つのファセットがあります。
-   [ニーズ](/docs/services/personality-insights/needs.html) は、個人の共感を呼ぶ商品の側面を説明します。このモデルには、12 個の特徴ニーズが含まれます。
-   [価値](/docs/services/personality-insights/values.html) は、個人の意思決定に影響を与える動機付け因子を説明します。このモデルには、5 つの価値が含まれます。

モデルがどのように開発されたのか、また、本サービスがモデルをどのように使用するのかについて詳しくは、『[サービスを支えるサイエンス](/docs/services/personality-insights/science.html)』を参照してください。

## ビッグ・ファイブのパーソナリティー特性の説明
{: #bigFive}

ビッグ・ファイブの各ディメンションが次の 3 つの表で説明されています。

-   *ファセット* は、ディメンションのファセットを紹介し、各ファセットのスコアが高い個人を描写しています。
-   *特性の範囲* は、ディメンションの各ファセットに関して多かれ少なかれ証拠となるようなスコアを持つ個人に当てはまると思われる一般的な説明と、そういった個人を描写すると思われる用語を提示しています。5 つすべてのディメンションのファセットについての*特性の範囲* 表を要約して 1 ページにした便利な表を見るには、<a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Facet-Characteristics.pdf" download="Personality-Insights-Facet-Characteristics.pdf">Personality-Insights-Facet-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="外部リンク・アイコン" title="外部リンク・アイコン" class="style-scope doc-content"></a> を参照してください。
-   *1 次ディメンションと 2 次ディメンション* は、パーソナリティー特性の組み合わせを説明して、ディメンションを他のディメンションに関連付ける情報を示しています。この表は、1 次特性と 2 次特性が相互にどのように関連して個人の複合的パーソナリティーを表す可能性があるのかについて、興味深い洞察を提供します。5 つすべてのディメンションについての *1 次特性と 2 次特性* 表を要約して 1 ページにした便利な表を見るには、<a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Dimension-Characteristics.pdf" download="Personality-Insights-Dimension-Characteristics.pdf">Personality-Insights-Dimension-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="外部リンク・アイコン" title="外部リンク・アイコン" class="style-scope doc-content"></a> を参照してください。
