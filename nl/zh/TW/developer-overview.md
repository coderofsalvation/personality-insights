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

# 開發人員概觀
{: #overviewDevelopers}

您可以透過「HTTP 具象狀態傳輸 (REST) API」來使用 {{site.data.keyword.personalityinsightsshort}} 服務。還有數項「軟體開發套件 (SDK)」可用來簡化各種語言和環境的應用程式開發。
{: shortdesc}

## 使用服務進行程式設計
{: #programming}

若要產生性格設定檔，請將文字傳送至服務的 HTTP `POST /v3/profile` 方法。您可以提交純文字、HTML 或 JSON 內容。服務可以用 JSON 或 CSV 格式傳回其分析。

針對每一個性格特質，服務都會報告一個*百分位數*，其為正規化的評分，用來說明作者的寫作風格在樣本母體內顯現的特質達到什麼程度。如果要求，服務也會傳回*原始評分*，這是未針對樣本母體正規化的絕對值。如果輸入文字有時間戳記，服務會根據星期幾和時間提供作者書寫習慣的摘要。而如果要求，服務也會針對其可用的每一個消費喜好傳回可能性評分。

如需使用服務的相關資訊，請參閱

-   [要求設定檔](/docs/services/personality-insights/input.html)
-   [瞭解 JSON 設定檔](/docs/services/personality-insights/output.html)
-   [瞭解 CSV 設定檔](/docs/services/personality-insights/output-csv.html)

### 將設定檔視覺化
{: #visualize}

服務提供 JavaScript 檔案集合，可讓您將設定檔視覺化成圖形。這些 Script 有助於搭配快取和內容配送網路來使用服務。其有賴於 JavaScript、jQuery、HTML 和 SVG 搭配「資料驅動文件」(`D3.js`) 檔案庫來描述結果。如需這些用戶端檔案的相關資訊，請參閱[使用軟體開發套件](#sdks)中列出的範例應用程式；如需 `D3.js` 的相關資訊，請參閱 [d3js.org ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://d3js.org/){: new_window}。

### CORS 支援
{: #CORS}

服務支援「跨原點資源共用 (CORS)」，可容許瀏覽器型用戶端直接從前端 Script 向服務發出非同步要求。CORS 可讓用戶端要求提出要求來源網域以外的網域資源；如此可讓 Web 應用程式規避原本會防止這類要求的同源安全原則。如需相關資訊，請參閱 [enable-cors.org ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://enable-cors.org/){: new_window}。

## 使用軟體開發套件
{: #sdks}

{{site.data.keyword.personalityinsightsshort}} 服務支援若干可簡化應用程式開發的 SDK。這些 SDK 適用於許多熱門的程式設計語言和平台，包括 Node.js、Java、Python 和 Apple&reg; iOS。如需 SDK 的完整清單及其用法的相關資訊，請參閱 [{{site.data.keyword.watson}} SDK](/docs/services/watson/getting-started-sdks.html)。所有 SDK 都可從 GitHub 上的 [watson-developer-cloud 名稱空間 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/watson-developer-cloud){: new_window} 取得。

服務也可讓您取得下列範例應用程式，以協助您開始使用：

-   您可以在 [personality-insights-nodejs 儲存庫 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} 存取使用 Node.js SDK 的應用程式。
-   您可以在 [personality-insights-java 儲存庫 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/watson-developer-cloud/personality-insights-java){: new_window} 存取使用 Java SDK 的應用程式。

針對行動應用程式開發，請參閱 [{{site.data.keyword.watson}} Developer Cloud Swift SDK ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://github.com/watson-developer-cloud/swift-sdk){: new_window}。所有 SDK 都支援使用服務認證或鑑別記號來進行鑑別。

## 進一步瞭解應用程式開發
{: #learn}

{{site.data.keyword.personalityinsightsshort}} 服務支援兩種典型的程式設計模型：*直接互動*，在此模型中，用戶端會直接與服務通訊；以及*透過 Proxy 轉遞*，在此模型中，用戶端與服務會透過位於 {{site.data.keyword.Bluemix_short}} 中的 Proxy 應用程式來交換所有資料（要求和結果）。

如需使用 {{site.data.keyword.watson}} Developer Cloud 服務和 {{site.data.keyword.Bluemix_notm}} 的相關資訊，請參閱下列項目：

-   如需使用 {{site.data.keyword.watson}} 服務和 {{site.data.keyword.Bluemix_notm}} 的簡介，請參閱[開始使用 {{site.data.keyword.watson}} 和 {{site.data.keyword.Bluemix_notm}}](/docs/services/watson/index.html)。
-   如需在 {{site.data.keyword.Bluemix_notm}} 中開發 {{site.data.keyword.watson}} 服務應用程式的無關語言簡介，請參閱 [{{site.data.keyword.Bluemix_notm}} 開發方法](/docs/services/watson/getting-started-bluemix.html)。
-   如需這兩種可用來開發 {{site.data.keyword.watson}} 應用程式之程式設計模型的相關資訊，請參閱 [{{site.data.keyword.watson}} 服務的程式設計模型](/docs/services/watson/getting-started-develop.html)：
    -   透過 Proxy 轉遞時，用戶端會依賴位於 {{site.data.keyword.Bluemix_notm}} 的 Proxy 伺服器來與服務通訊；它會透過 Proxy 應用程式來傳遞所有要求。透過 Proxy 轉遞要求僅根據服務認證來向服務進行鑑別；請參閱 [{{site.data.keyword.watson}} 服務的服務認證](/docs/services/watson/getting-started-credentials.html)。
    -   透過直接互動，用戶端只會使用 {{site.data.keyword.Bluemix_notm}} 中的 Proxy 應用程式來取得服務的鑑別記號，之後它就會直接與服務進行通訊。直接互動只會使用服務認證來取得記號；請參閱[用來鑑別的記號](/docs/services/watson/getting-started-tokens.html)。
-   若要瞭解如何控制針對所有 {{site.data.keyword.watson}} 服務所執行的預設要求記載，請參閱[控制 {{site.data.keyword.watson}} 服務的要求記載](/docs/services/watson/getting-started-logging.html)。
