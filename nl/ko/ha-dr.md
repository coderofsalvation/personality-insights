---

copyright:
  years: 2019
lastupdated: "2019-03-19"

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

# 고가용성 및 재해 복구
{: #ha-dr}

{{site.data.keyword.personalityinsightsfull}} 서비스는 {{site.data.keyword.cloud_notm}} 위치 어디에서나 고가용성을 제공합니다. 재해 복구를 위한 백업 및 복원 요구사항이 없습니다.
{: shortdesc}

## 고가용성
{: #high-availability}

{{site.data.keyword.personalityinsightsshort}} 서비스는 {{site.data.keyword.cloud_notm}} 위치 어디서나(예: Dallas 또는 Washington, DC) 단일 장애 지점 없이 고가용성을 제공합니다. 이 서비스는 {{site.data.keyword.cloud_notm}}에서 제공하는 다중 구역 영역(MZR) 기능을 통해 자동으로 투명하게 고가용성을 실현합니다.

{{site.data.keyword.cloud_notm}}를 사용하면 단일 위치 내에서 단일 장애 지점을 공유하지 않는 다중 구역을 사용할 수 있습니다. 또한 영역 내 구역 전반에서 자동 로드 밸런싱을 제공합니다.

## Disaster recovery
{: #disaster-recovery}

{{site.data.keyword.personalityinsightsshort}} 서비스는 Stateless. {{site.data.keyword.cloud_notm}}에 사용자 데이터를 저장하지 않습니다. 영역에서 치명적인 장애가 발생한 경우 다음 단계를 완료하십시오.

1.  다른 영역에서 서비스의 {{site.data.keyword.personalityinsightsshort}} 인스턴스를 작성하십시오. 
1.  새 서비스 인스턴스에 대한 URL및 인증 정보를 사용하도록 애플리케이션을 수정하십시오. 
