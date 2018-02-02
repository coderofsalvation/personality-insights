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

# 要求設定檔
{: #input}

若要分析內容，您可以使用 HTTP `POST` 要求方法來呼叫 {{site.data.keyword.personalityinsightsshort}} 服務的 `/v3/profile` 方法。您可以傳遞最多 20 MB 的內容至服務，以透過要求的主體來進行分析，但是服務不需要那麼多輸入，就能產生精確的性格設定檔；如需相關資訊，請參閱[提供足夠的輸入](#sufficient)。
{: shortdesc}

`/v3/profile` 方法包括可讓您指定要傳遞給服務及由服務傳回之內容類型的參數，以及每一種內容類型的語言。服務一律會傳回設定檔，可讓您深入瞭解輸入文字作者的性格特質。您也可以要求服務傳回原始評分和消費喜好。

下列各節說明 `/v3/profile` 方法的參數。如需要求結果的相關資訊，請參閱[瞭解 JSON 設定檔](/docs/services/personality-insights/output.html)和[瞭解 CSV 設定檔](/docs/services/personality-insights/output-csv.html)。如需 `/v3/profile` 方法的詳細資訊，請參閱 [API 參考資料![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}。

## 指定要求和回應格式
{: #formats}

您可以使用 `Content-Type` 和 `Accept` 標頭參數來指示要傳遞給方法的內容格式，以及服務回應的格式。您可以將任何組合的支援格式用於要求和回應。

<table>
  <caption>表 1. 指定要求和回應格式</caption>
  <tr>
    <th style="width:10%; text-align:left; vertical-align:bottom">
      格式
    </th>
    <th style="width:26%; text-align:center; vertical-align:bottom">
      引數
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      支援者<br/>
      <code>Content-Type</code>
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      支援者<br/>
      <code>Accept</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      純文字
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/plain</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      是（預設值）<br/><br/>
      服務會處理純文字而不進行修改。
    </td>
    <td style="text-align:center; vertical-align:top">
      否
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
      是<br/><br/>
      服務在處理內容之前，會先將內容中的標籤刪除。
    </td>
    <td style="text-align:center; vertical-align:top">
      否
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
      是<br/><br/>
      內容必須符合 <code>Content</code> 物件所定義的模型，也就是 <code>ContentItem</code> 物件的陣列。</td>
    <td style="text-align:center; vertical-align:top">
      是（預設值）<br/><br/>
      服務會將其結果傳回為 <code>Profile</code> 物件。
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
      否
    </td>
    <td style="text-align:center; vertical-align:top">
      是<br/><br/>
      依預設，服務會傳回單一列的數值結果。
      將選用的 <code>csv_headers</code> 查詢參數設為 <code>true</code>，以要求每一個輸出直欄的標頭。
    </td>
  </tr>
</table>

### 指定字集
{: #charset}

依預設，服務會針對輸入內容使用下列字集：

-   *若為純文字和 HTML 內容，*根據 HTTP 1.1 版規格，服務會使用「國際標準組織 (ISO)-8859-1」字集（實際上是 ASCII 字集）。
-   *若為 JSON 內容，*根據「網際網路工程任務組 (International Engineering Task Force, IETF)」第 8.1 條款的[徵求意見稿 (Request for Comment, RFC) 7159 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://tools.ietf.org/html/rfc7159#section-8.1){: new_window}，服務實際上一律會使用「Unicode 傳輸格式 (UTF)-8」字集。

提交純文字或 HTML 內容時，請將 `charset` 參數併入 `Content-Type` 標頭，以指示輸入文字的字元編碼。下列範例為純文字輸入指定 UTF-8 字元編碼：

```
Content-Type: text/plain;charset=utf-8
```
{: codeblock}

使用 `charset` 參數可以避免與非 ASCII 或不可列印字元相關聯的潛在問題。如果您傳遞 UTF-8 資料，但未指定字集，特殊字元可能會導致不正確的結果，或是 HTTP 4*nn* 或 5*nn* 錯誤。

### 使用 cURL
{: #charsetCurl}

為了防止在使用 cURL 時發生錯誤，請一律透過 `curl` 指令的 `--data-binary` 選項來傳遞內容，以保留內容的任何 UTF-8 編碼。如果您使用 `--data` 選項，以 ASCII 來傳遞內容，則指令會處理該輸入，進而導致 UTF-8 編碼的資料發生問題。

例如，下列 `curl` 指令會正確使用 `--data-binary` 選項來張貼指定 *filename* 的內容，而不進行其他處理。此指令也會將 `charset` 參數用於 `Content-Type` 標頭，且會明確要求預設的 JSON 回應格式。

```bash
curl -X POST --user {username}:{password}
--header "Content-Type: text/plain;charset=utf-8"
--header "Accept: application/json"
--data-binary @{filename}
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{: pre}

如需以不同要求和回應格式來呼叫服務的其他範例，請參閱[入門指導教學](/docs/services/personality-insights/getting-started.html)。

## 指定 JSON 輸入
{: #json}

若要傳遞 JSON 輸入，您可以使用 `Content` 物件。此物件包括 `ContentItem` 物件的陣列，而其中的每一個物件各包含內容的一個元素。此物件的唯一必要欄位是 `content`，用來提供要分析的文字。其他選用性欄位可讓您指定下列項目：

-   `id`（字串）是內容項目的唯一 ID。
-   `created`（整數）是 UNIX 時間戳記，指出內容項目建立的時間。
-   `updated`（整數）是 UNIX 時間戳記，指出內容項目前次更新的時間。
-   `contenttype`（字串）指出內容項目的類型，可為 `text/plain` 或 `text/html`。
-   `language`（字串）指出內容項目的語言：`ar`（阿拉伯文）、`en`（英文）、`es`（西班牙文）、`ja`（日文）或 `ko`（韓文）。請參閱[指定要求和回應語言](#languages)。
-   `parentid`（字串）是內容項目的母項項目的 `id`。
-   `reply`（布林）指出內容項目是否為對另一個項目的回覆。
-   `forward`（布林）指出內容項目是否為另一個項目的轉遞或副本。

JSON 輸入非常適合用於 Twitter 或其他由多項交談作業或貼文組成之社交網路的內容。您可以使用 JSON 來提交存在的資料，而不需要將作者的所有文字連結至單一字串。這還有更進一步的優點，就是可讓服務知道文字的哪些片段相關聯。

### JSON 輸入範例
{: jsonExample}

[入門指導教學](/docs/services/personality-insights/getting-started.html)中使用 JSON 檔案範例 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="外部鏈結圖示" title="外部鏈結圖示" class="style-scope doc-content"></a> 的範例。此檔案包含一連串的 Twitter 訊息。下列範例顯示檔案中的前幾個推文。

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

## 指定要求和回應語言
{: #languages}

您可以使用 `Content-Language` 和 `Accept-Language` 標頭參數來指示輸入內容的語言，以及服務回應的語言。您可以將任何組合的支援語言用於要求和回應。如果您未指示語言，則服務會將其英文訓練模型用於其分析，並對其結果採用英文。下表列出支援的輸入及輸出語言，並識別您用於語言相關參數的引數。

<table style="width:90%">
  <caption>表 2. 指定要求和回應語言</caption>
  <tr>
    <th style="width:28%; text-align:left; vertical-align:bottom">
      語言
    </th>
    <th style="width:12%; text-align:center; vertical-align:bottom">
      引數
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      支援者<br/>
      <code>Content-Language</code>
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      支援者<br/>
      <code>Accept-Language</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      阿拉伯文
    </td>
    <td style="text-align:center">
      <code>ar</code>
    </td>
    <td style="text-align:center">
      是
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      英文
    </td>
    <td style="text-align:center">
      <code>en</code>
    </td>
    <td style="text-align:center">
      是
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      日文
    </td>
    <td style="text-align:center">
      <code>ja</code>
    </td>
    <td style="text-align:center">
      是
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      韓文
    </td>
    <td style="text-align:center">
      <code>ko</code>
    </td>
    <td style="text-align:center">
      是
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      西班牙文
    </td>
    <td style="text-align:center">
      <code>es</code>
    </td>
    <td style="text-align:center">
      是
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      巴西葡萄牙文
    </td>
    <td style="text-align:center">
      <code>pt-br</code>
    </td>
    <td style="text-align:center">
      否
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      法文
    </td>
    <td style="text-align:center">
      <code>fr</code>
    </td>
    <td style="text-align:center">
      否
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      德文
    </td>
    <td style="text-align:center">
      <code>de</code>
    </td>
    <td style="text-align:center">
      否
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      義大利文
    </td>
    <td style="text-align:center">
      <code>it</code>
    </td>
    <td style="text-align:center">
      否
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      簡體中文
    </td>
    <td style="text-align:center">
      <code>zh-cn</code>
    </td>
    <td style="text-align:center">
      否
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      繁體中文
    </td>
    <td style="text-align:center">
      <code>zh-tw</code>
    </td>
    <td style="text-align:center">
      否
    </td>
    <td style="text-align:center">
      是
    </td>
  </tr>
</table>

以相同的語言提交所有文字；請不要在同一個要求中混合多種語言。針對兩個字元的語言引數，服務會將區域變式視為其母項語言；例如，它會將 `en-US` 解譯為 `en`。

### 指定 JSON 內容的語言
{: #languageJSON}

若為純文字和 HTML 輸入，`Content-Language` 標頭是指定語言的唯一方法。若為 JSON 輸入，您也可以使用 `ContentItem` 物件的 `language` 參數來指定每一個個別內容項目的語言。不過，以 `Content-Language` 標頭指定的語言會置換針對內容項目指定的語言；服務會忽略指定不同語言的內容項目。

省略 `Content-Type` 標頭，讓語言僅以內容項目的規格為基礎。服務會使用內容項目中最普遍的語言，如此可產生最佳的可能結果。它會計算每一種語言的內容項目數，並選取頻率最高的語言。如果多種語言都有相同的最高頻率，則服務會使用先達到該值的語言。同樣地，服務會忽略指定不同語言的內容項目。

### 語言考量
{: #languageNotes}

提交輸入文字時，請考量下列事項：

-   *若為英文，*結果是以美國文化規範為基礎。如果您從不同的文化來分析英文文字，可能需要相應地調整結果。
-   *若為阿拉伯文，*服務可以基於效能的理由，刪減輸入文字的數量。在特定的臨界值，阿拉伯文結果的精確度並不會隨著更多字詞而提升。如果服務刪減阿拉伯文輸入，則會傳回警告訊息，通知您其減少了用於設定檔的輸入文字數量。
-   *若為阿拉伯文和韓文，*服務無法為部分特質傳回有意義的結果。如需相關資訊，請參閱[阿拉伯文和韓文輸入的限制](/docs/services/personality-insights/numeric.html#limitations)。

如需使用翻譯文字的一般資訊，請參閱[從翻譯的文字推斷性格](/docs/services/personality-insights/guidance.html#translation)。

## 提供足夠的輸入
{: #sufficient}

只有提供適當數量和品質的充足資料，才能建立有意義的性格設定檔。語言的使用會隨著不同的文件和時機而自然改變，因此，少量的文字樣本可能無法代表個人的整體語言型樣。此外，不同特質和不同媒體的彙聚速度也會有所不同。

在某種程度上，愈多的字詞可能會產生愈好的結果，減少預測結果與作者實際評分之間的偏差，可以提升服務的精準度。您可以將最多 20 MB 的輸入內容傳送至服務，但是精確度會在大約 3000 字的輸入時趨於平穩；額外的內容並無法進一步提升設定檔的精確度。因此，服務只會從大型的要求中擷取並使用前 250 KB 的內容（任何 HTML 或 JSON 標記皆不計算在內）。

此數字並未對映確切的字數，這會依文字的語言和本質而異。例如，英文的平均字詞長度介於四到五個字元之間，所以此數字提供大約 50,000 個字詞，比服務產生精確設定檔所需的字數至少高出 15 倍。在截斷冗長的輸入之後，服務會改進回應時間，而不會犧牲精準度。回應 JSON 的 `word_count` 欄位會指出服務實際用於要求的字數，這會少於所提交的字數。

### 準則和建議
{: #sufficientGuidelines}

下表針對不同的輸入文字數量，報告兩個值：

-   以提供作為輸入的字數為基礎，所有特質的*平均「平均絕對誤差 (MAE)」*。MAE 愈小，服務的結果愈接近作者進行實際性格測試所得到的評分。
-   所有特質的推斷與實際評分之間的*平均相關性*。相關性愈接近 1，預測愈準確，然而高於 0.2 的相關性視為可接受，高於 0.4 的相關性則很少見。

此資訊是以英文語言資料為基礎，但一般準則適用於所有語言。如需平均 MAE 和相關性（包括特定語言的統計資料）的相關資訊，請參閱[服務的精準度](/docs/services/personality-insights/science.html#researchPrecise)。

<table style="width:80%">
  <caption>表 3. 平均 MAE 和相關性</caption>
  <tr>
    <th style="text-align:center; vertical-align:bottom; width:24%">字數</th>
    <th style="text-align:center; width:38%">平均 MAE<br/>（所有特質）</th>
    <th style="text-align:center; width:38%">平均相關性<br/>（所有特質）</th>
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

如下列準則所示，{{site.data.keyword.IBM_notm}} 建議您提供至少 1200 個字，但提供至少 600 個字即產生可接受的結果：

-   3000 個字足以達到服務的最大精準度。
-   至少 1200 個字所產生的 MAE 會在服務可傳回之最佳 MAE 的百分之二以內。
-   600 到 1200 個字所產生的 MAE 會在服務可傳回之最佳 MAE 的百分之三以內。
-   少於 600 個字會產生警告，但服務仍會分析該輸入。
-   少於 100 個字則會產生錯誤。

這些準則可協助您將結果的可靠性納入應用程式中。例如，對於建議電影的休閒應用程式，精準度低一點可能還可以接受；但對於提供較重要建議的應用程式，您可能就會需要比較精準的結果。如需服務如何推斷性格特質的相關資訊，請參閱[推斷性格特質的方式](/docs/services/personality-insights/science.html#researchInfer)。

## 要求原始評分
{: #rawScores}

服務一律會針對每一項性格特質（「五大性格特質」維度和面向、「需求」和「價值觀」）傳回正規化評分，作為其回應的一部分。如果您將 `raw_scores` 查詢參數設為 `true`，服務也可以報告每一項特質的 `raw_score`。原始評分只會根據作者的文字和特質的模型來表示該特質的評分，而不會將結果與樣本母體做比較。如需使用原始評分的相關資訊，請參閱[性格特質的原始評分](/docs/services/personality-insights/numeric.html#rawScores)。

## 要求消費喜好
{: #preferences}

服務一律會傳回性格模型的結果。當您將 `consumption_preferences` 查詢參數設為 `true` 時，服務也會根據其從輸入文字推斷的性格特質，傳回各種消費喜好的 `scores`。這些結果會指出作者喜好不同產品、服務和活動的傾向。企業可以使用這些結果，更充分瞭解作者的愛好，並為作者打造個人化的通訊和優惠方案。

如需不同消費喜好的相關資訊，請參閱[消費喜好](/docs/services/personality-insights/preferences.html)。如需解譯喜好數值結果的相關資訊，請參閱[消費喜好的評分](/docs/services/personality-insights/numeric.html#scores)。

## 指定介面版本
{: #version}

所有對 `/v3/profile` 方法的呼叫都必須包括 `version` 查詢參數，以指出您要使用的服務 API 和回應格式的版本。您要以日期來指定版本，格式為 `YYYY-MM-DD`；例如，指定 `2017-10-13` 代表 2017 年 10 月 13 日。此參數容許服務針對新版本來更新其 API 和回應格式，而不會岔斷現有的用戶端。

您指定的日期不需要完全符合服務的版本；服務會使用不超過所提供日期的版本。如果您指定的日期早於第 3 版的起始版本，則服務會使用第 3 版的 API。如果您指定的日期是未來的日期，或是晚於最新版本，則服務會使用最新版本。
