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

# 서비스를 뒷받침하는 과학
{: #science}

심리학, 마케팅 및 기타 분야의 용인된 이론은 인간의 언어가 성격, 사고 방식, 사회적 연줄 및 감정 상태를 반영한다는 것입니다. 특정 범주의 단어를 사용하는 빈도는 이러한 특성에 대한 단서를 제공해줄 수 있습니다. 많은 연구자들은 블로그, 에세이 및 트윗 등의 글쓰기에서 단어 사용의 다양성이 성격의 측면을 예측할 수 있음을 알아냈습니다([Fast &amp; Funder(2008)](/docs/services/personality-insights/references.html#fast2008), [Gill 등(2009)](/docs/services/personality-insights/references.html#gill2009), [Golbeck 등(2011)](/docs/services/personality-insights/references.html#golbeck2011), [Hirsh &amp; Peterson(2009)](/docs/services/personality-insights/references.html#hirsh2009) 및 [Yarkoni(2010)](/docs/services/personality-insights/references.html#yarkoni2010)).
{: shortdesc}

{{site.data.keyword.IBM_notm}}은 소셜 미디어 데이터에서 추론된 성격 특성이 사람들의 행동과 성향을 예측할 수 있는지 파악하기 위해 일련의 연구를 수행했습니다. {{site.data.keyword.IBM_notm}}은 특정 성격 특성을 지닌 사람들이 정보 수집과 유포 작업에서 더 많은 수가 응답하고 리트윗한다는 사실을 알아냈습니다. 예를 들어, 자극 추구에서 높은 점수를 받은 사람들은 응답할 가능성이 높은 반면에 신중함에서 높은 점수를 받은 사람들은 응답할 가능성이 낮습니다([Mahmud 등, 2013](/docs/services/personality-insights/references.html#mahmud2013)). 이와 유사하게 겸손함, 개방성 및 친화성에서 높은 점수를 받은 사람들은 정보를 유포시킬 가능성이 높습니다([Lee 등, 2014](/docs/services/personality-insights/references.html#lee2014)).

또한 {{site.data.keyword.IBM_notm}}은 소셜 미디어 언어에서 추론된 대로 높은 개방성과 낮은 감정 범위(신경증적 성향)를 지닌 사람들이 보다 호의적으로 반응(예: 광고 링크를 클릭하거나 계정을 팔로우함으로써)함을 알아냈으며, 이는 설문조사 기반, 기준 실제값 확인으로 입증된 결과입니다. 예를 들어, 높은 개방성과 낮은 감정 범위와 관련하여 사용자의 최상위 10퍼센트를 대상으로 실시한 경우에는 클릭 비율이 6.8퍼센트에서 11.3퍼센트로 증가된 결과를 얻었으며 팔로우 비율이 4.7퍼센트에서 8.8퍼센트로 증가된 결과를 얻었습니다. 

여러 최근 연구에서는 소셜 미디어 데이터에서 계산된 특성에 대해 유사한 결과를 발표했습니다. 소매점 데이터에 대한 최근의 한 연구에서는 질서 정연함, 자제력 및 신중함에서 높은 점수를 받고 무절제성에서 낮은 점수를 받은 사람들이 무작위 모집단보다 쿠폰을 사용할 가능성이 40퍼센트 높다는 사실을 알아냈습니다. 두 번째 연구에서는 특정 가치를 지닌 사람들이 특정 독서 성향을 보여준다는 사실을 알아냈습니다([Hsieh 등(2014)](/docs/services/personality-insights/references.html#hsieh2014)). 예를 들어, 자기초월 가치가 보다 높은 사람들은 환경 관련 기사 읽기에 관심을 보였으며 자기고양 가치가 보다 높은 사람들은 업무 관련 기사 읽기에 관심을 보여주었습니다. 600명이 넘는 Twitter 사용자에 대한 세 번째 연구에서는 개인의 성격 특성이 65퍼센트의 정확도로 브랜드 선호도를 예측할 수 있음을 알아냈습니다. 

다음 절에서는 이러한 상위 레벨 결과물을 기반으로 확장하여 {{site.data.keyword.personalityinsightsshort}} 서비스를 뒷받침하는 연구 및 개발을 설명합니다. 실제 존재하는 시나리오에 서비스를 적용하는 연구에 대한 자세한 정보는 [제공 중인 서비스](/docs/services/personality-insights/applied.html)를 참조하십시오. 

## 성격 모델 이해하기
{: #researchModels}

{{site.data.keyword.personalityinsightsshort}} 서비스에 대해 {{site.data.keyword.IBM_notm}}은 텍스트 정보에서 빅 파이브 특질과 성향, 욕구 및 가치에 대한 점수를 추론하는 모델을 개발했습니다. 서비스에서 보고하는 모델은 심리학, 심리언어학 및 마케팅 분야의 연구를 기반으로 합니다. 

-   [빅 파이브](/docs/services/personality-insights/models.html)는 심리학자가 개발한 성격 모델의 최상의 연구 성과 중 하나입니다([Costa &amp; McCrae, 1992](/docs/services/personality-insights/references.html#costa1992) 및 [Norman, 1963](/docs/services/personality-insights/references.html#norman1963)). 이는 사람들이 일반적으로 세상과 관계하는 방법을 기술하는 가장 널리 사용되는 성격 모델입니다. 서비스는 모델의 5개의 특질과 30개의 성향을 계산합니다. 특질은 종종 니모닉 *OCEAN*으로 참조됩니다. 여기서 *O*는 개방성(Openness), *C*는 성실성(Conscientiousness), *E*는 외향성(Extraversion), *A*는 친화성(Agreeableness), 그리고 *N*은 신경증적 성향(Neuroticism)을 나타냅니다. (신경증적 성향이라는 용어가 특정한 임상적 의미를 지닐 수 있으므로, 서비스는 보다 일반적으로 적용되는 표제인 감정 범위 하에서 이러한 통찰을 제시합니다.) 
-   [욕구](/docs/services/personality-insights/needs.html)는 인간 행동의 중요한 측면입니다. 연구 문헌에서는 다양한 유형의 인간 욕구가 보편적이며 소비자 행동에 직접적으로 영향을 준다고 제안합니다([Kotler &amp; Armstrong, 2013](/docs/services/personality-insights/references.html#kotler2013) 및 [Ford, 2005](/docs/services/personality-insights/references.html#ford2005)). 서비스에서 보고하는 12가지 범주의 욕구는 제품이나 서비스를 고려할 때 개인이 충족하기를 희망하는 욕망으로서 마케팅 문헌에 기술되어 있습니다. 
-   [가치](/docs/services/personality-insights/values.html)는 개인에게 무엇이 가장 중요한 지를 전달합니다. 이는 "사람들의 삶에서 지도 원리로서의 역할을 하는 다양한 중요성을 지닌 상황을 초월한 가치 있는 목표"입니다([Schwartz, 2006](/docs/services/personality-insights/references.html#schwartz2006)). Schwartz는 모든 가치에 공통인 5가지 특성을 요약합니다. (1) 가치는 믿음입니다. (2) 가치는 동기를 부여하는 구조입니다. (3) 가치는 특정 행위와 상황을 초월합니다. (4) 가치는 행위, 정책, 사람들 및 이벤트를 선택하고 평가하는 길잡이입니다. (5) 가치는 상대적 중요성에 따라 달라지며 이에 맞게 순위가 지정될 수 있습니다. 서비스는 Schwartz가 제안했으며 20개가 넘는 국가에서 검증된 5개의 기본적인 인간 가치를 계산합니다([Schwartz, 1992](/docs/services/personality-insights/references.html#schwartz1992)).

## 성격 특성을 추론하는 방법
{: #researchInfer}

{{site.data.keyword.personalityinsightsshort}} 서비스는 오픈 어휘 접근 방법을 기반으로 텍스트 정보에서 성격 특성을 추론합니다. 이 방법은 성격 추정에 대한 연구의 최신 경향을 반영합니다([Arnoux 등, 2017](/docs/services/personality-insights/references.html#arnoux2017), [Schwartz 등, 2013](/docs/services/personality-insights/references.html#schwartz2013) 및 [Plank &amp; Hovy, 2015](/docs/services/personality-insights/references.html#plank2015)).

서비스는 우선 입력 텍스트를 토큰화하여 *n*차원 공간에서의 표현을 개발합니다. 서비스는 [GloVe ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](http://nlp.stanford.edu/projects/glove/){: new_window}이라고 하는 오픈 소스 단어 임베딩 기술을 사용하여 입력 텍스트의 단어에 대한 벡터 표현을 가져옵니다([Pennington 등, 2014](/docs/services/personality-insights/references.html#pennington2014)). 그리고 이는 이 표현을 빅 파이브, 욕구 및 가치 특성의 성격 프로파일을 추론하는 기계 학습 알고리즘에 피드합니다. 알고리즘을 훈련시키기 위해, 서비스는 자체 Twitter 피드의 데이터와 함께 수천 명의 사용자에게 실시한 설문조사로부터 얻은 점수를 사용합니다. 

{{site.data.keyword.IBM_notm}}은 동일한 방법으로 지원되는 모든 언어에 대해 모델을 개발했습니다. 이 모델은 일단 사용자 인구통계(예: 연령, 성별 또는 문화)와는 무관하게 개발되었습니다. 향후에 {{site.data.keyword.IBM_notm}}은 다양한 인구통계 범주에 특정한 모델을 개발할 수 있습니다. 

서비스의 초기 버전에서는 자체 기계 학습 모델에서 LIWC(Linguistic Inquiry and Word Count) 심리언어학 사전을 사용했습니다. 그러나 방금 설명한 오픈 어휘 접근 방법은 LIWC 기반 모델보다 훨씬 우수합니다. 평균 MAE(Mean Absolute Error) 및 상관의 관점에서 각 언어에 대한 서비스의 정확도와 관련된 자세한 정보는 [서비스의 정확도](#researchPrecise)를 참조하십시오. 가장 정확한 결과를 얻기 위한 입력 텍스트 제공에 대한 안내는 [충분한 입력 제공](/docs/services/personality-insights/input.html#sufficient)을 참조하십시오. 

## 서비스의 정확도
{: #researchPrecise}

{{site.data.keyword.IBM_notm}}은 성격 프로파일 추론에 대한 서비스의 접근 방법의 정확도를 파악하기 위해 실증 연구를 수행했습니다. {{site.data.keyword.IBM_notm}}은 모든 특성과 언어에 대해 1500 - 2000명의 참가자로부터 설문조사 응답과 Twitter 피드를 수집했습니다. *기준 실제값*을 설정하기 위해, 참가자는 4개 세트의 표준 정신력 측정 테스트를 받았습니다. 

-   IPIP(International Personality Item Pool)에서 유도된 50개 항목 빅 파이브
-   IPIP-NEO(IPIP Neuroticism, Extraversion &amp; Openness)에서 유도된 120개 항목 성향
-   {{site.data.keyword.IBM_notm}}에서 개발한 52개 항목 기본 욕구
-   Schwartz가 개발한 26개 항목 기본 가치

그리고 {{site.data.keyword.IBM_notm}}은 자체 모델에 의해 유도된 점수를 Twitter 사용자에 대한 설문조사 기반 점수와 비교했습니다. 이러한 결과를 바탕으로, {{site.data.keyword.IBM_notm}}은 다양한 범주의 성격 특성에 대해 추론된 점수와 실제 점수 간에 [평균 MAE(Mean Absolute Error)](#preciseMAE) 및 [평균 상관](#preciseCorrelation)을 판별했습니다. [언어별 평균 MAE 및 상관](#precisePerLanguage)은 각각의 지원되는 언어에 대한 통계치를 제공합니다. 

### 평균 MAE(Mean Absolute Error)
{: #preciseMAE}

*MAE(Mean Absolute Error)*는 실제값과 예측값 간의 차이를 측정하는 데 사용되는 메트릭입니다. {{site.data.keyword.personalityinsightsshort}} 서비스의 경우, 실제값 또는 기준 실제값은 성격 설문조사를 실시하여 얻은 성격 점수입니다. 예측치는 서비스의 모델이 생성한 점수입니다. 

{{site.data.keyword.IBM_notm}}은 실제 점수와 예측 점수 간의 차이에 대한 절대값의 평균을 취하여 MAE를 계산했습니다. 실제값의 다과를 예측하는 것이 상관이 없으므로, {{site.data.keyword.IBM_notm}}은 절대값을 사용했습니다. 차이가 있는 한 모델은 오류의 크기에 따라 벌점을 받습니다. MAE가 낮을수록 모델의 성능은 높아집니다. {{site.data.keyword.IBM_notm}}은 MAE에 대해 0 - 1의 스케일을 사용합니다. 여기서 0은 오류 없음(예측된 값이 실제값과 정확히 동일함)을 의미하며 1은 최대 오류를 의미합니다. 

### 평균 상관
{: #preciseCorrelation}

*평균 상관*은 두 변수의 독립성을 측정하는 통계 용어입니다. 이 메트릭으로 {{site.data.keyword.IBM_notm}}은 다양한 범주의 성격 특성에 대해 추론된 점수와 실제 점수 간 상관을 측정했습니다. 예측한 점수가 실제 결과를 밀접하게 추적하는 경우에는 상관 점수가 높으며, 그렇지 않으면 점수가 낮습니다. 

{{site.data.keyword.IBM_notm}}은 -1에서 1 사이의 스케일로 상관을 측정합니다. 1은 완전한 순(증가) 선형 관계를 표시하며, -1은 완전한 역(감소) 선형 관계를 표시합니다. 기타 모든 경우에 값은 이러한 극단 사이에 위치합니다. 변수가 독립적인 경우(전혀 관계가 없음), 상관은 0입니다. 

{{site.data.keyword.IBM_notm}}에서는 최상의 예측에 대해 1에 근접한 숫자를 찾습니다. 그러나 성격은 텍스트에만 의존해서는 예측하기가 어렵습니다. 이러한 유형의 심리 모델의 경우, 0.4를 초과하는 상관은 좀처럼 보기가 어렵습니다. 이러한 영역에 대한 연구 문헌에서, 0.2를 초과하는 상관은 수용 가능하다고 간주됩니다. 

### 언어별 평균 MAE 및 상관
{: #precisePerLanguage}

다음 표에서는 {{site.data.keyword.personalityinsightsshort}} 서비스에 대한 언어별 평균 MAE 및 상관 결과를 보여줍니다. 해당 결과에 따라 서비스는 텍스트 데이터에서 성격 추정의 최첨단에 놓이게 됩니다. 관련 내용은 [Schwartz 등(2013)](/docs/services/personality-insights/references.html#schwartz2013) 및 [Plank 및 Hovy(2015)](/docs/services/personality-insights/references.html#plank2015)을 참조하십시오. 

<table>
  <caption>표 1. 언어별 평균 MAE 및 상관</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      언어
    </th>
    <th style="text-align:center; vertical-align:bottom">
      빅 파이브 특질
    </th>
    <th style="text-align:center; vertical-align:bottom">
      빅 파이브 성향
    </th>
    <th style="text-align:center; vertical-align:bottom">
      욕구
    </th>
    <th style="text-align:center; vertical-align:bottom">
      가치
    </th>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **영어**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      평균 MAE
    </td>
    <td style="text-align:center">
      0.12
    </td>
    <td style="text-align:center">
      0.12
    </td>
    <td style="text-align:center">
      0.11
    </td>
    <td style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      평균 상관
    </td>
    <td style="text-align:center">
      0.33
    </td>
    <td style="text-align:center">
      0.28
    </td>
    <td style="text-align:center">
      0.22
    </td>
    <td style="text-align:center">
      0.24
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **스페인어**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      평균 MAE
    </td>
    <td style="text-align:center">
      0.10
    </td>
    <td style="text-align:center">
      0.12
    </td>
    <td style="text-align:center">
      0.12
    </td>
    <td style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      평균 상관
    </td>
    <td style="text-align:center">
      0.35
    </td>
    <td style="text-align:center">
      0.21
    </td>
    <td style="text-align:center">
      0.24
    </td>
    <td style="text-align:center">
      0.19
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **일본어**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      평균 MAE
    </td>
    <td style="text-align:center">
      0.11
    </td>
    <td style="text-align:center">
      0.12
    </td>
    <td style="text-align:center">
      0.11
    </td>
    <td style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      평균 상관
    </td>
    <td style="text-align:center">
      0.27
    </td>
    <td style="text-align:center">
      0.22
    </td>
    <td style="text-align:center">
      0.25
    </td>
    <td style="text-align:center">
      0.19
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **아랍어**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      평균 MAE
    </td>
    <td style="text-align:center">
      0.09
    </td>
    <td style="text-align:center">
      0.12
    </td>
    <td style="text-align:center">
      0.11
    </td>
    <td style="text-align:center">
      0.10
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      평균 상관
    </td>
    <td style="text-align:center">
      0.17
    </td>
    <td style="text-align:center">
      0.14
    </td>
    <td style="text-align:center">
      0.13
    </td>
    <td style="text-align:center">
      0.14
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **한국어**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      평균 MAE
    </td>
    <td style="text-align:center">
      0.11
    </td>
    <td style="text-align:center">
      0.12
    </td>
    <td style="text-align:center">
      0.11
    </td>
    <td style="text-align:center">
      0.11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      평균 상관
    </td>
    <td style="text-align:center">
      0.21
    </td>
    <td style="text-align:center">
      0.21
    </td>
    <td style="text-align:center">
      0.13
    </td>
    <td style="text-align:center">
      0.12
    </td>
  </tr>
</table>

백분위수 점수를 계산하기 위해, {{site.data.keyword.IBM_notm}}은 매우 방대한 데이터 세트의 Twitter 사용자(영어의 경우 100만명의 사용자, 한국어의 경우 200,000명의 사용자, 아랍어와 일본어의 경우 각각 100,000명의 사용자, 그리고 스페인어의 경우 80,000명의 사용자)를 수집했으며 이들의 성격상을 계산했습니다. 그리고 {{site.data.keyword.IBM_notm}}은 각각의 계산된 프로파일의 원 점수를 해당 데이터 세트의 프로파일의 분포와 비교하여 백분위수를 판별했습니다. 

> **참고:** 아랍어와 한국어 입력의 경우, 서비스는 일부 성격 특성에 대해 의미 있는 백분위수와 원 점수를 생성할 수 없습니다. 자세한 정보는 [아랍어와 한국어 입력에 대한 제한사항](/docs/services/personality-insights/numeric.html#limitations)을 참조하십시오. 

## 소비 성향 이해하기
{: #researchPrefs}

성격과 구매 행동 간의 관계가 다양한 제품과 서비스 간에 연구되어 왔습니다. 

-   유기농 식품과 관련된 성향을 테스트하는 중에 [Chen(2007)](/docs/services/personality-insights/references.html#chen2007)은 개인의 성격 특성이 개인의 음식 선택 기준을 세우는 데 중요한 역할을 한다고 밝혔습니다. 
-   [Schlegelmilch 등(1996)](/docs/services/personality-insights/references.html#schlegelmilch1996)은 성격 변인과 친환경 구매 행위 간에 관계를 탐구했습니다. 작성자들은 소비자의 전반적인 환경적 의식이 친환경 구매 의사결정에 긍정적인 영향을 준다는 사실을 보여주었습니다. 
-   [Hymbaugh 및 Garrett(2007)](/docs/services/personality-insights/references.html#hymbaugh1974)는 성격과 스카이다이빙 간의 관계를 조사했으며, 모험심과 자극 추구에서 높은 점수를 받은 사람들이 일반적으로 스카이다이빙에 탐닉한다는 사실을 알아냈습니다. (자세한 정보는 [리스크 프로파일링](/docs/services/personality-insights/applied.html#otherRisk)을 참조하십시오.) 

소비 행위와 성격 간의 이러한 알려진 관계를 적용하는 것은 도전적인 일입니다. 이러한 작업의 대부분은 설문조사에서 유도된 성격 데이터를 사용했으며, 해당 모델은 공개적으로 사용될 수 없습니다. 따라서 {{site.data.keyword.IBM_notm}}은 이러한 소비 성향 모델을 직접 알아내기로 결정했습니다. 모델을 훈련시킬 때 {{site.data.keyword.IBM_notm}}은 특성으로서 {{site.data.keyword.personalityinsightsshort}} 서비스에서 리턴된 성격 점수를 사용했습니다. 결과적으로, 이러한 모델을 적용하여 서비스에서 사용자의 성격 특성을 계산할 때 예측은 보다 정확해질 수 있습니다. 

## 소비 성향을 추론하는 방법
{: #researchInferPrefs}

{{site.data.keyword.personalityinsightsshort}} 서비스는 입력 텍스트의 작성자에 대한 성격 프로파일의 결과를 기반으로 하여 소비 성향을 추론합니다. 기존 문헌에서 {{site.data.keyword.IBM_notm}}은 성격과 상관 관계가 있다고 입증된 104개의 소비 성향을 식별했습니다. 여기에는 쇼핑, 영화, 음악 및 기타 범주와 관련된 성향이 포함되어 있습니다. 그리고 {{site.data.keyword.IBM_notm}}은 각각의 소비 성향에 대한 개인의 성향을 평가할 수 있도록 정신력 측정 설문조사를 작성했습니다. 

{{site.data.keyword.IBM_notm}}은 약 600명의 개인으로부터 해당 설문조사에 대한 응답을 받았습니다. 또한 이들에 대한 Twitter 데이터(각 사용자마다 200개가 넘는 자체 작성된 트윗)를 보유하고 있습니다. {{site.data.keyword.IBM_notm}}은 각 개인에 대한 성격 프로파일을 수집하기 위해 서비스에 트윗을 제출했습니다. 그리고 이는 입력 특성 세트가 성격 정보인 각각의 소비 성향에 대한 분류자를 빌드했습니다. 

서비스에 포함시키기 위해, {{site.data.keyword.IBM_notm}}은 성격 기반 분류가 무작위 분류보다 최소한 9퍼센트 이상 우수한 성과를 보여준 소비 성향만 선택했습니다. 원래 104개의 성향 중에서 42개가 이러한 기준을 충족했으며 서비스에 의해 소비 성향으로 밝혀졌습니다. 

<!--
COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016

## How media influence inferred characteristics

{{site.data.keyword.IBM_notm}} conducted a validation study to understand the effect of media on inferred characteristics. To determine the accuracy of the service's approach to estimating characteristics, {{site.data.keyword.IBM_notm}} compared scores that were derived by its models with survey-based scores for Twitter users (for instance, approximately 500 users for English and more than 600 for Spanish).

To establish ground truth, participants took three sets of standard psychometric tests: 50-item Big Five (derived from the International Personality Item Pool, or IPIP), 52-item fundamental Needs (developed by {{site.data.keyword.IBM_notm}}), and 26-item basic Values (developed by Schwartz). {{site.data.keyword.IBM_notm}} conducted the study in two phases:

-   For the first study, conducted in 2013, {{site.data.keyword.IBM_notm}} recruited 256 Twitter users ([Gou et al., 2014](/docs/services/personality-insights/references.html#gou2014)). Although the models were learned from different sources, {{site.data.keyword.IBM_notm}} found that for more than 80 percent of the Twitter users, scores for characteristics that were inferred for all three models correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80). Specifically, scores that were derived by the service correlated with survey-based scores as follows:
    -   For 80.8 percent of participants' Big Five scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.75)
    -   For 86.6 percent of participants' Needs scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80)
    -   For 98.21 percent of participants' Values scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.55)
-   For the second study, conducted in 2015, {{site.data.keyword.IBM_notm}} recruited another set of 237 Twitter users. The study found that for Big Five and Values, scores for inferred characteristics correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.07 and 0.21) for every Twitter user. For needs, such significant correlation was observed for 90 percent of the users (p value &lt; 0.05 and correlation coefficient between 0.01 and 0.20).

In both studies, participants also rated on a five-point scale how well each derived characteristic matched their perceptions of themselves. Their ratings suggest that the inferred characteristics largely matched their self-perceptions. Specifically, means of all ratings were above 3 ("somewhat") out of 5 ("perfect").

-   For the 256 Twitter users of the first study, means were 3.4 (with a standard deviation of 1.14) for Big Five, 3.39 (with a standard deviation of 1.34) for Needs, and 3.13 (with a standard deviation of 1.17) for Values.
-   For the 237 Twitter users of the second study, means were 3.31 (with a standard deviation of 1.18) for Big Five, 3.37 (with a standard deviation of 1.22) for Needs, and 3.36 (with a standard deviation of 1.18) for Values.

COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016
-->

## 성격 설문조사에 대한 참고사항
{: #researchSurveys}

{{site.data.keyword.personalityinsightsshort}} 서비스를 개발할 때 {{site.data.keyword.IBM_notm}}은 성격 설문조사에 의존하여 성격 추정에 대한 기준 실제값 데이터를 설정했습니다. 기준 실제값은 추론을 통해서가 아닌 직접 관찰을 통해 얻은 사실 기반 데이터를 의미합니다. 기계 학습 모델에 대한 정확도의 일반적인 측정은 모델에 의해 추론된 점수를 기준 실제값 데이터과 비교하는 것입니다. 이전 절에서는 {{site.data.keyword.IBM_notm}}이 설문조사를 사용하여 서비스의 정확도를 검증하는 방법을 설명합니다. 

다음 참고사항은 성격 설문조사와 설문조사 기반 성격 평가의 사용에 대해 명확히 알려줍니다. 

-   성격 설문조사를 완료하려면 장기적으로 많은 시간이 소요됩니다. 따라서 {{site.data.keyword.IBM_notm}}의 연구에 참여할 의지가 있으며 실제로 가능한 Twitter 사용자 수에 따라 제약을 받습니다. {{site.data.keyword.IBM_notm}}은 이메일, 블로그 및 포럼 등과 같은 기타 온라인 미디어의 사용자는 물론 추가적인 사용자로 실증 연구를 수행했습니다. 
-   설문조사 기반 성격 평가는 자체 보고를 기반으로 하며, 이는 종종 개인의 성격을 실제로 반영하지 않을 수도 있습니다. 일부 사용자가 해당 설문조사에 방해가 되는 답변을 할 수도 있습니다. 이러한 상황을 줄이기 위해 {{site.data.keyword.IBM_notm}}은 주의를 환기시키는 질문을 포함시키고 너무 빨리 작성된 설문조사를 버림으로써 설문조사 응답을 필터링했습니다. 
-   추론된 점수와 설문조사 기반 점수 간의 상관이 긍정적임과 동시에 중요함에도 불구하고, 해당 결과는 추론된 점수가 항상 설문조사 기반 결과와 상관 관계를 지니지 않을 수도 있음을 내포합니다. 또한 {{site.data.keyword.IBM_notm}} 외부의 연구자들은 추론된 점수가 설문조사에서 얻은 점수와 얼마나 잘 일치하는지를 비교하기 위한 실험도 실시했으며, 완전히 일관된 일치는 보고된 바가 없습니다. 
    -   [Golbeck 등(2011)](/docs/services/personality-insights/references.html#golbeck2011)은 추론된 점수를 설문조사 기반 점수와 일치시킬 때 10 - 18퍼센트의 오류 비율을 보고했습니다. 
    -   [Sumner 등(2012)](/docs/services/personality-insights/references.html#sumner2012)은 성격 예측에 대해 약 65퍼센트의 정확도를 보고했습니다. 
    -   [Mairesse 및 Walker(2006)](/docs/services/personality-insights/references.html#mairesse2006)는 빅 파이브 성격 예측에 대해 60 - 70퍼센트의 정확도를 보고했습니다. 

일반적으로, 성격 설문조사의 자체 보고된 점수가 텍스트에서 추론된 점수와 항상 완전히 일치하지 않는다는 사실은 연구 문헌에서 널리 인정되고 있습니다. 그러나 보다 중요한 사실은 텍스트에서 추론된 특성이 다양한 실세계 행동을 신뢰할 만하게 예측할 수 있음을 {{site.data.keyword.IBM_notm}}에서 알아냈다는 점입니다. 
