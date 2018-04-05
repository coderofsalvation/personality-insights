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

# 튜토리얼 시작하기
{: #gettingStarted}

{{site.data.keyword.personalityinsightsfull}} 서비스는 소셜 미디어, 엔터프라이즈 데이터
또는 기타 디지털 통신에서 성격 특성에 대한 통찰을 유도합니다. 이 튜토리얼은 {{site.data.keyword.personalityinsightsshort}}
서비스를 빠르게 시작하는 데 도움이 될 수 있습니다. 예제에서는 서로 다른 유형의 입력으로 서비스의
`POST /v3/profile` 메소드를 호출하는 방법과 서로 다른 유형의 결과 및 결과 형식을 요청하는 방법을 보여줍니다.
{: shortdesc}

## 시작하기 전에
{: #before-you-begin}

- 서비스의 인스턴스 작성:
    - {: download} 이를 보는 경우에는 서비스 인스턴스가 작성된 것입니다. 이제 신임 정보를 가져오십시오.
    - 서비스에서 프로젝트 작성:
        1.  {{site.data.keyword.watson}} 개발자 콘솔 [서비스 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://console.{DomainName}/developer/watson/services){: new_window} 페이지로 이동하십시오.
        1.  {{site.data.keyword.personalityinsightsshort}}를 선택하고
**서비스 추가**를 클릭한 후에 무료 {{site.data.keyword.Bluemix_notm}} 계정에 등록하거나 로그인하십시오.
        1.  프로젝트 이름으로 `personality-tutorial`을 입력하고 **프로젝트 작성**을 클릭하십시오.
- 서비스 인스턴스를 인증하기 위한 신임 정보 복사:
    - {: download} (현재 보고 있는) 서비스 대시보드에서:
        1.  **서비스 신임 정보** 탭을 클릭하십시오.
        1.  **조치** 아래의 **신임 정보 보기**를 클릭하십시오.
        1.  `username`, `password` 및 `url` 값을 복사하십시오.
        {: download}
    - 개발자 콘솔에 있는 **personality-tutorial** 프로젝트의
**신임 정보** 섹션에서 `"personality_insights"`에 대한
`username`,  `password` 및 `url` 값을 복사하십시오.
- cURL을 보유 중인지 확인:
    - 예제에서는 cURL을 사용하여 HTTP 인터페이스의 메소드를 호출합니다.
[curl.haxx.se ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://curl.haxx.se/){: new_window}에서 운영 체제에 대한 버전을 설치하십시오.
SSL(Secure Sockets Layer) 프로토콜을 지원하는 버전을 설치하십시오. `PATH` 환경 변수에 설치된 2진 파일이 포함되는지 확인하십시오.

<!-- Remove this text after dedicated instances have the Developer Console: begin -->

{{site.data.keyword.Bluemix_dedicated_notm}}를 사용하는 경우, 카탈로그의
[{{site.data.keyword.personalityinsightsshort}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://console.{DomainName}/catalog/services/personality-insights/){: new_window}
페이지에서 서비스 인스턴스를 작성하십시오. 서비스 신임 정보를 찾는 방법에 대한 세부사항은
[Watson 서비스의
서비스 신임 정보 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](/docs/services/watson/getting-started-credentials.html#getting-credentials-manually){: new_window}를 참조하십시오.

<!-- Remove this text after dedicated instances have the Developer Console: end -->

## 1단계: 일반 텍스트 입력 전송 및 기본 JSON 결과 수신
{: #example1}

첫 번째 예제는 일반 텍스트 파일 `profile.txt`를
`POST /v3/profile` 메소드에 전달하고 기본 JSON 응답을 내재적으로 요청합니다.

1.  샘플 파일 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="외부 링크 아이콘" title="외부 링크 아이콘" class="style-scope doc-content"></a>를 다운로드하십시오.
1.  다음 명령을 실행하여 파일을 `/v3/profile` 메소드에 전송하고 기본 JSON 응답을 요청하십시오.
`Content-Type` 헤더에 포함된 `charset` 매개변수는 입력 텍스트의 문자 인코딩을 지정합니다.
    -   `{username}` 및 `{password}`를 이전 단계의 서비스 신임 정보로 대체하십시오.
    -   `{path_to_file}`을 수정하여 `profile.txt` 파일의 위치를 지정하십시오.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --data-binary "@{path_to_file}profile.txt" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
    ```
    {: pre}

서비스는 기본 메타데이터(예: 입력에서 단어의 수, 입력이 처리된 언어 모델,
입력과 연관된 경고)를 포함하는 JSON `Profile` 오브젝트를 리턴합니다. 자세한 정보는
[프로파일 오브젝트](/docs/services/personality-insights/output.html#outputJSON)를 참조하십시오.

프로파일에는 입력 텍스트에서 추론된 작성자에 대한 빅 파이브 성격, 욕구 및 가치 특성에 대한 정보가 포함되어 있습니다.
서비스는 각 특성에 대한 `percentile` 또는 정규화된 점수를 보고합니다.
서비스는 작성자의 결과와 샘플 모집단의 결과를 비교하여 백분위수를 계산합니다. 자세한 정보는
[성격 특성 결과](/docs/services/personality-insights/output.html#traitJSON)를 참조하십시오.

## 2단계: JSON 입력 전송 및 상세 JSON 결과 수신
{: #example2}

두 번째 예제는 JSON 파일 `profile.json`을
`/v3/profile` 메소드에 전달한 후에 다시 기본 JSON 응답을 받습니다.
예제에서는 입력의 추가적인 상세 분석을 위해 소비 성향과 원 점수를 요청합니다.

1.  Twitter 메시지의 콜렉션이 포함된 샘플 파일 <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="외부 링크 아이콘" title="외부 링크 아이콘" class="style-scope doc-content"></a>을 다운로드하십시오.
1.  다음 명령을 실행하여 파일을 `/v3/profile` 메소드로 전송하십시오.
예제에서는 `Content-Type` 헤더에 대해 `application/json`을 지정합니다.
`charset` 매개변수는 JSON 입력에 대해 필요하지 않습니다. 예제에서는 `consumption_preferences` 및
`raw_scores` 조회 매개변수를 `true`로 설정합니다.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --data-binary "@{path_to_file}profile.json" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"
    ```
    {: pre}

서비스는 이전 예제에서 리턴된 메타데이터 및 특성이 포함된 JSON 프로파일을 리턴합니다.
각 특성의 경우, 서비스에는 결과를 샘플 모집단과 비교하지 않고 입력 텍스트에만 기반하여
특성에 대한 작성자의 점수를 표시하는 `raw_score`도 포함되어 있습니다.

입력 컨텐츠에 시간소인이 포함되어 있으므로 서비스는 행동 특성도 보고합니다.
이는 각 요일과 일중 시간에 작성된 컨텐츠 항목의 `percentage`를 표시하는 시간 특성입니다.
자세한 정보는 [행동 결과](/docs/services/personality-insights/output.html#behaviorJSON)를 참조하십시오.

서비스는 소비 성향의 콜렉션에 대한 점수도 보고합니다.
점수는 추론된 특성을 기반으로 하여 작성자가 서로 다른 제품, 서비스 및 활동을 선호할 가능성을 표시합니다.
자세한 정보는 [소비 성향 결과](/docs/services/personality-insights/output.html#preferenceJSON)를 참조하십시오.

## 3단계: JSON 입력 전송 및 상세 CSV 결과 수신
{: #example3}

세 번째 예제는 두 번째 예제와 유사합니다. 이는 동일한 JSON 컨텐츠를 전달하며 동일한 결과를 요청합니다.
그러나 이 예제에서는 CSV(Comma-Separated Values) 형식의 응답을 요청하기 위해
`Accept` 헤더에 대해 `text/csv`를 지정합니다.
이는 cURL 명령의 `--output` 옵션을 사용하여 `profile.csv`로 이름 지정된 파일에 결과를 지정합니다.
예제에서는 `csv_headers` 조회 매개변수를 `true`로 설정하여 열 헤더가 결과에서 리턴되도록 요청합니다.

1.  다음 명령을 실행하여 JSON 파일을 `/v3/profile` 메소드로 전송하십시오.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary "@{path_to_file}profile.json" \
    --output profile.csv \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"
    ```
    {: pre}

CSV 응답 및 헤더의 세부 설명은 [CSV 프로파일 이해하기](/docs/services/personality-insights/output-csv.html)를 참조하십시오.

## 다음 단계

-   [프로파일 요청](/docs/services/personality-insights/input.html)에 대해서와
[JSON 프로파일 이해하기](/docs/services/personality-insights/output.html) 및
[CSV 프로파일 이해하기](/docs/services/personality-insights/output-csv.html)에 대해 자세히 알아봅니다.
-   빅 파이브, 욕구 및 가치 [성격 모델](/docs/services/personality-insights/models.html)에 대해 알아봅니다.
-   [API 참조서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크아이콘")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}에서 API에 대해 알아봅니다.
-   [API 탐색기 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v3){: new_window}에서 API와 상호작용합니다.
-   서비스에서 애플리케이션 개발에 대해 자세히 알아보려면 [Node.js 샘플 애플리케이션 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window}을 자세히 살펴보십시오.
