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

# 高可用性および災害復旧
{: #ha-dr}

{{site.data.keyword.personalityinsightsfull}} サービスは、どの {{site.data.keyword.cloud_notm}} ロケーション内でも高可用性を備えています。 災害復旧のためのバックアップおよび復元の要件はありません。
{: shortdesc}

## 高可用性
{: #high-availability}

{{site.data.keyword.personalityinsightsshort}} サービスは、どの {{site.data.keyword.cloud_notm}} ロケーション (例えば、ダラスまたはワシントン DC) 内でも単一障害点のない高可用性を備えています。 本サービスは、{{site.data.keyword.cloud_notm}} によって提供されるマルチゾーン・リージョン (MZR) 機能を使用して、自動的かつ透過的に高可用性を実現します。

{{site.data.keyword.cloud_notm}} は、単一ロケーション内で単一障害点を共有しない複数のゾーンを有効にします。 さらに、リージョン内の複数のゾーンにまたがる自動ロード・バランシングも提供します。

## 災害復旧
{: #disaster-recovery}

{{site.data.keyword.personalityinsightsshort}} サービスは、ステートレスです。 本サービスは、{{site.data.keyword.cloud_notm}} にユーザー・データを保管しません。リージョン内で深刻な障害が発生した場合は、以下のステップを実行します。

1.  別のリージョンで、{{site.data.keyword.personalityinsightsshort}} サービスの新規インスタンスを作成します。
1.  新規サービス・インスタンスの URL と資格情報を使用するように、アプリケーションを変更します。
