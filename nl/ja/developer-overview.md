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

# 開発者向けの概要
{: #overviewDevelopers}

{{site.data.keyword.personalityinsightsshort}} サービスは、HTTP Representational State Transfer (REST) API 経由で使用することができます。 さまざまな言語でアプリケーション開発を簡単にするために、いくつかの Software Development Kit (SDK) も利用可能です。
{: shortdesc}

## サービスでのプログラミング
{: #programming}

パーソナリティー・プロファイルを生成するには、サービスの HTTP `POST /v3/profile` メソッドにテキストを送信します。 プレーン・テキスト、HTML、または JSON コンテンツをサブミット可能です。 このサービスは、分析を JSON フォーマットまたは CSV フォーマットで返すことができます

各パーソナリティー特性について、このサービスでは*百分位数*を報告します。 百分位数は、筆者の記述内容がサンプル母集団内で特性を示す程度を表した正規化スコアです。 サービスは、要求された場合には、*ロー・スコア* も戻します。これは、サンプル母集団に対して正規化されていない絶対値です。 入力にタイム・スタンプが付いている場合、サービスは曜日や時刻による筆者の書く習慣の要約も示します。 また、要求された場合には、サービスは、有効な各消費嗜好性の可能性スコアも戻します。

サービスの使用について詳しくは、以下を参照してください。

-   [プロファイルの要求](/docs/services/personality-insights?topic=personality-insights-input)
-   [JSON プロファイルの解釈](/docs/services/personality-insights?topic=personality-insights-output)
-   [CSV プロファイルの解釈](/docs/services/personality-insights?topic=personality-insights-outputCSV)

### プロファイルの視覚化
{: #visualize}

サービスでは、プロファイルのグラフィックによる視覚化を可能にする JavaScript ファイルのコレクションが提供されます。 スクリプトにより、キャッシングとコンテンツ配布ネットワークを使用したサービスの利用が容易になります。 結果を表現するために、JavaScript、jQuery、HTML、SVG と、Data-Driven Documents (`D3.js`) ライブラリーに依存しています。 `D3.js` について詳しくは、[d3js.org ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://d3js.org/){: new_window} を参照してください。

### CORS サポート
{: #CORS}

サービスは、Cross-Origin Resource Sharing (CORS) をサポートしています。 CORS により、ブラウザー・ベースのクライアントで、フロントエンドのスクリプトからサービスに直接、非同期要求を行うことが可能になります。 CORS によって、CORS を使用しない場合にそうした要求を阻止する同一生成元セキュリティー・ポリシーが回避されます。

CORS を使用することで、Web ページは要求発信元ドメインの外部にある外部ドメインにリソースを要求できます。 詳しくは、[enable-cors.org ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://enable-cors.org/){: new_window} を参照してください。

## Software Development Kit の使用
{: #sdks}

アプリケーション開発を簡単にするために、{{site.data.keyword.personalityinsightsshort}} サービスでは SDK が利用可能です。 多くの一般的なプログラミング言語およびプラットフォーム用の {{site.data.keyword.ibmwatson}} SDK があります。 

-   すべての SDK のリストと GitHub の SDK へのリンクについては、[SDK の使用 (Using SDKs)](/docs/services/watson?topic=watson-using-sdks) を参照してください。
-   {{site.data.keyword.personalityinsightsshort}} サービス用の Node、Java、Python、Ruby および Go の各 SDK のすべてのメソッドについて詳しくは、[API リファレンス![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/apidocs/personality-insights){: new_window}を参照してください。

## アプリケーション開発の詳細
{: #learn-overview}

{{site.data.keyword.watson}} サービスと {{site.data.keyword.cloud}} を使用する方法について詳しくは、以下のセクションを参照してください。

-   {{site.data.keyword.watson}} サービスと {{site.data.keyword.cloud_notm}} の使用を始める方法については、[{{site.data.keyword.watson}} と {{site.data.keyword.cloud_notm}} の概要](/docs/services/watson?topic=watson-about)を参照してください。
-   すべての新規サービス・インスタンスは、認証に {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) を使用します。 古いサービス・インスタンスでは、認証に既存の Cloud Foundry サービス資格情報の `{username}` と `{password}` が引き続き使用される場合があります。 サービスに対する認証について詳しくは、リリース・ノートの [2018 年 10 月 30 日のサービス更新](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018)を参照してください。
-   {{site.data.keyword.personalityinsightsshort}} サービスの要求ロギングは使用不可になっています。 このサービスは、`X-Watson-Learning-Opt-Out` 要求ヘッダーが設定されているかどうかに関係なく、要求と応答からのデータをログに記録することも、保存することもありません。
