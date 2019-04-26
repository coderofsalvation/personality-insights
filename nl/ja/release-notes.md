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

# リリース・ノート
{: #release-notes}

以下のセクションに、{{site.data.keyword.personalityinsightsshort}} サービスの各リリースで組み込まれた新しいフィーチャーおよび変更を示します。 特に断りのない限り、変更はすべて前のリリースと互換性があり、すべての新規および既存のアプリケーションで自動的かつ透過的に使用可能になっています。
{: shortdesc}

このリリース・ノートは、すべての最新更新の*サービス・バージョン*と*インターフェース・バージョン*を文書化しています。 `version` 照会パラメーターによって*インターフェース・バージョン*を指定して、その更新で使用可能になった新しいフィーチャーおよび機能を使用します。 サービスは、`X-Service-Api-Version` 応答ヘッダーによって両方のバージョンを返します。
{: note}

## 2018 年 12 月 21 日
{: #December2018}

**サービス・バージョン** - `3.4.5`<br/> **インターフェース・バージョン** - `2017-10-13`

{{site.data.keyword.personalityinsightsshort}} API のバージョン 2 がサービスから削除されました。 サービスのバージョン 3 は 2016 年 10 月 19 日にリリースされました。 その時点で、ユーザーはできるだけ速やかにバージョン 2 からマイグレーションすることを強く勧められました。

## 2018 年 11 月 18 日
{: #November2018b}

**サービス・バージョン** - `3.4.5`<br/> **インターフェース・バージョン** - `2017-10-13`

{{site.data.keyword.personalityinsightsshort}} サービスが {{site.data.keyword.cloud}} ロンドン・ロケーション (**eu-gb**) で使用可能になりました。 他のすべてのロケーションと同様、ロンドンでもトークン・ベースの Identity and Access Management (IAM) 認証が使用されます。 このロケーションで作成するすべての新規サービス・インスタンスで、IAM 認証が使用されます。

## 2018 年 11 月 7 日
{: #November2018a}

**サービス・バージョン** - `3.4.5`<br/> **インターフェース・バージョン** - `2017-10-13`

{{site.data.keyword.personalityinsightsshort}} サービスが {{site.data.keyword.cloud_notm}} 東京ロケーション (**jp-tok**) で使用可能になりました。 他のすべてのロケーションと同様、東京でもトークン・ベースの Identity and Access Management (IAM) 認証が使用されます。 このロケーションで作成するすべての新規サービス・インスタンスで、IAM 認証が使用されます。

## 古いリリース
{: #older}

-   [2018 年 10 月 30 日](#October2018)
-   [2018 年 6 月 11 日](#June2018b)
-   [2018 年 6 月 4 日](#June2018a)
-   [2018 年 5 月 23 日](#March2018)
-   [2017 年 10 月 13 日](#October2017)
-   [2017 年 9 月 18 日](#September2017)
-   [2017 年 4 月 10 日](#April2017)
-   [2017 年 3 月 1 日](#March2017)
-   [2017 年 2 月 20 日](#February2017b)
-   [2017 年 2 月 13 日](#February2017)
-   [2017 年 1 月 13 日](#January2017)
-   [2016 年 12 月 15 日](#December2016)
-   [2016 年 11 月 15 日](#November2016)
-   [2016 年 10 月 20 日](#October2016b)
-   [2016 年 10 月 12 日](#October2016a)
-   [2016 年 8 月 31 日](#August2016)
-   [2016 年 7 月 14 日](#July2016b)
-   [2016 年 7 月 1 日](#July2016a)
-   [2016 年 6 月 7 日](#June2016b)
-   [2016 年 6 月 1 日](#June2016a)
-   [2016 年 5 月 17 日](#May2016)
-   [2016 年 3 月 18 日](#March2016)
-   [2015 年 7 月 9 日](#July2015)
-   [2015 年 2 月 23 日](#February2015)

### 2018 年 10 月 30 日
{: #October2018}

**サービス・バージョン** - `3.4.5`<br/> **インターフェース・バージョン** - `2017-10-13`

{{site.data.keyword.personalityinsightsshort}} サービスが、すべての地域でトークン・ベースの Identity and Access Management (IAM) 認証にマイグレーションされました。 すべての {{site.data.keyword.cloud_notm}} サービスが、IAM 認証を使用するようになりました。 各ロケーションで {{site.data.keyword.personalityinsightsshort}} サービスのマイグレーションが行われた日付を次に示します。

-   ダラス (**us-south**): 2018 年 10 月 30 日
-   フランクフルト (**eu-de**): 2018 年 10 月 30 日
-   ワシントン DC (**us-east**): 2018 年 6 月 11 日
-   シドニー (**au-syd**): 2018 年 6 月 4 日

IAM 認証への移行による影響は、新規のサービス・インスタンスと既存のサービス・インスタンスとで異なります。

-   *任意のロケーションで作成したすべての新規サービス・インスタンス*が、IAM 認証を使用してサービスにアクセスするようになりました。 ベアラー・トークンまたは API キーのいずれかを渡すことができます。 つまり、トークンを使用すれば、認証済み要求がサポートされるので、呼び出すたびにサービス資格情報を埋め込む必要がありません。API キーは HTTP 基本認証を使用します。 {{site.data.keyword.watson}} SDK を使用する場合は、API キーを渡して SDK にトークンのライフサイクルを管理させることができます。
-   *示されているマイグレーションの日付よりも前にロケーションで作成した既存のサービス・インスタンス* では、IAM 認証を使用するようにそれらを更新するまで、認証に以前の Cloud Foundry サービス資格情報の `{username}` と `{password}` が引き続き使用されます。 {{site.data.keyword.personalityinsightsshort}} サービスはステートレスであるため、以下のステップを実行して、IAM 認証を使用するように既存のサービス・インスタンスを変更することができます。 

    1.  サービス・インスタンスを削除して再作成する。
    1.  IAM 認証を使用するように、アプリケーション・コードを変更する。

詳しくは、以下の資料を参照してください。

-   サービス・インスタンスで使用する認証メカニズムを確認するには、[{{site.data.keyword.cloud_notm}} ダッシュボード ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/dashboard/apps){: new_window} で対象のインスタンスをクリックして、サービス資格情報を表示します。
-   Watson サービスで IAM トークンを使用する方法の詳細については、[IAM トークンによる認証](/docs/services/watson?topic=watson-iam)を参照してください。
-   Watson サービスで IAM API キーを使用する方法の詳細については、[IAM サービスの API キー](/docs/services/watson?topic=watson-api-key-bp)を参照してください。
-   IAM 認証の使用例については、[API リファレンス ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/apidocs/personality-insights){: new_window}を参照してください。

### 2018 年 6 月 11 日
{: #June2018b}

**サービス・バージョン** - `3.4.5`<br/> **インターフェース・バージョン** - `2017-10-13`

ワシントン DC (**us-east**) でホストされるサービス・インスタンスおよびアプリケーションを対象に、サービスが新しい API 認証プロセスをサポートするようになりました。 詳しくは、[2018 年 10 月 30 日のサービス更新](#October2018)を参照してください。

### 2018 年 6 月 4 日
{: #June2018a}

**サービス・バージョン** - `3.4.5`<br/> **インターフェース・バージョン** - `2017-10-13`

シドニー (**au-syd**) でホストされるサービス・インスタンスおよびアプリケーションを対象に、サービスが新しいAPI 認証プロセスをサポートするようになりました。 詳しくは、[2018 年 10 月 30 日のサービス更新](#October2018)を参照してください。

### 2018 年 3 月 23 日
{: #March2018}

**サービス・バージョン** - `3.4.4`<br/> **インターフェース・バージョン** - `2017-10-13`

-   サービスは、小規模な障害修正によって更新されました。 この変更は、アラビア語、日本語、韓国語の言語に固有のものです。
-   `POST /v3/profile` メソッドで `Accept` 要求ヘッダーが必須になりました。 `application/json` または `text/csv` のいずれかを必ず指定しなければなりません。

### 2017 年 10 月 13 日
{: #October2017}

**サービス・バージョン** - `3.4.0`<br/> **インターフェース・バージョン** - `2017-10-13`

-   パーソナリティー・プロファイルの `Trait` オブジェクトに、`significant` フィールドが含まれるようになりました。 ビッグ・ファイブのディメンション、ビッグ・ファイブのファセット、ニーズ、および価値のそれぞれについて、別々の `Trait` オブジェクトで結果が報告されます。 このオブジェクトの各インスタンスの `significant` フィールドは、以下に示すように、その特性の結果が要求の入力言語 (`Content-Language`) にとって意味があるかどうかについての結果を識別します。

    -   英語、スペイン語、および日本語の場合、このフィールドは、すべてのパーソナリティー特性で、常に `true` になります。
    -   アラビア語と韓国語の場合、このフィールドは、ほとんどのパーソナリティー特性で `true` ですが、サービスのモデルが意味のある結果を生成できない特性については `false` になります。 このフィールドは、特性の定数セットについては `false` になります。 完全リストについては、『[アラビア語および韓国語の入力の制限事項](/docs/services/personality-insights?topic=personality-insights-numeric#limitations)』を参照してください。 このフィールドが `false` である特性の結果についてはいずれも信頼しないでください。

    このサービスの JSON 応答コンテンツについて詳しくは、『[JSON プロファイルの解釈](/docs/services/personality-insights?topic=personality-insights-output)』を参照してください。
-   CSV 出力に、`*_significant` という名前のヘッダーの列が含まれるようになりました。 それぞれの列は、特性が意味があるものかどうかを示すためのブール値を提供します。 このサービスの CSV 応答コンテンツについて詳しくは、『[CSV プロファイルについて理解する (Understanding a CSV profile)](/docs/services/personality-insights?topic=personality-insights-outputCSV)』を参照してください。
-   このインターフェースの最新バージョンを使用するには、インターフェース・バージョン `2017-10-13` を `version` パラメーターに指定します。

### 2017 年 9 月 18 日
{: #September2017}

**サービス・バージョン** - `3.3.0`<br/> **インターフェース・バージョン** - `2016-10-19`

本サービスは、韓国語 (`ko`) での入力コンテンツをサポートするようになりました。 韓国語入力での平均絶対誤差 (MAE) と平均相関について詳しくは、『[言語ごとの MAE および平均相関 (Per-language average MAE and correlation)](/docs/services/personality-insights?topic=personality-insights-science#precisePerLanguage)』を参照してください。

本サービスのモデルは、韓国語入力のいくつかのパーソナリティー特性について、意味のある百分位数とロー・スコアを生成できません。 これらの特性の結果について詳しくは、『[アラビア語と韓国語の制限事項 (Limitations for Arabic and Korean input)](/docs/services/personality-insights?topic=personality-insights-numeric#limitations)』を参照してください。

### 2017 年 4 月 10 日
{: #April2017}

**サービス・バージョン** - `3.1.7`<br/> **インターフェース・バージョン** - `2016-10-19`

-   大量の入力コンテンツを含む要求の処理方法が変更されました。 サービスは、最大 20 MB のコンテンツを受け入れます。 ただし、*GloVe* に基づくモデルの場合、正確度は 3000 ワード前後の入力で横ばいになります。この動作は、テキストの量が増えるほど正確度が向上する、以前のモデルと異なります。一般にこのサービスは、正確なプロファイルを生成するために、以前のモデルと同じ量のコンテンツを必要としなくなりました。 しかし、追加のコンテンツには追加の処理時間が必要であり、要求が完了する前にタイムアウトになる可能性があります。

    そのため、サービスは、大きい要求のコンテンツの最初の 250 KB のみ (HTML または JSON のマークアップはカウントしない) を抽出して使用するようになりました。 単語数は言語およびテキストの性質によって変化するため、この数値は正確な単語数に対応するわけではありません。 例えば、英語では平均的なワード長は 4 文字から 5 文字のため、この数値で提供されるワード数は約 50,000 ワードとなり、このサービスに必要なワード数の少なくとも 15 倍になります。 応答 JSON の `word_count` フィールドは、サービスが要求に使用するワード数を示しています。それは、入力内のワード数より少ない可能性があります。

    サービスは、現在も、最大の正確度を得るために厳密に必要なワード数より多くのワード数に基づいてプロファイルを作成しているため、過去と同程度の正確度のプロファイルを生成します。ただし、サービスの応答時間は以前よりずっと速くなっています。 入力コンテンツの一部のみを使用する要求の場合、サービスは、ユーザーにその事実を認識させるために、以下の `CONTENT_TRUNCATED` 警告メッセージを返します。

    `For maximum accuracy while also optimizing processing time, only the first 250KB of input text (excluding markup) was analyzed. Accuracy levels off at approximately 3K words so this did not affect the accuracy of the profile.`

    詳しくは、『[十分な入力の提供](/docs/services/personality-insights?topic=personality-insights-input#sufficient)』を参照してください。
-   サービスは、小規模なセキュリティー修正によって更新されました。

### 2017 年 3 月 1 日
{: #March2017}

**サービス・バージョン** - `3.1.6`<br/> **インターフェース・バージョン** - `2016-10-19`

サービスは、ロギングの小規模な機能拡張によって更新されました。

### 2017 年 2 月 20 日
{: #February2017b}

**サービス・バージョン** - `3.1.5.1`<br/> **インターフェース・バージョン** - `2016-10-19`

サービスで、小規模なセキュリティー修正と障害修正による更新、および API 呼び出しの計量を改善するための更新が行われました。

### 2017 年 2 月 13 日
{: #February2017}

**サービス・バージョン** - `3.1.4`<br/> **インターフェース・バージョン** - `2016-10-19`

-   消費嗜好性リストが改善されました。 リストは、個人の主要なライフスタイル習慣と消費者特性を理解するために最も重要な嗜好性だけを含むようになりました。 消費嗜好性リストは、51 から 42 の項目に短縮されました。 残った項目は、さまざまな商品、サービス、およびアクティビティーを好む、筆者の傾向をより簡潔に表わし、結果に基づいた行動を取りやすくします。

    サービスは、以下の 9 個の消費嗜好性を返さなくなりました。

    -   <code>consumption_preferences_shopping</code> カテゴリーには、以下が含まれなくなりました。
        -   <code>consumption_preferences_automobile_resale_value</code>
    -   <code>consumption_preferences_reading</code> カテゴリーには、以下が含まれなくなりました。
        -   <code>consumption_preferences_read_motive_enjoyment</code><br/>
        -   <code>consumption_preferences_read_motive_information</code><br/>
        -   <code>consumption_preferences_read_motive_mandatory</code><br/>
        -   <code>consumption_preferences_read_motive_relaxation</code>
    -   <code>consumption_preferences_health_and_activity</code> カテゴリーには、以下が含まれなくなりました。
        -   <code>consumption_preferences_adventurous_sports</code>
        -   <code>consumption_preferences_fast_food_frequency</code>
    -   <code>consumption_preferences_volunteering</code> カテゴリーには、以下が含まれなくなりました。
        -   <code>consumption_preferences_volunteering_time</code>
        -   <code>consumption_preferences_volunteer_learning</code>

    残った嗜好性について詳しくは、『[消費嗜好性](/docs/services/personality-insights?topic=personality-insights-preferences)』を参照してください。
-   *アラビア語入力*の平均絶対誤差 (MAE) と平均相関に関する情報が、『[言語ごとの MAE と平均相関](/docs/services/personality-insights?topic=personality-insights-science#precisePerLanguage)』から入手できるようになりました。 さらに、このサービスのモデルは、パーソナリティー特性の集合について、意味のある百分位数とロー・スコアを生成できません。 これらの特性の結果について詳しくは、『[アラビア語と韓国語の制限事項 (Limitations for Arabic and Korean input)](/docs/services/personality-insights?topic=personality-insights-numeric#limitations)』を参照してください。

### 2017 年 1 月 13 日
{: #January2017}

**サービス・バージョン** - `3.1.2.1`<br/> **インターフェース・バージョン** - `2016-10-19`

Personality Insights サービスは、いくつかの小規模な障害修正によって更新されました。

### 2016 年 12 月 15 日
{: #December2016}

**サービス・バージョン** - `3.1.1`<br/> **インターフェース・バージョン** - `2016-10-19`

アラビア語の入力テキストについて、{{site.data.keyword.personalityinsightsshort}} サービスは、*GloVe* を使用してパーソナリティー・プロファイルを開発するようになりました。 サービスは、現在、どの言語についても、Linguistic Inquiry and Word Count (LIWC) 心理言語学ディクショナリーを使用していません。 このサービスでのパーソナリティー・ポートレイトの開発方法について詳しくは、『[パーソナリティー特性の推測方法](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)』を参照してください。

### 2016 年 11 月 15 日
{: #November2016}

**サービス・バージョン** - `3.1.0`<br/> **インターフェース・バージョン** - `2016-10-19`

-   日本語の入力テキストについて、{{site.data.keyword.personalityinsightsshort}} サービスは、*GloVe* を使用してパーソナリティー・プロファイルを開発するようになりました。 サービスは、現在、日本語の入力については、Linguistic Inquiry and Word Count (LIWC) 心理言語学ディクショナリーを使用していません。 詳しくは、『[パーソナリティー特性の推測方法](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)』を参照してください。
-   `ConsumptionPreferencesCategory` オブジェクトと `ConsumptionPreferences` オブジェクトの `name` フィールドは、`Accept-Language` 要求ヘッダーによって指定された言語でローカライズされたストリングで返されるようになりました。
-   この更新には、いくつかの小規模な障害修正が含まれています。

### 2016 年 10 月 20 日
{: #October2016b}

**サービス・バージョン** - `3.0.0`<br/> **インターフェース・バージョン** - `2016-10-19`

{{site.data.keyword.personalityinsightsshort}} サービスと API が大幅に更新されました。 API は、バージョン 2 からバージョン 3 に増分され、新しいフィーチャーが提供されています。 このリリース・ノートの残りのセクションでは、それらの変更について詳しく説明します。

バージョン 3 は、バージョン 2 と互換性がありません。新しいフィーチャーと変更を利用するために、バージョン 3 にマイグレーションすることをお勧めします。バージョン 3 へのマイグレーションは、新規バージョンのリリース・ノートに記載されている変更を使用するための、アプリケーションの更新と再デプロイのみで構成されています。 {{site.data.keyword.cloud_notm}} にサービスの新規インスタンスを作成する必要はなく、`v3` API の呼び出しのみが必要になります。

{{site.data.keyword.personalityinsightsshort}} API のバージョン 2 は、まもなくサービスから削除されます。 できるだけ速やかにバージョン 3 にマイグレーションすることを強くお勧めします。
{: note}

#### バージョン 3 の詳細情報

この資料ではこれから、{{site.data.keyword.personalityinsightsshort}} API のバージョン 3 について説明します。 以下のセクションで、インターフェースの新規バージョンの変更を要約します。

-   `/v3/profile` メソッドの呼び出しについて詳しくは、『[プロファイルの要求](/docs/services/personality-insights?topic=personality-insights-input)』を参照してください。
-   `/v3/profile` メソッドの応答について詳しくは、『[JSON プロファイルの解釈](/docs/services/personality-insights?topic=personality-insights-output) 』および『[CSV プロファイルの解釈](/docs/services/personality-insights?topic=personality-insights-outputCSV)』を参照してください。
-   バージョン 3 インターフェースについて詳しくは、『[API リファレンス![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/apidocs/personality-insights){: new_window}』を参照してください。

#### <code>/v3/profile</code> メソッドのパラメーターの変更

`/v3/profile` メソッドのパラメーターは以下のように変更されました。

-   API は、`consumption_preferences` という名前のオプション照会パラメーターを提供するようになりました。 このパラメーターは、消費嗜好性について推定される情報が結果とともに返されるかどうかを示すブール値を受け入れます。 デフォルトでは、この情報は応答には含まれません。 詳しくは、『[消費嗜好性の新規フィーチャー](#cp)』を参照してください。
-   必須の `version` 照会パラメーターが API に含まれるようになりました。このパラメーターは、要求される API のバージョンと、`YYYY-MM-DD` 形式の日付 (例えば、2016 年 10 月 19 日であれば `2016-10-19` と指定) として応答フォーマットを識別するストリングを受け入れます。 このパラメーターは、既存のクライアントを中断せずに、サービスが新しいバージョン用に API や応答フォーマットを更新することを可能にします。 API のバージョン 3 の初期ストリングは `2016-10-19` です。

    指定する日付は、サービスのバージョンと完全に一致している必要はありません。 本サービスは指定された日付までのバージョンを使用します。 バージョン 3 のリリース日付より前の日付を指定すると、サービスは API のバージョン 3 を使用します。 将来の日付、または最新バージョンより後の日付を指定すると、サービスは最新バージョンを使用します。
-   `include_raw` 照会パラメーターの名前は `raw_scores` に変更されました。
-   `headers` 照会パラメーターの名前は `csv_headers` に変更されました。

#### 消費嗜好性の新規フィーチャー
{: #cp}

消費嗜好性フィーチャーは、さまざまな消費者傾向を示す、筆者の傾向の標識を提供します。 `consumption_preferences` 照会パラメーターを `true` の値を指定して `/v3/profile` メソッドに渡すと、サービスは、`Profile` オブジェクトとともに以下の追加結果を返します。

-   `ConsumptionPreferencesCategory` オブジェクトの配列を提供する `consumption_preferences` フィールド。
-   それぞれの `ConsumptionPreferencesCategory` オブジェクトには、以下のフィールドが含まれます。
    -   `consumption_preference_category_id`: 消費嗜好性の 1 つのカテゴリーの ID。
    -   `name`: ユーザーから見える、カテゴリーの名前。
    -   `consumption_preferences`: カテゴリーの個別嗜好性の入力テキストから推定される結果を提供する `ConsumptionPreferences` オブジェクトの配列。
-   それぞれの `ConsumptionPreferences` オブジェクトには、以下のフィールドが含まれます。
    -   `consumption_preference_id`: 消費嗜好性の 1 つの ID。
    -   `name`: ユーザーから見える、消費嗜好性の名前。
    -   `score`: 以下のような消費嗜好性のスコア。

        -   `0.0` は可能性が低いことを示しています
        -   `0.5` は中立を示しています
        -   `1.0` は可能性が高いことを示しています

        一部の嗜好性のスコアはバイナリーで、中立値を許可しません。 スコアは、正規化された百分位数ではなく、入力テキストから推定された結果に基づく嗜好性を示しています。

消費嗜好性について詳しくは、『[消費嗜好性](/docs/services/personality-insights?topic=personality-insights-preferences)』を参照してください。

両方の消費嗜好性オブジェクトの `name` フィールドは、`Accept-Language` 要求ヘッダーに指定された言語に関係なく、常に英語で返されます。
{: note}

#### JSON オブジェクトおよびフィールドの変更

JSON の入出力オブジェクトとそれらのフィールドは、以下のように簡略化および明確化されました。

-   以下のフィールドは、要求によって `/v3/profile` メソッドに渡せる JSON `ContentItem` オブジェクトから削除されました。
    -   `userid`
    -   `sourceid`
    -   `charset` (以前は非推奨)

    これらのオブジェクトは、JSON 要求の本体で `Content` オブジェクトの `contentItems` 配列の要素として渡します。
-   `/v3/profile` メソッドによって返される JSON `Profile` オブジェクトの以下のフィールドが変更されました。
    -   以下のフィールドは削除されました。
        -   `id`
        -   `source`
    -   `tree` フィールドは削除されました。 これは、以下の 4 つの新規フィールドに置き換えられています。
        -   ビッグ・ファイブのパーソナリティー特性の `personality`。
        -   ニーズ特性の `needs`。
        -   価値特性の `values`。
        -   曜日および時刻でのコンテンツの分布に関する時間的結果の `behavior`。 このフィールドは、タイム・スタンプのある JSON 入力でのみ返されます。

        この変更は、事実上、JSON `Profile` オブジェクトで 1 段高いレベルに結果を移動して、再帰レベルを除去します。
    -   `processed_lang` フィールドの名前は `processed_language` に変更されました。
-   `/v3/profile` メソッドによって返される JSON `Trait` オブジェクトの以下のフィールドが名前変更されました。
    -   JSON `Trait` オブジェクトの `id` フィールドの名前は `trait_id` に変更されました。
    -   JSON `Trait` オブジェクトの `percentage` フィールドの名前は `percentile` に変更されました。
-   `/v3/profile` メソッドによって返される JSON `Trait` オブジェクトの以下のフィールドは削除されました。
    -   `sampling_error`
    -   `raw_sampling_error`

    サービスは、結果の精度を限定する平均絶対誤差 (MAE) を報告するようになりました。 さまざまな入力テキスト量での MAE について詳しくは、『[十分な入力の提供](/docs/services/personality-insights?topic=personality-insights-input#sufficient)』を参照してください。
-   `Profile` オブジェクトの `personality`、`needs`、および `values` の各フィールドでは、今も JSON `Trait` オブジェクトが返されます。 しかし、`behavior` フィールドは、以下のフィールドがある、`Behavior` という名前の JSON オブジェクトの配列を返します。
    -   `trait_id`
    -   `name`
    -   `category`
    -   `percentage`

    さらに、行動情報は、値のツリーとして返されなくなりました。 出力は、すべての時間的特性 (曜日と時刻) をリストする単一配列で構成されています。
-   `/v3/profile` メソッドによって返される可能性がある JSON `Warnings` オブジェクトの `id` フィールドの名前は `warnings_id` に変更されました。

#### JSON ID の変更
{: #ids}

`Trait` オブジェクトおよび新規の `Behavior` オブジェクトの `trait_id` (以前の `id`) フィールドに対してサービスが返す JSON ID は、以下のように変更されました。

-   ビッグ・ファイブディメンションの ID は、ストリング `big5_` で開始されるようになりました。
-   ビッグ・ファイブのファセットの ID は、ストリング `facet_` で開始されるようになりました。
-   ニーズの ID は、ストリング `need_` で開始されるようになりました。
-   価値の ID は、ストリング `value_` で開始されるようになりました。
-   すべての時間的特性の ID は、ストリング `behavior_` で開始されるようになりました。
-   時刻に関連した時間的特性の ID では、12 時間表記の時刻 (例えば、`0:00 am`) ではなく、4 桁の 24 時間表記の時刻 (例えば、`behavior_0000`) が使用されるようになりました。
-   文字はすべて小文字になりました。
-   スペースとハイフンは、アンダースコアーになりました。

#### CSV ヘッダーの変更
{: #headers}

CSV 出力についてサービスが返せるオプションの列ヘッダーは以下のように変更されました。

-   JSON 出力の `trait_id` について述べられているすべての変更は、CSV ヘッダーにも適用されます。
-   ビッグ・ファイブディメンションのロー・スコアのヘッダーは、ストリング `big5_` で開始されるようになりました。
-   ビッグ・ファイブのファセットのロー・スコアのヘッダーは、ストリング `facet_` で開始されるようになりました。
-   ニーズのロー・スコアのヘッダーは、ストリング `need_` で開始されるようになりました。
-   価値のロー・スコアのヘッダーは、ストリング `value_` で開始されるようになりました。
-   処理済みの言語列のヘッダーは、`processed_lang` ではなく、`processed_language` に変更されました。
-   `user` 列と `source_id` 列は返されなくなりました。
-   文字はすべて小文字になりました。
-   スペースとハイフンは、アンダースコアーになりました。

#### <code>visualize</code> メソッドの削除

サービスの API のバージョン 2 には、以前のリリースで `/v3/profile` メソッドへの呼び出しの結果を視覚化するために使用されていた、非推奨の `visualize` メソッドが含まれていました。 この `visualize` メソッドは、サービスの API から削除されました。 サービスは、プロファイルのグラフィック視覚化を可能にする JavaScript ファイルの集合を引き続き提供します。 詳しくは、[プロファイルの視覚化](/docs/services/personality-insights?topic=personality-insights-overviewDevelopers#visualize) を参照してください。

### 2016 年 10 月 12 日
{: #October2016a}

スペイン語の入力テキストについて、{{site.data.keyword.personalityinsightsshort}} サービスは、*GloVe* を使用してパーソナリティー・プロファイルを開発するようになりました。 サービスは、現在、スペイン語の入力については、Linguistic Inquiry and Word Count (LIWC) 心理言語学ディクショナリーを使用していません。 サービスは、英語入力テキストの新規モデルの使用を 8 月 31 日に開始しました。 まもなく他の入力言語にもこの新規モデルを適用する予定です。 新規モデルについて詳しくは、『[パーソナリティー特性の推測方法](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)』を参照してください。

### 2016 年 8 月 31 日
{: #August2016}

サービスは、*GloVe* を使用してパーソナリティー・プロファイルを開発するようになりました。 *GloVe* とは、オープン・ソースの単語埋め込み手法です。 詳しくは、『[パーソナリティー特性の推測方法](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)』を参照してください。 サービスはこの新しい方法を英語入力テキストでのみ使用しています。 その他の言語については、サービスは引き続き Linguistic Inquiry and Word Count (LIWC) 心理言語ディクショナリーを使用しています。 サービスでは、将来すべての言語でオープン・ソースによる手法を使用する予定です。

英語入力で使用される新規モデルについて、サービスは、トレーニングされたモデルの結果の平均絶対誤差 (MAE) を報告します。 さまざまな入力テキスト量によって MAE がどう変わるかについて詳しくは、『[十分な入力の提供](/docs/services/personality-insights?topic=personality-insights-input#sufficient)』を参照してください。

{{site.data.keyword.IBM_notm}} は、将来英語以外のモデルの MAE を報告する予定です。 {{site.data.keyword.IBM_notm}} は、サンプリング・エラーの代わりに MAE を使用して、提供される入力テキスト量によってサービスの精度がどのように変化するかを究明する予定です。

### 2016 年 7 月 14 日
{: #July2016b}

-   アラビア語入力について、サービスは、パフォーマンス上の理由により、入力テキストの量を削減できるようになりました。 ある特定のしきい値で、アラビア語の結果の正確度は、ワード数を増やしても向上しなくなります。 サービスがアラビア語の入力テキストを削減すると、以下のメッセージとともに `PARTIAL_TEXT_USED` 警告が返されます。

    `The text provided to compute the profile was trimmed for performance reasons. This action does not affect the accuracy of the output, as not all of the input text was required.`
-   この更新には、障害修正および内部改善が含まれています。

### 2016 年 7 月 1 日
{: #July2016a}

-   サービスの価格プランが、{{site.data.keyword.personalityinsightsshort}} ユーザーに低い価格を提供するようになりました。 詳しくは、[{{site.data.keyword.cloud_notm}} カタログ ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/catalog/services/personality-insights/){: new_window}の『{{site.data.keyword.personalityinsightsshort}} サービス』を参照してください。
-   `Accept-Language` ヘッダーを使用して指定できる、サポート対象の応答言語リストには、現在、以下の言語が含まれています。
    -   `ar` (アラビア語)
    -   `de` (ドイツ語)
    -   `en` (英語、デフォルト)
    -   `es` (スペイン語)
    -   `fr` (フランス語)
    -   `it` (イタリア語)
    -   `ja` (日本語)
    -   `ko` (韓国語)
    -   `pt-br` (ブラジル・ポルトガル語)
    -   `zh-cn` (中国語 (簡体字))
    -   `zh-tw` (中国語 (繁体字))

    詳しくは、『[要求および応答の言語の指定](/docs/services/personality-insights?topic=personality-insights-input#languages-input)』を参照してください。
-   `/v2/profile` メソッドは、現在、以下の HTTP 状況コードを返すことができます。
    -   429 *Too Many Requests*: サービスが処理しているコンテンツ言語の要求数が多過ぎます。 しばらく待ってから、要求を再試行してください。 その言語について多くの要求を送信している場合は、要求を送信する速度を絞ることを検討してください。
    -   504 *Gateway Timeout*: 要求がタイムアウトになったか、処理に長い時間がかかりました。 しばらく待ってから、要求を再試行してください。 入力に含まれているワードが多すぎる (例えば、20,000 を超える) 場合は、ワード数を削減することを検討してください。ただし、意味のある入力のガイドラインは維持してください。

    このメソッドは、503 *Service Unavailable* を返さなくなりました。 返される可能性のある応答コードについて詳しくは、『[API リファレンス![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/apidocs/personality-insights){: new_window}』を参照してください。
-   この更新には、障害修正および内部改善が含まれています。

### 2016 年 6 月 7 日
{: #June2016b}

-   サービスは、Cross-Origin Resource Sharing (CORS) をサポートして、ブラウザー・ベースのクライアントが直接サービスを呼び出すことを許可するようになりました。 詳しくは、『[CORS サポート](/docs/services/personality-insights?topic=personality-insights-overviewDevelopers#CORS)』を参照してください。
-   日本語テキストに対するサービスのパフォーマンスが著しく向上しました。
-   この更新には、障害修正および内部改善が含まれています。

### 2016 年 6 月 1 日
{: #June2016a}

サービスは、障害修正および内部改善のために更新されました。 また、サービスによって返される JSON 結果に、新しい最上位フィールド `warnings` が追加されました。 詳しくは、「[API reference ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/apidocs/personality-insights){: new_window}」を参照してください。

### 2016 年 5 月 17 日
{: #May2016}

サービスは、障害修正および内部改善のために更新されました。

### 2016 年 3 月 18 日
{: #March2016}

サービスは、以下の言語をサポートするようになりました。

-   サービスでは、入力テキストとしてアラビア語 (`ar`)、英語 (`en`)、スペイン語 (`es`)、および日本語 (`ja`) の 4 つの言語がサポートされています。 言語を指定するには、プレーン・テキストおよび HTML の入力用の HTTP `Content-Language` ヘッダーを使用するか、JSON 入力用の `ContentItem` オブジェクトの `language` プロパティーを使用します。
-   サービスでは、応答についても同じ 4 つの言語がサポートされています。 応答の言語を指定するには、`Accept-Language` ヘッダーを使用します。

入力と応答には、任意の言語の組み合わせを使用できます。 言語を示さないと、サービスはデフォルトで英語を使用します。 詳しくは、『[要求および応答の言語の指定](/docs/services/personality-insights?topic=personality-insights-input#languages-input)』を参照してください。 さらに、ブログ投稿『[Arabic and Japanese support is now available for {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.personalityinsightsshort}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/blogs/watson/2016/04/arabic-japanese-support-now-available-ibm-watson-personality-insights/){: new_window}』を参照することもできます。

アラビア語のコンテンツは、他の言語より、分析にかなり多くのコンピューティング・サイクルを必要とするため、処理に非常に長い時間がかかります。 サービスは、すべての言語の入力テキスト量について、同じ 20 MB の制限をサポートしていますが、アラビア語のコンテンツの実際的制限は、タイムアウトを避けるために、それより少なくなる可能性があります。 日本語のコンテンツも処理に時間がかかりますが、アラビア語に比べれば、その遅延はそれほど重大な意味を持ちません。
{: note}

### 2015 年 7 月 9 日
{: #July2015}

-   *言語サポート。* 英語とスペイン語のコンテンツを分析することができます。 入力テキストの言語は、`/v2/profile` メソッドの `Content-Language` ヘッダーを使用して示します。 言語の指定について詳しくは、『[要求および応答の言語の指定](/docs/services/personality-insights?topic=personality-insights-input#languages-input)』を参照してください。
-   *ロー・スコア。* 入力テキストとサービスのモデルから計算されるロー・スコアとロー・サンプリング・エラーを要求することができます。 これらの値は、正規化もサンプル母集団との比較も行われません。 ロー・スコアは、特定のシナリオにカスタム正規化を適用したいお客様や、サンプル母集団との比較を必要としないお客様にとって有用です。 ロー・スコアを要求するには、`/v2/profile` メソッドの `include_raw` 照会パラメーターを `true` に設定します。 詳しくは、『[数値結果の解釈](/docs/services/personality-insights?topic=personality-insights-numeric)』を参照してください。
-   *モデルの機能拡張。* 最新の研究に基づいて、{{site.data.keyword.IBM_notm}} は、パーソナリティー特性の推定のいくつかの方法をさらに改善しました。 これらの変更は、サービスのユーザーから認識されることはありません。 変更によって、サービスから入手した以前の結果が無効化されることもありません。 これらの研究、および推定に対するサービスの方法について詳しくは、『[パーソナリティー特性の推測方法](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)』を参照してください。

### 2015 年 2 月 23 日
{: #February2015}

2015 年 2 月 23 日現在、{{site.data.keyword.personalityinsightsshort}} サービスは、ベータ版として使用可能だった、以前の User Modeling サービスの一般出荷可能 (GA) バージョンです。 GA 版では、ユーザーは新規サービスのインスタンスにマイグレーションする必要があります。 サービスのベータ版と GA 版には以下のような違いがあります。

-   {{site.data.keyword.personalityinsightsshort}} サービスは、User Modeling サービスと互換性があります。 記載されている違いは、現在のアプリケーションに影響を与えずに、柔軟性を向上させ、結果を改善します。
-   {{site.data.keyword.cloud_notm}} でのサービスの作成に使用されるパラメーターが変更されました。 現在は、`user_modeling` の代わりに `personality_insights` というサービス名を使用し、`user_modeling_free_plan` の代わりに `"IBM Watson Personality Insights Monthly Plan"` というサービス・プランを使用するようになりました。
-   `/v2/profile` メソッドは、2 つの新規入力フォーマットを受け入れます。 `Content-Type` ヘッダーは、JSON (`application/json`) に加え、プレーン・テキスト (`text/plain`) (デフォルト) と HTML (`text/html`) の入力フォーマットを受け入れるようになりました。
-   `/v2/profile` メソッドは、新規出力フォーマットを返すようになりました。 `Accept` ヘッダーは、JSON (`application/json`) (デフォルト) に加え、CSV (`text/csv`) の出力フォーマットを受け入れるようになりました。
-   `/v2/profile` メソッドに、パーセンテージ値を報告する各特性の新しい出力要素 `sampling_error` が含まれるようになりました。 サンプリング・エラーは、入力テキストに基づく筆者の百分位数についてのサービスの信頼度レベルを示す二重値として返されます。
-   ニーズ・モデルは、特性の値の分布をより適切に正規化するために、改善されたトークン化および処理を採用しています。 User Modeling API によって生成された結果は、再計算することをお勧めします。
-   `visualize` メソッドは現在非推奨となり、将来のリリースからは完全に削除されます。 サンプル・アプリケーションに付属する `personality.js` JavaScript ファイルを使用すると、クライアントから同様の結果を出すことができます。 `textsummary.js` JavaScript ファイルは、サービスの結果について追加のフォーマット設定を提供します。
