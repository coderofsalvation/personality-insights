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

# 入門指導教學
{: #gettingStarted}

{{site.data.keyword.personalityinsightsfull}} 服務從社交媒體、企業資料或其他數位通訊中，衍生出性格特質的相關洞察分析。本指導教學可協助您快速開始使用 {{site.data.keyword.personalityinsightsshort}} 服務。範例會顯示如何以不同類型的輸入來呼叫服務的 `POST /v3/profile` 方法，以及如何要求不同類型的輸出和輸出格式。
{: shortdesc}

## 開始之前
{: #before-you-begin}

- 建立服務的實例：
    - {: download} 如果您看到這個，表示您已建立服務實例。現在則要取得您的認證。
    - 從服務建立專案：
        1.  移至 {{site.data.keyword.watson}} 開發人員主控台 [服務 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://console.{DomainName}/developer/watson/services){: new_window} 頁面。
        1.  選取 {{site.data.keyword.personalityinsightsshort}}，按一下**新增服務**，然後註冊免費的 {{site.data.keyword.Bluemix_notm}} 帳戶或登入。
        1.  鍵入 `personality-tutorial` 作為專案名稱，然後按一下**建立專案**。
- 複製認證，以向服務實例進行鑑別：
    - {: download} 從服務儀表板（您正在查看的畫面）：
        1.  按一下**服務認證**標籤。
        1.  按一下**動作**下的**檢視認證**。
        1.  複製 `username`、`password` 和 `url` 值。{: download}
    - 在「開發人員主控台」中，從 **personality-tutorial** 專案的**認證**區段複製 `"personality_insights"` 的 `username`、`password` 和 `url` 值。
- 確定您具有 cURL：
    - 範例會使用 cURL 來呼叫 HTTP 介面的方法。從 [curl.haxx.se ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://curl.haxx.se/){: new_window} 安裝適用於您作業系統的版本。安裝支援 Secure Sockets Layer (SSL) 通訊協定的版本。請務必在 `PATH` 環境變數中併入已安裝的二進位檔。

<!-- Remove this text after dedicated instances have the Developer Console: begin -->

如果您使用 {{site.data.keyword.Bluemix_dedicated_notm}}，請從「型錄」中的 [{{site.data.keyword.personalityinsightsshort}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://console.{DomainName}/catalog/services/personality-insights/){: new_window} 頁面建立服務實例。如需如何尋找服務認證的詳細資料，請參閱 [Watson 服務的服務認證 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](/docs/services/watson/getting-started-credentials.html#getting-credentials-manually){: new_window}。

<!-- Remove this text after dedicated instances have the Developer Console: end -->

## 步驟 1：傳送純文字輸入，並接收基本 JSON 輸出
{: #example1}

第一個範例會將純文字檔 `profile.txt` 傳遞至 `POST /v3/profile` 方法，並隱含地要求預設 JSON 回應。

1.  下載範例檔案 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="外部鏈結圖示" title="外部鏈結圖示" class="style-scope doc-content"></a>。
1.  發出下列指令，將檔案傳送至 `/v3/profile` 方法，並要求預設 JSON 回應。`Content-Type` 標頭隨附的 `charset` 參數會指定輸入文字的字元編碼。
    -   將 `{username}` 和 `{password}` 取代為前一個步驟中的服務認證。
    -   修改 `{path_to_file}`，以指定 `profile.txt` 檔案的位置。

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --data-binary "@{path_to_file}profile.txt" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
    ```
    {: pre}

服務會傳回 JSON `Profile` 物件，其中包括基本 meta 資料，例如輸入中的字數、用來處理輸入的語言模型，以及與輸入相關聯的任何警告。如需相關資訊，請參閱 [Profile 物件](/docs/services/personality-insights/output.html#outputJSON)。

此設定檔包括作者的「五大性格」、「需求」和「價值觀」特質的相關資訊（從輸入文字推斷）。服務會針對每一項性質報告 `percentile` 或正規化評分。服務會將作者的結果與樣本母體的結果做比較，以計算百分位數。如需相關資訊，請參閱[性格特質輸出](/docs/services/personality-insights/output.html#traitJSON)。

## 步驟 2：傳送 JSON 輸入，並接收詳細的 JSON 輸出
{: #example2}

第二個範例會將 JSON 檔 `profile.json` 傳遞至 `/v3/profile` 方法，再次接受預設 JSON 回應。範例會要求消費喜好和原始評分，以取得更詳細的輸入分析。

1.  下載範例檔案 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="外部鏈結圖示" title="外部鏈結圖示" class="style-scope doc-content"></a>，其中包含 Twitter 訊息的集合。
1.  發出下列指令，將檔案傳送至 `/v3/profile` 方法。範例會為 `Content-Type` 標頭指定 `application/json`；JSON 輸入不需要 `charset` 參數。範例會將 `consumption_preferences` 和 `raw_scores` 查詢參數設為 `true`。

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --data-binary "@{path_to_file}profile.json" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"
    ```
    {: pre}

服務會傳回 JSON 設定檔，其中包括前一個範例所傳回的 meta 資料和特質。針對每一項特質，服務也會各併入一個 `raw_score`（代表僅根據輸入文字的作者特質評分），而不會將結果與樣本母體做比較。

因為輸入內容包括時間戳記，所以服務也會報告行為特質。這些是時間特質，可指出在星期幾和幾點建立之內容項目的 `percentage`。如需相關資訊，請參閱[行為輸出](/docs/services/personality-insights/output.html#behaviorJSON)。

服務也會報告其消費喜好集合的評分。評分會根據所推斷的特質，指出作者喜好不同產品、服務和活動的可能性。如需相關資訊，請參閱[消費喜好輸出](/docs/services/personality-insights/output.html#preferenceJSON)。

## 步驟 3：傳送 JSON 輸入，並接收詳細的 CSV 輸出
{: #example3}

第三個範例與第二個範例類似：它會傳遞相同的 JSON 內容，並要求相同的結果。但這個範例會為 `Accept` 標頭指定 `text/csv`，以要求逗點區隔值 (CSV) 格式的回應。它會使用 cURL 指令的 `--output` 選項，將結果導向至名為 `profile.csv` 的檔案。此範例將 `csv_headers` 查詢參數設為 `true`，以要求隨輸出傳回直欄標頭。

1.  發出下列指令，將 JSON 檔傳送至 `/v3/profile` 方法。

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary "@{path_to_file}profile.json" \
    --output profile.csv \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"
    ```
    {: pre}

如需 CSV 回應和標頭的詳細說明，請參閱[瞭解 CSV 設定檔](/docs/services/personality-insights/output-csv.html)。

## 後續步驟

-   進一步瞭解[要求設定檔](/docs/services/personality-insights/input.html)，並參閱[瞭解 JSON 設定檔](/docs/services/personality-insights/output.html)和[瞭解 CSV 設定檔](/docs/services/personality-insights/output-csv.html)。
-   瞭解「五大性格特質」、「需求」和「價值觀」的[性格模型](/docs/services/personality-insights/models.html)。
-   在 [API 參考資料 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window} 中進一步瞭解 API
-   在 [API 瀏覽器 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v3){: new_window} 中與 API 互動。
-   瀏覽 [Node.js 範例應用程式 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window}，以進一步瞭解如何使用服務進行應用程式開發。
