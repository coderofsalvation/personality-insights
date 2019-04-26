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

# 숫자 결과 해석
{: #numeric}

{{site.data.keyword.personalityinsightsshort}} 서비스는 각각의 성격 및 행동 특성에 대한
숫자 결과와 각각의 소비 성향에 대한 숫자 결과를 리턴합니다. 값은 제공되는 정보에 따라 다릅니다.
{: shortdesc}

아랍어와 한국어 입력의 경우, 서비스는 다수의 성격 특성에 대해 의미 있는 백분위수와 원 점수를 생성할 수 없습니다. 자세한 정보는 [아랍어와 한국어 입력에 대한 제한사항](#limitations)을 참조하십시오.
{: note}

## 성격 특성에 대한 백분위수
{: #percentiles}

각각의 요청마다, 서비스는 항상 각각의 빅 파이브, 가치 및 욕구 성격 특성에 대해 `percentile`로서
정규화된 점수를 보고합니다. 정규화된 점수는 서비스가 입력 텍스트에서 추론한 특질을 기반으로 하여 각 특성에 대한 백분위수 순위를 제시합니다. 
서비스는 작성자의 텍스트에 대한 원 점수를 샘플 모집단의 결과와 비교함으로써 정규화된 점수를 계산합니다. 
서비스는 각 백분위수를 0 - 1 범위의 double 값으로서 보고합니다.

예를 들어, 성격 특성 `big5_extraversion`에 대한 `0.64980796071382`의
백분위수는 텍스트 작성자가 해당 특성에 대해 65번째 백분위수에 있음을 표시합니다. 
작성자의 글쓰기는 샘플 모집단에서 64퍼센트보다 크고 34퍼센트 미만인 정도로 경향을 보여줍니다. 
백분위수의 정밀도는 요청에서 입력으로 제출된 단어의 수에 따라 다릅니다.  자세한 정보는 [충분한 입력 제공](/docs/services/personality-insights?topic=personality-insights-input#sufficient)을 참조하십시오.

빅 파이브 특질 및 성향에 대해 보고된 백분위수 간에는 수학적 관계가 존재하지 않습니다. 
서비스는 사용된 단어와 해당 특질 또는 성향에 대해 설문조사 참가자의 점수 간의 상관 관계를
기반으로 하여 각각의 특질 및 성향에 대해 정규화된 백분위수를 개별적으로 계산합니다. 
따라서 성향이 특질의 세분화된 설명을 제공함에도 불구하고 특질의 6개 성향에 대한 점수를 추가한다고 해서
반드시 해당 특질에 대한 백분위수가 산출되지는 않습니다. 원 점수의 경우도 이와 마찬가지입니다.
{: note}

## 성격 특성에 대한 원 점수
{: #rawScores-numeric}

요청의 `raw_scores` 조회 매개변수에 대해 `true`를 지정하는 경우,
서비스는 각각의 성격 특성에 대해 `raw_score`를 보고합니다. 
원 점수는 해당 특성에 대한 모델과 작성자의 텍스트에만 기반하여 특정 특성에 대한 점수를 표시합니다. 원 점수를 생성할 때 서비스는 결과를 샘플 모집단과 비교하지 않습니다. 
원 점수는 작성자가 성격 테스트를 실시하여 받는 점수로서 해석됩니다.

서비스는 각각의 원 점수를 0 - 1 범위의 double 값으로서 보고합니다.
보다 높은 점수는 일반적으로 작성자가 해당 특성을 지녔을 가능성이 보다 많음을 표시합니다. 
그러나 원 점수는 합산하여 고려되어야 합니다. 값의 범위는 실제로 0 - 1보다 훨씬 작을 수 있습니다.
따라서 개별 점수는 전체 점수와 해당 범위의 컨텍스트에서 고려되어야 합니다. 
그러나 예를 들어 일반적으로 성격 특성 `big5_extraversion`에 대한
`0.56817738781166`의 원 점수는 작성자가 성격 테스트에서 이 점수를 받았을 가능성이 높음을 표시합니다. 
이 원 점수를 이전 절의 동일한 작성자 및 특성에 대해 보고된 정규화된 백분위수와 비교하십시오.

서비스는 특정 시나리오에 대해 사용자 정의 정규화를 적용하려고 하거나 샘플 모집단과의 비교가 필요하지 않은 사용자에게 원 점수를
사용할 수 있도록 허용합니다. 작성자의 특성이 대규모 샘플 모집단과 비교되는 방법을 알고 싶은 사용자는 정규화된 점수를 사용할 수 있습니다. 
원 데이터에서 자체 정규화된 백분위수 점수를 유도하고자 하는 사용자는
다른 샘플 모집단에 대해 원 점수를 비교하고 정규화에 대한 다른 접근 방법을 적용할 수 있습니다.

특정 특성에 대한 백분위수로 원 점수를 정규화하려면 원 점수를 특성에 대한 평균과 표준편차가 알려져 있는 샘플 모집단과 비교하십시오. 
예를 들어, {{site.data.keyword.IBM_notm}}은 Twitter 사용자의 대규모 샘플 모집단으로부터 데이터를 수집하는 연구를 수행했습니다. 
{{site.data.keyword.IBM_notm}}은 각각의 성격 특성에 대해 사용자의 점수를 계산한 후에 각각의 특성에 대해 평균과 표준편차를 설정했습니다. 
입력 텍스트의 분석으로부터 추론된 원 점수의 백분위수 점수를 계산하기 위해,
서비스는 해당 특성에 대한 샘플 Twitter 모집단에서 파생된 평균과 표준편차를 사용합니다. 

## 행동 특성에 대한 백분율
{: #percentages}

해당 컨텐츠 항목에 시간소인이 있는 JSON 데이터를 제출하는 경우, 서비스는 각각의 행동 특성에 대해 `percentage`를 보고합니다. 
행동 특성은 입력의 시간적 분포를 식별합니다. 백분율은 각 요일과 일중 시간 중에 발생한 컨텐츠 항목의 수를 표시합니다. 
예를 들어, 행동 특성 `behavior_0000`에 대한 `0.4561049445005`의
백분율은 컨텐츠 항목의 약 46퍼센트가 자정에서 오전 1시 사이에 작성되었음을 의미합니다.

## 소비 성향에 대한 점수
{: #scores}

요청의 `consumption_preferences` 조회 매개변수에 대해 `true`를
지정하는 경우, 서비스는 각 성향에 대해 `score`가 포함된 소비 성향을 보고합니다. 
서비스는 입력 텍스트에서 추론된 성격 특성에서 점수를 유도합니다. 점수는 텍스트 작성자가 이를 선호할 가능성의 정도를 표시하는 double 값입니다. 
이는 선호도의 표시이며 정규화된 백분율은 아닙니다.

일부 성향의 경우, 점수는 3개의 값 중에서 하나입니다. 

-   `0.0`: 작성자가 항목을 선호할 가능성이 거의 없습니다. 
일부 성향의 경우, 작성자의 관심도가 하위 레벨임을 의미하는 것으로 값을 해석할 수 있습니다. 
-   `0.5`: 작성자가 해당 항목에 대해 중립입니다. 
일부 성향의 경우, 이 값은 작성자의 관심도가 중간 레벨임을 의미할 수 있습니다.
-   `1.0`: 작성자가 항목을 선호할 가능성이 높습니다. 일부 성향의 경우, 이 값은 관심도가 상위 레벨임을 의미합니다.

기타 성향의 경우, 점수는 2진 값을 표시합니다. 입력 텍스트의 작성자가 해당 항목에 대해 관심을 가질 가능성이
매우 낮거나(`0.0`) 매우 높습니다(`1.0`). 또는 작성자의 관심도가 하위 레벨이거나 상위 레벨입니다. 
일부 경우에 점수는 단순한 '예' 또는 '아니오' 응답을 표시할 수 있습니다(예: 작성자가 사회적 대의명분을 위해 자원 봉사를 했을 가능성이 있음).

범주별 모든 성향과 해당 결과의 범위에 대한 전체 목록은
[소비 성향](/docs/services/personality-insights?topic=personality-insights-preferences)을 참조하십시오.

## 아랍어와 한국어 입력에 대한 제한사항
{: #limitations}

아랍어와 한국어 입력의 경우, 서비스의 모델은 성격 특성의 서브세트에 대해 의미 있는 결과를 생성할 수 없습니다. 
다음 특성의 경우, 정규화된 백분위수 점수는 항상 `0.5`이며 원 점수는 항상 원래 분포의 평균입니다. 
이러한 각 특성에 대해 `significant` 필드는 항상 `false`입니다. 
작성자의 성격 프로파일의 일부로서 이러한 특성에 대한 결과에 의존하지 *마십시오*.

<table>
  <caption>표 1. 해당 결과가 중요하지 않은 특성</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      특성
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      의미 없는<br/>아랍어 결과
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      의미 없는<br/>아랍어 결과
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      빅 파이브 특질
    </td>
    <td style="text-align:left; vertical-align:top">
      감정 범위
    </td>
    <td style="text-align:left; vertical-align:top">
없음
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      빅 파이브 성향
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; line-height:110%; padding:0px">
          *친화성*: 이타주의, 협력, 겸손함 및 신뢰
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *성실성*: 성취 노력 및 의무감
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *외향성*: 쾌활함 및 친근함(사교적)
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *감정 범위*: 분노(격노), 걱정을 잘하는, 무절제 및 강한 자의식
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *개방성*: 모험심, 상상력 및 지적 능력
        </li>
      </ul>
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; padding:0px">
          *외향성*: 자극 추구
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      욕구
    </td>
    <td style="text-align:left; vertical-align:top">
      이상적, 자유, 사랑, 현실성 및 체계
    </td>
    <td style="text-align:left; vertical-align:top">
      자유 및 안정성
    </td>
  </tr>
  </tr>
    <td style="text-align:left; vertical-align:top">
      가치
    </td>
    <td style="text-align:left; vertical-align:top">
      자기고양
    </td>
    <td style="text-align:left; vertical-align:top">
      보수성
    </td>
  </tr>
</table>
