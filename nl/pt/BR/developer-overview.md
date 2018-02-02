---

Copyright: years: 2015, 2017 lastupdated: "2017-10-12"

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

# Visão Geral para desenvolvedores
{: #overviewDevelopers}

É possível usar o {{site.data.keyword.personalityinsightsshort}} serviço por meio de um HTTP Representational State Transfer (REST) API. Vários kits de desenvolvimento de software (SDKs) também estão disponíveis para simplificar o desenvolvimento de aplicativos em vários idiomas e ambientes.
{: shortdesc}

## Programando com o serviço
{: #programming}

Para produzir um perfil de personalidade, você envia o texto para o serviço HTTP `POST /v3/profile` método. Você pode enviar texto simples, HTML ou conteúdo JSON. O serviço pode retornar suas análises em formato JSON ou CSV

Para cada característica de personalidade, o serviço relata um *percentual*, que é uma pontuação normalizada que descreve a extensão na qual a gravação do autor exibe uma característica em uma população de amostra. Se solicitado, o serviço também retorna um *bruto pontuação*, que é um valor absoluto que não está normalizado para uma população de amostra. Se a entrada for data, o serviço fornece um resumo dos hábitos de escrita do autor com relação ao dia da semana e hora do dia. E se solicitado, o serviço também retorna uma pontuação para cada probabilidade de seu consumo de preferências disponíveis.

Para obter mais informações sobre como usar o serviço, consulte

-   [Solicitando um perfil](/docs/services/personality-insights/input.html)
-   [Entendendo um perfil JSON](/docs/services/personality-insights/output.html)
-   [Entendendo um perfil CSV](/docs/services/personality-insights/output-csv.html)

### Visualizando um perfil
{: #visualize}

O serviço fornece uma coleção de arquivos JavaScript que permitem a visualização gráfica de um perfil. Os scripts facilitam uso do serviço com redes de distribuição em cache e conteúdo. Eles dependem de JavaScript, jQuery, HTML e SVG com a biblioteca de Dados-Driven Documents (`D3.js`) para representar os resultados. Para obter informações sobre esses arquivos do lado do cliente, consulte os aplicativos de amostra citados em [Usando Software Development Kits](#sdks); para obter mais informações sobre o `D3.js`, consulte [d3js.org ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://d3js.org/){: new_window}.

### Suporte ao CORS
{: #CORS}

O serviço suporta Cross-Origin Resource Sharing (CORS) para permitir que os clientes baseados em navegador para fazer solicitações assíncronas diretamente para o serviço de scripts de front-end. CORS permite que os clientes solicitar recursos de um domínio que está fora do domínio a partir do qual o pedido foi originado; ele permite que aplicativos da web alternativa a mesma política de segurança de origem, que seja evita que tais pedidos. Para obter mais informações, consulte [enable-cors.org ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://enable-cors.org/){: new_window}.

## Usando Software Development Kits
{: #sdks}

O serviço {{site.data.keyword.personalityinsightsshort}} suporta um número de SDKs para desenvolvimento de aplicativo simplificado. Os SDKs estão disponíveis para muitas linguagens e plataformas de programação populares, incluindo Node.js, Java, Python e Apple&reg; iOS. Para obter uma lista completa de SDKs e informações sobre como usá-los, consulte [{{site.data.keyword.watson}} SDKs](/docs/services/watson/getting-started-sdks.html). Todos os SDKs estão disponíveis a partir do [watson-developer-cloud namespace ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/watson-developer-cloud){: new_window} no GitHub.

O serviço também disponibiliza os aplicativos de amostra a seguir para ajudá-lo a iniciar:

-   Você pode acessar um aplicativo que usa o SDK do Node.js no [personalidade-insights-nodejs repositório ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window}.
-   Você pode acessar um aplicativo que usa o SDK Java no [personalidade-insights-java repositório ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/watson-developer-cloud/personality-insights-java){: new_window}.

Para desenvolvimento móvel, consulte o [{{site.data.keyword.watson}} Developer Cloud Swift SDK ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/watson-developer-cloud/swift-sdk){: new_window}. Todos os SDKs suportam a autenticação usando suas credenciais de serviço ou um token de autenticação.

## Aprender mais sobre o desenvolvimento de aplicativos
{: #learn}

O {{site.data.keyword.personalityinsightsshort}} serviço suporta dois modelos de programação típica: *interação direta*, no qual o cliente se comunica com o serviço diretamente; e *retransmissão por meio de um proxy*, na qual a troca cliente e o serviço todos os dados (pedidos e resultados) através de um aplicativo proxy que reside em {{site.data.keyword.Bluemix_short}}.

Para obter mais informações sobre como trabalhar com o {{site.data.keyword.watson}} Developer Cloud serviços e {{site.data.keyword.Bluemix_notm}}, consulte o seguinte:

-   Para obter uma introdução ao trabalho com {{site.data.keyword.watson}} serviços e {{site.data.keyword.Bluemix_notm}}, consulte [Introdução ao {{site.data.keyword.watson}} e {{site.data.keyword.Bluemix_notm}}](/docs/services/watson/index.html).
-   Para um idioma, independente introdução ao desenvolver aplicativos de serviços no {{site.data.keyword.Bluemix_notm}} {{site.data.keyword.watson}} , consulte [{{site.data.keyword.Bluemix_notm}} abordagens de desenvolvimento](/docs/services/watson/getting-started-bluemix.html).
-   Para obter informações sobre os dois modelos de programação disponíveis para desenvolvimento de aplicativos do {{site.data.keyword.watson}}, consulte [Modelos de programação para serviços{{site.data.keyword.watson}}](/docs/services/watson/getting-started-develop.html):
    -   Com afinação através de um proxy, o cliente depende de um servidor proxy que reside em {{site.data.keyword.Bluemix_notm}} para se comunicar com o serviço; ele transmite todas as solicitações por meio do aplicativo proxy. Enviando solicitações por meio de um proxy depende apenas em credenciais de serviço para autenticar com o serviço; consulte [Serviço credenciais para {{site.data.keyword.watson}} serviços](/docs/services/watson/getting-started-credentials.html).
    -   Com a interação direta, o cliente usa o aplicativo proxy no {{site.data.keyword.Bluemix_notm}} apenas para obter um token de autenticação para o serviço, após o qual ele se comunica diretamente com o serviço. Interação Direta usa credenciais de serviço apenas para obter um token; consulte [Tokens para autenticação](/docs/services/watson/getting-started-tokens.html).
-   Para obter informações sobre como controlar a solicitação padrão de criação de log que é executada para todos os {{site.data.keyword.watson}} serviços, consulte [Controlando solicitação de criação de log para {{site.data.keyword.watson}} serviços](/docs/services/watson/getting-started-logging.html).
