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

# 개발자에 대한 개요
{: #overviewDevelopers}

HTTP REST(Representational State Transfer) API를 통해 {{site.data.keyword.personalityinsightsshort}} 서비스를 사용할 수 있습니다. 다양한 언어와 환경에서 애플리케이션 개발을 단순화할 수 있도록 여러 소프트웨어 개발 킷(SDK)도 사용 가능합니다.
{: shortdesc}

## 서비스의 프로그래밍
{: #programming}

성격 프로파일을 생성하려면 텍스트를 서비스의 HTTP `POST /v3/profile` 메소드에 전송하십시오. 일반 텍스트, HTML 또는 JSON 컨텐츠를 제출할 수 있습니다. 서비스는 JSON 또는 CSV 형식으로 자체 분석을 리턴할 수 있습니다. 

각각의 성격 특성에 대해 서비스는 작성자의 글쓰기가 샘플 모집단 내에서 특성을 보여주는 정도를 기술하는 정규화된 점수인 *백분위수*를 보고합니다. 요청된 경우, 서비스는 샘플 모집단에 대해 정규화되지 않은 절대값인 *원 점수*도 리턴합니다. 입력에 시간소인이 있는 경우, 서비스는 요일 및 일중 시간과 관련하여 작성자의 글쓰기 습관에 대한 요약을 제공합니다. 요청된 경우, 서비스는 사용 가능한 각각의 소비 성향에 대한 가능성 점수도 리턴합니다. 

서비스 사용에 대한 자세한 정보는 다음을 참조하십시오. 

-   [프로파일 요청](/docs/services/personality-insights/input.html)
-   [JSON 프로파일 이해하기](/docs/services/personality-insights/output.html)
-   [CSV 프로파일 이해하기](/docs/services/personality-insights/output-csv.html)

### 프로파일 시각화
{: #visualize}

이 서비스는 프로파일의 그래픽 시각화를 가능하게 하는 Javascript 파일의 콜렉션을 제공합니다. 스크립트를 사용하면 캐싱 및 컨텐츠 배포 네트워크에서 서비스의 사용이 용이해집니다. 이는 데이터 구동 문서(`D3.js`) 라이브러리와 함께 JavaScript, jQuery, HTML 및 SVG에 의존하여 결과를 보여줍니다. 이러한 클라이언트 측 파일에 대한 정보는 [소프트웨어 개발 킷 사용](#sdks)에서 인용된 샘플 애플리케이션을 참조하십시오. `D3.js`에 대한 자세한 정보는 [d3js.org ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://d3js.org/){: new_window}를 참조하십시오. 

### CORS 지원
{: #CORS}

서비스는 브라우저 기반 클라이언트가 프론트 엔드 스크립트의 서비스에 대해 직접 비동기 요청을 작성할 수 있도록 CORS(Cross-Origin Resource Sharing)를 지원합니다. CORS를 사용하여 클라이언트는 요청이 발생한 도메인의 외부에 있는 도메인으로부터 자원을 요청할 수 있습니다. 이를 사용하여 웹 애플리케이션은 동일 오리진 보안 정책으로 작업할 수 있으며, 그렇지 않으면 해당 요청이 차단됩니다. 자세한 정보는 [enable-cors.org ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://enable-cors.org/){: new_window}를 참조하십시오. 

## 소프트웨어 개발 킷 사용
{: #sdks}

{{site.data.keyword.personalityinsightsshort}} 서비스는 간단한 애플리케이션 개발을 위해 다수의 SDK를 지원합니다. Node.js, Java, Python 및 Apple&reg; iOS 등을 포함하여 많은 일반적인 프로그래밍 언어와 플랫폼에 대해 SDK를 사용할 수 있습니다. SDK의 전체 목록과 이의 사용에 대한 정보는 [{{site.data.keyword.watson}} SDK](/docs/services/watson/getting-started-sdks.html)를 참조하십시오. 모든 SDK는 GitHub의 [watson-developer-cloud 네임스페이스 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://github.com/watson-developer-cloud){: new_window}에서 사용 가능합니다. 

서비스에서는 사용자가 시작하는 데 도움이 되도록 다음의 샘플 애플리케이션도 제공합니다. 

-   [personality-insights-nodejs 저장소 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window}에서 Node.js SDK를 사용하는 애플리케이션에 액세스할 수 있습니다. 
-   [personality-insights-java 저장소 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://github.com/watson-developer-cloud/personality-insights-java){: new_window}에서 Java SDK를 사용하는 애플리케이션에 액세스할 수 있습니다. 

모바일 개발의 경우에는 [{{site.data.keyword.watson}} Developer Cloud Swift SDK ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://github.com/watson-developer-cloud/swift-sdk){: new_window}를 참조하십시오. 모든 SDK에서는 서비스 신임 정보 또는 인증 토큰을 사용한 인증을 지원합니다. 

## 애플리케이션 개발에 대해 자세히 알아보기
{: #learn}

{{site.data.keyword.personalityinsightsshort}} 서비스는 두 개의 일반 프로그래밍 모델을 지원합니다. 하나는 클라이언트가 서비스와 직접 통신하는 *직접 상호작용*이며, 다른 하나는 클라이언트와 서비스가 {{site.data.keyword.Bluemix_short}}에 상주하는 프록시 애플리케이션을 통해 모든 데이터(요청 및 결과)를 교환하는 *프록시를 통한 릴레이*입니다. 

{{site.data.keyword.watson}} Developer Cloud 서비스와 {{site.data.keyword.Bluemix_notm}} 관련 작업에 대한 자세한 정보는 다음을 참조하십시오. 

-   {{site.data.keyword.watson}} 서비스와 {{site.data.keyword.Bluemix_notm}} 관련 작업에 대한 소개는 [{{site.data.keyword.watson}} 및 {{site.data.keyword.Bluemix_notm}} 시작하기](/docs/services/watson/index.html)를 참조하십시오. 
-   {{site.data.keyword.Bluemix_notm}}에서 {{site.data.keyword.watson}} 서비스 애플리케이션 개발에 대한 언어 독립적인 소개는 [{{site.data.keyword.Bluemix_notm}} 개발 접근 방법](/docs/services/watson/getting-started-bluemix.html)을 참조하십시오. 
-   {{site.data.keyword.watson}} 애플리케이션 개발에 사용 가능한 두 개의 프로그래밍 모델에 대한 정보는 [{{site.data.keyword.watson}} 서비스에 대한 프로그래밍 모델](/docs/services/watson/getting-started-develop.html)을 참조하십시오. 
    -   프록시를 통한 릴레이에서, 클라이언트는 {{site.data.keyword.Bluemix_notm}}에 상주하는 프록시 서버에 의존하여 서비스와 통신합니다. 이는 프록시 애플리케이션을 통해 모든 요청을 전달합니다. 프록시를 통한 요청 릴레이는 서비스 신임 정보에만 의존하여 서비스를 인증합니다. [{{site.data.keyword.watson}} 서비스에 대한 서비스 신임 정보](/docs/services/watson/getting-started-credentials.html)를 참조하십시오. 
    -   직접 상호작용에서, 클라이언트는 {{site.data.keyword.Bluemix_notm}}의 프록시 애플리케이션만 사용하여 서비스에 대한 인증 토큰을 가져오며 이후에 이는 서비스와 직접 통신합니다. 직접 상호작용은 서비스 신임 정보만 사용하여 토큰을 가져옵니다. [인증을 위한 토큰](/docs/services/watson/getting-started-tokens.html)을 참조하십시오. 
-   모든 {{site.data.keyword.watson}} 서비스에 대해 수행되는 기본 요청 로깅의 제어에 대한 정보는 [{{site.data.keyword.watson}} 서비스의 요청 로깅 제어](/docs/services/watson/getting-started-logging.html)를 참조하십시오. 
