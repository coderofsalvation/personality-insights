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

# Visão geral para desenvolvedores
{: #overviewDevelopers}

É possível usar o serviço do {{site.data.keyword.personalityinsightsshort}} por meio de uma API de Representational State Transfer (REST) HTTP. Vários Kits de Desenvolvimento de Software (SDKs) também estão disponíveis para simplificar o desenvolvimento de aplicativos em vários idiomas.
{: shortdesc}

## Programando com o serviço
{: #programming}

Para produzir um perfil de personalidade, você envia o texto para o método HTTP `POST /v3/profile` do serviço. É possível enviar conteúdo em texto sem formatação, HTML ou JSON. O serviço pode retornar suas análises em formato JSON ou CSV

Para cada característica de personalidade, o serviço relata um *percentil*. O percentil é uma pontuação normalizada que descreve a extensão na qual a gravação do autor exibe uma característica dentro de uma população de amostra. Se solicitado, o serviço também retorna uma *pontuação bruta*, que é um valor absoluto que não é normalizado em relação a uma população de amostra. Se a entrada tiver registro de data e hora, o serviço fornecerá um resumo dos hábitos de gravação do autor por dia da semana e hora do dia. E, se solicitado, o serviço também retornará uma pontuação de probabilidade para cada uma de suas preferências de consumo disponíveis.

Para obter mais informações sobre como usar o serviço, consulte

-   [Solicitando um perfil](/docs/services/personality-insights?topic=personality-insights-input)
-   [Entendendo um perfil JSON](/docs/services/personality-insights?topic=personality-insights-output)
-   [Entendendo um perfil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV)

### Visualizando um perfil
{: #visualize}

O serviço fornece uma coleção de arquivos JavaScript que permitem a visualização gráfica de um perfil. Os scripts facilitam o uso do serviço com redes de distribuição de conteúdo e armazenamento em cache. Eles dependem de JavaScript, jQuery, HTML e SVG com a biblioteca de Data-Driven Documents (`D3.js`) para representar os resultados. Para obter mais informações sobre `D3.js`, consulte [d3js.org ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://d3js.org/){: new_window}.

### Suporte ao CORS
{: #CORS}

O serviço suporta o Cross-Origin Resource Sharing (CORS). O CORS permite que os clientes baseados em navegador façam solicitações assíncronas diretamente para o serviço por meio de scripts de front-end. O CORS evita a política de segurança da mesma origem, que, de outra maneira, impede essas solicitações.

Usando o CORS, as páginas da web podem solicitar recursos de um domínio estrangeiro, um que está fora do domínio do qual a solicitação se originou. Para obter mais informações, consulte [enable-cors.org ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://enable-cors.org/){: new_window}.

## Usando kits de desenvolvimento de software
{: #sdks}

SDKs estão disponíveis para o serviço {{site.data.keyword.personalityinsightsshort}} para simplificar o desenvolvimento de aplicativo. SDKs do {{site.data.keyword.ibmwatson}} estão disponíveis para muitas linguagens de programação e plataformas populares.

-   Para obter uma lista completa de SDKs e links para os SDKs no GitHub, consulte [Usando SDKs](/docs/services/watson?topic=watson-using-sdks).
-   Para obter informações detalhadas sobre todos os métodos dos SDK do Node, do Java, do Python, do Ruby e do Go para o serviço {{site.data.keyword.personalityinsightsshort}}, consulte a [Referência da API ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/apidocs/personality-insights){: new_window}.

## Aprendendo mais sobre o desenvolvimento de aplicativo
{: #learn-overview}

Para obter mais informações sobre como trabalhar com serviços do {{site.data.keyword.watson}} e do {{site.data.keyword.cloud}}, consulte as seções a seguir:

-   Para obter uma introdução ao trabalho com serviços do {{site.data.keyword.watson}} e o {{site.data.keyword.cloud_notm}}, consulte [Introdução ao {{site.data.keyword.watson}} e ao {{site.data.keyword.cloud_notm}}](/docs/services/watson?topic=watson-about).
-   Todas as novas instâncias de serviço usam o {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) para autenticação. As instâncias de serviço mais antigas podem continuar a usar o `{username}` e a `{password}` por meio de suas credenciais de serviço do Cloud Foundry existentes para autenticação. Para obter mais informações sobre a autenticação para o serviço, consulte a [atualização de serviço de 30 de outubro de 2018](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018) nas notas sobre a liberação.
-   A criação de log de solicitação está desativada para o serviço {{site.data.keyword.personalityinsightsshort}}. O serviço não registra ou retém dados de solicitações e respostas, independentemente de o cabeçalho da solicitação `X-Watson-Learning-Opt-Out`ser configurado.
