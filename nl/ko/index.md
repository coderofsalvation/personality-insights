---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-27"

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

# 관련 정보
{: #about}

> **서비스 업데이트:** *{{site.data.keyword.personalityinsightsshort}} 서비스는 2018년 11월 18일에 업데이트되었습니다. 이제 서비스를 {{site.data.keyword.cloud}} 런던 위치에서 이용할 수 있습니다. 자세한 정보는 릴리스 정보의 [2018년 11월 18일 서비스 업데이트](/docs/services/personality-insights?topic=personality-insights-release-notes#November2018b)를 참조하십시오. *

{{site.data.keyword.personalityinsightsfull}} 서비스는 소셜 미디어, 엔터프라이즈 데이터 또는 기타 디지털 통신으로부터 통찰을 이끌어내기 위한 API(Application Programming Interface)를 제공합니다. 서비스는 언어 분석을 사용하여 이메일, 문자 메시지, 트윗 및 포럼 게시물 등의 디지털 통신으로부터 개인의 고유 성격 특성을 추론합니다.
{: shortdesc}

서비스는 잠재적으로 잡음이 있는 소셜 미디어로부터 해당 성격 특성을 반영하는 개인상을 추론합니다. 또한 이는 다양한 제품, 서비스 및 활동을 선호할 가능성을 표시하는 개인의 소비 성향을 판별할 수도 있습니다.

## 성격 특성
{: #models-index}

{{site.data.keyword.personalityinsightsshort}} 서비스는 3개의 기본 모델을 기반으로 하여 성격 특성을 추론합니다.

-   **빅 파이브** 성격 특성은 개인이 세상을 대하는 방식을 일반적으로 기술하는 가장 널리 사용되는 모델을 나타냅니다. 이 모델에는 *친화성*, *성실성*, *외향성*, *감정 범위* 및 *개방성*의 5개 기본 특질이 포함되어 있습니다. 각각의 특질에는 해당 특질에 따라 개인을 추가로 특성화하는 6개의 성향이 있습니다.
-   **욕구**는 제품의 어떠한 측면이 개인에게 반향을 불러일으킬 가능성이 있는지 설명합니다. 이 모델에는 *흥미*, *조화*, *호기심*, *이상*, *친밀감*, *자기 표현*, *자유*, *사랑*, *실용성*, *안정*, *도전*, *구조*와 같은 12개의 특성적 욕구가 포함되어 있습니다.
-   **가치**는 개인의 의사결정에 영향을 주는 동기 요인을 설명합니다. 이 모델에는 *자기초월/타인 돕기*, *보수성/전통*, *쾌락주의/삶을 즐기기*, *자기고양/성취* 및 *변화 수용/흥미*의 5개 가치가 포함되어 있습니다.

자세한 정보는 [성격 모델](/docs/services/personality-insights?topic=personality-insights-models)을 참조하십시오.

## 소비 성향
{: #preferences-index}

입력 텍스트에서 추론된 성격 특성을 기반으로 하여, 서비스는 작성자의 소비 성향에 대한 표현을 리턴할 수도 있습니다. 소비 성향은 작성자가 서로 다른 제품, 서비스 및 활동을 추구할 가능성을 표시합니다. 이 서비스는 개인의 성향을 *쇼핑*, *음악*, *영화*, *독서 및 학습*, *건강 및 활동*, *자원 봉사*, *환경 관심도* 및 *사업가 정신*의 8개 범주로 그룹화합니다. 각각의 범주에는 한 개에서 십여 개까지의 개별 성향이 포함되어 있습니다.

자세한 정보는 [소비 성향](/docs/services/personality-insights?topic=personality-insights-preferences)을 참조하십시오.

## 서비스의 이점
{: #benefits}

{{site.data.keyword.ibmwatson}} 플랫폼의 코어 서비스로서, {{site.data.keyword.personalityinsightsshort}} 서비스는 비즈니스에 도움이 되는 통찰을 제공할 수 있습니다.

-   클라이언트의 성향을 학습하고 고객 만족도를 개선하며 클라이언트와의 관계를 강화함으로써 심층 레벨에서 고객을 파악합니다.
-   클라이언트 확보, 관계 유지 및 참여도를 개선합니다.
-   개별 클라이언트에 대해 제품, 서비스, 캠페인 및 커뮤니케이션을 보다 알맞게 조정하기 위해 고도의 개인화된 참여와 상호작용을 안내합니다.

서비스의 이점을 누리는 방법에 대한 자세한 정보는 [유스 케이스](/docs/services/personality-insights?topic=personality-insights-usecases)를 참조하십시오.

## 언어 지원
{: #languages-index}

서비스는 다음 언어를 지원합니다. 요청과 응답에 대해 지원되는 언어를 임의로 조합하여 사용할 수 있지만, 모든 입력 텍스트는 동일한 언어여야 합니다. 자세한 정보는 [요청 및 응답 언어 지정](/docs/services/personality-insights?topic=personality-insights-input#languages-input)을 참조하십시오.

<table style="width:75%">
  <caption>표 1. 지원되는 언어</caption>
  <tr>
    <th style="width:50%; text-align:center">
      요청 언어
    </th>
    <th style="width:50%; text-align:center">
      응답 언어
    </th>
  </tr>
  <tr>
    <td style="text-align:center; vertical-align:top">
      아랍어<br/>
      영어<br/>
      일본어<br/>
      한국어<br/>
      스페인어
    </td>
    <td style="text-align:center; vertical-align:top">
      아랍어<br/>
      영어<br/>
      일본어<br/>
      한국어<br/>
      스페인어<br/>
      브라질 포르투갈어<br/>
      프랑스어<br/>
      독일어<br/>
      이태리어<br/>
      중국어<br/>
      대만어
    </td>
  </tr>
</table>

## HIPAA
{: hipaa}

US Health Insurance Portability and Accountability Act (HIPAA) 지원은 {{site.data.keyword.personalityinsightsshort}} 서비스에 적용되지 않습니다. 서비스는 상태 비저장(Stateless) 방식입니다. {{site.data.keyword.cloud_notm}}에 사용자 데이터를 저장하지 않습니다. 

## 서비스에 대해 자세히 알아보기
{: #learn-index}

-   {{site.data.keyword.personalityinsightsshort}} 서비스의 [빠른 데모 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://personality-insights-demo.ng.bluemix.net/){: new_window}를 사용하면 입력 텍스트를 분석하여 작성자의 소비 성향이 포함된 성격상을 개발할 수 있습니다. 
-   {{site.data.keyword.watson}} [Starter Kits ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://www.ibm.com/watson/developercloud/starter-kits.html){: new_window}의 애플리케이션은 서비스의 데모를 제공합니다. 
-   [제공 중인 서비스](/docs/services/personality-insights?topic=personality-insights-applied) 및 [서비스를 뒷받침하는 과학](/docs/services/personality-insights?topic=personality-insights-science)에서는 서비스의 기반이 되는 연구에 대한 정보를 제공합니다.
-   [{{site.data.keyword.cloud_notm}} 카탈로그 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/catalog/services/personality-insights/){: new_window}의 {{site.data.keyword.personalityinsightsshort}} 서비스는 서비스에 사용 가능한 가격 플랜에 대해 설명합니다. 
