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

# 開發人員概觀
{: #overviewDevelopers}

您可以透過「HTTP 具象狀態傳輸 (REST) API」來使用 {{site.data.keyword.personalityinsightsshort}} 服務。還有數項「軟體開發套件 (SDK)」可用來簡化各種語言的應用程式開發。
{: shortdesc}

## 使用服務進行程式設計
{: #programming}

若要產生性格設定檔，請將文字傳送至服務的 HTTP `POST /v3/profile` 方法。您可以提交純文字、HTML 或 JSON 內容。服務可以用 JSON 或 CSV 格式傳回其分析。

對於每一個性格特質，服務會報告*百分位數*。百分位數為正規化的評分，用來說明作者的寫作風格在樣本母體內顯現的特質達到什麼程度。如果要求，服務也會傳回*原始評分*，這是未針對樣本母體正規化的絕對值。如果輸入文字有時間戳記，服務會依據星期幾和時間提供作者書寫習慣的摘要。而如果要求，服務也會針對其可用的每一個消費喜好傳回可能性評分。

如需使用服務的相關資訊，請參閱

-   [要求設定檔](/docs/services/personality-insights?topic=personality-insights-input)
-   [瞭解 JSON 設定檔](/docs/services/personality-insights?topic=personality-insights-output)
-   [瞭解 CSV 設定檔](/docs/services/personality-insights?topic=personality-insights-outputCSV)

### 將設定檔視覺化
{: #visualize}

服務提供 JavaScript 檔案集合，可讓您將設定檔視覺化成圖形。這些 Script 有助於搭配快取和內容配送網路來使用服務。其有賴於 JavaScript、jQuery、HTML 和 SVG 搭配「資料驅動文件」(`D3.js`) 檔案庫來描述結果。如需 `D3.js` 的相關資訊，請參閱 [d3js.org ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://d3js.org/){: new_window}。

### CORS 支援
{: #CORS}

服務支援「跨原點資源共用 (CORS) 」。CORS 容許瀏覽器型用戶端直接從前端 Script 向服務發出非同步要求。CORS 規避原本會防止這類要求的同源安全原則。

透過使用 CORS，讓網頁可以要求外來網域（位於最先提出要求的來源網域以外）的資源。如需相關資訊，請參閱 [enable-cors.org ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://enable-cors.org/){: new_window}。

## 使用軟體開發套件
{: #sdks}

SDK 可供 {{site.data.keyword.personalityinsightsshort}} 服務來簡化應用程式開發。{{site.data.keyword.ibmwatson}} SDK 適用於許多熱門的程式設計語言和平台。

-   如需 SDK 的完整清單及 GitHub 上 SDK 的鏈結，請參閱[使用 SDK](/docs/services/watson?topic=watson-using-sdks)。
-   如需 {{site.data.keyword.personalityinsightsshort}} 服務的 Node、Java、 Python、Ruby 及 Go SDK 的所有方法的詳細資訊，請參閱 [API 參考資料 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://{DomainName}/apidocs/personality-insights){: new_window}。

## 進一步瞭解應用程式開發
{: #learn-overview}

如需使用 {{site.data.keyword.watson}} 服務和 {{site.data.keyword.cloud}} 的相關資訊，請參閱下列各節：

-   如需使用 {{site.data.keyword.watson}} 服務和 {{site.data.keyword.cloud_notm}} 的簡介，請參閱[開始使用 {{site.data.keyword.watson}} 和 {{site.data.keyword.cloud_notm}}](/docs/services/watson?topic=watson-about)。
-   所有新的服務實例都使用 {{site.data.keyword.cloud_notm}} Identity and Access Managemen (IAM) 來進行鑑別。較舊的服務實例可能會繼續使用現有 Cloud Foundry 服務認證中的 `{username}` 和 `{password}` 進行鑑別。如需對服務進行鑑別的相關資訊，請參閱版本注意事項中的 [2018 年 10 月 30 日服務更新](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018)。
-   已停用 {{site.data.keyword.personalityinsightsshort}} 服務的要求記載。無論是否設定 `X-Watson-Learning-Opt-Out` 要求標頭，服務都不會記載或保留要求和回應的資料。
