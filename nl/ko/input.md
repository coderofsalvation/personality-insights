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

# 프로파일 요청
{: #input}

컨텐츠를 분석하려면 HTTP `POST` 요청 메소드를 사용하여
{{site.data.keyword.personalityinsightsshort}} 서비스의 `/v3/profile` 메소드를 호출하십시오. 
요청의 본문을 통해 분석될 최대 20MB의 컨텐츠를 서비스에 전달할 수 있지만,
서비스는 정확한 성격 프로파일을 생성하기 위해 이보다 훨씬 적은 입력을 요구합니다.
자세한 정보는 [충분한 입력 제공](#sufficient)을 참조하십시오.
{: shortdesc}

`/v3/profile` 메소드에는 각 컨텐츠 유형의 언어는 물론
서비스에 전달되고 서비스에 의해 리턴될 컨텐츠의 유형을 지정할 수 있도록 허용하는 매개변수가 포함되어 있습니다. 
서비스는 항상 입력 텍스트 작성자의 성격 특성에 대한 통찰을 제공하는 프로파일을 리턴합니다. 
또한 서비스가 원 점수와 소비 성향을 리턴하도록 요청할 수도 있습니다. 

다음 절에서는 `/v3/profile` 메소드의 매개변수에 대해 설명합니다. 
요청의 결과에 대한 정보는 [JSON 프로파일 이해하기](/docs/services/personality-insights/output.html) 및
[CSV 프로파일 이해하기](/docs/services/personality-insights/output-csv.html)를 참조하십시오. `/v3/profile` 메소드에 대한 자세한 정보는
[API 참조서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}를 참조하십시오. 

## 요청 및 응답 형식 지정
{: #formats}

`Content-Type` 및 `Accept` 헤더 매개변수를 사용하여
메소드에 전달 중인 컨텐츠의 형식과 서비스의 응답에 대한 형식을 표시할 수 있습니다. 
요청과 응답에 대해 지원되는 형식을 임의로 조합하여 사용할 수 있습니다. 

<table>
  <caption>표 1. 요청 및 응답 형식 지정</caption>
  <tr>
    <th style="width:10%; text-align:left; vertical-align:bottom">
      형식
    </th>
    <th style="width:26%; text-align:center; vertical-align:bottom">
      인수
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      지원 기준: <br/>
      <code>Content-Type</code>
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      지원 기준: <br/>
      <code>Accept</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      일반 텍스트
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/plain</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      예(기본값)<br/><br/>
      서비스가 수정 없이 일반 텍스트를 처리합니다.
    </td>
    <td style="text-align:center; vertical-align:top">
      아니오
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
      예<br/><br/>
      서비스가 처리 전에 컨텐츠에서 태그를 제거합니다.
    </td>
    <td style="text-align:center; vertical-align:top">
      아니오
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
      예<br/><br/>
      컨텐츠가 <code>ContentItem</code> 오브젝트의 배열인 <code>Content</code> 오브젝트에서 정의하는 모델을 따라야 합니다.
    </td>
    <td style="text-align:center; vertical-align:top">
      예(기본값)<br/><br/>
      서비스가 <code>Profile</code> 오브젝트로서 해당 결과를 리턴합니다.
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
      아니오
    </td>
    <td style="text-align:center; vertical-align:top">
      예<br/><br/>
      기본적으로, 서비스가 단일 행의 숫자 결과를 리턴합니다.
      결과의 각 열에 대한 헤더를 요청하려면 선택적 <code>csv_headers</code> 조회 매개변수를 <code>true</code>로 설정하십시오.
    </td>
  </tr>
</table>

### 문자 세트 지정
{: #charset}

기본적으로, 서비스는 입력 컨텐츠에 대해 다음의 문자 세트를 사용합니다. 

-   *일반 텍스트 및 HTML 컨텐츠의 경우,* 서비스는 HTTP 버전 1.1 스펙에 따라
ISO(International Standards Organization)-8859-1 문자 세트(사실상 ASCII 문자 세트)를 사용합니다. 
-   *JSON 컨텐츠의 경우,* 서비스는 사실상 IETF(International Engineering Task Force)
[RFC(Request for Comment) 7159 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://tools.ietf.org/html/rfc7159#section-8.1){: new_window}의
8.1절에 따라 항상 UTF(Unicode Transformation Format)-8 문자 세트를 사용합니다. 

일반 텍스트 또는 HTML 컨텐츠를 제출하는 경우에는 `charset` 매개변수를 `Content-Type`
헤더에 포함하여 입력 텍스트의 문자 인코딩을 표시하십시오. 다음 예제는 일반 텍스트 입력에 대한 UTF-8 문자 인코딩을 지정합니다. 

```
Content-Type: text/plain;charset=utf-8
```
{: codeblock}

`charset` 매개변수를 사용하면 ASCII 이외의 문자나 인쇄 불가능한 문자와 연관된 잠재적 문제점을 피할 수 있습니다. 
문자 세트를 지정하지 않고 UTF-8 데이터를 전달하는 경우에는 특수 문자 때문에 잘못된 결과가 발생하거나
HTTP 4*nn* 또는 5*nn* 오류가 발생할 수 있습니다. 

### cURL 사용
{: #charsetCurl}

cURL 사용 시의 오류를 방지하려면, 컨텐츠에 대해 UTF-8 인코딩이 유지될 수 있도록 항상
`curl` 명령의 `--data-binary` 옵션을 통해 컨텐츠를 전달하십시오. 
`--data` 옵션을 사용하여 ASCII로서 컨텐츠를 전달하면 명령이 입력을
처리할 수 있으며, 이는 UTF-8로 인코딩된 데이터에 대해 문제점을 발생시킬 수 있습니다. 

예를 들어, 다음 `curl` 명령은 올바르게 `--data-binary` 옵션을 사용하여
추가적인 처리 없이 지정된 *filename*의 컨텐츠를 게시합니다. 또한 이 명령은 `Content-Type` 헤더의
`charset` 매개변수를 사용하며, 이는 기본 JSON 응답 형식을 명시적으로 요청합니다. 

```bash
curl -X POST --user {username}:{password}
--header "Content-Type: text/plain;charset=utf-8"
--header "Accept: application/json"
--data-binary @{filename}
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{: pre}

다양한 요청 및 응답 형식의 서비스 호출에 대한 추가적인 예제는
[시작하기 튜토리얼](/docs/services/personality-insights/getting-started.html)을 참조하십시오. 

## JSON 입력 지정
{: #json}

JSON 입력을 전달하려면 `Content` 오브젝트를 사용합니다. 
오브젝트에는 `ContentItem` 오브젝트의 배열이 포함되어 있으며, 각각에는 컨텐츠의 요소가 포함되어 있습니다. 
오브젝트의 유일한 필수 필드는 분석될 텍스트를 제공하는 `content`입니다. 기타 선택적 필드를 사용하여 다음을 지정할 수 있습니다. 

-   `id`(문자열)는 컨텐츠 항목의 고유 ID입니다. 
-   `created`(정수)는 컨텐츠 항목이 작성된 시점을 표시하는 UNIX 시간소인입니다. 
-   `updated`(정수)는 컨텐츠 항목이 마지막으로 업데이트된 시점을 표시하는 UNIX 시간소인입니다. 
-   `contenttype`(문자열)은 컨텐츠 항목의 유형(`text/plain` 또는 `text/html`)을 표시합니다. 
-   `language`(문자열)는 컨텐츠 항목의 언어(`ar`(아랍어), `en`(영어),
`es`(스페인어), `ja`(일본어) 또는 `ko`(한국어))를 표시합니다. 
[요청 및 응답 언어 지정](#languages)을 참조하십시오. 
-   `parentid`(문자열)는 컨텐츠 항목의 상위 항목의 `id`입니다. 
-   `reply`(부울)는 컨텐츠 항목이 다른 항목에 대한 응답인지 여부를 표시합니다. 
-   `forward`(부울)는 컨텐츠 항목이 다른 항목의 전달본 또는 사본인지 여부를 표시합니다. 

JSON 입력은 Twitter 또는 다중 대화나 포스트로 구성된 기타 소셜 네트워크의 컨텐츠에 매우 적합합니다. 
작성자의 모든 텍스트를 단일 문자열로 연결하는 대신, JSON을 사용하여 존재하는 데이터를 제출할 수 있습니다. 
여기에는 텍스트의 관련된 부분을 서비스가 알 수 있도록 허용하는 추가적인 장점이 있습니다. 

### 예제 JSON 입력
{: jsonExample}

[시작하기 튜토리얼](/docs/services/personality-insights/getting-started.html)의 예제에서는 샘플 JSON 파일
<a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="외부 링크 아이콘" title="외부 링크 아이콘" class="style-scope doc-content"></a>을 사용합니다. 
이 파일에는 일련의 Twitter 메시지가 포함되어 있습니다. 다음 예제에서는 파일의 처음 일부 트윗을 보여줍니다. 

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

## 요청 및 응답 언어 지정
{: #languages}

`Content-Language` 및 `Accept-Language` 헤더 매개변수를 사용하여 입력 컨텐츠의
언어와 서비스 응답의 언어를 표시할 수 있습니다. 요청과 응답에 대해 지원되는 언어를 임의로 조합하여 사용할 수 있습니다. 
언어를 명시하지 않은 경우, 서비스는 분석에 대해서는 영어 훈련 모델을 사용하며 해당 결과에 대해서는 영어를 사용합니다. 
다음 표에는 지원되는 입력 및 출력 언어가 나열되어 있으며 언어 관련 매개변수에서 사용할 수 있는 인수가 식별되어 있습니다. 

<table style="width:90%">
  <caption>표 2. 요청 및 응답 언어 지정</caption>
  <tr>
    <th style="width:28%; text-align:left; vertical-align:bottom">
      언어
    </th>
    <th style="width:12%; text-align:center; vertical-align:bottom">
      인수
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      지원 기준: <br/>
      <code>Content-Language</code>
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      지원 기준: <br/>
      <code>Accept-Language</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      아랍어
    </td>
    <td style="text-align:center">
      <code>ar</code>
    </td>
    <td style="text-align:center">
예</td>
    <td style="text-align:center">
예</td>
  </tr>
  <tr>
    <td style="text-align:left">
      영어
    </td>
    <td style="text-align:center">
      <code>en</code>
    </td>
    <td style="text-align:center">
      예</td>
    <td style="text-align:center">
예</td>
  </tr>
  <tr>
    <td style="text-align:left">
      일본어
    </td>
    <td style="text-align:center">
      <code>ja</code>
    </td>
    <td style="text-align:center">
예</td>
    <td style="text-align:center">
예</td>
  </tr>
  <tr>
    <td style="text-align:left">
      한국어
    </td>
    <td style="text-align:center">
      <code>ko</code>
    </td>
    <td style="text-align:center">
예</td>
    <td style="text-align:center">
예</td>
  </tr>
  <tr>
    <td style="text-align:left">
      스페인어
    </td>
    <td style="text-align:center">
      <code>es</code>
    </td>
    <td style="text-align:center">
예</td>
    <td style="text-align:center">
예</td>
  </tr>
  <tr>
    <td style="text-align:left">
      브라질 포르투갈어
    </td>
    <td style="text-align:center">
      <code>pt-br</code>
    </td>
    <td style="text-align:center">
아니오</td>
    <td style="text-align:center">
예</td>
  </tr>
  <tr>
    <td style="text-align:left">
      프랑스어
    </td>
    <td style="text-align:center">
      <code>fr</code>
    </td>
    <td style="text-align:center">
아니오</td>
    <td style="text-align:center">
예</td>
  </tr>
  <tr>
    <td style="text-align:left">
      독일어
    </td>
    <td style="text-align:center">
      <code>de</code>
    </td>
    <td style="text-align:center">
아니오</td>
    <td style="text-align:center">
예</td>
  </tr>
  <tr>
    <td style="text-align:left">
      이태리어
    </td>
    <td style="text-align:center">
      <code>it</code>
    </td>
    <td style="text-align:center">
아니오</td>
    <td style="text-align:center">
예</td>
  </tr>
  <tr>
    <td style="text-align:left">
      중국어
    </td>
    <td style="text-align:center">
      <code>zh-cn</code>
    </td>
    <td style="text-align:center">
아니오</td>
    <td style="text-align:center">
예</td>
  </tr>
  <tr>
    <td style="text-align:left">
      대만어
    </td>
    <td style="text-align:center">
      <code>zh-tw</code>
    </td>
    <td style="text-align:center">
아니오</td>
    <td style="text-align:center">
예</td>
  </tr>
</table>

모든 텍스트를 동일한 언어로 제출하십시오. 동일한 요청에 여러 언어를 혼합하지 마십시오. 
두 문자 언어 인수의 경우, 서비스는 지역적 변종을 상위 언어로 처리합니다.
예를 들어, 이는 `en-US`를 `en`으로 처리합니다. 

### JSON 컨텐츠에 대한 언어 지정
{: #languageJSON}

일반 텍스트 및 HTML 입력의 경우, `Content-Language` 헤더는 언어를 지정하는 유일한 방법입니다. 
JSON 입력의 경우, `ContentItem` 오브젝트의 `language` 매개변수를 사용하여
각각의 개별 컨텐츠 항목의 언어를 지정할 수도 있습니다. 그러나 `Content-Language` 헤더로 지정된 언어는
컨텐츠 항목에 대해 지정된 언어를 대체하며, 서비스는 다른 언어를 지정하는 컨텐츠 항목을 무시합니다. 

언어가 컨텐츠 항목의 스펙만을 기반으로 하도록 하려면 `Content-Type` 헤더를 생략하십시오. 
서비스는 컨텐츠 항목 중에서 가장 일반적인 언어를 사용하며, 이는 최상의 가능한 결과를 산출합니다. 
이는 각 언어에 대해 컨텐츠 항목의 수를 계수하며 빈도가 가장 높은 언어를 선택합니다. 
여러 언어의 최대 빈도가 동일한 경우, 서비스는 해당 값에 최초로 도달한 언어를 사용합니다. 
다시 말하지만, 서비스는 다른 언어를 지정하는 컨텐츠 항목을 무시합니다. 

### 언어 고려사항
{: #languageNotes}

입력 텍스트를 제출할 때는 다음을 고려하십시오. 

-   *영어의 경우,* 결과는 미국의 문화 규범을 기반으로 합니다. 
다른 문화에서 영어 텍스트를 분석하는 경우에는 알맞게 결과를 조정해야 할 수 있습니다. 
-   *아랍어의 경우,* 서비스는 성능상의 이유 때문에 일정 양의 입력 텍스트를 잘라낼 수 있습니다. 
특정 임계값에서, 아랍어 결과의 정확도는 단어를 추가해도 더 이상 높아지지 않습니다. 서비스가 아랍어 입력을 잘라내는 경우,
이는 경고 메시지를 리턴하여 프로파일에 사용된 입력 텍스트의 일정 양을 줄였음을 알립니다. 
-   *아랍어 및 한국어의 경우,* 서비스는 특성의 서브세트에 대해 의미 있는 결과를 리턴할 수 없습니다. 
자세한 정보는 [아랍어와 한국어 입력에 대한 제한사항](/docs/services/personality-insights/numeric.html#limitations)을 참조하십시오. 

번역된 텍스트 사용에 대한 일반 정보는 [번역된 텍스트에서 성격 추정](/docs/services/personality-insights/guidance.html#translation)을 참조하십시오. 

## 충분한 입력 제공
{: #sufficient}

의미 있는 성격 프로파일은 적절한 양과 품질의 충분한 데이터가 제공된 경우에만 작성될 수 있습니다. 
문서마다 그리고 시간마다 언어 사용이 자연히 다르므로, 작은 텍스트 샘플은 개인의 전체 언어 패턴을 대표할 수 없습니다. 
더구나 서로 다른 특성과 서로 다른 미디어는 다소 서로 다른 비율로 수렴됩니다. 

어느 정도까지는 단어를 추가하면 보다 나은 결과를 생성할 가능성이 많으며,
예상 결과와 작성자의 실제 점수 간의 편차를 줄임으로써 서비스의 정밀도를 개선시킵니다. 
최대 20MB의 입력 컨텐츠를 서비스를 전송할 수 있지만, 정확도는 약 3000개 단어의 입력에서 정체를 유지합니다.
컨텐츠를 추가해도 프로파일의 정확도는 더 이상 증가되지 않습니다. 따라서 서비스는 대량 요청에서
처음 250KB의 컨텐츠만 추출하여 사용하며 HTML 또는 JSON 마크업은 계수하지 않습니다. 

이 숫자는 정확한 단어 수로 맵핑되지 않으며, 이는 텍스트의 언어와 특성에 따라 달라집니다. 
예를 들어, 영어에서 평균 단어 길이는 4 - 5자 사이이므로 이 숫자는 약 50,000개의 단어를 제공하며,
이는 정확한 프로파일을 생성하기 위해 서비스에서 요구하는 단어보다 최소한 15배 이상의 단어입니다. 
긴 입력을 잘라냄으로써 서비스는 정밀도를 낮추지 않으면서도 응답 시간을 개선합니다. 
응답 JSON의 `word_count` 필드는
서비스가 요청에 대해 실제 사용하는 단어의 수를 표시하며, 이는 제출된 단어의 수보다 적을 수 있습니다. 

### 가이드라인 및 권장사항
{: #sufficientGuidelines}

다음 표에서는 서로 다른 입력 텍스트 양에 대한 두 개의 값을 보고합니다. 

-   입력으로 제공된 단어의 수를 기반으로 모든 특성 간의 *평균 MAE(Mean Absolute Error)*. 
MAE가 더 작을수록, 서비스의 결과가 실제 성격 테스트를 실시하여 작성자가 받은 점수에 더 근접합니다. 
-   모든 특성에서 추론된 점수와 실제 점수 간의 *평균 상관*. 
0.2를 초과하는 상관이 허용 가능하며 0.4를 초과하는 상관이 드물지만, 상관이 1에 근접할수록 예측이 개선됩니다. 

정보는 영어 데이터를 기반으로 하지만, 일반적인 가이드라인은 모든 언어에 적용됩니다. 
언어 특정 통계를 포함하여 평균 MAE 및 상관에 대한 자세한 정보는
[서비스의 정확도](/docs/services/personality-insights/science.html#researchPrecise)를 참조하십시오. 

<table style="width:80%">
  <caption>표 3. 평균 MAE 및 상관</caption>
  <tr>
    <th style="text-align:center; vertical-align:bottom; width:24%">단어 수</th>
    <th style="text-align:center; width:38%">평균 MAE<br/>(모든 특성에서)</th>
    <th style="text-align:center; width:38%">평균 상관<br/>(모든 특성에서)</th>
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

다음 가이드라인에서 제시하는 대로 {{site.data.keyword.IBM_notm}}은 최소한
1200개 단어를 제공하도록 권장하지만, 최소한 600개 단어를 제공해야 허용할 만한 결과가 나타납니다. 

-   3000개 단어는 서비스의 최대 정밀도를 얻기에 충분합니다. 
-   최소한 1200개 단어는 서비스가 리턴할 수 있는 최상의 MAE의 2퍼센트 내에 있는 MAE를 결과로 생성합니다. 
-   600 - 1200개 사이의 단어는 서비스가 리턴할 수 있는 최상의 MAE의 3퍼센트 내에 있는 MAE를 결과로 생성합니다. 
-   600개 미만의 단어는 경고를 생성하지만 서비스는 입력을 계속 분석합니다. 
-   100개 미만의 단어는 오류를 생성합니다. 

이러한 가이드라인은 애플리케이션에 대한 결과의 신뢰성을 수용하는 데 도움이 될 수 있습니다. 
예를 들어, 영화를 추천하는 일반 애플리케이션의 경우에는 정밀도가 낮아도 만족할 수 있습니다.
보다 중요한 추천을 하는 애플리케이션의 경우에는 보다 정확한 결과를 요구할 가능성이 큽니다. 
서비스가 성격 특성을 추론하는 방법에 대한 자세한 정보는
[성격 특성이 추론되는 방법](/docs/services/personality-insights/science.html#researchInfer)을 참조하십시오. 

## 원 점수 요청
{: #rawScores}

서비스는 응답의 일부로서 항상 각각의 성격 특성(빅 파이브 특질 및 성향, 욕구 및 가치)에 대해 정규화된 점수를 리턴합니다. 
`raw_scores` 조회 매개변수를 `true`로 설정하는 경우,
서비스는 각각의 특성에 대해 `raw_score`를 보고할 수도 있습니다. 
원 점수는 결과를 샘플 모집단과 비교하지 않고 해당 특성에 대한 모델과 작성자의 텍스트에만 기반하여 특성에 대한 점수를 표시합니다. 
원 점수 사용에 대한 자세한 정보는
[성격 특성에 대한 원 점수](/docs/services/personality-insights/numeric.html#rawScores)를 참조하십시오. 

## 소비 성향 요청
{: #preferences}

서비스는 항상 성격 모델에 대한 결과를 리턴합니다. `consumption_preferences`
조회 매개변수를 `true`로 설정하는 경우, 서비스는 입력 텍스트에서 추론된
성격 특성을 기반으로 다양한 소비 성향에 대한 `scores`도 리턴합니다. 
이러한 결과는 작성자가 서로 다른 제품, 서비스 및 활동을 선호할 경향을 표시합니다. 비즈니스는 이 결과를 사용하여
작성자의 성향을 보다 잘 파악할 수 있으며 작성자에 대한 커뮤니케이션과 오퍼링을 개인화할 수 있습니다. 

서로 다른 소비 성향에 대한 자세한 정보는 [소비 성향](/docs/services/personality-insights/preferences.html)을 참조하십시오. 
성향에 대한 숫자 결과의 해석에 대한 정보는 [소비 성향에 대한 점수](/docs/services/personality-insights/numeric.html#scores)를 참조하십시오. 

## 인터페이스 버전 지정
{: #version}

사용할 응답 형식과 서비스 API의 버전을 표시할 수 있도록 `/v3/profile` 메소드에 대한 모든 호출에는
`version` 조회 매개변수가 포함되어 있어야 합니다. `YYYY-MM-DD` 형식의 날짜로서
버전을 지정하십시오. 예를 들어, 2017년 10월 13일의 경우에는 `2017-10-13`을 지정하십시오. 
매개변수를 사용하여 서비스는 기존 클라이언트를 중단하지 않고도 새 버전에 대해 API 및 응답 형식을 업데이트할 수 있습니다. 

지정하는 날짜는 서비스의 버전과 정확히 일치하지 않아도 됩니다. 서비스는 늦어도 사용자가 제공하는 날짜까지의 버전을 사용합니다. 
버전 3의 초기 릴리스보다 이른 날짜를 지정하면 서비스는 API의 버전 3을 사용합니다. 
미래의 날짜를 지정하거나 아니면 가장 최신 버전 이후의 날짜를 지정하는 경우, 서비스는 최신 버전을 사용합니다.

