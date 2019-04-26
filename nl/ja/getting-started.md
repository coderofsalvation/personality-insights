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
{:go: .ph data-hd-programlang='go'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}
{:download: .download}
{:apikey: data-credential-placeholder='apikey'}
{:url: data-credential-placeholder='url'}
{:hide-dashboard: .hide-dashboard}

# 入門チュートリアル
{: #gettingStarted}

{{site.data.keyword.personalityinsightsfull}} サービスは、ソーシャル・メディア、エンタープライズ・データ、またはその他のデジタル・コミュニケーションからパーソナリティー特性の洞察を導きます。 このチュートリアルを利用すると、{{site.data.keyword.personalityinsightsshort}} サービスを簡単に始めることができます。 さまざまなタイプの入力を使用してサービスの `POST /v3/profile` メソッドを呼び出す方法と、さまざまなタイプの出力および出力形式を要求する方法が、例で示されています。
{: shortdesc}

このチュートリアルでは、認証に {{site.data.keyword.cloud}} Identity and Access Management (IAM) API キーを使用します。 古いサービス・インスタンスでは、認証に既存の Cloud Foundry サービス資格情報の `{username}` と `{password}` が引き続き使用される場合があります。 ご使用のサービス・インスタンスに適したアプローチを使用して認証を行ってください。 サービスによる IAM 認証の使用について詳しくは、リリース・ノートの [2018 年 10 月 30 日のサービス更新](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018)を参照してください。
{: important}

## 始める前に
{: #before-you-begin}

-   {: hide-dashboard} サービスのインスタンスを作成します。
    1.  {: hide-dashboard} {{site.data.keyword.cloud_notm}} カタログの [{{site.data.keyword.personalityinsightsshort}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/catalog/services/personality-insights){: new_window} ページに移動します。
    1.  {: hide-dashboard} 無料の {{site.data.keyword.cloud_notm}} アカウントを登録するか、ログインします。
    1.  {: hide-dashboard} **「作成」**をクリックします。
-   サービス・インスタンスに認証するための資格情報をコピーします。
    1.  {: hide-dashboard} [{{site.data.keyword.cloud_notm}} ダッシュボード ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/dashboard/apps){: new_window}から、{{site.data.keyword.personalityinsightsshort}} サービス・インスタンスをクリックして、{{site.data.keyword.personalityinsightsshort}} サービス・ダッシュボード・ページに移動します。
    1.  **「管理」**ページで、 **「表示」**をクリックして資格情報を表示します。
    1.  `「API キー」`の値と`「URL」`の値をコピーします。
-   `curl` コマンドを使用できることを確認します。
    -   例では `curl` コマンドを使用して HTTP インターフェースのメソッドを呼び出します。 [curl.haxx.se ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://curl.haxx.se/){: new_window} から、ご使用のオペレーティング・システムに対応したバージョンをインストールします。 Secure Sockets Layer (SSL) プロトコルをサポートするバージョンをインストールしてください。 必ず、インストールしたバイナリー・ファイルを `PATH` 環境変数に含めてください。

コマンドを入力するときに、`{apikey}` と `{url}` は実際の API キーと URL に置き換えてください。 変数値を示す中括弧は、コマンドから取り除きます。 実際の値は、以下の例のようになります。
{: hide-dashboard}

```bash
curl -X POST -u "apikey:L_HALhLVIksh1b73l97LSs6R_3gLo4xkujAaxm7i-b9x"
. . .
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{:pre}
{: hide-dashboard}

## ステップ 1: プレーン・テキスト入力を送信して、基本 JSON 出力を受信する
{: #example1}

最初の例では、プレーン・テキスト・ファイル `profile.txt` を `POST /v3/profile` メソッドに渡して、JSON 応答を要求します。

1.  サンプル・ファイル <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="外部リンク・アイコン" title="外部リンク・アイコン"></a> をダウンロードします。
1.  以下のコマンドを実行して、ファイルを `/v3/profile` メソッドに送信し、JSON 応答を要求します。
    -   `Content-Type` ヘッダーでは、入力がプレーン・テキスト `text/plain` であることを指定します。 ヘッダーに含まれる `charset` パラメーターでは、入力テキストの文字エンコードを指定します。
    -   `Accept` ヘッダーでは、`application/json` を指定して、JSON 出力が要求されていることを示します。
    -   {: hide-dashboard} `{apikey}` と `{url}` は実際の情報に置き換えてください。
    -   `{path_to_file}` は、`profile.txt` ファイルの場所を指定するように変更します。

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.txt \
    "{url}/v3/profile?version=2017-10-13"{: url}
    ```
    {: pre}

JSON `Profile` オブジェクトが、サービスから戻されます。これには、入力内の語数、入力を処理した言語モデル、入力に関連した警告などの基本メタデータが含まれます。 詳しくは、[Profile オブジェクト](/docs/services/personality-insights?topic=personality-insights-output#outputJSON)を参照してください。

プロファイルには、入力テキストから推測した、筆者のビッグ・ファイブ・パーソナリティー、ニーズ、価値の特性に関する情報が含まれます。 サービスでは、各特性の `percentile`、つまり正規化スコアを報告します。 筆者の結果をサンプル母集団の結果と比較することで、サービスは百分位数を算出します。 詳しくは、[パーソナリティー特性の出力](/docs/services/personality-insights?topic=personality-insights-output#traitJSON)を参照してください。

## ステップ 2: JSON 入力を送信して、詳細な JSON 出力を受信する
{: #example2}

2 番目の例では、JSON ファイル `profile.json` を `/v3/profile` メソッドに渡して、もう一度 JSON 応答を要求します。この例では、入力を詳細に分析するために、消費嗜好性とロー・スコアを要求します。

1.  サンプル・ファイル <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="外部リンク・アイコン" title="外部リンク・アイコン"></a> をダウンロードします。これには、Twitter メッセージのコレクションが含まれています。
1.  以下のコマンドを実行して、ファイルを `/v3/profile` メソッドに送信します。 この例では、`Content-Type` ヘッダーと `Accept` ヘッダーに `application/json` を指定します。JSON 入力に `charset` パラメーターは不要です。例では、`consumption_preferences` と `raw_scores` の照会パラメーターを `true` に設定しています。

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.json \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"{: url}
    ```
    {: pre}

前の例で戻されたメタデータと特性を含む JSON プロファイルが、サービスから戻されます。 各特性について、`raw_score` も含められています。これは、サンプル母集団と結果を比較せずに、入力テキストのみに基づいて特性に関する筆者のスコアを表すものです。

入力コンテンツにタイム・スタンプが含まれるため、行動特性もサービスで報告されます。 これらは、それぞれの曜日および時刻に作成されたコンテンツ項目の `percentage` を示す時間的特性です。 詳しくは、[行動出力](/docs/services/personality-insights?topic=personality-insights-output#behaviorJSON)を参照してください。

サービスでは、消費嗜好性のコレクションのスコアも報告されます。 スコアは、推測された特性に基づいて、筆者がさまざまな商品、サービス、活動を嗜好する可能性を示します。 詳しくは、[消費嗜好性の出力](/docs/services/personality-insights?topic=personality-insights-output#preferenceJSON)を参照してください。

## ステップ 3: JSON 入力を送信して、詳細な CSV 出力を受信する
{: #example3}

3 番目の例は、2 番目と似ていて、同じ JSON コンテンツを渡して同じ結果を要求します。 しかし、この例では `Accept` ヘッダーに `text/csv` を指定して、コンマ区切り値 (CSV) 形式の応答を要求します。 `curl` コマンドの `--output` オプションを使用して、`profile.csv` という名前のファイルに結果を送ります。 例では、`csv_headers` 照会パラメーターを `true` に設定して、列見出しが出力に戻されるよう要求します。

1.  以下のコマンドを実行して、JSON ファイルを `/v3/profile` メソッドに送信します。 `Content-Type` ヘッダーでは、入力コンテンツを `application/json` として指定し、`Accept` ヘッダーでは、CSV 出力 `text/csv` を要求します。

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary @{path_to_file}profile.json \
    --output profile.csv \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"{: url}
    ```
    {: pre}

CSV 応答とヘッダーの詳細説明については、[『CSV プロファイルの解釈』](/docs/services/personality-insights?topic=personality-insights-outputCSV)を参照してください。

## 次のステップ
{: #gsns}

-   [『プロファイルの要求』](/docs/services/personality-insights?topic=personality-insights-input)、[『JSON プロファイルの解釈』](/docs/services/personality-insights?topic=personality-insights-output)、[『CSV プロファイルの解釈』](/docs/services/personality-insights?topic=personality-insights-outputCSV)の詳細を確認します。
-   ビッグ・ファイブ、ニーズ、価値の[パーソナリティー・モデル](/docs/services/personality-insights?topic=personality-insights-models)の詳細を確認します。
-   [API リファレンス![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/apidocs/personality-insights){: new_window} で API の詳細を確認します。
-   [Node.js サンプル・アプリケーション ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} を探索して、サービスでのアプリケーション開発の詳細を確認します。
