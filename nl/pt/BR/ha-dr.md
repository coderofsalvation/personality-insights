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

# Alta disponibilidade e recuperação de desastre
{: #ha-dr}

O serviço {{site.data.keyword.personalityinsightsfull}}está altamente disponível dentro de qualquer local {{site.data.keyword.cloud_notm}}. Ele não possui requisitos de backup e restauração para recuperação de desastre.
{: shortdesc}

## Alta disponibilidade
{: #high-availability}

O serviço {{site.data.keyword.personalityinsightsshort}}está altamente disponível sem nenhum ponto único de falha em qualquer local de {{site.data.keyword.cloud_notm}}(por exemplo, Dallas ou Washington, DC). O serviço obtém alta disponibilidade de forma automática e transparente por meio do recurso MZR (Multizona Region) fornecido pelo {{site.data.keyword.cloud_notm}}.

O{{site.data.keyword.cloud_notm}}permite diversas zonas que não compartilham um único ponto de falha em um único local. Ele também fornece balanceamento de carga automático entre as zonas dentro de uma região.

## Recuperação de desastre
{: #disaster-recovery}

O serviço {{site.data.keyword.personalityinsightsshort}} é sem estado. Ele não armazena dados do usuário no {{site.data.keyword.cloud_notm}}. No caso de uma falha catastrófica em uma região, conclua as etapas a seguir:

1.  Crie uma nova instância do serviço {{site.data.keyword.personalityinsightsshort}} em uma região diferente.
1.  Modifique o seu aplicativo para usar a URL e as credenciais para a nova instância de serviço.
