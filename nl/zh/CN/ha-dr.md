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

# 高可用性和灾难恢复
{: #ha-dr}

{{site.data.keyword.personalityinsightsfull}} 服务在任何 {{site.data.keyword.cloud_notm}} 位置都具有高可用性。它没有用于灾难恢复的备份和复原需求。
{: shortdesc}

## 高可用性
{: #high-availability}

{{site.data.keyword.personalityinsightsshort}} 服务高度可用，在任何 {{site.data.keyword.cloud_notm}} 位置（例如，达拉斯或华盛顿特区）中都无单点故障。该服务通过 {{site.data.keyword.cloud_notm}} 提供的多专区区域 (MZR) 功能自动且透明地实现高可用性。

{{site.data.keyword.cloud_notm}} 支持不在单个位置中分担单点故障的的多个专区。它还在一个区域中的各个专区之间提供自动负载均衡。

## 灾难恢复
{: #disaster-recovery}

{{site.data.keyword.personalityinsightsshort}} 服务无状态。它不在 {{site.data.keyword.cloud_notm}} 上存储任何用户数据。如果区域中发生灾难性故障，请完成以下步骤：

1.  在其他区域中创建 {{site.data.keyword.personalityinsightsshort}} 服务的新实例。
1.  修改应用程序以使用新服务实例的 URL 和凭证。
