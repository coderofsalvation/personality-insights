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

# サービスを支えるサイエンス
{: #science}

心理学、マーケティング、およびその他のフィールドでは、人間の言語はパーソナリティー、思考スタイル、社会的つながり、および感情の状態を反映するという理論が広く受け入れられています。 ある特定のカテゴリーの単語の使用頻度によって、これらの特性のヒントを得ることができます。ブログ、エッセイ、およびツイートなどの書く場面における単語の使用法の違いでパーソナリティーの側面が予測できることが、複数の研究者によって発見されました ([Fast と Funder (2008)](/docs/services/personality-insights?topic=personality-insights-references#fast2008)、[Gill ほか (2009)](/docs/services/personality-insights?topic=personality-insights-references#gill2009)、[Golbeck ほか (2011)](/docs/services/personality-insights?topic=personality-insights-references#golbeck2011)、[Hirsh と Peterson (2009)](/docs/services/personality-insights?topic=personality-insights-references#hirsh2009)、および [Yarkoni (2010)](/docs/services/personality-insights?topic=personality-insights-references#yarkoni2010))。
{: shortdesc}

{{site.data.keyword.IBM_notm}} では、ソーシャル・メディアのデータから推測されるパーソナリティー特性が、人々の行動や嗜好を予測できるかどうかを理解するための一連の研究を実施しました。 {{site.data.keyword.IBM_notm}} は、特定のパーソナリティー特性を持つ人々が、情報収集タスクと情報拡散タスクにおいて応答およびリツイートする回数が高いことを発見しました。 例えば、「刺激希求性」のスコアが高い人々は応答する可能性が高くなり、「注意深さ」のスコアが高い人々は応答する可能性が低くなります ([Mahmud ほか (2013)](/docs/services/personality-insights?topic=personality-insights-references#mahmud2013))。同様に、「謙虚さ」、「開放性」、および「親しみやすさ」のスコアが高い人々は、情報を拡散する可能性が高くなります ([Lee ほか (2014)](/docs/services/personality-insights?topic=personality-insights-references#lee2014))。

また、{{site.data.keyword.IBM_notm}} は、ソーシャル・メディアの言語から推測して「開放性」のスコアが高く、かつ「情緒不安定性」(神経症的傾向) のスコアが低い人々は、(例えば、広告リンクをクリックしたり、アカウントをフォローしたりして) より好意的に応答したという結果を発見しました。 これらの結果は、サーベイに基づく一般的特徴検査によって裏付けられています。 例えば、「開放性」のスコアが最も高く、かつ「情緒不安定性」のスコアが最も低いという観点から 10 パーセントのユーザーをターゲットとした結果、クリック率は 6.8 パーセントから 11.3 パーセント、フォロー率は 4.7 パーセントから 8.8 パーセントに上昇しました。

ソーシャル・メディアのデータから計算された特性について、最近の複数の研究で同様の結果が発表されました。 小売店のデータに関する最近のある研究では、「秩序性」、「自制力」、および「注意深さ」のスコアが高く、かつ「利己的」のスコアが低い人々は、無作為の母集団と比べ、クーポンに応答する可能性が 40 パーセントも高いことが分かりました。2 番目の研究では、特定の価値を持つ人々が、特定の読書の関心を示したことが分かりました ([Hsieh ほか (2014)](/docs/services/personality-insights?topic=personality-insights-references#hsieh2014))。 例えば、「自己超越」の価値が高い人々は、環境に関する記事を読むことに関心を示し、「自己増進」の価値が高い人々は、仕事に関する記事を読むことに関心を示しました。 600 人を超える Twitter ユーザーについての 3 番目の研究では、個人のパーソナリティー特性が、その人のブランド嗜好を 65 パーセントの正確度で予測できることが分かりました。

以下のセクションは、大まかに分かったこれらの内容をさらに広げて、{{site.data.keyword.personalityinsightsshort}} サービスをサポートする研究と開発について説明します。 サービスを具体的なシナリオに適用する研究について詳しくは、『[サービスの応用](/docs/services/personality-insights?topic=personality-insights-applied)』を参照してください。

## パーソナリティー・モデルを理解する
{: #researchModels}

{{site.data.keyword.personalityinsightsshort}} サービスのために、{{site.data.keyword.IBM_notm}}は、テキスト情報からビッグ・ファイブのディメンションとファセット、ニーズ、および価値のスコアを推測するためのモデルを開発しました。 サービスで報告されるモデルは、心理学、心理言語学、およびマーケティングの各フィールドの研究に基づいています。

-   [ビッグ・ファイブ](/docs/services/personality-insights?topic=personality-insights-models)は、心理学者たち ([Costa および McCrae (1992)](/docs/services/personality-insights?topic=personality-insights-references#costa1992)、および [Norman (1963)](/docs/services/personality-insights?topic=personality-insights-references#norman1963)) によって開発されたパーソナリティー・モデルについての最も代表的な研究の 1 つです。 これは、一般に個人が世間とどのように関わっているかを示す、最も広く使用されているパーソナリティー・モデルです。 サービスは、モデルの 5 個のディメンションと 30 個のファセットを計算します。 これらのディメンションは、*OCEAN* という簡略記号でよく言及されます。この場合、*O* は「開放性」(Openness)、*C* は「誠実性」(Conscientiousness)、*E* は「外向性」(Extraversion)、*A* は「協調性」(Agreeableness)、*N* は「神経症的傾向」(Neuroticism) を示しています。 (「神経症的傾向」(Neuroticism) という用語は特定の臨床的意味を持つ場合があるため、このサービスではそのような洞察を、より一般的に適用可能な用語「情緒不安定性 (Emotional range)」で表します。)
-   [ニーズ](/docs/services/personality-insights?topic=personality-insights-needs)は、人間の行動の重要な側面です。 研究文献は、いくつかのタイプの人間のニーズは普遍的で、消費者行動に直接影響することを示唆しています ([Kotler と Armstrong (2013)](/docs/services/personality-insights?topic=personality-insights-references#kotler2013)、および [Ford (2005)](/docs/services/personality-insights?topic=personality-insights-references#ford2005))。サービスで報告される 12 のカテゴリーのニーズは、マーケティング文献で、個人が商品またはサービスを検討している時に満たしたい願望として説明されています。
-   [価値](/docs/services/personality-insights?topic=personality-insights-values)は、個人にとって何が最も重要かを伝えます。 価値とは、「望ましい、状況超越的な目標であり、程度の差はあれ、人々の生活を導くための原則として用いられるもの」です ([Schwartz (2006)](/docs/services/personality-insights?topic=personality-insights-references#schwartz2006))。 Schwartz は、すべての価値に共通の 5 つの特徴を次のように要約しています。

    1.  価値とは信念である。
    1.  価値とは動機的要因である。
    1.  価値は、特定の行動や状況を超越する。
    1.  価値は、行動、方針、人、および出来事の選択や評価の指針となる。
    1.  価値は、相対的重要性によって異なり、重要性によってランク付けできる。

    このサービスでは、Schwartz によって提案され、20 か国を超える国で検証が行われたこれらの 5 つの基本的な人間の価値を計算します ([Schwartz (1992)](/docs/services/personality-insights?topic=personality-insights-references#schwartz1992))。

## パーソナリティー特性の推測方法
{: #researchInfer}

{{site.data.keyword.personalityinsightsshort}} サービスは、オープン・ソースによる手法に基づいてテキスト情報からパーソナリティー特性を推測します。 この方式は、パーソナリティー推測に関する研究での最新の傾向を反映しています ([Arnoux ほか (2017)](/docs/services/personality-insights?topic=personality-insights-references#arnoux2017)、[Schwartz ほか (2013)](/docs/services/personality-insights?topic=personality-insights-references#schwartz2013)、および [Plank と Hovy (2015)](/docs/services/personality-insights?topic=personality-insights-references#plank2015))。

サービスは、最初に入力テキストをトークン化して、*n* ディメンション・スペースで表記を作成します。 サービスは、オープン・ソースの単語埋め込み手法である [GloVe ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](http://nlp.stanford.edu/projects/glove/){: new_window} を使用して、入力テキスト内の単語のベクトル表記を入手します ([Pennington ほか (2014)](/docs/services/personality-insights?topic=personality-insights-references#pennington2014))。次に、この表記を、ビッグ・ファイブ、ニーズ､および価値の各特性によってパーソナリティー・プロファイルを推測する機械学習アルゴリズムに提供します。 このアルゴリズムをトレーニングするために、サービスは、何千人もの Twitter ユーザーを対象に行われたサーベイからのスコアと彼らの Twitter フィードのデータを使用します。

{{site.data.keyword.IBM_notm}} は、サポート対象言語のすべてのモデルをまったく同じ方法で開発しました。 これらのモデルは、年齢、性別、または文化などのユーザーの人口統計とは無関係に開発されました。 将来、{{site.data.keyword.IBM_notm}} は、さまざまな人口統計カテゴリーに固有のモデルを開発する可能性があります。

このサービスの以前のバージョンでは、機械学習モデルには Linguistic Inquiry and Word Count (LIWC) 心理言語ディクショナリーが使用されていました。 しかし、オープン・ソースによる手法は、LIWC ベースのモデルよりパフォーマンスが優れています。 平均絶対誤差 (MAE) と平均相関の観点から見た、このサービスの各言語での精度については、『[サービスの精度](#researchPrecise)』を参照してください。 最も正確な結果を得るための入力テキストの提供に関するガイダンスについては、『[十分な入力の提供](/docs/services/personality-insights?topic=personality-insights-input#sufficient)』を参照してください。

## サービスの精度
{: #researchPrecise}

{{site.data.keyword.IBM_notm}} は、パーソナリティー・プロファイルを推測するためのこのサービスの手法の正確度を理解するために検証研究を実施しました。 {{site.data.keyword.IBM_notm}} は、すべての特性と言語を対象に、1500 人から 2000 人の参加者のサーベイの回答と Twitter フィードを収集しました。 *一般的特徴*を確立するために、参加者は次の 4 セットの標準心理テストを行いました。

-   IPIP (International Personality Item Pool) から取得した 50 項目のビッグ・ファイブ
-   IPIP-NEO (IPIP Neuroticism, Extraversion &amp; Openness) から派生した 120 項目のファセット
-   {{site.data.keyword.IBM_notm}} で開発された 52 項目の基本的ニーズ
-   Schwartz によって開発された 26 項目の基本的価値

次に、{{site.data.keyword.IBM_notm}} は、モデルによって導出されたスコアを、サーベイに基づいた Twitter ユーザーのスコアと比較しました。 これらの結果に基づいて、{{site.data.keyword.IBM_notm}} は、パーソナリティー特性のさまざまなカテゴリーについて、推測されるスコアと実際のスコア間の[平均絶対誤差](#preciseMAE)と[平均相関](#preciseCorrelation)を判別しました。 『[言語ごとの MAE と平均相関](#precisePerLanguage)』には、各サポート対象言語の統計値が記載されています。

### 平均絶対誤差
{: #preciseMAE}

*平均絶対誤差 (MAE)* は、実際値と予測値の差を測定するために使用されるメトリックです。 {{site.data.keyword.personalityinsightsshort}} サービスでは、実際値、つまり一般的特徴は、パーソナリティー・サーベイの実施によって入手したパーソナリティー・スコアです。 予測値は、サービスのモデルが生成するスコアです。

{{site.data.keyword.IBM_notm}} は、実際のスコアと予測されるスコアの差の絶対値の平均をとることにより MAE を計算しました。 {{site.data.keyword.IBM_notm}} が絶対値を使用したのは、実際値が大きいか小さいかの予測は無関係であるためです。 差がある限り、モデルはエラーの大きさによって不利益になります。 MAE が小さいほど、モデルのパフォーマンスは向上します。 {{site.data.keyword.IBM_notm}} は MAE に 0 から 1 のスケールを使用しています。この場合、0 はエラーなし (予測値が実際値と完全に一致) を意味し、1 は最大数のエラーを意味します。

### 平均相関
{: #preciseCorrelation}

*平均相関*は、2 つの変数の相互依存を測定する統計用語です。 {{site.data.keyword.IBM_notm}} は、このメトリックを使用して、さまざまなカテゴリーのパーソナリティー特性で、推測されるスコアと実際のスコアの相関を測定しました。 予測されるスコアが実際の結果を接近して追跡している場合、相関スコアは高くなり、そうでない場合、スコアは低くなります。

{{site.data.keyword.IBM_notm}} は、-1 から 1 のスケールで相関を測定します。

-   1 は完全に真っすぐな (増加する) 線形関係を示します。
-   -1 は完全に逆の (減少する) 線形関係を示します。

他のすべてのケースでは、値はこれらの両極の間にあります。 変数が独立している (まったく何の関係も持っていない) 場合、相関は 0になります。

最良の予測のために、{{site.data.keyword.IBM_notm}} は、より 1 に近い数値を探します。 しかし、パーソナリティーは、テキストのみに基づいて予測することは難しく、またこれらのタイプの心理的モデルで相関が 0.4 を越えることはめったにありません。 この分野の研究文献では、0.2 よりも大きい相関は許容できると見なされます。

### 言語ごとの MAE と平均相関
{: #precisePerLanguage}

以下の表に、{{site.data.keyword.personalityinsightsshort}} サービスでの言語ごとの MAE と平均相関の結果を示します。 これらの結果により、『[Schwartz ほか (2013)](/docs/services/personality-insights?topic=personality-insights-references#schwartz2013)』と『[Plank と Hovy (2015)](/docs/services/personality-insights?topic=personality-insights-references#plank2015)』によって示された、テキスト・データからのパーソナリティー推測の最先端にこのサービスが位置づけられます。

<table summary="最初の列に言語が示されている各行に対して、その下の 2 行にビッグ・ファイブのディメンション、ビッグ・ファイブのファセット、ニーズ、価値の MAE と平均相関が示されます。">
  <caption>表 1. 言語別の MAE と平均相関</caption>
  <tr>
    <th id="language" style="text-align:left; vertical-align:bottom">
      言語
    </th>
    <th id="dimensions" style="text-align:center; vertical-align:bottom">
      ビッグ・ファイブのディメンション
    </th>
    <th id="facets" style="text-align:center; vertical-align:bottom">
      ビッグ・ファイブのファセット
    </th>
    <th id="needs" style="text-align:center; vertical-align:bottom">
      ニーズ
    </th>
    <th id="values" style="text-align:center; vertical-align:bottom">
      価値
    </th>
  </tr>
  <tr>
    <th id="arabic" headers="language" colspan="5" style="text-align:left">
      **アラビア語**
    </th>
  </tr>
  <tr>
    <td headers="language arabic" style="text-align:left">
      MAE
    </td>
    <td headers="dimensions arabic" style="text-align:center">
      0.09
    </td>
    <td headers="facets arabic" style="text-align:center">
      0.12
    </td>
    <td headers="needs arabic" style="text-align:center">
      0.11
    </td>
    <td headers="values arabic" style="text-align:center">
      0.10
    </td>
  </tr>
  <tr>
    <td headers="language arabic" style="text-align:left">
      平均相関
    </td>
    <td headers="dimensions arabic" style="text-align:center">
      0.17
    </td>
    <td headers="facets arabic" style="text-align:center">
      0.14
    </td>
    <td headers="needs arabic" style="text-align:center">
      0.13
    </td>
    <td headers="values arabic" style="text-align:center">
      0.14
    </td>
  </tr>
  <tr>
    <th id="english" headers="language" colspan="5" style="text-align:left">
      **英語**
    </th>
  </tr>
  <tr>
    <td headers="language english" style="text-align:left">
      MAE
    </td>
    <td headers="dimensions english" style="text-align:center">
      0.12
    </td>
    <td headers="facets english" style="text-align:center">
      0.12
    </td>
    <td headers="needs english" style="text-align:center">
      0.11
    </td>
    <td headers="values english" style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td headers="language english" style="text-align:left">
      平均相関
    </td>
    <td headers="dimensions english" style="text-align:center">
      0.33
    </td>
    <td headers="facets english" style="text-align:center">
      0.28
    </td>
    <td headers="needs english" style="text-align:center">
      0.22
    </td>
    <td headers="values english" style="text-align:center">
      0.24
    </td>
  </tr>
  <tr>
    <th id="japanese" headers="language" colspan="5" style="text-align:left">
      **日本語**
    </th>
  </tr>
  <tr>
    <td headers="language japanese" style="text-align:left">
      MAE
    </td>
    <td headers="dimensions japanese" style="text-align:center">
      0.11
    </td>
    <td headers="facets japanese" style="text-align:center">
      0.12
    </td>
    <td headers="needs japanese" style="text-align:center">
      0.11
    </td>
    <td headers="values japanese" style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td headers="language japanese" style="text-align:left">
      平均相関
    </td>
    <td headers="dimensions japanese" style="text-align:center">
      0.27
    </td>
    <td headers="facets japanese" style="text-align:center">
      0.22
    </td>
    <td headers="needs japanese" style="text-align:center">
      0.25
    </td>
    <td headers="values japanese" style="text-align:center">
      0.19
    </td>
  </tr>
  <tr>
    <th id="korean" headers="language" colspan="5" style="text-align:left">
      **韓国語**
    </th>
  </tr>
  <tr>
    <td headers="language korean" style="text-align:left">
      MAE
    </td>
    <td headers="dimensions korean" style="text-align:center">
      0.11
    </td>
    <td headers="facets korean" style="text-align:center">
      0.12
    </td>
    <td headers="needs korean" style="text-align:center">
      0.11
    </td>
    <td headers="values korean" style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td headers="language korean" style="text-align:left">
      平均相関
    </td>
    <td headers="dimensions korean" style="text-align:center">
      0.21
    </td>
    <td headers="facets korean" style="text-align:center">
      0.21
    </td>
    <td headers="needs korean" style="text-align:center">
      0.13
    </td>
    <td headers="values korean" style="text-align:center">
      0.12
    </td>
  </tr>
  <tr>
    <th id="spanish" headers="language" colspan="5" style="text-align:left">
      **スペイン語**
    </th>
  </tr>
  <tr>
    <td headers="language spanish" style="text-align:left">
      MAE
    </td>
    <td headers="dimensions spanish" style="text-align:center">
      0.10
    </td>
    <td headers="facets spanish" style="text-align:center">
      0.12
    </td>
    <td headers="needs spanish" style="text-align:center">
      0.12
    </td>
    <td headers="values spanish" style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td headers="language spanish" style="text-align:left">
      平均相関
    </td>
    <td headers="dimensions spanish" style="text-align:center">
      0.35
    </td>
    <td headers="facets spanish" style="text-align:center">
      0.21
    </td>
    <td headers="needs spanish" style="text-align:center">
      0.24
    </td>
    <td headers="values spanish" style="text-align:center">
      0.19
    </td>
  </tr>
</table>

これらの百分位数スコアを計算するために、{{site.data.keyword.IBM_notm}} は、以下のような Twitter ユーザーの非常に大規模なデータ・セットを収集し、彼らの人物像を計算しました。

-   英語ユーザー 100 万人
-   韓国語ユーザー 200,000 人
-   アラビア語と日本語のユーザー それぞれ 100,000 人
-   スペイン語ユーザー 80,000 人

次に、{{site.data.keyword.IBM_notm}} は、データ・セットから計算された各プロファイルのロー・スコアとプロファイルの分布とを比較して百分位数を決定しました。

アラビア語と韓国語の入力の場合、サービスは一部のパーソナリティー特性について、意味のある百分位数とロー・スコアを生成できません。 詳しくは、『[アラビア語および韓国語の入力の制限事項](/docs/services/personality-insights?topic=personality-insights-numeric#limitations)』を参照してください。
{: note}

## 消費嗜好性を理解する
{: #researchPrefs}

以下のように、さまざまな商品およびサービスにわたってパーソナリティーと購買行動の間の関係が研究されました。

-   [Chen (2007)](/docs/services/personality-insights?topic=personality-insights-references#chen2007) は、オーガニック食品に関する嗜好をテストしているときに、個人の食品選択基準の確立において個人のパーソナリティー特性が重要な役割を果たしていることを示しました。
-   [Schlegelmilch ほか (1996)](/docs/services/personality-insights?topic=personality-insights-references#schlegelmilch1996) は、パーソナリティー変数と、環境に配慮した購買行動の間の関係を探求しました。 これらの筆者は、消費者の全体的な環境意識が、植物購入の決定にプラスの影響を及ぼすことを示しました。
-   [Hymbaugh および Garrett (2007)](/docs/services/personality-insights?topic=personality-insights-references#hymbaugh1974) は、パーソナリティーとスカイダイビングの関係を調査し、「冒険」と「刺激希求性」のスコアが高い人々は、一般にスカイダイビングに熱中することを発見しました。 (詳しくは、『[リスク・プロファイル](/docs/services/personality-insights?topic=personality-insights-applied#otherRisk)』を参照。)

消費行動とパーソナリティー間のこれらの既知の関係を適用することは容易ではありません。 作業の多くは、サーベイから取得したパーソナリティー・データを使用しており、モデルは公表されていません。 したがって、{{site.data.keyword.IBM_notm}} は、これらの消費嗜好性モデルを直接学習することを決定しました。 モデルをトレーニングしているとき、{{site.data.keyword.IBM_notm}} は、{{site.data.keyword.personalityinsightsshort}} サービスから返されたパーソナリティー・スコアをフィーチャーとして使用しました。その結果、このサービスで、これらのモデルを適用してユーザーのパーソナリティー特性を計算した場合、予測がより正確になる可能性が高くなります。

## 消費嗜好性の推測方法
{: #researchInferPrefs}

{{site.data.keyword.personalityinsightsshort}} サービスは、入力テキストの筆者のパーソナリティー・プロファイルの結果に基づいて消費嗜好性を推測します。 既存の文献から、{{site.data.keyword.IBM_notm}} は、パーソナリティーとの相関が証明されている 104 個の消費嗜好性を識別しました。 これらの嗜好には、買物、映画、音楽、およびその他のカテゴリーに関連した嗜好が含まれています。 次に、{{site.data.keyword.IBM_notm}} は、各消費行動の個人の傾向を評価するために心理測定サーベイを作成しました。

{{site.data.keyword.IBM_notm}} は、約 600 人の個人からそのサーベイの回答と、それらのユーザーの Twitter データ (各ユーザーの 200 を超える自己作成ツイート) を入手しました。 {{site.data.keyword.IBM_notm}} は、それらのツイートをサービスに送信して、各個人のパーソナリティー・プロファイルを収集しました。 次に、各消費嗜好性の分類器を作成しました。そこでの入力フィーチャー・セットはパーソナリティー情報でした。

サービスへの組み込みに際して、{{site.data.keyword.IBM_notm}} は、パーソナリティーに基づいた分類の方が、無作為の分類より、パフォーマンスが少なくとも 9 パーセント優れている消費嗜好性のみを選択しました。 元の 104 個の嗜好のうち 42 個がこの基準を満たしており、サービスによって消費嗜好性として公開されています。

<!--
COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016

## How media influence inferred characteristics

{{site.data.keyword.IBM_notm}} conducted a validation study to understand the effect of media on inferred characteristics. To determine the accuracy of the service's approach to estimating characteristics, {{site.data.keyword.IBM_notm}} compared scores that were derived by its models with survey-based scores for Twitter users (for instance, approximately 500 users for English and more than 600 for Spanish).

To establish ground truth, participants took three sets of standard psychometric tests: 50-item Big Five (derived from the International Personality Item Pool, or IPIP), 52-item fundamental Needs (developed by {{site.data.keyword.IBM_notm}}), and 26-item basic Values (developed by Schwartz). {{site.data.keyword.IBM_notm}} conducted the study in two phases:

-   For the first study, conducted in 2013, {{site.data.keyword.IBM_notm}} recruited 256 Twitter users ([Gou and others, 2014](/docs/services/personality-insights?topic=personality-insights-references#gou2014)). Although the models were learned from different sources, {{site.data.keyword.IBM_notm}} found that for more than 80 percent of the Twitter users, scores for characteristics that were inferred for all three models correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80). Specifically, scores that were derived by the service correlated with survey-based scores as follows:
    -   For 80.8 percent of participants' Big Five scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.75)
    -   For 86.6 percent of participants' Needs scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80)
    -   For 98.21 percent of participants' Values scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.55)
-   For the second study, conducted in 2015, {{site.data.keyword.IBM_notm}} recruited another set of 237 Twitter users. The study found that for Big Five and Values, scores for inferred characteristics correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.07 and 0.21) for every Twitter user. For needs, such significant correlation was observed for 90 percent of the users (p value &lt; 0.05 and correlation coefficient between 0.01 and 0.20).

In both studies, participants also rated on a five-point scale how well each derived characteristic matched their perceptions of themselves. Their ratings suggest that the inferred characteristics largely matched their self-perceptions. Specifically, means of all ratings were above 3 ("somewhat") out of 5 ("perfect").

-   For the 256 Twitter users of the first study, means were 3.4 (with a standard deviation of 1.14) for Big Five, 3.39 (with a standard deviation of 1.34) for Needs, and 3.13 (with a standard deviation of 1.17) for Values.
-   For the 237 Twitter users of the second study, means were 3.31 (with a standard deviation of 1.18) for Big Five, 3.37 (with a standard deviation of 1.22) for Needs, and 3.36 (with a standard deviation of 1.18) for Values.

COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016
-->

## パーソナリティー・サーベイについての注記
{: #researchSurveys}

{{site.data.keyword.personalityinsightsshort}} サービスを開発したとき、{{site.data.keyword.IBM_notm}} は、パーソナリティー・サーベイに基づいて、パーソナリティー推測の一般的特徴データを確立しました。一般的特徴は、推測からではなく、直接の観察から得た、事実に基づくデータを指します。 機械学習モデルでの標準的な正確度の測定方法は、モデルによって推測されるスコアと一般的特徴データを比較するというものです。 前のセクションで、サービスの正確度を検証するために {{site.data.keyword.IBM_notm}} がどのようにサーベイを使用したかについて説明しています。

以下に、パーソナリティー・サーベイとサーベイに基づいたパーソナリティー推定の使用についてわかりやすく示します。

-   パーソナリティー・サーベイは、完了までに長い時間がかかります。 サーベイの結果は、{{site.data.keyword.IBM_notm}} の研究に意欲的に参加することのできた Twitter ユーザーの数によって制約されています。 {{site.data.keyword.IBM_notm}} は、ユーザーの数を増やして、また E メール、ブログ、およびフォーラムなどの他のオンライン・メディアのユーザーでも検証研究を実施することを計画しています。
-   サーベイに基づいたパーソナリティー推定は自己報告に基づいており、必ずしもその人のパーソナリティーを真に反映したものでない可能性があります。ユーザーによっては、そのようなサーベイに対してノイズの多い回答を出す可能性もあります。 ノイズを減らすために、{{site.data.keyword.IBM_notm}} では、注意力検査の質問を含めたり、あまりにも短時間で完了されたサーベイを破棄したりすることによって、サーベイの回答をフィルターに掛けました。
-   推測されるスコアとサーベイに基づいたスコアの相関は肯定的であり重要ではあるものの、結果は、推測されたスコアが必ずしもサーベイに基づいた結果と相関しない可能性があることを示唆しています。 {{site.data.keyword.IBM_notm}} 外部の研究者は、推測されたスコアとサーベイから得たスコアがどのくらい一致しているかを比較するための実験も行いましたが、いずれの実験でも、完全に一貫性のある一致は報告されませんでした。
    -   [Golbeck ほか (2011)](/docs/services/personality-insights?topic=personality-insights-references#golbeck2011) は、推測されるスコアとサーベイに基づいたスコアをマッチングした場合の 10 パーセントから 18 パーセントのエラー率を報告しました。
    -   [Sumner ほか (2012)](/docs/services/personality-insights?topic=personality-insights-references#sumner2012) は、パーソナリティー予測で約 65 パーセントの正確度を報告しました。
    -   [Mairesse および Walker (2006)](/docs/services/personality-insights?topic=personality-insights-references#mairesse2006) は、ビッグ・ファイブ・パーソナリティー予測で 60 パーセントから 70 パーセントの正確度を報告しました。

一般に、パーソナリティー・サーベイの自己報告スコアが、テキストから推測されるスコアと必ずしも完全に一致しないことは、研究文献において広く受け入れられています。 しかし、より重要なことは、多くの場合、テキストから推測される特性によって現実世界の行動を確実に予測できることが {{site.data.keyword.IBM_notm}} の研究で分かったことです。
