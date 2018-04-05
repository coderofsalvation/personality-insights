---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-18"

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
{:download: .download}

# 概要チュートリアル
{: #gettingStarted}

{{site.data.keyword.personalityinsightsfull}} サービスは、ソーシャル・メディア、エンタープライズ・データ、またはその他のデジタル・コミュニケーションからパーソナリティー特性の洞察を導きます。このチュートリアルを利用すると、{{site.data.keyword.personalityinsightsshort}} サービスを簡単に始めることができます。さまざまなタイプの入力を使用してサービスの `POST /v3/profile` メソッドを呼び出す方法と、さまざまなタイプの出力および出力形式を要求する方法が、例で示されています。
{: shortdesc}

## 始める前に
{: #before-you-begin}

- サービスのインスタンスを作成します。
    - {: download} これが表示されている場合は、サービス・インスタンスを作成済みです。資格情報を入手してください。
    - サービスからプロジェクトを作成します。
        1.  {{site.data.keyword.watson}} Developer Console の[サービス ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://console.{DomainName}/developer/watson/services){: new_window} ページに移動します。
        1.  {{site.data.keyword.personalityinsightsshort}} を選択し、**「サービスの追加」**をクリックして、無料の {{site.data.keyword.Bluemix_notm}} アカウントに登録するか、ログインします。
        1.  プロジェクト名に `personality-tutorial` と入力し、**「プロジェクトの作成」**をクリックします。
- サービス・インスタンスに認証するための資格情報をコピーします。
    - {: download} サービス・ダッシュボード (現在表示されている画面) から、以下を行います。
        1.  **「サービス資格情報」**タブをクリックします。
        1.  **「アクション」**の下で**「資格情報の表示」**をクリックします。
        1.  `username`、`password`、`url` の値をコピーします。
        {: download}
    - Developer Console の **personality-tutorial** プロジェクトで、**「資格情報」**セクションから`「personality_insights」`の `username`、`password`、`url` の値をコピーします。
- cURL があることを確認します。
    - 例では、cURL を使用して HTTP インターフェースのメソッドを呼び出します。[curl.haxx.se ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://curl.haxx.se/){: new_window} から、ご使用のオペレーティング・システムに対応したバージョンをインストールします。Secure Sockets Layer (SSL) プロトコルをサポートするバージョンをインストールしてください。必ず、インストールしたバイナリー・ファイルを `PATH` 環境変数に含めてください。

<!-- Remove this text after dedicated instances have the Developer Console: begin -->

{{site.data.keyword.Bluemix_dedicated_notm}} を使用する場合は、カタログの [{{site.data.keyword.personalityinsightsshort}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://console.{DomainName}/catalog/services/personality-insights/){: new_window} ページからサービス・インスタンスを作成します。サービス資格情報を見つける方法の詳細については、[Watson サービスのサービス資格情報 (Service credentials for Watson services) ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](/docs/services/watson/getting-started-credentials.html#getting-credentials-manually){: new_window} を参照してください。

<!-- Remove this text after dedicated instances have the Developer Console: end -->

## ステップ 1: プレーン・テキスト入力を送信して、基本 JSON 出力を受信する
{: #example1}

最初の例では、プレーン・テキスト・ファイル `profile.txt` を `POST /v3/profile` メソッドに渡して、デフォルト JSON 応答を暗黙的に要求します。

1.  サンプル・ファイル <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="外部リンク・アイコン" title="外部リンク・アイコン" class="style-scope doc-content"></a> をダウンロードします。
1.  以下のコマンドを実行して、ファイルを `/v3/profile` メソッドに送信し、デフォルト JSON 応答を要求します。`Content-Type` ヘッダーに含まれる `charset` パラメーターでは、入力テキストの文字エンコードを指定します。
    -   `{username}` と `{password}` は、前のステップで入手したサービス資格情報に置き換えます。
    -   `{path_to_file}` は、`profile.txt` ファイルの場所を指定するように変更します。

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --data-binary "@{path_to_file}profile.txt" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
    ```
    {: pre}

JSON `Profile` オブジェクトが、サービスから戻されます。これには、入力内の語数、入力を処理した言語モデル、入力に関連した警告などの基本メタデータが含まれます。詳しくは、[Profile オブジェクト](/docs/services/personality-insights/output.html#outputJSON)を参照してください。

プロファイルには、入力テキストから推測した、筆者のビッグ・ファイブ・パーソナリティー、ニーズ、価値の特性に関する情報が含まれます。サービスでは、各特性の `percentile`、つまり正規化スコアを報告します。筆者の結果をサンプル母集団の結果と比較することで、サービスは百分位数を算出します。詳しくは、[パーソナリティー特性の出力](/docs/services/personality-insights/output.html#traitJSON)を参照してください。

## ステップ 2: JSON 入力を送信して、詳細な JSON 出力を受信する
{: #example2}

2 番目の例では、JSON ファイル `profile.json` を `/v3/profile` メソッドに渡して、同様にデフォルト JSON 応答を受け取ります。この例では、入力を詳細に分析するために、消費嗜好性とロー・スコアを要求します。

1.  サンプル・ファイル <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="外部リンク・アイコン" title="外部リンク・アイコン" class="style-scope doc-content"></a> をダウンロードします。これには、Twitter メッセージのコレクションが含まれています。
1.  以下のコマンドを実行して、ファイルを `/v3/profile` メソッドに送信します。この例では、`Content-Type` ヘッダーに `application/json` を指定します。JSON 入力に `charset` パラメーターは不要です。例では、`consumption_preferences` と `raw_scores` の照会パラメーターを `true` に設定しています。

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --data-binary "@{path_to_file}profile.json" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"
    ```
    {: pre}

前の例で戻されたメタデータと特性を含む JSON プロファイルが、サービスから戻されます。各特性について、`raw_score` も含められています。これは、サンプル母集団と結果を比較せずに、入力テキストのみに基づいて特性に関する筆者のスコアを表すものです。

入力コンテンツにタイム・スタンプが含まれるため、行動特性もサービスで報告されます。これらは、それぞれの曜日および時刻に作成されたコンテンツ項目の `percentage` を示す時間的特性です。詳しくは、[行動出力](/docs/services/personality-insights/output.html#behaviorJSON)を参照してください。

サービスでは、消費嗜好性のコレクションのスコアも報告されます。スコアは、推測された特性に基づいて、筆者がさまざまな商品、サービス、活動を嗜好する可能性を示します。詳しくは、[消費嗜好性の出力](/docs/services/personality-insights/output.html#preferenceJSON)を参照してください。

## ステップ 3: JSON 入力を送信して、詳細な CSV 出力を受信する
{: #example3}

3 番目の例は、2 番目と似ていて、同じ JSON コンテンツを渡して同じ結果を要求します。しかし、この例では `Accept` ヘッダーに `text/csv` を指定して、コンマ区切り値 (CSV) 形式の応答を要求します。cURL コマンドの `--output` オプションを使用して、`profile.csv` という名前のファイルに結果を送ります。例では、`csv_headers` 照会パラメーターを `true` に設定して、列見出しが出力に戻されるよう要求します。

1.  以下のコマンドを実行して、JSON ファイルを `/v3/profile` メソッドに送信します。

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary "@{path_to_file}profile.json" \
    --output profile.csv \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"
    ```
    {: pre}

CSV 応答とヘッダーの詳細説明については、[『CSV プロファイルの解釈』](/docs/services/personality-insights/output-csv.html)を参照してください。

## 次のステップ

-   [『プロファイルの要求』](/docs/services/personality-insights/input.html)、[『JSON プロファイルの解釈』](/docs/services/personality-insights/output.html)、[『CSV プロファイルの解釈』](/docs/services/personality-insights/output-csv.html)の詳細を確認します。
-   ビッグ・ファイブ、ニーズ、価値の[パーソナリティー・モデル](/docs/services/personality-insights/models.html)の詳細を確認します。
-   [API リファレンス![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window} で API の詳細を確認します。
-   [API Explorer ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v3){: new_window} で API を操作します。
-   [Node.js サンプル・アプリケーション ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} を探索して、サービスでのアプリケーション開発の詳細を確認します。
