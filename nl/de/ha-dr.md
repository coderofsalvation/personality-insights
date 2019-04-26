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

# Hochverfügbarkeit und Disaster-Recovery
{: #ha-dr}

Der {{site.data.keyword.personalityinsightsfull}}-Service ist an jedem {{site.data.keyword.cloud_notm}}-Standort hoch verfügbar. Es bestehen keine Sicherung- und und Wiederherstellungsanforderungen zur Disaster-Recovery.
{: shortdesc}

## Hochverfügbarkeit
{: #high-availability}

Der {{site.data.keyword.personalityinsightsshort}}-Service ist hoch verfügbar und weist an keinem {{site.data.keyword.cloud_notm}}-Standort (zum Beispiel Dallas oder Washington, D. C.) einen Single Point of Failure auf. Die Hochverfügbarkeit des Service wird durch die von {{site.data.keyword.cloud_notm}} bereitgestellte MZR-Funktion (MZR: Multi-Zone Region) auf automatische und transparente Weise erzielt.

{{site.data.keyword.cloud_notm}} ermöglicht die Verwendung mehrerer Zonen, die keinen gemeinsamen Single Point of Failure an einem einzelnen Standort aufweisen. Außerdem wird ein automatischer Lastausgleich zwischen den Zonen in einer Region bereitgestellt.

## Disaster-Recovery
{: #disaster-recovery}

Der {{site.data.keyword.personalityinsightsshort}}-Service ist statusunabhängig. Er speichert keine Benutzerdaten in {{site.data.keyword.cloud_notm}}. Führen Sie bei Auftreten einer katastrophalen Störung in einer Region die folgenden Schritte durch:

1.  Erstellen Sie in einer anderen Region eine neue Instanz des {{site.data.keyword.personalityinsightsshort}}-Service.
1.  Bearbeiten Sie Ihre Anwendung so, dass sie die URL und Berechtigungsnachweise für die neue Serviceinstanz verwendet.
