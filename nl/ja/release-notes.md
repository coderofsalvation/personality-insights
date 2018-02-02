---

copyright:
  years: 2015, 2017
lastupdated: "2017-11-28"

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

# リリース・ノート
{: #release-notes}

以下のセクションに、{{site.data.keyword.personalityinsightsshort}} サービスの各リリースで組み込まれた新しいフィーチャーおよび変更を示します。特に断りのない限り、変更はすべて後方互換であり、すべての新規および既存のアプリケーションで自動的かつトランスペアレントに使用可能になりました。
{: shortdesc}

> **注:** このリリース・ノートは、すべての最新更新の*サービス・バージョン*と*インターフェース・バージョン*を文書化しています。`version` 照会パラメーターによって*インターフェース・バージョン*を指定して、その更新で使用可能になった新しいフィーチャーおよび機能を使用します。サービスは、`X-Service-Api-Version` 応答ヘッダーによって両方のバージョンを返します。

## 2017 年 10 月 13 日
{: #October2017}

**サービス・バージョン:** `3.4.0`<br/> **インターフェース・バージョン:** `2017-10-13`

-   パーソナリティー・プロファイルの `Trait` オブジェクトに、追加の `significant` フィールドが含まれるようになりました。ビッグ・ファイブのディメンション、ビッグ・ファイブのファセット、ニーズ、および価値のそれぞれについて、別々の `Trait` オブジェクトで結果が報告されます。このオブジェクトの各インスタンスの `significant` フィールドは、以下に示すように、その特性の結果が要求の入力言語 (`Content-Language`) にとって意味があるかどうかについての結果を識別します。

    -   英語、スペイン語、および日本語の場合、このフィールドは、すべてのパーソナリティー特性で、常に `true` になります。
    -   アラビア語と韓国語の場合、このフィールドは、ほとんどのパーソナリティー特性で `true` ですが、サービスのモデルが意味のある結果を生成できないものについては `false` になります。このフィールドは、特性の定数セットについては `false` になります。完全リストについては、『[アラビア語と韓国語の制限事項 (Limitations for Arabic and Korean input)](/docs/services/personality-insights/numeric.html#limitations)』を参照してください。このフィールドが `false` である特性の結果についてはいずれも信頼しないでください。

    このサービスの JSON 応答コンテンツについては、『[JSON プロファイルの解釈](/docs/services/personality-insights/output.html)』を参照してください。
-   CSV 出力に、`*_significant` という名前のヘッダーの追加列が含まれるようになりました。それぞれの列は、特性が意味があるものかどうかを示すためのブール値を提供します。このサービスの CSV 応答コンテンツについては、『[CSV プロファイルについて理解する (Understanding a CSV profile)](/docs/services/personality-insights/output-csv.html)』を参照してください。
-   このインターフェースの最新バージョンを使用するための、`version` パラメーターによって指定されるインターフェース・バージョンは `2017-10-13` です。

## 2017 年 9 月 18 日
{: #September2017}

**サービス・バージョン:** `3.3.0`<br/> **インターフェース・バージョン:** `2016-10-19`

本サービスは、韓国語 (`ko`) での入力コンテンツをサポートするようになりました。韓国語入力での平均絶対誤差 (MAE) と平均相関については、『[言語ごとの MAE および平均相関 (Per-language average MAE and correlation)](/docs/services/personality-insights/science.html#precisePerLanguage)』を参照してください。

本サービスのモデルは、韓国語入力のいくつかのパーソナリティー特性について、意味のある百分位数とロー・スコアを生成できません。これらの特性の結果について詳しくは、『[アラビア語と韓国語の制限事項 (Limitations for Arabic and Korean input)](/docs/services/personality-insights/numeric.html#limitations)』を参照してください。

## 2017 年 4 月 10 日
{: #April2017}

**サービス・バージョン:** `3.1.7`<br/> **インターフェース・バージョン:** `2016-10-19`

-   大量の入力コンテンツを含む要求の処理方法が変更されました。サービスは、最大 20 MB のコンテンツを受け入れます。ただし、*GloVe* に基づくモデルの場合、正確度は 3000 ワード前後の入力で横ばいになります。この点は、テキストの量が増えるほど正確度が向上する、以前のモデルと異なります。一般にこのサービスは、正確なプロファイルを生成するために、以前のモデルと同じ量のコンテンツを必要としなくなりました。しかし、追加のコンテンツには追加の処理時間が必要であり、要求が完了する前にタイムアウトになる可能性があります。

    そのため、サービスは、大きい要求のコンテンツの最初の 250 KB のみ (HTML または JSON のマークアップはカウントしない) を抽出して使用するようになりました。単語数は言語およびテキストの性質によって変化するため、この数値は正確な単語数に対応するわけではありません。例えば、英語では平均的なワード長は 4 文字から 5 文字のため、この数値で提供されるワード数は約 50,000 ワードとなり、このサービスに必要なワード数の少なくとも 15 倍になります。応答 JSON の `word_count` フィールドは、サービスが実際に要求に使用するワード数を示しています。それは、入力内のワード数より少ない可能性があります。

    サービスは、現在も、最大の正確度を得るために厳密に必要なワード数より多くのワード数に基づいてプロファイルを作成しているため、過去と同程度の正確度のプロファイルを生成します。ただし、サービスの応答時間は以前よりずっと速くなっています。入力コンテンツの一部のみを使用する要求の場合、サービスは、ユーザーにその事実を認識させるために、以下の `CONTENT_TRUNCATED` 警告メッセージを返します。

    `For maximum accuracy while also optimizing processing time, only the first 250KB of input text (excluding markup) was analyzed. Accuracy levels off at approximately 3K words so this did not affect the accuracy of the profile.`

    詳しくは、『[十分な入力の提供](/docs/services/personality-insights/input.html#sufficient)』を参照してください。
-   サービスは、小規模なセキュリティー修正によって更新されました。

## 古いリリース
{: #older}

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

### 2017 年 3 月 1 日
{: #March2017}

**サービス・バージョン:** `3.1.6`<br/> **インターフェース・バージョン:** `2016-10-19`

{{site.data.keyword.personalityinsightsshort}} サービスは、ロギングの小規模な機能拡張によって更新されました。

### 2017 年 2 月 20 日
{: #February2017b}

**サービス・バージョン:** `3.1.5.1`<br/> **インターフェース・バージョン:** `2016-10-19`

Personality Insights サービスで、小規模なセキュリティー修正と障害修正による更新、および API 呼び出しの計量を改善するための更新が行われました。

### 2017 年 2 月 13 日
{: #February2017}

**サービス・バージョン:** `3.1.4`<br/> **インターフェース・バージョン:** `2016-10-19`

-   消費嗜好性リストが、個人の主要なライフスタイル習慣と消費者特性を理解するために最も重要な嗜好性だけを含むように改善されました。消費嗜好性リストは、51 から 42 の項目に短縮されました。残った項目は、さまざまな商品、サービス、およびアクティビティーを好む、筆者の傾向をより簡潔に表わし、結果に基づいたアクションの実行をより容易にします。サービスは、以下の 9 個の消費嗜好性を返さなくなりました。残った嗜好性について詳しくは、『[消費嗜好性](/docs/services/personality-insights/preferences.html)』を参照してください。

    <table>
      <caption>表 1. 消費嗜好性の変更</caption>
      <tr>
        <th style="text-align:left">カテゴリー</th>
        <th style="text-align:left">削除された消費嗜好性</th>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_shopping</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_automobile_resale_value</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_reading</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_read_motive_enjoyment</code>
            <code>consumption_preferences_read_motive_information</code>
            <code>consumption_preferences_read_motive_mandatory</code>
            <code>consumption_preferences_read_motive_relaxation</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_health_and_activity</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_adventurous_sports</code>
            <code>consumption_preferences_fast_food_frequency</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_volunteering</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_volunteering_time</code>
            <code>consumption_preferences_volunteer_learning</code>
          </p>
        </td>
      </tr>
    </table>

-   *アラビア語入力*の平均絶対誤差 (MAE) と平均相関に関する情報が、『[言語ごとの MAE と平均相関](/docs/services/personality-insights/science.html#precisePerLanguage)』から入手できるようになりました。さらに、このサービスのモデルは、パーソナリティー特性の集合について、意味のある百分位数とロー・スコアを生成できません。これらの特性の結果について詳しくは、『[アラビア語と韓国語の制限事項 (Limitations for Arabic and Korean input)](/docs/services/personality-insights/numeric.html#limitations)』を参照してください。

### 2017 年 1 月 13 日
{: #January2017}

**サービス・バージョン:** `3.1.2.1`<br/> **インターフェース・バージョン:** `2016-10-19`

Personality Insights サービスは、いくつかの小規模な障害修正によって更新されました。

### 2016 年 12 月 15 日
{: #December2016}

**サービス・バージョン:** `3.1.1`<br/> **インターフェース・バージョン:** `2016-10-19`

アラビア語の入力テキストについて、{{site.data.keyword.personalityinsightsshort}} サービスは、*GloVe*と呼ばれるオープン・ソースの単語埋め込み手法を使用してパーソナリティー・プロファイルを開発するようになりました。サービスは、現在、どの言語についても、Linguistic Inquiry and Word Count (LIWC) 心理言語学ディクショナリーを使用していません。このサービスでのパーソナリティー・ポートレイトの開発方法について詳しくは、『[パーソナリティー特性の推測方法](/docs/services/personality-insights/science.html#researchInfer)』を参照してください。

### 2016 年 11 月 15 日
{: #November2016}

**サービス・バージョン:** `3.1.0`<br/> **インターフェース・バージョン:** `2016-10-19`

-   日本語の入力テキストについて、{{site.data.keyword.personalityinsightsshort}} サービスは、*GloVe* と呼ばれるオープン・ソースの単語埋め込み手法を使用してパーソナリティー・プロファイルを開発するようになりました。サービスは現在、日本語入力に Linguistic Inquiry and Word Count (LIWC) 心理言語ディクショナリーを使用していません。詳しくは、『[パーソナリティー特性の推測方法](/docs/services/personality-insights/science.html#researchInfer)』を参照してください。
-   `ConsumptionPreferencesCategory` オブジェクトと `ConsumptionPreferences` オブジェクトの `name` フィールドは、`Accept-Language` 要求ヘッダーによって指定された言語でローカライズされたストリングで返されるようになりました。
-   この更新には、いくつかの小規模な障害修正が含まれています。

### 2016 年 10 月 20 日
{: #October2016b}

**サービス・バージョン:** `3.0.0`<br/> **インターフェース・バージョン:** `2016-10-19`

{{site.data.keyword.personalityinsightsshort}} サービスと API が大幅に更新されました。API は、バージョン 2 からバージョン 3 に増分され、新しいフィーチャーが提供されています。このリリース・ノートの残りのセクションでは、それらの変更について詳しく説明します。

バージョン 3 は、バージョン 2 と後方互換ではありません。新しいフィーチャーと変更を利用するために、バージョン 3 にマイグレーションすることをお勧めします。バージョン 3 へのマイグレーションは、新規バージョンのリリース・ノートに記載されている変更を使用するための、アプリケーションの更新と再デプロイのみで構成されています。{{site.data.keyword.Bluemix_notm}} にサービスの新規インスタンスを作成する必要はなく、`v3` API の呼び出しのみが必要になります。

> **注:** {{site.data.keyword.personalityinsightsshort}} API のバージョン 2 は、近い将来サービスから削除されます。できるだけ速やかにバージョン 3 にマイグレーションすることを強くお勧めします。現在、バージョン 2 のリファレンス資料には『[V2 用の API リファレンス![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/watson/developercloud/personality-insights/api/v2/){: new_window}』からアクセスできます。また、バージョン 2 への呼び出しをテストし、サービスからのライブ応答を表示するための対話式ツールには、『[v2 用の API Explorer (API explorer for v2) ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v2){: new_window}』からアクセスできます。

#### バージョン 3 の詳細情報

この資料ではこれから、{{site.data.keyword.personalityinsightsshort}} API のバージョン 3 について説明します。以下のセクションで、インターフェースの新規バージョンの変更を要約します。

-   `/v3/profile` メソッドの呼び出しについては、『[プロファイルの要求](/docs/services/personality-insights/input.html)』を参照してください。
-   `/v3/profile` メソッドの応答については、『[JSON プロファイルの解釈](/docs/services/personality-insights/output.html) 』および『[CSV プロファイルの解釈](/docs/services/personality-insights/output-csv.html)』を参照してください。
-   バージョン 3 インターフェースの詳細については、『[API リファレンス![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}』を参照してください。

#### <code>/v3/profile</code> メソッドのパラメーターの変更

`/v3/profile` メソッドのパラメーターは以下のように変更されました。

-   API は、`consumption_preferences` という名前のオプション照会パラメーターを提供するようになりました。このパラメーターは、消費嗜好性について推定される情報が結果とともに返されるかどうかを示すブール値を受け入れます。デフォルトでは、この情報は応答には含まれません。詳しくは、『[消費嗜好性の新規フィーチャー](#cp)』を参照してください。
-   `version` という名前の必須照会パラメーターが API に含まれるようになりました。このパラメーターは、要求される API のバージョンと、`YYYY-MM-DD` 形式の日付 (例えば、2016 年 10 月 19 日であれば `2016-10-19` と指定) として応答フォーマットを識別するストリングを受け入れます。このパラメーターは、既存のクライアントを中断せずに、サービスが新しいバージョン用に API や応答フォーマットを更新することを可能にします。API のバージョン 3 の初期ストリングは `2016-10-19` です。

    指定する日付は、サービスのバージョンと完全に一致している必要はありません。本サービスは指定された日付までのバージョンを使用します。バージョン 3 のリリース日付より前の日付を指定すると、サービスは API のバージョン 3 を使用します。将来の日付、または最新バージョンより後の日付を指定すると、サービスは最新バージョンを使用します。
-   `include_raw` 照会パラメーターの名前は `raw_scores` に変更されました。
-   `headers` 照会パラメーターの名前は `csv_headers` に変更されました。

#### 消費嗜好性の新規フィーチャー
{: #cp}

消費嗜好性フィーチャーは、さまざまな消費者傾向を示す、筆者の傾向の標識を提供します。`consumption_preferences` 照会パラメーターを `true` の値を指定して `/v3/profile` メソッドに渡すと、サービスは、`Profile` オブジェクトとともに以下の追加結果を返します。

-   `ConsumptionPreferencesCategory` オブジェクトの配列を提供する `consumption_preferences` フィールド。
-   それぞれの `ConsumptionPreferencesCategory` オブジェクトには、以下のフィールドが含まれます。
    -   `consumption_preference_category_id`: 消費嗜好性の 1 つのカテゴリーの ID。
    -   `name`: ユーザーから見える、カテゴリーの名前。
    -   `consumption_preferences`: カテゴリーの個別嗜好性の入力テキストから推定される結果を提供する `ConsumptionPreferences` オブジェクトの配列。
-   それぞれの `ConsumptionPreferences` オブジェクトには、以下のフィールドが含まれます。
    -   `consumption_preference_id`: 消費嗜好性の 1 つの ID。
    -   `name`: ユーザーから見える、消費嗜好性の名前。
    -   `score`: 消費嗜好性のスコア。多くの嗜好性で、`0.0` は可能性が低いことを示し、`0.5` は中立を示し、`1.0` は可能性が高いことを示しています。一部の嗜好性のスコアはバイナリーで、中立値を許可しません。スコアは、正規化された百分位数ではなく、入力テキストから推定された結果に基づく嗜好性を示しています。

消費嗜好性について詳しくは、『[消費嗜好性](/docs/services/personality-insights/preferences.html)』を参照してください。

> **注:** 現在、両方の消費嗜好性オブジェクトの `name` フィールドは、`Accept-Language` 要求ヘッダーに指定された言語に関係なく、常に英語で返されます。

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
    - `tree` フィールドは削除されました。これは、以下の 4 つの新規フィールドに置き換えられています。
        -   ビッグ・ファイブパーソナリティー特性の `personality`。
        -   ニーズ特性の `needs`。
        -   価値特性の `values`。
        -   曜日および時刻でのコンテンツの分布に関する時間的結果の `behavior`。このフィールドは、タイム・スタンプのある JSON 入力でのみ返されます。

    この変更は、事実上、JSON `Profile` オブジェクトで 1 段高いレベルに結果を移動して、再帰レベルを除去します。
    -   `processed_lang` フィールドの名前は `processed_language` に変更されました。
-   `/v3/profile` メソッドによって返される JSON `Trait` オブジェクトの以下のフィールドが名前変更されました。
    -   JSON `Trait` オブジェクトの `id` フィールドの名前は `trait_id` に変更されました。
    -   JSON `Trait` オブジェクトの `percentage` フィールドの名前は `percentile` に変更されました。
-   `/v3/profile` メソッドによって返される JSON `Trait` オブジェクトの以下のフィールドは削除されました。
    -   `sampling_error`
    -   `raw_sampling_error`

    サービスは、結果の精度を限定する平均絶対誤差 (MAE) を報告するようになりました。さまざまな入力テキスト量での MAE について詳しくは、『[十分な入力の提供](/docs/services/personality-insights/input.html#sufficient)』を参照してください。
-   `Profile` オブジェクトの `personality`、`needs`、および `values` の各フィールドでは、今も JSON `Trait` オブジェクトが返されます。しかし、`behavior` フィールドは、以下のフィールドがある、`Behavior` という名前の JSON オブジェクトの配列を返します。
    -   `trait_id`
    -   `name`
    -   `category`
    -   `percentage`

    さらに、行動情報は、値のツリーとして返されなくなりました。出力は、すべての時間的特性 (曜日と時刻) をリストする単一配列で構成されています。
-   `/v3/profile` メソッドによって返される可能性がある JSON `Warnings` オブジェクトの `id` フィールドの名前は `warnings_id` に変更されました。

#### JSON ID の変更
{: #ids}

`Trait` オブジェクトおよび新規の `Behavior` オブジェクトの `trait_id` (以前の `id`) フィールドに対してサービスが返す JSON ID は、以下のように変更されました。

-   ビッグ・ファイブディメンションの ID は、ストリング `big5_` で開始されるようになりました。
-   ビッグ・ファイブファセットの ID は、ストリング `facet_` で開始されるようになりました。
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
-   ビッグ・ファイブファセットのロー・スコアのヘッダーは、ストリング `facet_` で開始されるようになりました。
-   ニーズのロー・スコアのヘッダーは、ストリング `need_` で開始されるようになりました。
-   価値のロー・スコアのヘッダーは、ストリング `value_` で開始されるようになりました。
-   処理済みの言語列のヘッダーは、`processed_lang` ではなく、`processed_language` に変更されました。
-   `user` 列と `source_id` 列は返されなくなりました。
-   文字はすべて小文字になりました。
-   スペースとハイフンは、アンダースコアーになりました。

#### <code>visualize</code> メソッドの削除

サービスの API のバージョン 2 には、以前のリリースで `/v3/profile` メソッドへの呼び出しの結果を視覚化するために使用されていた、非推奨の `visualize` メソッドが含まれていました。この `visualize` メソッドは、サービスの API から削除されました。サービスは、プロファイルのグラフィック視覚化を可能にする JavaScript ファイルの集合を引き続き提供します。詳しくは、『[プロファイルの視覚化 (Visualizing a profile)](/docs/services/personality-insights/developer-overview.html#visualize)』を参照してください。

### 2016 年 10 月 12 日
{: #October2016a}

スペイン語の入力テキストについて、{{site.data.keyword.personalityinsightsshort}} サービスは、*GloVe* と呼ばれるオープン・ソースの単語埋め込み手法を使用してパーソナリティー・プロファイルを開発するようになりました。このサービスは、スペイン語入力に関して、Linguistic Inquiry and Word Count (LIWC) 心理言語ディクショナリーを使用しなくなりました。サービスは、英語入力テキストの新規モデルの使用を 8 月 31 日に開始しました。近い将来、他の入力言語にもこの新しいモデルが適用されます。新規モデルについて詳しくは、『[パーソナリティー特性の推測方法](/docs/services/personality-insights/science.html#researchInfer)』を参照してください。

### 2016 年 8 月 31 日
{: #August2016}

{{site.data.keyword.personalityinsightsshort}} サービスは、*GloVe* と呼ばれるオープン・ソースの単語埋め込み手法を使用してパーソナリティー・プロファイルを開発するようになりました。詳しくは、『[パーソナリティー特性の推測方法](/docs/services/personality-insights/science.html#researchInfer)』を参照してください。現在、サービスはこの新しい方法を英語入力テキストでのみ使用しています。その他の言語については、サービスは引き続き Linguistic Inquiry and Word Count (LIWC) 心理言語ディクショナリーを使用しています。サービスの将来のバージョンでは、すべての言語でオープン・ソースによる手法が使用されます。

英語入力で使用される新規モデルについて、サービスは、トレーニングされたモデルの結果の平均絶対誤差 (MAE) を報告します。さまざまな入力テキスト量によって MAE がどう変わるかについて、『[十分な入力の提供](/docs/services/personality-insights/input.html#sufficient)』を参照してください。サービスの将来のバージョンは、英語以外のモデルの MAE を報告し、(サンプリング・エラーと対照的に) MAE を使用して、提供される入力テキスト量に基づいてサービスの精度がどのように変化するかを判別することを推奨します。

### 2016 年 7 月 14 日
{: #July2016b}

-   アラビア語入力について、サービスは、パフォーマンス上の理由により、入力テキストの量を削減できるようになりました。ある特定のしきい値で、アラビア語の結果の正確度は、ワード数を増やしても向上しなくなります。サービスがアラビア語の入力テキストを削減すると、以下のメッセージとともに `PARTIAL_TEXT_USED` 警告が返されます。

    `The text provided to compute the profile was trimmed for performance reasons. This action does not affect the accuracy of the output, as not all of the input text was required.`
-   この更新には、追加の障害修正および内部改善が含まれています。

### 2016 年 7 月 1 日
{: #July2016a}

-   サービスの価格プランが、{{site.data.keyword.personalityinsightsshort}} ユーザーに低い価格を提供するように変更されました。詳しくは、{{site.data.keyword.Bluemix_short}} カタログ ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン"){: new_window} の『[{{site.data.keyword.personalityinsightsshort}} サービス』を参照してください。
-   Accept-Language ヘッダーを使用して指定できる、サポート対象の応答言語リストには、現在、以下の言語が含まれています。
    -   ar (アラビア語)
    -   de (ドイツ語)
    -   en (英語、デフォルト)
    -   es (スペイン語)
    -   fr (フランス語)
    -   it (イタリア語)
    -   ja (日本語)
    -   ko (韓国語)
    -   pt-br (ブラジル・ポルトガル語)
    -   zh-cn (中国語 (簡体字))
    -   zh-tw (中国語 (繁体字))

    詳しくは、『[要求および応答の言語の指定](/docs/services/personality-insights/input.html#languages)(https://console.ng.bluemix.net/catalog/services/personality-insights/)]』を参照してください。
-   `/v2/profile` メソッドは、現在、以下の HTTP 状況コードを返すことができます。
    -   429 *Too Many Requests*: サービスが現在処理しているコンテンツ言語の要求数が多過ぎます。しばらく待ってから、要求を再試行してください。その言語について多くの要求を送信している場合は、要求を送信する速度を絞ることを検討してください。
    -   504 *Gateway Timeout*: 要求がタイムアウトになったか、処理に長い時間がかかりました。しばらく待ってから、要求を再試行してください。入力に多数のワード (例えば、20,000 を超えるワード) が含まれている場合は、意味のある入力のガイドラインを維持しつつ、ワード数を削減することを検討してください。

    このメソッドは、503 *Service Unavailable* を返さなくなりました。返される可能性のある応答コードについて詳しくは、『[API リファレンス![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}』を参照してください。
-   この更新には、追加の障害修正および内部改善が含まれています。

### 2016 年 6 月 7 日
{: #June2016b}

-   サービスは、Cross-Origin Resource Sharing (CORS) をサポートして、ブラウザー・ベースのクライアントが直接サービスを呼び出すことを許可するようになりました。詳しくは、『[CORS サポート](/docs/services/personality-insights/developer-overview.html#CORS)』を参照してください。
-   日本語テキストを処理する際のサービスのパフォーマンスが著しく向上しました。
-   この更新には、追加の障害修正および内部改善が含まれています。

### 2016 年 6 月 1 日
{: #June2016a}

{{site.data.keyword.personalityinsightsshort}} サービスは、障害修正および内部改善のために更新されました。また、サービスによって返される JSON 結果に、追加の最上位フィールド `warnings` が追加されました。詳しくは、『[API リファレンス![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}』を参照してください。

### 2016 年 5 月 17 日
{: #May2016}

{{site.data.keyword.personalityinsightsshort}} サービスは、障害修正および内部改善のために更新されました。

### 2016 年 3 月 18 日
{: #March2016}

サービスは、以下の言語をサポートするようになりました。

-   入力テキストの 4 つの言語: アラビア語 (`ar`)、英語 (`en`)、スペイン語 (`es`)、および日本語 (`ja`)。言語を指定するには、プレーン・テキストおよび HTML の入力用の HTTP `Content-Language` ヘッダーを使用するか、JSON 入力用の `ContentItem` オブジェクトの `language` プロパティーを使用します。
-   応答についても、同じ 4 つの言語がサポートされます。応答の言語を指定するには、`Accept-Language` ヘッダーを使用します。

入力と応答には、任意の言語の組み合わせを使用できます。いずれの場合も、言語を示さないと、サービスはデフォルトで英語を使用します。詳しくは、『[要求および応答の言語の指定](/docs/services/personality-insights/input.html#languages)』を参照してください。
さらに、ブログ投稿『[Arabic and Japanese support is now available for {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.personalityinsightsshort}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/blogs/watson/2016/04/arabic-japanese-support-now-available-ibm-watson-personality-insights/){: new_window}』を参照して追加情報を確認してください。

> **注:** アラビア語のコンテンツは、他の言語より、分析にかなり多くのコンピューティング・サイクルを必要とするため、処理に非常に長い時間がかかります。サービスは、すべての言語の入力テキスト量について、同じ 20 MB の制限をサポートしていますが、アラビア語のコンテンツの実際的制限は、タイムアウトを避けるために、それより少なくなる可能性があります。日本語のコンテンツも処理に時間がかかりますが、アラビア語に比べれば、その遅延はそれほど重大な意味を持ちません。

### 2015 年 7 月 9 日
{: #July2015}

-   *言語サポート。* サービスでは、英語とスペイン語のコンテンツの分析が可能になりました。入力テキストの言語は、`/v2/profile` メソッドの `Content-Language` ヘッダーを使用して示します。言語の指定については、『[要求および応答の言語の指定](/docs/services/personality-insights/input.html#languages)』を参照してください。
-   *ロー・スコア。* 入力テキストとサービスのモデルから計算されるロー・スコアとロー・サンプリング・エラーの要求がサービスで可能になりました。これらの値は、正規化もサンプル母集団との比較も行われません。ロー・スコアは、特定のシナリオにカスタム正規化を適用したいお客様や、サンプル母集団との比較を必要としないお客様にとって有用です。ロー・スコアを要求するには、`/v2/profile` メソッドの `include_raw` 照会パラメーターを `true` に設定します。詳しくは、『[数値結果の解釈](/docs/services/personality-insights/numeric.html)』を参照してください。
-   *モデルの機能拡張。* 最新の研究に基づいて、{{site.data.keyword.IBM_notm}} は、パーソナリティー特性の推定のいくつかの方法をさらに改善しました。これらの変更は、サービスのユーザーからは認識されることはなく、サービスから入手した、以前の結果が無効化されることもありません。これらの研究、および推定に対するサービスの方法について詳しくは、『[パーソナリティー特性の推測方法](/docs/services/personality-insights/science.html#researchInfer)』を参照してください。

### 2015 年 2 月 23 日
{: #February2015}

2015 年 2 月 23 日現在、{{site.data.keyword.personalityinsightsshort}} サービスは、ベータ版として使用可能だった、以前の User Modeling サービスの一般出荷可能 (GA) バージョンです。GA 版では、ユーザーは新規サービスのインスタンスにマイグレーションする必要があります。サービスのベータ版と GA 版には以下のような違いがあります。

-   {{site.data.keyword.personalityinsightsshort}} サービスは、User Modeling サービスと後方互換です。このセクションで述べる違いは、現在のアプリケーションに影響を与えずに、柔軟性を向上させ、結果を改善します。
-   {{site.data.keyword.Bluemix_short}} でのサービスの作成に使用されるパラメーターが変更されました。現在は、`user_modeling` の代わりに `personality_insights` というサービス名を使用し、`user_modeling_free_plan` の代わりに `"IBM Watson Personality Insights Monthly Plan"` というサービス・プランを使用するようになりました。
-   `/v2/profile` メソッドは、2 つの新規入力フォーマットを受け入れます。`Content-Type` ヘッダーは、JSON (`application/json`) に加え、プレーン・テキスト (`text/plain`) (デフォルト) と HTML (`text/html`) の入力フォーマットを受け入れるようになりました。
-   `/v2/profile` メソッドは、新規出力フォーマットを返すようになりました。`Accept` ヘッダーは、JSON (`application/json`) (デフォルト) に加え、CSV (`text/csv`) の出力フォーマットを受け入れるようになりました。
-   `/v2/profile` メソッドに、パーセンテージ値を報告する各特性の新しい出力要素 `sampling_error` が含まれるようになりました。サンプリング・エラーは、入力テキストに基づく筆者の百分位数についてのサービスの信頼度レベルを示す二重値として返されます。
-   ニーズ・モデルは、特性の値の分布をより適切に正規化するために、改善されたトークン化および処理を採用しています。User Modeling API によって生成された結果は、再計算することをお勧めします。
-   `visualize` メソッドは現在非推奨となり、将来のリリースからは完全に削除されます。サンプル・アプリケーションに付属する `personality.js` JavaScript ファイルを使用すると、クライアントから同様の結果を出すことができます。`textsummary.js` JavaScript ファイルは、サービスの結果について追加のフォーマット設定を提供します。
