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

# 성격 모델
{: #models}

{{site.data.keyword.personalityinsightsshort}} 서비스는 데이터 분석 알고리즘과 결합하여 언어의 심리학에 기반을 두고 있습니다. 
서비스는 사용자가 보낸 컨텐츠를 분석하고 입력 작성자에 대한 성격 프로파일을 리턴합니다. 서비스는 3개의 모델을 기반으로 성격 특성을 추론합니다.
{: shortdesc}

-   *빅 파이브* 성격 특성은 개인이 세상을 대하는 방식을 일반적으로 기술하는
가장 널리 사용되는 모델을 나타냅니다. 모델에는 5개의 기본 특질이 포함되어 있습니다. 
    -   [*친화성*](/docs/services/personality-insights/agreeableness.html)은 타인에 대한 연민과 협력에 대한 개인적 성향입니다. 
    -   [*성실성*](/docs/services/personality-insights/conscientiousness.html)은 체계적 또는 사려 깊은 방식으로 행동하는 개인적 성향입니다. 
    -   [*외향성*](/docs/services/personality-insights/extraversion.html)은 타인과 만났을 때 자극을 받는 개인적 성향입니다. 
    -   [*감정 범위*](/docs/services/personality-insights/emotional-range.html)(*신경증적 성향* 또는 *자연적 반응*이라고도 함)는 개인의 감정이 개인의 환경에 민감한 정도를 의미합니다. 
    -   [*개방성*](/docs/services/personality-insights/openness.html)은 개인이 다양한 활동을 경험하기 위해 열린 마음을 지닌 정도입니다. 

    이러한 각각의 최상위 레벨 특질에는 해당 특질에 따라 개인을 추가로 특성화하는 6개의 성향이 있습니다.
-   [욕구](/docs/services/personality-insights/needs.html)는 제품의 어떠한 측면이 개인에게 반향을 불러일으키는지 설명합니다. 모델에는 12개의 특성 욕구가 포함되어 있습니다. 
-   [가치](/docs/services/personality-insights/values.html)는 개인의 의사결정에 영향을 주는 동기 요인을 설명합니다. 모델에는 5개의 가치가 포함되어 있습니다. 

모델이 개발된 방법과 서비스가 이를 사용하는 방법에 대한 자세한 정보는
[서비스를 뒷받침하는 과학](/docs/services/personality-insights/science.html)을 참조하십시오. 

## 빅 파이브 성격 특성의 설명
{: #bigFive}

각각의 빅 파이브 특질이 3개의 표로 설명되어 있습니다. 

-   *성향*은 특질의 성향을 소개하며 각 성향에서 높은 점수를 받는 개인에 대해 설명합니다. 
-   *특성의 범위*는 각각의 개인을 기술할 수 있는 용어와 함께
해당 점수가 특질의 각 성향의 다소를 입증하는 개인에 적용될 수 있는 일반 설명을 제시합니다. 
모든 5개 특질의 성향에 대한 *특성의 범위* 표를 요약하는 편리한 단일 페이지 표를 보려면
<a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Facet-Characteristics.pdf" download="Personality-Insights-Facet-Characteristics.pdf">Personality-Insights-Facet-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="외부 링크 아이콘" title="외부 링크 아이콘" class="style-scope doc-content"></a>를 참조하십시오. 
-   *기본 및 보조 특질*은 특질을 다른 특질과 연관시키는 정보를 제시하며, 성격 특성의 조합을 설명합니다. 
이 표는 기본 및 보조 특성이 상호 연관되어 개인의 복합 성격을 제시하는 방법에 대한 흥미로운 통찰을 제공합니다. 
모든 5개 특질에 대한 *기본 및 보조 특성* 표를 요약하는 편리한 단일 페이지 표를 보려면
<a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Dimension-Characteristics.pdf" download="Personality-Insights-Dimension-Characteristics.pdf">Personality-Insights-Dimension-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="외부 링크 아이콘" title="외부 링크 아이콘" class="style-scope doc-content"></a>을 참조하십시오. 
