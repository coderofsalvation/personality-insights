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

# 開発者向けの概要
{: #overviewDevelopers}

{{site.data.keyword.personalityinsightsshort}} サービスは、HTTP Representational State Transfer (REST) API 経由で使用することができます。さまざまな言語や環境でアプリケーション開発を簡単にするために、いくつかの Software Development Kit (SDK) も利用可能です。
{: shortdesc}

## サービスでのプログラミング
{: #programming}

パーソナリティー・プロファイルを生成するには、サービスの HTTP `POST /v3/profile` メソッドにテキストを送信します。プレーン・テキスト、HTML、または JSON コンテンツをサブミット可能です。このサービスは、分析を JSON フォーマットまたは CSV フォーマットで返すことができます

各パーソナリティー特性について、サービスは*百分位数* を報告します。これは、筆者の記述内容がサンプル母集団内で特性を示す程度を表した正規化スコアです。サービスは、要求された場合には、*ロー・スコア* も戻します。これは、サンプル母集団に対して正規化されていない絶対値です。入力にタイム・スタンプが付いている場合、サービスは曜日や時刻に関して筆者の書く習慣の要約も示します。また、要求された場合には、サービスは、有効な各消費嗜好性の可能性スコアも戻します。

サービスの使用について詳しくは、以下を参照してください。

-   [プロファイルの要求](/docs/services/personality-insights/input.html)
-   [JSON プロファイルの解釈](/docs/services/personality-insights/output.html)
-   [CSV プロファイルの解釈
](/docs/services/personality-insights/output-csv.html)

### プロファイルの視覚化
{: #visualize}

サービスでは、プロファイルのグラフィックによる視覚化を可能にする JavaScript ファイルのコレクションが提供されます。スクリプトにより、キャッシングとコンテンツ配布ネットワークを使用したサービスの利用が容易になります。結果を表現するために、JavaScript、jQuery、HTML、SVG と、Data-Driven Documents (`D3.js`) ライブラリーに依存しています。これらのクライアント・サイド・ファイルについては、[Software Development Kit の使用](#sdks)で引用されたサンプル・アプリケーションを参照してください。`D3.js` について詳しくは、[d3js.org ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://d3js.org/){: new_window} を参照してください。

### CORS サポート
{: #CORS}

このサービスは、Cross-Origin Resource Sharing (CORS) をサポートし、ブラウザー・ベースのクライアントが、フロントエンドのスクリプトからサービスに直接、非同期要求を行うことが可能です。CORS により、クライアントは、要求発信元ドメインの外部にあるドメインにリソースを要求できます。そうした要求を阻止する同一生成元セキュリティー・ポリシーを Web アプリケーションが回避することができます。詳しくは、[enable-cors.org ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://enable-cors.org/){: new_window} を参照してください。

## Software Development Kit の使用
{: #sdks}

{{site.data.keyword.personalityinsightsshort}} サービスは、アプリケーション開発を簡単にするための SDK を数多くサポートしています。Node.js、Java、Python、Apple&reg; iOS など、一般的な多くのプログラミング言語およびプラットフォーム向けの SDK があります。SDK の全リストとその使用については、[{{site.data.keyword.watson}} SDK](/docs/services/watson/getting-started-sdks.html) を参照してください。SDK はすべて、GitHub の [watson-developer-cloud 名前空間 ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://github.com/watson-developer-cloud){: new_window} から入手可能できます。

始めるにあたって、以下のサンプル・アプリケーションも利用可能です。

-   Node.js SDK を使用するアプリケーションには、[personality-insights-nodejs リポジトリー ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} でアクセスできます。
-   Java SDK を使用するアプリケーションには、[personality-insights-java リポジトリー ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://github.com/watson-developer-cloud/personality-insights-java){: new_window} でアクセスできます。

モバイル開発については、[{{site.data.keyword.watson}} Developer Cloud Swift SDK ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://github.com/watson-developer-cloud/swift-sdk){: new_window} を参照してください。すべての SDK は、サービス資格情報または認証トークンを使用した認証をサポートします。

## アプリケーション開発の詳細
{: #learn}

{{site.data.keyword.personalityinsightsshort}} サービスは、2 つの標準的なプログラミング・モデルをサポートしています。クライアントがサービスと直接通信する*直接対話* と、クライアントとサービスが {{site.data.keyword.Bluemix_short}} 内のプロキシー・アプリケーションを通じてすべてのデータ (要求と結果) を交換する*プロキシー経由のリレー* のプログラミング・モデルです。

{{site.data.keyword.watson}} Developer Cloud サービスと {{site.data.keyword.Bluemix_notm}} の作業について詳しくは、以下を参照してください。

-   {{site.data.keyword.watson}} サービスと {{site.data.keyword.Bluemix_notm}} の作業の概要については、[{{site.data.keyword.watson}} および {{site.data.keyword.Bluemix_notm}} 概説 (Getting started with {{site.data.keyword.watson}} and {{site.data.keyword.Bluemix_notm}})](/docs/services/watson/index.html) を参照してください。
-   {{site.data.keyword.Bluemix_notm}} での {{site.data.keyword.watson}} サービス・アプリケーション開発に関する、言語に依存しない概要については、[{{site.data.keyword.Bluemix_notm}} の開発アプローチ ({{site.data.keyword.Bluemix_notm}} development approaches)](/docs/services/watson/getting-started-bluemix.html) を参照してください。
-   {{site.data.keyword.watson}} アプリケーションの開発に使用できる 2 つのプログラミング・モデルについては、[{{site.data.keyword.watson}} サービスのプログラミング・モデル (Programming models for {{site.data.keyword.watson}} services)](/docs/services/watson/getting-started-develop.html) を参照してください。
    -   プロキシー経由のリレーで、クライアントは {{site.data.keyword.Bluemix_notm}} 内のプロキシー・サーバーに依存してサービスと通信します。すべての要求は、 プロキシー・アプリケーション経由で受け渡します。プロキシー経由の要求のリレーでは、サービスでの認証にサービス資格情報のみを信頼します。[{{site.data.keyword.watson}} サービスのサービス資格情報 (Service credentials for {{site.data.keyword.watson}} services)](/docs/services/watson/getting-started-credentials.html) を参照してください。
    -   直接対話で、クライアントは、サービスの認証トークンを入手するためにのみ、{{site.data.keyword.Bluemix_notm}} 内のプロキシー・アプリケーションを使用し、その後は、サービスと直接通信します。直接対話では、トークンの入手のみにサービス資格情報を使用します。[認証のトークン (Tokens for authentication)](/docs/services/watson/getting-started-tokens.html) を参照してください。
-   すべての {{site.data.keyword.watson}} サービスに実行されるデフォルト要求ロギングの制御については、[{{site.data.keyword.watson}} サービスの要求ロギングの制御 (Controlling request logging for {{site.data.keyword.watson}} services)](/docs/services/watson/getting-started-logging.html) を参照してください。
