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

# プロファイルの要求
{: #input}

コンテンツを分析するため、HTTP `POST` 要求メソッドを使用して {{site.data.keyword.personalityinsightsshort}} サービスの `/v3/profile` メソッドを呼び出します。最大 20 MB の分析対象コンテンツを要求本体を介してサービスに渡すことができますが、このサービスが正確なパーソナリティー・プロファイルを生成するために必要とする入力はもっと少量です。詳しくは、『[十分な入力の提供](#sufficient)』を参照してください。
{: shortdesc}

`/v3/profile` メソッドに含まれているパラメーターを使用して、サービスに渡すコンテンツおよびサービスから返されるコンテンツのタイプと、各タイプのコンテンツの言語を指定できます。本サービスは、入力テキストの筆者のパーソナリティー特性についての洞察を提供するプロファイルを常に返します。ロー・スコアおよび消費嗜好性を返すようにサービスに要求することもできます。

以降のセクションでは、`/v3/profile` メソッドのパラメーターについて説明します。要求の結果について詳しくは、『[JSON プロファイルの解釈](/docs/services/personality-insights/output.html)』および 『[CSV プロファイルの解釈](/docs/services/personality-insights/output-csv.html)』を参照してください。 `/v3/profile` メソッドについて詳しくは、[API リファレンス![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window} を参照してください。

## 要求および応答のフォーマットの指定
{: #formats}

ヘッダー・パラメーター `Content-Type` および `Accept` を使用して、メソッドに渡すコンテンツのフォーマットと、本サービスからの応答のフォーマットを指示することができます。サポートされているフォーマットを任意に組み合わせて、要求および応答に使用できます。

<table>
  <caption>表 1. 要求および応答のフォーマットの指定</caption>
  <tr>
    <th style="width:10%; text-align:left; vertical-align:bottom">
      フォーマット
    </th>
    <th style="width:26%; text-align:center; vertical-align:bottom">
      引数
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      <code>Content-Type</code><br/>でサポートされる
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      <code>Accept</code><br/>でサポートされる
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      プレーン・テキスト
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/plain</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      はい (デフォルト)<br/><br/>
      本サービスはプレーン・テキストを変更せずに処理します。
    </td>
    <td style="text-align:center; vertical-align:top">
      いいえ
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      HTML
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/html</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      はい<br/><br/>
      本サービスはタグを除去してからコンテンツを処理します。
    </td>
    <td style="text-align:center; vertical-align:top">
      いいえ
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      JSON
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>application/json</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      はい<br/><br/>
      コンテンツは、<code>ContentItem</code> オブジェクトからなる配列である <code>Content</code> オブジェクトによって定義されるモデルに準拠している必要があります。
    </td>
    <td style="text-align:center; vertical-align:top">
      はい (デフォルト)<br/><br/>
      本サービスは、結果を 1 つの <code>Profile</code> オブジェクトとして返します。
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      CSV
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/csv</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      いいえ
    </td>
    <td style="text-align:center; vertical-align:top">
      はい<br/><br/>
      デフォルトでは、本サービスは数値結果を含んでいる単一行を返します。
      出力の各列にヘッダーを付けるよう要求するには、オプションの <code>csv_headers</code> 照会パラメーターを <code>true</code> に設定します。
    </td>
  </tr>
</table>

### 文字セットの指定
{: #charset}

デフォルトでは、本サービスは入力コンテンツに対して以下の文字セットを使用します。

-   *プレーン・テキストおよび HTML のコンテンツの場合、*本サービスは HTTP バージョン 1.1 仕様通りに、国際標準化機構 (ISO)-8859-1 文字セット (実効的には ASCII 文字セット) を使用します。
-   *JSON コンテンツの場合、*本サービスは International Engineering Task Force (IETF) [Request for Comment (RFC) 7159 ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://tools.ietf.org/html/rfc7159#section-8.1){: new_window} のセクション 8.1 通りに、実質的には常に Unicode Transformation Format (UTF)-8 文字セットを使用します。

プレーン・テキストまたは HTML のコンテンツを送信するときに、入力テキストの文字エンコード方式を指示するには、`Content-Type` ヘッダーと共に `charset` パラメーターを含めます。次の例は、プレーン・テキスト入力に対して UTF-8 文字エンコード方式を指定しています。

```
Content-Type: text/plain;charset=utf-8
```
{: codeblock}

`charset` パラメーターを使用することによって、非 ASCII 文字または印刷不能文字に関連する潜在的問題を回避できます。文字セットを指定せずに UTF-8 データを渡した場合、特殊文字が原因で、正しくない結果や、HTTP 4*nn* エラーまたは 5*nn* エラーが発生する可能性があります。

### cURL の使用
{: #charsetCurl}

cURL を使用する際のエラーを回避するには、常に `curl` コマンドの `--data-binary` オプションを介してコンテンツを渡して、コンテンツの UTF-8 エンコード方式を保持するようにします。`--data` オプションを使用してコンテンツを ASCII として渡すと、コマンドは入力を処理することができるため、UTF-8 でエンコードされたデータの場合に問題が起こることがあります。

例えば、次の `curl` コマンドは `--data-binary` オプションを正しく使用して、指定された *filename* のコンテンツを追加処理なしで送ります。また、このコマンドは、`Content-Type` ヘッダーと共に `charset` パラメーターを使用しており、明示的にデフォルト JSON 応答フォーマットを要求しています。

```bash
curl -X POST --user {username}:{password}
--header "Content-Type: text/plain;charset=utf-8"
--header "Accept: application/json"
--data-binary @{filename}
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{: pre}

さまざまな要求フォーマットおよび応答フォーマットを指定して本サービスを呼び出す追加例については、『[入門チュートリアル](/docs/services/personality-insights/getting-started.html)』を参照してください。

## JSON 入力の指定
{: #json}

JSON 入力を渡すには、`Content` オブジェクトを使用します。このオブジェクトは、`ContentItem` オブジェクトからなる 1 つの配列を含み、`ContentItem` オブジェクトのそれぞれがコンテンツの 1 つのエレメントを含みます。オブジェクトの唯一の必須フィールドは、分析対象のテキストを提供する `content` です。その他のオプション・フィールドでは、以下を指定できます。

-   `id` (string) は、コンテンツ・アイテムの固有 ID です。
-   `created` (integer) は、コンテンツ・アイテムがいつ作成されたのかを示す UNIX タイム・スタンプです。
-   `updated` (integer) は、コンテンツ・アイテムが最後に更新されたのはいつなのかを示す UNIX タイム・スタンプです。
-   `contenttype` (string) は、コンテンツ・アイテムのタイプが `text/plain` と `text/html` のどちらなのかを示します。
-   `language` (string) は、コンテンツ・アイテムの言語を示します。`ar` (アラビア語)、`en` (英語)、`es` (スペイン語)、`ja` (日本語)、または `ko` (韓国語) のいずれかです。『[要求および応答の言語の指定](#languages)』を参照してください。
-   `parentid` (string) は、コンテンツ・アイテムの親アイテムの `id` です。
-   `reply` (boolean) は、コンテンツ・アイテムが別のアイテムへの返信かどうかを示します。
-   `forward` (boolean) は、コンテンツ・アイテムが別のアイテムの転送またはコピーかどうかを示します。

JSON 入力は、複数の会話や投稿からなる Twitter またはその他のソーシャル・ネットワークからのコンテンツに適しています。筆者のすべてのテキストを連結して単一ストリングにする代わりに、JSON を使用すればデータをそのままの形で送信できます。このほうが、本サービスがテキストの各部分の関連を把握するのにずっと役立ちます。

### JSON 入力の例
{: jsonExample}

[入門チュートリアル](/docs/services/personality-insights/getting-started.html)にある例では、サンプル JSON ファイル <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="外部リンク・アイコン" title="外部リンク・アイコン" class="style-scope doc-content"></a> が使用されています。このファイルには一連の Twitter メッセージが含まれています。このファイルの冒頭のいくつかのツイートは次の例のとおりです。

```javascript
{
  "contentItems": [
    {
      "content": "Wow, I liked @TheRock before, now I really SEE how special he is. The daughter story was IT for me. So great! #MasterClass",
      "contenttype": "text/plain",
      "created": 1447639154000,
      "id": "666073008692314113",
      "language": "en"
    },
    {
      "content": ".@TheRock how did you Know to listen to your gut and Not go back to football? #Masterclass",
      "contenttype": "text/plain",
      "created": 1447638226000,
      "id": "666069114889179136",
      "language": "en"
    },
    . . .
  ]
}
```
{: codeblock}

## 要求および応答の言語の指定
{: #languages}

ヘッダー・パラメーター `Content-Language` および `Accept-Language` を使用して、入力コンテンツの言語と、本サービスからの応答の言語を指示できます。サポートされている言語を任意に組み合わせて、要求および応答に使用できます。言語が指定されていない場合、本サービスは英語でトレーニングされたモデルを分析に使用し、結果には英語を使用します。以下の表に、サポートされる入力および出力の言語と、言語に関連するパラメーターで使用する引数を示します。

<table style="width:90%">
  <caption>表 2. 要求および応答の言語の指定</caption>
  <tr>
    <th style="width:28%; text-align:left; vertical-align:bottom">
      言語
    </th>
    <th style="width:12%; text-align:center; vertical-align:bottom">
      引数
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      <code>Content-Language</code><br/>でサポートされる
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      <code>Accept-Language</code><br/>でサポートされる
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      アラビア語
    </td>
    <td style="text-align:center">
      <code>ar</code>
    </td>
    <td style="text-align:center">
      はい
    </td>
    <td style="text-align:center">
      はい
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      英語
    </td>
    <td style="text-align:center">
      <code>en</code>
    </td>
    <td style="text-align:center">
      はい
    </td>
    <td style="text-align:center">
      はい
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      日本語
    </td>
    <td style="text-align:center">
      <code>ja</code>
    </td>
    <td style="text-align:center">
      はい
    </td>
    <td style="text-align:center">
      はい
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      韓国語
    </td>
    <td style="text-align:center">
      <code>ko</code>
    </td>
    <td style="text-align:center">
      はい
    </td>
    <td style="text-align:center">
      はい
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      スペイン語
    </td>
    <td style="text-align:center">
      <code>es</code>
    </td>
    <td style="text-align:center">
      はい
    </td>
    <td style="text-align:center">
      はい
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      ブラジル・ポルトガル語
    </td>
    <td style="text-align:center">
      <code>pt-br</code>
    </td>
    <td style="text-align:center">
      いいえ
    </td>
    <td style="text-align:center">
      はい
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      フランス語
    </td>
    <td style="text-align:center">
      <code>fr</code>
    </td>
    <td style="text-align:center">
      いいえ
    </td>
    <td style="text-align:center">
      はい
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      ドイツ語
    </td>
    <td style="text-align:center">
      <code>de</code>
    </td>
    <td style="text-align:center">
      いいえ
    </td>
    <td style="text-align:center">
      はい
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      イタリア語
    </td>
    <td style="text-align:center">
      <code>it</code>
    </td>
    <td style="text-align:center">
      いいえ
    </td>
    <td style="text-align:center">
      はい
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      中国語 (簡体字)
    </td>
    <td style="text-align:center">
      <code>zh-cn</code>
    </td>
    <td style="text-align:center">
      いいえ
    </td>
    <td style="text-align:center">
      はい
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      中国語 (繁体字)
    </td>
    <td style="text-align:center">
      <code>zh-tw</code>
    </td>
    <td style="text-align:center">
      いいえ
    </td>
    <td style="text-align:center">
      はい
    </td>
  </tr>
</table>

すべてのテキストを同じ言語で送信し、同じ要求に複数の言語を混在させないでください。本サービスは、2 文字の言語引数の場合は地方変異形をその親言語として処理します。例えば、`en-US` を `en` と解釈します。

### JSON コンテンツの言語の指定
{: #languageJSON}

プレーン・テキストおよび HTML の入力の場合、言語を指定する唯一の方法は `Content-Language` ヘッダーです。JSON 入力の場合、`ContentItem` オブジェクトの `language` パラメーターを使用して、個々のコンテンツ・アイテムの言語を指定することもできます。ただし、`Content-Language` ヘッダーで指定された言語が、コンテンツ・アイテムに対して指定された言語をオーバーライドし、異なる言語を指定しているコンテンツ・アイテムは無視されます。

言語がコンテンツ・アイテムの指定にのみ基づくようにするには、`Content-Type` ヘッダーを省略します。本サービスでは、可能な限り最良の結果を得られるよう、コンテンツ・アイテムの中で最もよく使用されている言語が使用されます。言語ごとのコンテンツ・アイテム数を数えて、最も頻繁に使用されている言語が選択されます。最大頻度が複数の言語で同じである場合、最初にその値に達した言語が使用されます。この場合も、異なる言語を指定するコンテンツ・アイテムは無視されます。

### 言語の考慮事項
{: #languageNotes}

入力テキストを送信するときには、以下を考慮してください。

-   *英語の場合、*結果は米国の文化規範に基づきます。異なる文化圏からの英語テキストを分析する場合、それに応じて結果の調整が必要になることがあります。
-   *アラビア語の場合、*本サービスはパフォーマンス上の理由のために入力テキスト量を削減することがあります。一定のしきい値を境に、さらに多くの単語を使用してもアラビア語での結果の正確度は向上しなくなります。本サービスは、アラビア語入力を削減した場合、プロファイルのために使用した入力テキストの量を削減したことを知らせる警告メッセージを返します。
-   *アラビア語および韓国語の場合、*本サービスは、一部の特性については意味のある結果を返すことができません。詳しくは、『[アラビア語および韓国語の入力の制限事項](/docs/services/personality-insights/numeric.html#limitations)』を参照してください。

翻訳されたテキストの使用について詳しくは、『[翻訳テキストからのパーソナリティーの推論](/docs/services/personality-insights/guidance.html#translation)』を参照してください。

## 十分な入力の提供
{: #sufficient}

有意義なパーソナリティー・プロファイルを作成できるのは、質量ともに適切なデータが十分に提供された場合のみです。言語使用は文書ごとに異なり、時とともに変化するという性質があるため、少量のテキストのサンプルが個人の言語パターン全体を表すことはあまりありません。さらに、さまざまな特性および多様なメディアは、少しずつ異なる率で収束します。

ある点までは、単語数が多くなると、予測される結果と筆者の実スコアとの間のずれが小さくなって本サービスの精度が向上し、より良好な結果が生成される傾向があります。本サービスには 20 MB までの入力コンテンツを送信できますが、正確度は約 3000 単語の入力で横ばいになり、それ以上のコンテンツがあってもプロファイルの正確度は向上しません。したがって、本サービスは、大きな要求の場合は最初の 250 KB  (HTML または JSON のマークアップはカウントされません) のコンテンツのみを抜き出して使用します。

単語数は言語およびテキストの性質によって変化するため、この数値は正確な単語数に対応するわけではありません。例えば、英語の場合、単語の平均の長さは 4 文字と 5 文字の間であるため、この数値は約 50,000 の単語を提供しますが、これは本サービスが正確なプロファイルを生成するために必要とする単語数の 15 倍以上です。本サービスは、大きな入力を切り捨てることによって、精度を犠牲にすることなく応答時間を改善します。応答 JSON 内の `word_count` フィールドは本サービスが要求のために実際に使用する単語の数を示し、送信された単語の数よりも少ないことがあります。

### ガイドラインおよび推奨事項
{: #sufficientGuidelines}

以下の表に、異なる量の入力テキストに対する次の 2 つの値を示します。

-   入力として提供された単語の数に基づく、すべての特性での*平均 MAE (平均絶対誤差)*。MAE が小さいほど、本サービスの結果は筆者が実際の性格診断テストで受け取るであろうスコアに近くなります。
-   すべての特性での推論されたスコアと実際のスコアとの間の*平均相関*。0.2 より大きい相関は受け入れ可能と見なされ、0.4 より大きい相関はめったにありませんが、相関が 1 に近いほど予測は良くなります。

この情報は英語データに基づいていますが、一般ガイドラインはすべての言語に当てはまります。言語特有の統計情報も含めて、平均 MAE および平均相関について詳しくは、『[サービスの精度](/docs/services/personality-insights/science.html#researchPrecise)』を参照してください。

<table style="width:80%">
  <caption>表 3. 平均 MAE および平均相関</caption>
  <tr>
    <th style="text-align:center; vertical-align:bottom; width:24%">単語数</th>
    <th style="text-align:center; width:38%">すべての特性での<br/>平均 MAE</th>
    <th style="text-align:center; width:38%">すべての特性での<br/>平均相関</th>
  </tr>
  <tr>
    <td style="text-align:center">3000</td>
    <td style="text-align:center">12.1%</td>
    <td style="text-align:center">0.257</td>
  </tr>
  <tr>
    <td style="text-align:center">1200</td>
    <td style="text-align:center">12.2%</td>
    <td style="text-align:center">0.237</td>
  </tr>
  <tr>
    <td style="text-align:center">600</td>
    <td style="text-align:center">12.3%</td>
    <td style="text-align:center">0.212</td>
  </tr>
  <tr>
    <td style="text-align:center">300</td>
    <td style="text-align:center">12.5%</td>
    <td style="text-align:center">0.175</td>
  </tr>
  <tr>
    <td style="text-align:center">100</td>
    <td style="text-align:center">12.7%</td>
    <td style="text-align:center">0.095</td>
  </tr>
</table>

以下のガイドラインが示すように、{{site.data.keyword.IBM_notm}} は少なくとも 1200 単語を提供することを推奨していますが、最低限 600 単語を提供すれば、受け入れ可能な結果が生成されます。

-   3000 単語の場合、本サービスの最大精度の達成に十分です。
-   1200 単語以上の場合、MAE は本サービスが返すことのできる最高の MAE の 2 パーセント以内になります。
-   600 単語から 1200 単語の場合、MAE は、本サービスが返すことのできる最高の MAE の 3 パーセント以内になります。
-   600 単語未満の場合、警告が生成されますが、本サービスは入力の分析を行います。
-   100 単語未満の場合、エラーが生成されます。

これらのガイドラインは、結果の信頼性をアプリケーションに合わせて調整するのに役立ちます。例えば、映画を推薦するちょっとしたアプリケーションにはそれほどの精度は必要なく、もっと重大な勧告を行うアプリケーションにはもっと正確な結果が必要であるといったことが考えられます。本サービスがどのようにパーソナリティー特性を推論するのかについて詳しくは、『[パーソナリティー特性の推測方法](/docs/services/personality-insights/science.html#researchInfer)』を参照してください。

## ロー・スコアの要求
{: #rawScores}

本サービスでは、応答の一部として、各パーソナリティー特性 (ビッグ・ファイブのディメンションおよびファセット、ニーズ、および価値) に対して、常に正規化したスコアが返されます。`raw_scores` 照会パラメーターを `true` に設定すると、各特性の `raw_score` (ロー・スコア) も報告されます。ロー・スコアは、結果がサンプル母集団と比較されない、筆者のテキストおよび特性のモデルのみに基づいた、特性のスコアを表します。ロー・スコアの使用について詳しくは、『[パーソナリティー特性のロー・スコア](/docs/services/personality-insights/numeric.html#rawScores)』を参照してください。

## 消費嗜好性の要求
{: #preferences}

本サービスでは、常にパーソナリティー・モデルの結果が返されます。`consumption_preferences` 照会パラメーターを `true` に設定すると、入力テキストから推論したパーソナリティー特性に基づいた、さまざまな消費嗜好性の `score` (スコア) も返されます。これらの結果は、さまざまな商品、サービス、およびアクティビティーに対する筆者の好みの傾向を表します。これらの結果をビジネスで使用して、筆者の傾向をより正確に把握したり、筆者向けに対話や提案をパーソナライズしたりできます。

さまざまな消費嗜好性について詳しくは、『[消費嗜好性](/docs/services/personality-insights/preferences.html)』を参照してください。消費嗜好性の数値結果の解釈について詳しくは、『[消費嗜好性のスコア](/docs/services/personality-insights/numeric.html#scores)』を参照してください。

## インターフェース・バージョンの指定
{: #version}

`/v3/profile` メソッドの呼び出しには、本サービスの API および応答フォーマットのどのバージョンを使用するのかを指定する `version` 照会パラメーターが必ず含まれていなければなりません。バージョンは `YYYY-MM-DD` という形式の日付として指定します。例えば、2017 年 10 月 13 日の場合は `2017-10-13` と指定します。このパラメーターによって、本サービスは、既存クライアントを中断することなく、API および応答フォーマットを新バージョンに更新できます。

指定する日付は、サービスのバージョンと完全に一致している必要はありません。本サービスは指定された日付までのバージョンを使用します。バージョン 3 の最初のリリースより前の日付を指定すると、本サービスはバージョン 3 の API を使用します。将来の日付、または最新バージョンより後の日付を指定すると、サービスは最新バージョンを使用します。
