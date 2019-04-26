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

# 개발자에 대한 개요
{: #overviewDevelopers}

HTTP REST(Representational State Transfer) API를 통해 {{site.data.keyword.personalityinsightsshort}} 서비스를 사용할 수 있습니다. 다양한 언어에서 애플리케이션 개발을 단순화할 수 있도록 여러 소프트웨어 개발 킷(SDK)도 사용 가능합니다.
{: shortdesc}

## 서비스의 프로그래밍
{: #programming}

성격 프로파일을 생성하려면 텍스트를 서비스의 HTTP `POST /v3/profile` 메소드에 전송하십시오. 일반 텍스트, HTML 또는 JSON 컨텐츠를 제출할 수 있습니다. 서비스는 JSON 또는 CSV 형식으로 자체 분석을 리턴할 수 있습니다.

각 성격 특성에 대해 서비스에서 *백분위수*를 보고합니다. 백분위수는 정규화된 점수로서 작성자의 글쓰기가 표본 모집단 내에서 특성을 나타내는 범위를 나타냅니다. 요청된 경우, 서비스는 샘플 모집단에 대해 정규화되지 않은 절대값인 *원 점수*도 리턴합니다. 입력에 시간소인이 있는 경우 해당 서비스는 작성자의 글쓰기 습관에 대한 요약을 요일 및 하루 중 시간별로 제공합니다. 요청된 경우, 서비스는 사용 가능한 각각의 소비 성향에 대한 가능성 점수도 리턴합니다.

서비스 사용에 대한 자세한 정보는 다음을 참조하십시오.

-   [프로파일 요청](/docs/services/personality-insights?topic=personality-insights-input)
-   [JSON 프로파일 이해하기](/docs/services/personality-insights?topic=personality-insights-output)
-   [CSV 프로파일 이해하기](/docs/services/personality-insights?topic=personality-insights-outputCSV)

### 프로파일 시각화
{: #visualize}

이 서비스는 프로파일의 그래픽 시각화를 가능하게 하는 Javascript 파일의 콜렉션을 제공합니다. 스크립트를 사용하면 캐싱 및 컨텐츠 배포 네트워크에서 서비스의 사용이 용이해집니다. 이는 데이터 구동 문서(`D3.js`) 라이브러리와 함께 JavaScript, jQuery, HTML 및 SVG에 의존하여 결과를 보여줍니다. `D3.js`에 대한 자세한 정보는 [d3js.org ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://d3js.org/){: new_window}를 참조하십시오. 

### CORS 지원
{: #CORS}

이 서비스는 CORS(Cross-Origin Resource Sharing)를 지원합니다. CORS를 사용하면 브라우저 기반 클라이언트가 프론트 엔드 스크립트에서 서비스로 직접 비동기 요청을 할 수 있습니다. CORS는 동일 출처 보안 정책을 우회하거나 그렇지 않으면 이러한 요청을 차단합니다. 

CORS를 사용하여 웹 페이지는 요청이 시작된 도메인의 외부 도메인에서 리소스를 요청할 수 있습니다. 자세한 정보는 [enable-cors.org ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://enable-cors.org/){: new_window}를 참조하십시오.

## 소프트웨어 개발 킷 사용
{: #sdks}

애플리케이션 개발을 단순화하기 위해 SDK를 {{site.data.keyword.personalityinsightsshort}} 서비스에 사용할 수 있습니다. {{site.data.keyword.ibmwatson}} SDK는 많은 대중적인 프로그래밍 언어 및 플랫폼에 사용할 수 있습니다. 

-   SDK의 전체 목록과 GitHub의 SDK에 대한 링크는 [SDK 사용](/docs/services/watson?topic=watson-using-sdks)을 참조하십시오. 
-   {{site.data.keyword.personalityinsightsshort}} 서비스에 대한 Node, Java, Python, Ruby 및 Go SDK의 모든 메소드에 대한 자세한 정보는 [API 참조서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/apidocs/personality-insights){: new_window}를 참조하십시오. 

## 애플리케이션 개발에 대해 자세히 알아보기
{: #learn-overview}

{{site.data.keyword.watson}} 서비스 및 {{site.data.keyword.cloud}} 관련 작업에 대한 자세한 정보는 다음 절을 참조하십시오. 

-   {{site.data.keyword.watson}} 서비스 및 {{site.data.keyword.cloud_notm}} 관련 작업에 대한 소개는 [{{site.data.keyword.watson}} 및 {{site.data.keyword.cloud_notm}} 시작하기](/docs/services/watson?topic=watson-about)를 참조하십시오.
-   모든 새로운 서비스 인스턴스는 인증을 위해 {{site.data.keyword.cloud_notm}} Identity and Access Management(IAM)를 사용합니다. 이전 서비스 인스턴스는 인증을 위해 기존 Cloud Foundry 서비스 인증 정보의 `{username}` 및 `{password}`를 계속 사용할 수 있습니다. 서비스 인증에 대한 자세한 내용은 릴리스 정보에 있는 [2018년 10월 30일 서비스 업데이트](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018)를 참조하십시오. 
-   {{site.data.keyword.personalityinsightsshort}} 서비스에서 요청 로깅이 사용 안함으로 설정되어 있습니다. 이 서비스는 `X-Watson-Learning-Opt-Out` 요청 헤더가 설정되어 있는지 여부에 관계없이 요청 및 응답의 데이터를 기록하거나 보관하지 않습니다. 
