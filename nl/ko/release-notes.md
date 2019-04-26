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

# 릴리스 정보
{: #release-notes}

다음 절에는 {{site.data.keyword.personalityinsightsshort}} 서비스의 각 릴리스에 대해 포함된 새 기능과 변경사항이 문서화되어 있습니다. 달리 명시되지 않은 한 모든 변경사항은 이전 릴리스와 호환되며 모든 신규 및 기존애플리케이션에 자동으로 투명하게 제공됩니다.
{: shortdesc}

릴리스 정보에는 모든 최신 업데이트에 대한 *서비스 버전*과 *인터페이스 버전*이 문서화되어 있습니다. `version` 조회 매개변수에서 *인터페이스 버전*을 지정하면 해당 업데이트에서 사용 가능한 새 특성과 기능을 사용할 수 있습니다. 이 서비스는 `X-Service-Api-Version` 응답 헤더로 두 버전을 모두 리턴합니다.
{: note}

## 2018년 12월 21일
{: #December2018}

**서비스 버전** - `3.4.5`<br/> **인터페이스 버전** - `2017-10-13`

{{site.data.keyword.personalityinsightsshort}} API 버전 2가 서비스에서 제거되었습니다. 서비스의 버전 3은 2016년 10월 19일에 릴리스되었습니다. 그 당시 사용자에게 버전 2에서 최대한 빨리 마이그레이션할 것을 강력히 권장했습니다. 

## 2018년 11월 18일
{: #November2018b}

**서비스 버전** - `3.4.5`<br/> **인터페이스 버전** - `2017-10-13`

이제 {{site.data.keyword.personalityinsightsshort}} 서비스를 {{site.data.keyword.cloud}} 런던 위치(**eu-gb**)에서 이용할 수 있습니다. 모든 위치와 마찬가지로 런던도 토큰 기반의 Identity and Access Management(IAM) 인증을 사용합니다. 이 위치에서 생성한 모든 새 서비스 인스턴스는 IAM 인증을 사용합니다. 

## 2018년 11월 7일
{: #November2018a}

**서비스 버전** - `3.4.5`<br/> **인터페이스 버전** - `2017-10-13`

이제 {{site.data.keyword.personalityinsightsshort}} 서비스를 {{site.data.keyword.cloud_notm}} 도쿄 위치(**jp-tok**)에서 이용할 수 있습니다. 모든 위치와 마찬가지로 도쿄도 토큰 기반의 Identity and Access Management(IAM) 인증을 사용합니다. 이 위치에서 생성한 모든 새 서비스 인스턴스는 IAM 인증을 사용합니다. 

## 이전 릴리스
{: #older}

-   [2018년 10월 30일](#October2018)
-   [2018년 6월 11일](#June2018b)
-   [2018년 6월 4일](#June2018a)
-   [2018년 3월 23일](#March2018)
-   [2017년 10월 13일](#October2017)
-   [2017년 9월 18일](#September2017)
-   [2017년 4월 10일](#April2017)
-   [2017년 3월 1일](#March2017)
-   [2017년 2월 20일](#February2017b)
-   [2017년 2월 13일](#February2017)
-   [2017년 1월 13일](#January2017)
-   [2016년 12월 15일](#December2016)
-   [2016년 11월 15일](#November2016)
-   [2016년 10월 20일](#October2016b)
-   [2016년 10월 12일](#October2016a)
-   [2016년 8월 31일](#August2016)
-   [2016년 7월 14일](#July2016b)
-   [2016년 7월 1일](#July2016a)
-   [2016년 6월 7일](#June2016b)
-   [2016년 6월 1일](#June2016a)
-   [2016년 5얼 17일](#May2016)
-   [2016년 3월 18일](#March2016)
-   [2015년 7월 9일](#July2015)
-   [2015년 2월 23일](#February2015)

### 2018년 10월 30일
{: #October2018}

**서비스 버전** - `3.4.5`<br/> **인터페이스 버전** - `2017-10-13`

The {{site.data.keyword.personalityinsightsshort}} 서비스는 모든 위치에 대해 토큰 기반 Identity and Access Management (IAM) 인증으로 마이그레이션했습니다. 모든 {{site.data.keyword.cloud_notm}} 서비스는 이제 IAM 인증을 사용합니다. 각 위치에서 {{site.data.keyword.personalityinsightsshort}} 서비스가 다음 날짜에 마이그레이션되었습니다. 

-   달라스 (**us-south**): 2018년 10월 30일
-   프랑크프르트(**eu-de**): 2018년 10월 30일
-   워싱턴, DC (**us-east**): 2018년 6월 11일
-   시드니 (**au-syd**): 2018년 6월 4일

IAM 인증으로 마이그레이션은 신규 및 기존 서비스 인스턴스에 다르게 영향을 줍니다. 

-   *모든 위치에서 작성된 모든 새 서비스 인스턴스*는 이제 IAM 인증을 사용하여 서비스에 액세스합니다. 베어러 토큰 또는 API 키를 전달할 수 있습니다. 토큰은 모든 호출에 서비스 인증 정보를 포함하지 않고 인증된 요청을 지원합니다. API 키는 HTTP 기본 인증을 사용합니다. {{site.data.keyword.watson}} SDK 중 하나를 사용할 때 API 키를 전달하고 SDK가 토큰의 라이프사이클을 관리하도록 할 수 있습니다. 
-   *표시된 마이그레이션 날짜 이전에 위치에서 생성한 기존 서비스 인스턴스*는 IAM 인증을 사용하도록 업데이트할 때까지 인증에 대한 이전 Cloud Foundry 서비스 인증 정보에서 `{username}` 및 `{password}`를 계속 사용합니다. {{site.data.keyword.personalityinsightsshort}} 서비스는 상태 비저장(Stateless) 방식이기 때문에 다음 단계를 수행하여 기존 서비스 인스턴스 변환을 통해 IAM 인증을 사용할 수 있습니다. 

    1.  서비스 인스턴스를 삭제하고 다시 작성하십시오.
    1.  IAM 인증을 사용하도록 애플리케이션 코드를 수정하십시오.

자세한 정보는 다음 문서를 참조하십시오. 

-   서비스 인스턴스가 사용하는 인증 메커니즘을 확인하려면 [{{site.data.keyword.cloud_notm}} 대시보드 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/dashboard/apps){: new_window}에서 인스턴스를 클릭하여 서비스 인증 정보를 보십시오. 
-   Watson 서비스에서 IAM 토큰 사용에 대한 자세한 정보는 [IAM 토큰으로 인증](/docs/services/watson?topic=watson-iam)을 참조하십시오. 
-   Watson 서비스에서 IAM API 키 사용에 관한 자세한 정보는 [IAM 서비스 API키](/docs/services/watson?topic=watson-api-key-bp)를 참조하십시오. 
-   IAM 인증 사용의 예제는 [API 참조서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/apidocs/personality-insights){: new_window}를 참조하십시오. 

### 2018년 6월 11일
{: #June2018b}

**서비스 버전** - `3.4.5`<br/> **인터페이스 버전** - `2017-10-13`

워싱턴, DC (**us-east**)에서 호스팅되는 서비스 인스턴스 및 애플리케이션의 경우, 이제 새로운 API 인증 프로세스를 지원합니다. 자세한 정보는 [2018년 10월 30일 서비스 업데이트](#October2018)를 참조하십시오.

### 2018년 6월 4일
{: #June2018a}

**서비스 버전** - `3.4.5`<br/> **인터페이스 버전** - `2017-10-13`

시드니(**au-syd**)에서 호스팅되는 서비스 인스턴스 및 애플리케이션의 경우, 이제 새로운 API 인증 프로세스를 지원합니다. 자세한 정보는 [2018년 10월 30일 서비스 업데이트](#October2018)를 참조하십시오.

### 2018년 3월 23일
{: #March2018}

**서비스 버전** - `3.4.4`<br/> **인터페이스 버전** - `2017-10-13`

-   서비스가 사소한 결함 수정사항으로 업데이트되었습니다. 변경은 아랍어, 일본어, 한국어에만 국한되었습니다. 
-   이제 `Accept` 요청 헤더는 `POST /v3/profile` 메소드가 필요합니다. `application/json` 또는 `text/csv`중 하나를 지정해야 합니다. 

### 2017년 10월 13일
{: #October2017}

**서비스 버전** - `3.4.0`<br/> **인터페이스 버전** - `2017-10-13`

-   성격 프로파일의 `Trait` 오브젝트에 이제 `significant` 필드가 포함되었습니다. 개별 `Trait` 오브젝트는 각각의 빅 파이브 특질, 빅 파이브 성향, 욕구 및 가치에 대한 결과를 보고합니다. 오브젝트의 각 인스턴스의 `significant` 필드는 특성에 대한 결과가 요청의 입력 언어(`Content-Language`)에 대해 의미가 있는지 여부를 식별합니다. 

    -   영어, 스페인어 및 일본어의 경우, 모든 성격 특성에 대해 이 필드는 항상 `true`입니다.
    -   아랍어 및 한국어의 경우, 이 필드는 대부분의 성격 특성에 대해 `true`이지만 서비스의 모델이 의미 있는 결과를 생성할 수 없는 경우에 대해서는 `false`입니다. 이 필드는 상수 특성 세트에 대해 `false`입니다. 전체 목록은 [아랍어와 한국어 입력 제한사항](/docs/services/personality-insights?topic=personality-insights-numeric#limitations)을 참조하십시오. 이 필드가 `false`인 특성에 대해서는 결과를 신뢰하지 마십시오.

서비스의 JSON 응답 컨텐츠에 대한 자세한 정보는 [JSON 프로파일 이해](/docs/services/personality-insights?topic=personality-insights-output)를 참조하십시오.
-   또한 이제, CSV 결과에는 표제가 `*_significant`로 이름 지정된 열이 포함되어 있습니다. 각각의 열은 특성이 의미 있는지 여부를 표시하는 부울 값을 제공합니다. 서비스의 CSV 응답 컨텐츠에 대한 자세한 정보는 [CSV 프로파일 이해](/docs/services/personality-insights?topic=personality-insights-outputCSV)를 참조하십시오. 
-   최신 버전의 인터페이스를 사용하려면 `version` 매개변수에 인터페이스 버전 `2017-10-13`을 지정하십시오. 

### 2017년 9월 18일
{: #September2017}

**서비스 버전** - `3.3.0`<br/> **인터페이스 버전** - `2016-10-19`

서비스는 이제 한국어(`ko`)의 입력 컨텐츠를 지원합니다. 한국어 입력에 대한 평균 MAE(Mean Absolute Error) 및 평균 상관에 대한 자세한 정보는 [언어별 평균 MAE 및 상관](/docs/services/personality-insights?topic=personality-insights-science#precisePerLanguage)을 참조하십시오. 

서비스의 모델은 한국어 입력의 일부 성격 특성에 대해 의미 있는 백분위수와 원 점수를 생성할 수 없습니다. 이러한 특성에 대한 결과와 관련된 자세한 정보는 [아랍어와 한국어 입력에 대한 제한사항](/docs/services/personality-insights?topic=personality-insights-numeric#limitations)을 참조하십시오.

### 2017년 4월 10일
{: #April2017}

**서비스 버전** - `3.1.7`<br/> **인터페이스 버전** - `2016-10-19`

-   서비스가 많은 양의 입력 컨텐츠가 있는 요청을 처리하는 방법을 변경했습니다. 서비스는 최대 20MB의 컨텐츠를 허용합니다. 그러나 *GloVe* 기반 모델에서 정확도는 약 3000개 단어의 입력에서 안정을 유지합니다. 이 동작은 텍스트가 추가되면 정확도가 증가되는 이전 모델과는 다른 양상입니다. 일반적으로, 서비스는 정확한 프로파일을 생성하기 위해 더 이상 많은 컨텐츠를 요구하지 않습니다. 그러나 컨텐츠를 추가하면 처리 시간이 더 많이 필요하며, 따라서 완료 전에 요청의 제한시간이 초과될 수 있습니다. 

    따라서 서비스는 이제 대량 요청에서 처음 250KB의 컨텐츠만 추출하여 사용하며 HTML 또는 JSON 마크업은 계수하지 않습니다. 이 숫자는 정확한 단어 수로 맵핑되지 않으며, 이는 텍스트의 언어와 특성에 따라 달라집니다. 예를 들어, 영어에서 평균 단어 길이는 4 - 5자 사이이므로 이 숫자는 약 50,000개의 단어를 제공하며, 이는 서비스에서 요구하는 단어보다 최소한 15배 이상입니다. 응답 JSON의 `word_count` 필드는 서비스가 요청에 대해 사용하는 단어의 수를 표시하며, 이는 입력의 단어 수보다 적을 수 있습니다. 

    아직까지 이는 최대 정확도를 위해 엄격히 요구되는 것보다 더 많은 단어에 프로파일의 기반을 두고 있으므로, 서비스는 이전과 같이 정확한 프로파일을 생성합니다. 그러나 서비스는 이전보다 훨씬 더 빠르게 응답합니다. 입력 컨텐츠 중 일부만 사용하는 요청의 경우, 서비스는 사용자가 해당 사실을 인식할 수 있도록 다음의 `CONTENT_TRUNCATED` 경고 메시지를 리턴합니다.

    `처리 시간도 최적화하면서 최대 정확도를 유지하기 위해, 입력 텍스트의 처음 250KB만 분석되었습니다(마크업 제외). 정확도가 약 3K 단어에서 안정을 유지하므로, 이는 프로파일의 정확도에 영향을 주지 않았습니다. `

자세한 정보는 [충분한 입력 제공](/docs/services/personality-insights?topic=personality-insights-input#sufficient)을 참조하십시오.
-   서비스가 사소한 보안 수정사항으로 업데이트되었습니다.

### 2017년 3월 1일
{: #March2017}

**서비스 버전** - `3.1.6`<br/> **인터페이스 버전** - `2016-10-19`

서비스가 로깅에 대한 사소한 개선사항으로 업데이트되었습니다. 

### 2017년 2월 20일
{: #February2017b}

**서비스 버전** - `3.1.5.1`<br/> **인터페이스 버전** - `2016-10-19`

서비스가 사소한 보안 및 결함 수정사항으로 업데이트되었으며, API 호출의 미터링이 개선되었습니다. 

### 2017년 2월 13일
{: #February2017}

**서비스 버전** - `3.1.4`<br/> **인터페이스 버전** - `2016-10-19`

-   소비 성향 목록이 세부 조정되었습니다. 목록에는 이제 개인의 주요 생활 습관 및 소비 특성을 파악하는 데 가장 중요한 성향만 포함됩니다. 소비 성향 목록이 51개에서 42개로 줄었습니다. 나머지 성향은 다양한 제품, 서비스 및 활동을 선호할 작성자의 가능성을 더욱 간결하게 표현하여 결과에 따라 조치를 취하기 훨씬 더 쉬워집니다.  

    서비스는 더 이상 다음의 9개 소비 성향을 리턴하지 않습니다: 

    -   <code>consumption_preferences_shopping</code> 범주는 더 이상 다음을 포함하지 않습니다. 
        -   <code>consumption_preferences_automobile_resale_value</code>
    -   <code>consumption_preferences_reading</code> 범주는 더 이상 다음을 포함하지 않습니다. 
        -   <code>consumption_preferences_read_motive_enjoyment</code><br/>
        -   <code>consumption_preferences_read_motive_information</code><br/>
        -   <code>consumption_preferences_read_motive_mandatory</code><br/>
        -   <code>consumption_preferences_read_motive_relaxation</code>
    -   <code>consumption_preferences_health_and_activity</code> 범주는 더 이상 다음을 포함하지 않습니다. 
        -   <code>consumption_preferences_adventurous_sports</code>
        -   <code>consumption_preferences_fast_food_frequency</code>
    -   <code>consumption_preferences_volunteering</code> 범주는 더 이상 다음을 포함하지 않습니다. 
        -   <code>consumption_preferences_volunteering_time</code>
        -   <code>consumption_preferences_volunteer_learning</code>

나머지 성향에 대한 자세한 정보는 [소비 성향](/docs/services/personality-insights?topic=personality-insights-preferences)을 참조하십시오.
-   *아랍어 입력의 경우*, 평균 MAE(Mean Absolute Error) 및 평균 상관에 대한 정보는 이제 [언어별 평균 MAE 및 상관](/docs/services/personality-insights?topic=personality-insights-science#precisePerLanguage)에서 사용 가능합니다. 또한 서비스의 모델은 성격 특성의 콜렉션에 대해 의미 있는 백분위수와 원 점수를 생성할 수 없습니다. 이러한 특성에 대한 결과와 관련된 자세한 정보는 [아랍어와 한국어 입력에 대한 제한사항](/docs/services/personality-insights?topic=personality-insights-numeric#limitations)을 참조하십시오.

### 2017년 1월 13일
{: #January2017}

**서비스 버전** - `3.1.2.1`<br/> **인터페이스 버전** - `2016-10-19`

Personality Insights가 약간의 사소한 결함 수정사항으로 업데이트되었습니다.

### 2016년 12월 15일
{: #December2016}

**서비스 버전** - `3.1.1`<br/> **인터페이스 버전** - `2016-10-19`

아랍어 입력의 경우, {{site.data.keyword.personalityinsightsshort}} 서비스는 이제 *GloVe*를 사용하여 성격 프로파일을 개발합니다. 서비스는 어떤 언어에 대해서도 더 이상 LIWC(Linguistic Inquiry and Word Count) 심리언어학 사전을 사용하지 않습니다.서비스가 성격상을 개발하는 방법에 대한 자세한 정보는 [성격 특성이 추론되는 방법](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)을 참조하십시오.

### 2016년 11월 15일
{: #November2016}

**서비스 버전** - `3.1.0`<br/> **인터페이스 버전** - `2016-10-19`

-   일본어 입력의 경우, {{site.data.keyword.personalityinsightsshort}} 서비스는 이제 *GloVe*를 사용하여 성격 프로파일을 개발합니다. 서비스는 일본어 입력에 대해서 더 이상 LIWC(Linguistic Inquiry and Word Count) 심리언어학 사전을 사용하지 않습니다. 자세한 정보는 [성격 특성이 추론되는 방법](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)을 참조하십시오.
-   `ConsumptionPreferencesCategory` 및 `ConsumptionPreferences` 오브젝트의 `name` 필드는 이제`Accept-Language` 요청 헤더에서 지정된 언어의 현지화된 문자열로 리턴됩니다. 
-   업데이트에는 약간의 사소한 결함 수정사항이 포함되어 있습니다.

### 2016년 10월 20일
{: #October2016b}

**서비스 버전** - `3.0.0`<br/> **인터페이스 버전** - `2016-10-19`

{{site.data.keyword.personalityinsightsshort}} 서비스 및 해당 API가 상당히 업데이트되었습니다. API가 버전 2에서 버전 3으로 올라갔으며 새 기능을 제공합니다. 이 릴리스 정보의 나머지 절에서는 변경사항을 자세히 설명합니다.

버전 3은 버전 2와 호환이 가능하지 않습니다. 새 기능과 변경사항을 활용하려면 버전 3으로 마이그레이션하도록 권장합니다. 버전 3으로의 마이그레이션은 새 버전에 대해 이 릴리스 정보에서 설명한 변경사항을 사용할 수 있도록 애플리케이션 업데이트와 재배치로만 이루어져 있습니다. {{site.data.keyword.cloud_notm}}에서 서비스의 새 인스턴스를 작성할 필요는 없습니다. `v3` API 호출만 필요합니다. 

{{site.data.keyword.personalityinsightsshort}} API 버전 2가 서비스에서 곧 제거됩니다. 가급적이면 빠른 시간 내에 버전 3으로 마이그레이션하도록 적극 권장합니다.
{: note}

#### 버전 3에 대한 자세한 정보

이 문서에서는 이제 {{site.data.keyword.personalityinsightsshort}} API의 버전 3에 대해 설명합니다. 다음 절에는 인터페이스의 새 버전에 대한 변경사항이 요약되어 있습니다.

-   `/v3/profile` 메소드 호출에 대한 자세한 정보는 [프로파일 요청](/docs/services/personality-insights?topic=personality-insights-input)을 참조하십시오. 
-   `/v3/profile` 메소드의 응답에 대한 자세한 정보는 [JSON 프로파일 이해하기](/docs/services/personality-insights?topic=personality-insights-output) 및 [CSV 프로파일 이해하기](/docs/services/personality-insights?topic=personality-insights-outputCSV)를 참조하십시오. 
-   버전 3 인터페이스에 대한 자세한 정보는 [API 참조서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/apidocs/personality-insights){: new_window}를 참조하십시오. 

#### <code>/v3/profile</code> 메소드의 매개변수에 대한 변경사항

`/v3/profile` 메소드의 매개변수가 변경되었습니다. 

-   API는 이제 `consumption_preferences`로 이름 지정된 선택적 조회 매개변수를 제공합니다. 이 매개변수는 소비 성향에 대해 추론된 정보가 결과와 함께 리턴되는지 여부를 표시하는 부울 값을 허용합니다. 기본적으로, 해당 정보는 응답에 포함되지 않습니다. 자세한 정보는 [새 소비 성향 기능](#cp)을 참조하십시오.
-   API에는 이제 `version` 필수 조회 매개변수가 포함됩니다. 매개변수는 API 및 응답 형식의 요청된 버전을 식별하는 문자열을 `YYYY-MM-DD` 양식의 날짜로서 허용합니다. 예를 들어, 2016년 10월 19일의 경우에는 `2016-10-19`를 지정하십시오. 이 매개변수를 사용하여 서비스는 기존 클라이언트를 중단하지 않고 새 버전에 대해 자체 API 또는 응답 형식을 업데이트할 수 있습니다. API의 버전 3의 초기 문자열은 `2016-10-19`입니다.

    지정하는 날짜는 서비스 버전과 정확히 일치하지 않아도 됩니다. 서비스는 사용자가 제공하는 날짜 이후 버전을 사용합니다. 버전 3의 릴리스 날짜보다 이른 날짜를 지정하면 서비스는 API의 버전 3을 사용합니다. 미래의 날짜를 지정하거나 아니면 가장 최신 버전 이후의 날짜를 지정하는 경우, 서비스는 최신 버전을 사용합니다.
-   `include_raw` 조회 매개변수의 이름은 이제 `raw_scores`입니다.
-   `headers` 조회 매개변수의 이름은 이제 `csv_headers`입니다.

#### 새 소비 성향 기능
{: #cp}

소비 성향 기능은 서로 다른 소비자 성향을 드러내는 작성자의 경향에 대한 표시를 제공합니다. `true` 값의 `consumption_preferences` 조회 매개변수를 `/v3/profile` 메소드에 전달하는 경우, 서비스는 `Profile` 오브젝트와 함께 추가 결과를 리턴합니다. 

-   `ConsumptionPreferencesCategory` 오브젝트의 배열을 제공하는 `consumption_preferences` 필드.
-   각 `ConsumptionPreferencesCategory` 오브젝트에는 다음 필드가 포함됩니다.
    -   `consumption_preference_category_id`: 소비 성향 범주 중 하나의 ID.
    -   `name`: 사용자에게 보이는 범주의 이름.
    -   `consumption_preferences`: 범주의 개별 성향에 대한 입력 텍스트에서 추론된 결과를 제공하는 `ConsumptionPreferences` 오브젝트의 배열. 
-   각 `ConsumptionPreferences` 오브젝트에는 다음 필드가 포함됩니다.
    -   `consumption_preference_id`: 소비 성향 중 하나의 ID,
    -   `name`: 사용자에게 보이는 소비 성향의 이름.
    -   `score`: 소비 성향에 대한 점수: 

        -   `0.0`은 가능성 없음을 나타냅니다. 
        -   `0.5`은 중립을 나타냅니다. 
        -   `1.0`은 가능성이 많음을 나타냅니다. 

        일부 성향의 경우 점수는 2진이며 중립 값을 허용하지 않습니다. 점수는 정규화된 백분위수가 아니라 입력 텍스트에서 추론된 결과를 기반으로 하는 성향의 표시입니다. 

소비 성향에 대한 자세한 정보는 [소비 성향](/docs/services/personality-insights?topic=personality-insights-preferences)을 참조하십시오.

두 소비 성향 오브젝트에 대한 `name` 필드는 `Accept-Language` 요청 헤더에서 지정된 언어와는 무관하게 항상 영어로 리턴됩니다.
{: note}

#### JSON 오브젝트 및 필드에 대한 변경사항

JSON 입력 및 결과 오브젝트와 해당 필드가 단순화되고 명료화되었습니다. 

-   요청으로 `/v3/profile` 메소드에 전달할 수 있는 JSON `ContentItem` 오브젝트에서 다음 필드가 제거되었습니다. 
    -   `userid`
    -   `sourceid`
    -   `charset`(이미 더 이상 사용되지 않음)

    사용자는 `Content` 오브젝트의 `contentItems` 배열의 요소로서 JSON 요청의 본문에서 이러한 오브젝트를 전달합니다.
-   `/v3/profile` 메소드가 리턴한 JSON `Profile` 오브젝트의 다음 필드가 변경되었습니다. 
    -   다음 필드가 제거되었습니다. 
        -   `id`
        -   `source`
    -   `tree` 필드가 제거되었습니다. 이는 4개의 새 필드로 대체되었습니다.
        -   `personality`: 빅 파이브 성격 특성의 경우
        -   `needs`: 욕구 특성의 경우
        -   `values`: 가치 특성의 경우
        -   `behavior`: 요일 및 일중 시간에 컨텐츠의 배포에 대한 시간 결과의 경우. 이 필드는 시간소인이 있는 JSON 입력의 경우에만 리턴됩니다.

    이 변경사항은 JSON `Profile` 오브젝트에서 효과적으로 결과를 한 레벨 높게 이동시키며, 반복의 레벨을 제거시킵니다.
    -   `processed_lang` 필드의 이름은 이제 `processed_language`입니다.
-   `/v3/profile` 메소드에 의해 리턴된 JSON `Trait` 오브젝트의 다음 필드는 이름이 변경되었습니다. 
    -   JSON `Trait` 오브젝트의 `id` 필드의 이름은 이제 `trait_id`입니다.
    -   JSON `Trait` 오브젝트의 `percentage` 필드의 이름은 이제 `percentile`입니다.
-   `/v3/profile` 메소드에 의해 리턴된 JSON `Trait` 오브젝트의 다음 필드는 제거되었습니다. 
    -   `sampling_error`
    -   `raw_sampling_error`

    서비스는 이제 결과의 정밀도를 보장하는 평균 MAE(Mean Absolute Error)를 보고합니다. 서로 다른 양의 입력 텍스트에 대한 MAE와 관련된 자세한 정보는 [충분한 입력 제공](/docs/services/personality-insights?topic=personality-insights-input#sufficient)을 참조하십시오.
-   JSON `Trait` 오브젝트는 `Profile` 오브젝트의 `personality`, `needs` 및 `values` 필드에 대해 계속 리턴됩니다. 그러나 `behavior` 필드는 다음 필드가 있는 `Behavior`로 이름 지정된 JSON 오브젝트의 배열을 리턴합니다. 
    -   `trait_id`
    -   `이름`
    -   `category`
    -   `percentage`

    또한 행동 정보는 더 이상 값의 트리로서 리턴되지 않습니다. 결과는 모든 시간 특성(요일 및 일중 시간)을 나열하는 단일 배열로 구성되어 있습니다.
-   `/v3/profile` 메소드가 리턴할 수 있는 JSON `Warnings` 오브젝트의 `id` 필드의 이름은 이제 `warnings_id`입니다.

#### JSON ID에 대한 변경사항
{: #ids}

새 `Behavior` 오브젝트 및 `Trait`의 `trait_id`(이전의 `id`) 필드에 대해 서비스가 리턴하는 JSON ID가 변경되었습니다. 

-   빅 파이브 특질에 대한 ID는 이제 문자열 `big5_`로 시작합니다.
-   빅 파이브 성향에 대한 ID는 이제 문자열 `facet_`로 시작합니다.
-   욕구에 대한 ID는 이제 문자열 `need_`로 시작합니다.
-   가치에 대한 ID는 이제 문자열 `value_`로 시작합니다.
-   모든 시간 특성에 대한 ID는 이제 문자열 `behavior_`로 시작합니다.
-   이제 일중 시간과 관련된 시간 특성의 ID가 12시간의 시간 형식(예: `0:00 am`)이 아닌 4자리의 24시간의 시간 형식(예: `behavior_0000`)을 사용합니다. 
-   모든 문자는 이제 소문자입니다.
-   공백 및 하이픈은 이제 밑줄입니다.

#### CSV 헤더에 대한 변경사항
{: #headers}

CSV 결과에 대해 서비스가 리턴할 수 있는 선택적 열 헤더가 변경되었습니다. 

-   JSON 결과의 `trait_id`에 대해 기술된 모든 변경사항은 CSV 헤더에도 적용됩니다. 
-   빅 파이브 특질에 대한 원 점수의 헤더는 이제 문자열 `big5_`로 시작합니다.
-   빅 파이브 성향에 대한 원 점수의 헤더는 이제 문자열 `facet_`로 시작합니다.
-   욕구에 대한 원 점수의 헤더는 이제 문자열 `need_`로 시작합니다.
-   가치에 대한 원 점수의 헤더는 이제 문자열 `value_`로 시작합니다.
-   처리된 언어 열의 헤더가 이제 `processed_lang`이 아닌 `processed_language`입니다.
-   `user` 및 `source_id` 열은 더 이상 리턴되지 않습니다.
-   모든 문자는 이제 소문자입니다.
-   공백 및 하이픈은 이제 밑줄입니다.

#### <code>visualize</code> 메소드의 제거

서비스의 API의 버전 2에 `/v3/profile` 메소드에 대한 호출의 결과를 시각화하기 위해 이전 릴리스에서 사용되었던 더 이상 사용되지 않는 `visualize` 메소드가 포함되어 있습니다. `visualize` 메소드는 서비스의 API에서 제거되었습니다. 이 서비스는 프로파일의 그래픽 시각화를 가능하게 하는 Javascript 파일의 콜렉션을 계속해서 제공합니다. 자세한 정보는 [프로파일 시각화](/docs/services/personality-insights?topic=personality-insights-overviewDevelopers#visualize)를 참조하십시오. 

### 2016년 10월 12일
{: #October2016a}

스페인어 입력의 경우, {{site.data.keyword.personalityinsightsshort}} 서비스는 이제 *GloVe*를 사용하여 성격 프로파일을 개발합니다. 서비스는 스페인어 입력에 대해서 더 이상 LIWC(Linguistic Inquiry and Word Count) 심리언어학 사전을 사용하지 않습니다. 서비스는 8월 31일에 영어 입력 텍스트에 대한 새 모델을 사용하기 시작했습니다. 머지 않아 나머지 입력 언어에 새 모델을 적용할 계획입니다. 새 모델에 대한 자세한 정보는 [성격 특성이 추론되는 방법](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)을 참조하십시오.

### 2016년 8월 31일
{: #August2016}

서비스는 이제 *GloVe*를 사용하여 성격 프로파일을 개발합니다. *GloVe*는 오픈 소스 단어 임베딩 기술입니다. 자세한 정보는 [성격 특성이 추론되는 방법](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)을 참조하십시오. 서비스는 영어 입력 텍스트에 대해서만 새 접근 방법을 사용합니다. 기타 언어의 경우, 서비스는 계속해서 LIWC(Linguistic Inquiry and Word Count) 심리언어학 사전을 사용합니다. 이 서비스는 앞으로 모든 언어에 대해 오픈 어휘 접근 방식을 사용할 계획입니다. 

영어 입력에 사용되는 새 모델의 경우, 서비스는 자체 훈련된 모델에 대해 결과의 평균 MAE(Mean Absolute Error)를 보고합니다. 서로 다른 양의 입력 텍스트로 MAE가 변경되는 방법에 대한 자세한 정보는 [충분한 입력 제공](/docs/services/personality-insights?topic=personality-insights-input#sufficient)을 참조하십시오. 

{{site.data.keyword.IBM_notm}}은 앞으로 영어 이외의 모델에 대해서는 MAE를 보고할 계획입니다. {{site.data.keyword.IBM_notm}}은 사용자가 제공하는 입력 텍스트의 양에 따라 서비스의 정밀도가 어떻게 변화하는지 판별하기 위해 샘플링 오류 대신 MAE를 사용할 계획입니다. 

### 2016년 7월 14일
{: #July2016b}

-   아랍어 입력의 경우, 서비스는 이제 성능상의 이유 때문에 일정 양의 입력 텍스트를 잘라낼 수 있습니다. 특정 임계값에서, 아랍어에 대한 결과의 정확도는 단어를 추가해도 더 이상 높아지지 않습니다. 서비스가 아랍어 입력 텍스트를 잘라내는 경우, 이는 다음 메시지와 함께 `PARTIAL_TEXT_USED` 경고를 리턴합니다.

    `성능상의 이유 때문에 프로파일을 계산하기 위해 제공된 텍스트가 잘렸습니다. 모든 입력 텍스트가 필요하지는 않으므로, 이 조치는 결과의 정확도에 영향을 주지 않습니다. `
-   업데이트에는 결함 수정사항 및 내부 개선사항이 포함되어 있습니다. 

### 2016년 7월 1일
{: #July2016a}

-   이제 서비스 가격 플랜은 {{site.data.keyword.personalityinsightsshort}} 사용자를 위해 더 낮은 가격을 제공합니다. 자세한 정보는 [{{site.data.keyword.cloud_notm}} 카탈로그의 {{site.data.keyword.personalityinsightsshort}} 서비스 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/catalog/services/personality-insights/){: new_window}를 참조하십시오.
-   `Accept-Language` 헤더로 지정될 수 있는 지원되는 응답 언어의 목록에는 이제 다음이 포함됩니다. 
    -   `ar`(아랍어)
    -   `de`(독일어)
    -   `en`(영어, 기본값)
    -   `es`(스페인어)
    -   `fr`(프랑스어)
    -   `it`(이태리어)
    -   `ja`(일본어)
    -   `ko`(한국어)
    -   `pt-br`(브라질 포르투갈어)
    -   `zh-cn`(중국어)
    -   `zh-tw`(대만어)

자세한 정보는 [요청 및 응답 언어 지정](/docs/services/personality-insights?topic=personality-insights-input#languages-input)을 참조하십시오.
-   `/v2/profile` 메소드는 이제 다음의 HTTP 상태 코드를 리턴합니다.
    -   429 *너무 많은 요청*: 서비스가 컨텐츠 언어에 대해 너무 많은 요청을 처리 중입니다. 잠시 대기한 후에 다시 요청을 시도하십시오. 언어에 대해 많은 요청을 제출 중인 경우에는 요청을 제출하는 속도를 조절하는 것을 고려하십시오.
    -   504 *게이트웨이 제한시간 초과*: 요청 제한시간이 초과되었거나 처리에 너무 많은 시간이 걸렸습니다. 잠시 대기한 후에 다시 요청을 시도하십시오. 입력에 너무 많은 수의 단어가 포함된 경우(예: 20,000개 초과), 의미 있는 입력에 대한 가이드라인을 준수하면서 단어의 수를 줄이는 것을 고려하십시오. 

    메소드는 더 이상 503 *사용 불가능한 서비스*를 리턴하지 않습니다. 가능한 응답 코드에 대한 자세한 정보는 [API 참조서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/apidocs/personality-insights){: new_window}를 참조하십시오.
-   업데이트에는 결함 수정사항 및 내부 개선사항이 포함되어 있습니다. 

### 2016년 6월 7일
{: #June2016b}

-   서비스는 이제 브라우저 기반 클라이언트가 서비스를 직접 호출할 수 있도록 CORS(Cross-Origin Resource Sharing)를 지원합니다. 자세한 정보는 [CORS 지원](/docs/services/personality-insights?topic=personality-insights-overviewDevelopers#CORS)을 참조하십시오.
-   일본어 텍스트에 대한 서비스의 성능이 상당히 개선되었습니다. 
-   업데이트에는 결함 수정사항 및 내부 개선사항이 포함되어 있습니다. 

### 2016년 6월 1일
{: #June2016a}

서비스가 결함 수정사항 및 내부 개선사항을 위해 업데이트되었습니다. 새로운 최상위 레벨 필드인 `warnings`가 서비스에서 리턴하는 JSON 결과에 추가되었습니다. 자세한 정보는 [API 참조서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/apidocs/personality-insights){: new_window}를 참조하십시오.


### 2016년 5얼 17일
{: #May2016}

서비스가 결함 수정사항 및 내부 개선사항을 위해 업데이트되었습니다. 

### 2016년 3월 18일
{: #March2016}

서비스는 이제 다음 언어를 지원합니다.

-   서비스가 지원하는 4개 언어의 입력 텍스트: 아랍어(`ar`), 영어(`en`), 스페인어(`es`) 및 일본어(`ja`). 언어를 지정하려면 일반 텍스트 및 HTML 입력에 대해 HTTP `Content-Language` 헤더를 사용하거나, JSON 입력에 대해 `ContentItem` 오브젝트의 `language` 특성을 사용하십시오.
-   서비스는 4개 해당 언어의 응답을 지원합니다. 응답의 언어를 지정하려면 `Accept-Language` 헤더를 사용하십시오.

입력과 응답에 대한 언어를 임의로 조합하여 사용할 수 있습니다. 언어를 표시하지 않으면 서비스의 기본 언어는 영어입니다. 자세한 정보는 [요청 및 응답 언어 지정](/docs/services/personality-insights?topic=personality-insights-input#languages-input)을 참조하십시오. 블로그 게시물 [{{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.personalityinsightsshort}}에 대해 이제 아랍어 및 일본어 지원이 사용 가능함 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/blogs/watson/2016/04/arabic-japanese-support-now-available-ibm-watson-personality-insights/){: new_window}도 참조하십시오. 

기타 언어보다 분석하는 데 훨씬 더 많은 컴퓨팅 사이클이 필요하므로, 아랍어 컨텐츠는 처리하는 데 상당히 더 오래 걸립니다. 서비스가 모든 언어에 대해 입력 텍스트의 양에서 동일한 20MB 한계를 지원하지만, 제한시간 초과를 피하기 위해 아랍어 컨텐츠에 대한 실제 한계는 더 낮을 수 있습니다. 일본어 컨텐츠도 처리하는 데 더 오랜 시간이 걸리지만, 아랍어의 경우보다는 지연이 덜 유의미한 중요성을 갖습니다.
{: note}

### 2015년 7월 9일
{: #July2015}

-   *언어 지원.* 영어와 스페인어 컨텐츠를 모두 분석할 수 있습니다. `/v2/profile` 메소드의 `Content-Language` 헤더에서 입력 텍스트의 언어를 표시하십시오. 언어 지정에 대한 자세한 정보는 [요청 및 응답 언어 지정](/docs/services/personality-insights?topic=personality-insights-input#languages-input)을 참조하십시오. 
-   *원 점수.* 서비스의 모델 및 입력 텍스트에서 계산된 원 점수와 원 샘플링 오류를 요청할 수 있습니다. 값은 정규화되거나 샘플 모집단과 비교되지 않습니다. 원 점수는 특정 시나리오에 대해 사용자 정의 정규화를 적용하려고 하거나 샘플 모집단과의 비교가 필요 없는 고객에게 유용합니다. 사용자는 `/v2/profile` 메소드의 `include_raw` 조회 매개변수를 `true`로 설정하여 원 점수를 요청합니다. 자세한 정보는 [숫자 결과 해석](/docs/services/personality-insights?topic=personality-insights-numeric)을 참조하십시오.
-   *모델 개선사항.* 최신 연구를 기반으로, {{site.data.keyword.IBM_notm}}은 성격 특성을 추론하는 접근 방법 중 일부를 추가로 개선했습니다. 변경사항은 서비스 사용자에게 투명하게 공개되며, 이로 인해 서비스에서 얻는 이전 결과가 무효화되지는 않습니다. 추론을 위한 서비스의 접근 방법과 연구에 대한 자세한 정보는 [성격 특성이 추론되는 방법](/docs/services/personality-insights?topic=personality-insights-science#researchInfer)을 참조하십시오.

### 2015년 2월 23일
{: #February2015}

2015년 2월 23일 현재, {{site.data.keyword.personalityinsightsshort}} 서비스는 베타 릴리스로 사용 가능하던 이전의 사용자 모델링 서비스의 GA(Generally Available) 버전입니다. GA 릴리스를 사용하려면 사용자가 새 서비스의 인스턴스로 마이그레이션해야 합니다. 서비스의 베타 및 GA 버전 간에는 다음의 차이점이 존재합니다.

-   {{site.data.keyword.personalityinsightsshort}} 서비스는 사용자 모델링 서비스와 호환이 가능합니다. 기술할 차이점은 현재 애플리케이션에 영향을 주지 않고 추가 유연성과 개선된 결과를 제공한다는 것입니다. 
-   {{site.data.keyword.cloud_notm}}에서 서비스 작성에 사용되는 매개변수가 변경되었습니다. 이제는 `user_modeling` 대신에 `personality_insights`의 서비스 이름을 사용하며, `user_modeling_free_plan` 대신에 `"IBM Watson Personality Insights 월별 플랜"`의 서비스 플랜을 사용합니다.
-   `/v2/profile` 메소드는 두 개의 새 입력 형식을 허용합니다. `Content-Type` 헤더는 이제 JSON(`application/json`)에 추가하여 입력 형식 일반 텍스트(`text/plain`)(기본값임) 및 HTML(`text/html`)을 허용합니다.
-   `/v2/profile` 메소드는 이제 새 결과 형식을 리턴합니다. `Accept` 헤더는 이제 JSON(`application/json`)(기본값임)에 추가하여 결과 형식 CSV(`text/csv`)를 허용합니다.
-   `/v2/profile` 메소드에는 이제 백분율 값이 보고되는 각 특성에 대해 새 결과 요소 `sampling_error`가 포함되어 있습니다. 샘플 오류는 입력 텍스트를 기반으로 하여 작성자의 백분위수로 서비스의 신뢰 레벨을 표시하는 double 값으로 리턴됩니다.
-   욕구 모델은 개선된 토큰화 및 처리를 채택함으로써 해당 특성에 대한 값의 분포를 보다 잘 정규화합니다. 사용자 모델링 API에 의해 생성된 결과를 다시 계산하도록 권고합니다.
-   `visualize` 메소드는 이제 더 이상 사용되지 않으며 향후 릴리스에서 완전히 제거될 예정입니다. 동일 애플리케이션에서 제공되는 `personality.js` JavaScript 파일을 사용하여 클라이언트의 유사한 결과를 얻을 수 있습니다. `textsummary.js` JavaScript 파일은 서비스의 결과에 대한 추가 형식화를 제공합니다. 
