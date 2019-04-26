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

# 시작하기 튜토리얼
{: #gettingStarted}

{{site.data.keyword.personalityinsightsfull}} 서비스는 소셜 미디어, 엔터프라이즈 데이터 또는 기타 디지털 통신에서 성격 특성에 대한 통찰을 유도합니다. 이 튜토리얼은 {{site.data.keyword.personalityinsightsshort}} 서비스를 빠르게 시작하는 데 도움이 될 수 있습니다. 예제에서는 서로 다른 유형의 입력으로 서비스의 `POST /v3/profile` 메소드를 호출하는 방법과 서로 다른 유형의 결과 및 결과 형식을 요청하는 방법을 보여줍니다.
{: shortdesc}

이 튜토리얼에서는 {{site.data.keyword.cloud}} Identity and Access Management(IAM) API 키를 인증에 사용합니다. 이전 서비스 인스턴스는 인증을 위해 기존 Cloud Foundry 서비스 인증 정보의 `{username}` 및 `{password}`를 계속 사용할 수 있습니다. 서비스 인스턴스에 적합한 접근 방식을 사용하여 인증을 받습니다. 서비스의 IAM 인증 사용에 대한 자세한 정보는 릴리스 정보에 있는 [2018년 10월 30일 서비스 업데이트](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018)를 참조하십시오.
{: important}

## 시작하기 전에
{: #before-you-begin}

-   {: hide-dashboard}서비스의 인스턴스 작성:
    1.  {: hide-dashboard}{{site.data.keyword.cloud_notm}} 카탈로그의 [{{site.data.keyword.personalityinsightsshort}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/catalog/services/personality-insights){:new_window} 페이지로 이동하십시오.
    1.  {: hide-dashboard}무료 {{site.data.keyword.cloud_notm}} 계정에 등록하거나 로그인하십시오.
    1.  {: hide-dashboard}**작성**을 클릭하십시오.
-   서비스 인스턴스를 인증하기 위한 신임 정보 복사:
    1.  {: hide-dashboard}[{{site.data.keyword.cloud_notm}} 대시보드 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/dashboard/apps){: new_window}에서 {{site.data.keyword.personalityinsightsshort}} 서비스 인스턴스를 클릭하여 {{site.data.keyword.personalityinsightsshort}} 서비스 대시보드 페이지로 이동하십시오. 
    1.  **관리** 페이지에서 **표시**를 클릭하여 인증 정보를 보십시오. 
    1.  `API Key` 및 `URL` 값을 복사하십시오. 
-   `curl` 명령이 있는지 확인하십시오. 
    -   예제에서는 `curl` 명령을 사용하여 HTTP 인터페이스의 메소드를 호출합니다. [curl.haxx.se ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://curl.haxx.se/){: new_window}에서 운영 체제에 대한 버전을 설치하십시오. SSL(Secure Sockets Layer) 프로토콜을 지원하는 버전을 설치하십시오. `PATH` 환경 변수에 설치된 2진 파일이 포함되는지 확인하십시오.

명령을 입력할 때 실제 API 키와 URL로 `{apikey}` 및 `{url}`을 바꾸십시오. 명령에서 변수값을 나타내는 중괄호를 생략하십시오. 실제 값은 다음 예제와 유사합니다.
{: hide-dashboard}

```bash
curl -X POST -u "apikey:L_HALhLVIksh1b73l97LSs6R_3gLo4xkujAaxm7i-b9x"
. . .
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{:pre}
{: hide-dashboard}

## 1단계: 일반 텍스트 입력 전송 및 기본 JSON 결과 수신
{: #example1}

첫 번째 예제는 일반 텍스트 파일 `profile.txt`를 `POST /v3/profile` 메소드에 전달하고 JSON 응답을 요청합니다. 

1.  샘플 파일 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="외부 링크 아이콘" title="외부 링크 아이콘"></a>를 다운로드하십시오.
1.  다음 명령을 실행하여 파일을 `/v3/profile` 메소드에 전송하고 JSON 응답을 요청하십시오. 
    -   `Content-Type` 헤더는 입력이 일반 텍스트, `text/plain`임을 지정합니다. 헤더에 포함된 `charset`매개변수는 입력 텍스트의 문자열 인코딩을 식별합니다. 
    -   `Accept` 헤더는 JSON 출력이 요청되었음을 나타내기 위해 `application/json`을 지정합니다. 
    -   {: hide-dashboard}사용자 정보로 `{apikey}` 및 `{url}`을 바꾸십시오. 
    -   `{path_to_file}`을 수정하여 `profile.txt` 파일의 위치를 지정하십시오.

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.txt \
    "{url}/v3/profile?version=2017-10-13"{: url}
    ```
    {: pre}

서비스는 기본 메타데이터(예: 입력에서 단어의 수, 입력이 처리된 언어 모델, 입력과 연관된 경고)를 포함하는 JSON `Profile` 오브젝트를 리턴합니다. 자세한 정보는 [프로파일 오브젝트](/docs/services/personality-insights?topic=personality-insights-output#outputJSON)를 참조하십시오.

프로파일에는 입력 텍스트에서 추론된 작성자에 대한 빅 파이브 성격, 욕구 및 가치 특성에 대한 정보가 포함되어 있습니다. 서비스는 각 특성에 대한 `percentile` 또는 정규화된 점수를 보고합니다. 서비스는 작성자의 결과와 샘플 모집단의 결과를 비교하여 백분위수를 계산합니다. 자세한 정보는 [성격 특성 결과](/docs/services/personality-insights?topic=personality-insights-output#traitJSON)를 참조하십시오.

## 2단계: JSON 입력 전송 및 상세 JSON 결과 수신
{: #example2}

두 번째 예제는 JSON 파일 `profile.json`을 `/v3/profile` 메소드에 전달한 후에 다시 JSON 응답을 요청합니다. 예제에서는 입력의 추가적인 상세 분석을 위해 소비 성향과 원 점수를 요청합니다.

1.  Twitter 메시지의 콜렉션이 포함된 샘플 파일 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="외부 링크 아이콘" title="외부 링크 아이콘"></a>을 다운로드하십시오.
1.  다음 명령을 실행하여 파일을 `/v3/profile` 메소드로 전송하십시오. 예제에서는 `Content-Type` 및 `Accept` 헤더에 대해 `application/json`을 지정합니다. `charset` 매개변수는 JSON 입력에 필요하지 않습니다. 예제에서는 `consumption_preferences` 및 `raw_scores` 조회 매개변수를 `true`로 설정합니다.

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.json \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"{: url}
    ```
    {: pre}

서비스는 이전 예제에서 리턴된 메타데이터 및 특성이 포함된 JSON 프로파일을 리턴합니다. 
각 특성의 경우, 서비스에는 결과를 샘플 모집단과 비교하지 않고 입력 텍스트에만 기반하여
특성에 대한 작성자의 점수를 표시하는 `raw_score`도 포함되어 있습니다.

입력 컨텐츠에 시간소인이 포함되어 있으므로 서비스는 행동 특성도 보고합니다. 
이는 각 요일과 일중 시간에 작성된 컨텐츠 항목의 `percentage`를 표시하는 시간 특성입니다. 자세한 정보는 [행동 결과](/docs/services/personality-insights?topic=personality-insights-output#behaviorJSON)를 참조하십시오.

서비스는 소비 성향의 콜렉션에 대한 점수도 보고합니다. 
점수는 추론된 특성을 기반으로 하여 작성자가 서로 다른 제품, 서비스 및 활동을 선호할 가능성을 표시합니다. 자세한 정보는 [소비 성향 결과](/docs/services/personality-insights?topic=personality-insights-output#preferenceJSON)를 참조하십시오.

## 3단계: JSON 입력 전송 및 상세 CSV 결과 수신
{: #example3}

세 번째 예제는 두 번째 예제와 유사합니다. 이는 동일한 JSON 컨텐츠를 전달하며 동일한 결과를 요청합니다. 
그러나 이 예제에서는 CSV(Comma-Separated Values) 형식의 응답을 요청하기 위해
`Accept` 헤더에 대해 `text/csv`를 지정합니다. 
이는 `curl` 명령의 `--output` 옵션을 사용하여 `profile.csv`로 이름 지정된 파일에 결과를 지정합니다. 
예제에서는 `csv_headers` 조회 매개변수를 `true`로 설정하여 열 헤더가 결과에서 리턴되도록 요청합니다.

1.  다음 명령을 실행하여 JSON 파일을 `/v3/profile` 메소드로 전송하십시오. `Content-Type` 헤더는 `application/json`으로 입력 컨텐츠를 지정하고 `Accept` 헤더는 CSV 출력 `text/csv`를 요청합니다. 

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary @{path_to_file}profile.json \
    --output profile.csv \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"{: url}
    ```
    {: pre}

CSV 응답 및 헤더의 세부 설명은 [CSV 프로파일 이해하기](/docs/services/personality-insights?topic=personality-insights-outputCSV)를 참조하십시오.

## 다음 단계
{: #gsns}

-   [프로파일 요청](/docs/services/personality-insights?topic=personality-insights-input)에 대해서와
[JSON 프로파일 이해하기](/docs/services/personality-insights?topic=personality-insights-output) 및
[CSV 프로파일 이해하기](/docs/services/personality-insights?topic=personality-insights-outputCSV)에 대해 자세히 알아봅니다.
-   빅 파이브, 욕구 및 가치 [성격 모델](/docs/services/personality-insights?topic=personality-insights-models)에 대해 알아봅니다.
-   [API 참조서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크아이콘")](https://{DomainName}/apidocs/personality-insights){: new_window}에서 API에 대해 알아봅니다.
-   서비스에서 애플리케이션 개발에 대해 자세히 알아보려면 [Node.js 샘플 애플리케이션 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window}을 자세히 살펴보십시오.
