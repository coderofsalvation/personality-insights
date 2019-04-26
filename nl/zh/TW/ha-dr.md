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

# 高可用性及災難回復
{: #ha-dr}

{{site.data.keyword.personalityinsightsfull}} 服務在任何 {{site.data.keyword.cloud_notm}} 位置內都具有高可用性。它沒有備份及還原災難回復的需求。
{: shortdesc}

## 高可用性
{: #high-availability}

{{site.data.keyword.personalityinsightsshort}} 服務具有高可用性，且任何 {{site.data.keyword.cloud_notm}} 位置內都沒有單一失敗點（例如，達拉斯或華盛頓特區）。此服務會透過 {{site.data.keyword.cloud_notm}} 提供的多區 (MZR) 功能，自動透通地達成高可用性。

{{site.data.keyword.cloud_notm}} 會啟用未在單一位置內共用單一失敗點的多個區域。它也會提供地區內各個區域的自動負載平衡。

## 災難回復
{: #disaster-recovery}

{{site.data.keyword.personalityinsightsshort}} 服務為無狀態。它不會在 {{site.data.keyword.cloud_notm}} 上儲存任何使用者資料。萬一地區發生災難性失效時，請完成下列步驟：

1.  在不同地區建立 {{site.data.keyword.personalityinsightsshort}} 服務的新實例。
1.  請修改您的應用程式以使用新服務實例的 URL 及認證。
