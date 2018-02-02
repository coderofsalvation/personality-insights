---

copyright:
  years: 2015, 2017
lastupdated: "2017-09-13"

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

# 프로파일 이해하기
{: #output}

1.  <span style="color:#003F69">서비스에 의해 리턴된 점수를 어떨게 해석합니까?</span>

    -   [숫자 결과 해석](/docs/services/personality-insights/numeric.html)에서는 서비스에 의해 리턴된 백분위수를
해석하는 방법에 대해 설명합니다. 여기에는 행동 백분율 및 선택적 원 점수, 그리고 서비스가 리턴할 수 있는 소비 성향에 대한 정보도 정보되어 있습니다. 

1.  <span style="color:#003F69">특질의 성향에 대한 점수를 추가할 때 해당 특질에 대한 점수가 산출되지 않는 이유는 무엇입니까? </span>

    -   [성격 특성에 대한
백분위수](/docs/services/personality-insights/numeric.html#percentiles)에서는 이 질문에 대한 답변을 제공합니다. 간단히 요약하면, 서비스는 각 특질과 성향에 대한
정규화된 백분위수를 개별적으로 계산합니다. 특질 및 해당 성향 간에는 수학적 관계가 존재하지 않습니다. 

1.  <span style="color:#003F69">언제 백분위수 점수 대신에 원 점수를 사용합니까?</span>

    -   [성격 특성에 대한
원 점수](/docs/services/personality-insights/numeric.html#rawScores)에서는 이러한 선택에 대한 통찰을 제공합니다. 간단히 요약하면, 특정 시나리오에 대해
사용자 정의 정규화를 개발하거나 샘플 모집단과의 비교가 필요하지 않은 경우에는 원 점수를 사용할 수 있습니다. 
작성자의 결과가 샘플 모집단과 비교되는 방법을 알아야 하는 경우에는 백분위수 점수를 사용하십시오. 

1.  <span style="color:#003F69">백분위수 점수에 대해 원 점수를 어떻게 정규화합니까?</span>

    -   [성격 특성에 대한 원 점수](/docs/services/personality-insights/numeric.html#rawScores)에서는
원 점수의 정규화에 대한 상위 레벨의 안내를 제공하며 정규화에 대한 {{site.data.keyword.IBM_notm}}의 접근 방법에 대해 설명합니다. 

1.  <span style="color:#003F69">{{site.data.keyword.personalityinsightsshort}} 시각화를 어떻게 해석합니까?</span>

    -   [숫자 결과 해석](/docs/services/personality-insights/numeric.html)에서는 시각화에 표시된 숫자 결과를 해석하는 방법에 대해 설명합니다. 
