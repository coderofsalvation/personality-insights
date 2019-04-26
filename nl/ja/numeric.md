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

# 数値結果の解釈
{: #numeric}

{{site.data.keyword.personalityinsightsshort}} サービスは、各パーソナリティー特性および行動特性の数値結果、および各消費嗜好性の数値結果を返します。 それらの値が提供する情報はそれぞれ異なります。
{: shortdesc}

アラビア語および韓国語の入力の場合、多くのパーソナリティー特性について本サービスは有意な百分位数スコアおよびロー・スコアを生成できません。 詳しくは、『[アラビア語および韓国語の入力の制限事項](#limitations)』を参照してください。
{: note}

## パーソナリティー特性の百分位数
{: #percentiles}

本サービスは、要求ごとに、ビッグ・ファイブ、価値、およびニーズの各パーソナリティー特性に対して、常に正規化されたスコアを `percentile` (百分位数) で報告します。 正規化されたスコアは、本サービスが入力テキストから推論した品質に基づいた、各特性の百分位数ランキングを表します。本サービスでは、筆者のテキストに対するロー・スコアをサンプル母集団からの結果と比較することによって、正規化されたスコアが計算されます。 各百分位数は 0 から 1 までの範囲内の倍精度で報告されます。

例えば、パーソナリティー特性 `big5_extraversion` (ビッグ・ファイブの外向性) の百分位数が `0.64980796071382` である場合、この特性での筆者のスコアは 65 番目の百分位数であることを示します。この筆者が書いた内容は、サンプル母集団の 64 パーセントよりも大きく 34 パーセントよりも少ない範囲にあるという傾向を示しています。 百分位数の精度は、要求で入力として送信された単語の数に基づきます。 詳しくは、『[十分な入力の提供](/docs/services/personality-insights?topic=personality-insights-input#sufficient)』を参照してください。

ビッグ・ファイブのディメンションおよびファセットのそれぞれに関して報告される百分位数の間に数学的な関連はありません。 本サービスは、各ディメンションおよびファセットに関する正規化された百分位数を、当該ディメンションまたはファセットに関するサーベイ参加者のスコアと参加者が使用する単語との間の相関関係に基づいて、独立して計算します。 したがって、ファセットはディメンションの詳細記述を提供するものであるとはいっても、あるディメンションの 6 個のファセットのスコアを合算した結果が必ずしもそのディメンションの百分位数になるわけではありません。 ロー・スコアについても同じです。
{: note}

## パーソナリティー特性のロー・スコア
{: #rawScores-numeric}

要求の `raw_scores` 照会パラメーターに `true` を指定すると、本サービスは各パーソナリティー特性の `raw_score` (ロー・スコア) を報告します。 ロー・スコアは、筆者のテキストおよび特性のモデルのみに基づいた、特性のスコアを表します。ロー・スコアを生成する際、本サービスは結果をサンプル母集団と比較しません。 ロー・スコアは、性格診断テストの結果として筆者が受け取るであろうスコアであると解釈できます。

本サービスは、各ロー・スコアを 0 から 1 までの範囲の倍精度で報告します。一般的に、スコアが大きいほど、筆者がその特性を持っている可能性が高くなります。 ただし、ロー・スコアは総合的に判断する必要があります。実際には値の範囲は 0 から 1 までよりもずっと狭い範囲にあるため、すべてのスコアおよびスコア全体の範囲を考慮して、個々のスコアを検討する必要があります。 しかし、一般的に、ロー・スコア (例えばパーソナリティー特性 `big5_extraversion` (ビッグ・ファイブの外向性) の `0.56817738781166`) は、筆者が性格診断テストを受けたらこのスコアを得る可能性が高いことを示します。 このロー・スコアを、前のセクションで同じ筆者および同じ特性に関して報告された正規化済み百分位数と比較してみてください。

本サービスは、特定のシナリオのためにカスタム正規化を適用したいと考えているユーザー、または、サンプル母集団との比較を必要としないユーザーのために、ロー・スコアを使用可能にしています。 筆者の特性は大きなサンプル母集団に比べてどうなのかを知りたいユーザーは、正規化されたスコアを使用できます。 独自の正規化済み百分位数スコアを生データから導出したいユーザーは、ロー・スコアを別のサンプル母集団と比較し、別の正規化手法を適用できます。

特定の特性のロー・スコアを正規化して百分位数にするには、ロー・スコアを、その特性についての平均偏差および標準偏差が分かっているサンプル母集団と比較します。 例えば、{{site.data.keyword.IBM_notm}} は Twitter ユーザーの大きなサンプル母集団からデータを収集するための調査を実施しました。 {{site.data.keyword.IBM_notm}} は、各パーソナリティー特性についてそれらのユーザーのスコアを計算し、各特性の平均偏差および標準偏差を設定しました。 本サービスでは、入力テキストの分析から推論したロー・スコアに対する百分位数スコアを計算するために、その特性について Twitter サンプル母集団から導出した平均偏差および標準偏差が使用されています。

## 行動特性のパーセンテージ
{: #percentages}

コンテンツ・アイテムにタイム・スタンプが付いている JSON データを送信すると、本サービスは各行動特性に対して `percentage` (パーセンテージ) を報告します。 行動特性は、入力の時間的分布を示します。 パーセンテージは、各曜日および各時刻にコンテンツ・アイテムのうちのいくつが発生したのかを示します。 例えば、行動特性 `behavior_0000` のパーセンテージが `0.4561049445005` である場合、コンテンツ・アイテムのうち約 46 パーセントが午前 0 時から午前 1:00 までの間に発生したことを意味します。

## 消費嗜好性のスコア
{: #scores}

要求の `consumption_preferences` 照会パラメーターに `true` を指定すると、本サービスは消費嗜好性を報告します。そこでは、それぞれの消費嗜好性の `score` (スコア) が示されます。 本サービスは、入力テキストから推論したパーソナリティー特性を元にスコアを導出します。 スコアは、テキストの筆者が当該アイテムを好む可能性を示す倍精度の数値です。 これは好みを示すものであり、正規化されたパーセンテージではありません。

一部の消費嗜好性では、スコアは以下の 3 つの値のいずれかです。

-   `0.0`: 筆者がそのアイテムを好む可能性は非常に低いです。 一部の消費嗜好性では、この値は筆者の関心が低いことを意味していると解釈できます。
-   `0.5`: 筆者はそのアイテムに関して中立的です。 一部の消費嗜好性では、この値は筆者の関心が中程度であることを意味していると解釈できます。
-   `1.0`: 筆者がそのアイテムを好む確率は非常に高いです。 一部の消費嗜好性では、この値は関心が高いことを示します。

その他の消費嗜好性では、スコアは 2 項値を表します。 入力テキストの筆者がそのアイテムに対する関心を持っている確率が低い (`0.0`) または高い (`1.0`) かのどちらかです。つまり、筆者の関心レベルが低いか高いかのどちらかです。 場合によっては、スコアは単純に「はい」または「いいえ」の応答を表すこともあります (例えば、筆者が社会貢献のためのボランティア活動を経験したことがありそうか)。

すべての消費嗜好性のカテゴリー別のリストおよび結果の範囲については、『[消費嗜好性](/docs/services/personality-insights?topic=personality-insights-preferences)』を参照してください。

## アラビア語および韓国語の入力の制限事項
{: #limitations}

アラビア語および韓国語の入力の場合、一部のパーソナリティー特性について本サービスのモデルは意味のある結果を生成できません。 以下の特性では、正規化された百分位数スコアは常に `0.5` であり、ロー・スコアは常に元の分布の平均です。 これらの特性の `significant` (有意) フィールドは常に `false` です。 筆者のパーソナリティー・プロファイルの一部としてのこれらの特性に関する結果に依存*しないでください*。

<table>
  <caption>表 1. 結果が有意ではない特性</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      特性
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      アラビア語の場合の<br/>有意ではない結果
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      韓国語の場合の<br/>有意ではない結果
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      ビッグ・ファイブのディメンション
    </td>
    <td style="text-align:left; vertical-align:top">
      情緒不安定性
    </td>
    <td style="text-align:left; vertical-align:top">
      なし
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      ビッグ・ファイブのファセット
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; line-height:110%; padding:0px">
          *協調性*: 利他主義、協力、謙虚、信頼
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *誠実性*: 達成追及、忠実
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *外向性*: 快活、友好的 (外向き)
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *情緒不安定性*: 怒り (激怒)、心配性、利己的、自意識過剰
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *開放性*: 冒険心、想像力、知性
        </li>
      </ul>
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; padding:0px">
          *外向性*: 興奮を求める
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      ニーズ
    </td>
    <td style="text-align:left; vertical-align:top">
      理想、自由、愛、実用性、および構造
    </td>
    <td style="text-align:left; vertical-align:top">
      自由および安定性
    </td>
  </tr>
  </tr>
    <td style="text-align:left; vertical-align:top">
      価値
    </td>
    <td style="text-align:left; vertical-align:top">
      自己高揚
    </td>
    <td style="text-align:left; vertical-align:top">
      不変
    </td>
  </tr>
</table>
