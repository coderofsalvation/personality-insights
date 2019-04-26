---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-27"

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

# 製品情報
{: #about}

> **サービス更新:** *{{site.data.keyword.personalityinsightsshort}} サービスは、2018 年 11 月 18 日に更新されました。 本サービスが {{site.data.keyword.cloud}} ロンドン・ロケーションで使用可能になりました。 詳しくは、リリース・ノートの [2018 年 11 月 18 日のサービス更新](/docs/services/personality-insights?topic=personality-insights-release-notes#November2018b)を参照してください。*

{{site.data.keyword.personalityinsightsfull}} サービスは、ソーシャル・メディア、企業データ、またはその他のデジタル通信から洞察を引き出すためのアプリケーション・プログラミング・インターフェース (API) を提供します。 本サービスは、E メール、テキスト・メッセージ、ツイート、フォーラム投稿などのデジタル通信を元に、言語分析を使用して個人の持つパーソナリティー特性を推論します。
{: shortdesc}

このサービスは、ノイズが含まれていることのあるソーシャル・メディアを元に、個人の持つさまざまなパーソナリティー特性を反映する人物像を推論します。 また、各種の商品、サービス、およびアクティビティーを個人が好む可能性を示す消費嗜好性を判定することもできます。

## パーソナリティー特性
{: #models-index}

{{site.data.keyword.personalityinsightsshort}} サービスは、3 つの主要なモデルに基づいてパーソナリティー特性を推論します。

-   **ビッグ・ファイブ** のパーソナリティー特性は、個人が世界とどのように関与しているかを一般的に記述するために最も広く使用されるモデルを表します。 このモデルには、*協調性*、*誠実性*、*外向性*、*情緒不安定性*、および*開放性* という 5 つの主要なディメンションが含まれます。 各ディメンションには、そのディメンションに従って個人をさらに特徴付ける 6 つのファセットがあります。
-   **ニーズ** は、個人の共感を呼ぶ可能性がある商品の側面を説明します。 モデルには、*興奮*、*調和*、*好奇心*、*理想*、*親近感*、*自己表現*、*自由*、*愛*、*実用性*、*安定性*、*挑戦*、および*構造* の 12 個の特徴のニーズがあります。
-   **価値** は、個人の意思決定に影響を与える動機を説明します。 このモデルには、*自己超越/人助け*、*不変/伝統*、*快楽主義/人生を楽しむ*、*自己高揚/成功*、および*変化に対して抵抗感を持たない/興奮* という 5 つの価値が含まれます。

詳しくは、『[パーソナリティー・モデル](/docs/services/personality-insights?topic=personality-insights-models)』を参照してください。

## 消費嗜好性
{: #preferences-index}

本サービスは、入力テキストから推論されたパーソナリティー特性に基づいて、筆者の消費嗜好性の程度を返すこともできます。 消費嗜好性は、さまざまな商品、サービス、およびアクティビティーを筆者が望む可能性を示します。 本サービスは、個人の消費嗜好性を、*ショッピング*、*音楽*、*映画*、*読書および学習*、*健康および運動*、*ボランティア活動*、*環境への関心*、および*起業家精神* の 8 つのカテゴリーにグループ化しています。 各カテゴリーには、1 個から数十個の個人の消費嗜好性が含まれます。

詳しくは、『[消費嗜好性](/docs/services/personality-insights?topic=personality-insights-preferences)』を参照してください。

## サービスの利点
{: #benefits}

{{site.data.keyword.personalityinsightsshort}} サービスは、{{site.data.keyword.ibmwatson}} プラットフォームの中核サービスの 1 つとして、ビジネスに役立つ洞察を提供できます。

-   顧客の好みを学習し、顧客満足度を改善し、顧客との関係を強化することで、より深いレベルまで顧客を理解できます。
-   顧客の獲得、保持、および顧客エンゲージメントを改善できます。
-   高度にパーソナライズされたエンゲージメントおよび対話を元に、商品、サービス、キャンペーン、およびコミュニケーションを個々の顧客に合わせてより良く調整することができます。

本サービスの利用方法について詳しくは、『[ユース・ケース](/docs/services/personality-insights?topic=personality-insights-usecases)』を参照してください。

## 言語サポート
{: #languages-index}

本サービスでは以下の言語がサポートされています。 サポートされている言語の任意の組み合わせを要求および応答に使用できますが、すべての入力テキストは同じ言語でなければなりません。 詳しくは、『[要求および応答の言語の指定](/docs/services/personality-insights?topic=personality-insights-input#languages-input)』を参照してください。

<table style="width:75%">
  <caption>表 1. サポートされる言語</caption>
  <tr>
    <th style="width:50%; text-align:center">
      要求の言語
    </th>
    <th style="width:50%; text-align:center">
      応答の言語
    </th>
  </tr>
  <tr>
    <td style="text-align:center; vertical-align:top">
      アラビア語<br/>
      英語<br/>
      日本語<br/>
      韓国語<br/>
      スペイン語
    </td>
    <td style="text-align:center; vertical-align:top">
      アラビア語<br/>
      英語<br/>
      日本語<br/>
      韓国語<br/>
      スペイン語<br/>
      ブラジル・ポルトガル語<br/>
      フランス語<br/>
      ドイツ語<br/>
      イタリア語<br/>
      中国語 (簡体字)<br/>
      中国語 (繁体字)
    </td>
  </tr>
</table>

## HIPAA
{: hipaa}

米国における医療保険の積算と責任に関する法律 (HIPAA) への対応は、{{site.data.keyword.personalityinsightsshort}} サービスには適用されません。 本サービスは、ステートレスです。 本サービスは、{{site.data.keyword.cloud_notm}} にユーザー・データを保管しません。

## サービスに関する詳細情報
{: #learn-index}

-   {{site.data.keyword.personalityinsightsshort}} サービスの [クイック・デモ ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://personality-insights-demo.ng.bluemix.net/){: new_window} では、入力テキストを分析して、筆者の消費嗜好性を含む人物像を明らかにすることができます。
-   {{site.data.keyword.watson}} [Starter Kits ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](http://www.ibm.com/watson/developercloud/starter-kits.html){: new_window} にあるアプリケーションは、本サービスを説明します。
-   『[サービスの応用](/docs/services/personality-insights?topic=personality-insights-applied)』および『[サービスを支えるサイエンス](/docs/services/personality-insights?topic=personality-insights-science)』には、本サービスの基盤となっている研究についての説明があります。
-   [{{site.data.keyword.cloud_notm}} カタログ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/catalog/services/personality-insights/){: new_window} 中の {{site.data.keyword.personalityinsightsshort}} サービスでは、本サービス用に選択可能な価格プランが説明されています。
