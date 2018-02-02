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

# Entendendo um perfil
{: #output}

1.  <span style="color:#003F69">Como interpretar os resultados que são retornados pelo serviço?</span>

    -   [Interpretando os resultados numéricos](/docs/services/personality-insights/numeric.html) descreve como interpretar o percentil que é retornada pelo serviço. Ele também inclui informações sobre as porcentagens de comportamento e a opcionais resultados brutos e preferências de consumo que o serviço pode retornar.

1.  <span style="color:#003F69">Por que adicionar os resultados para os aspectos de uma dimensão não ceder a pontuação para essa dimensão?</span>

    -   [percentis para as características da personalidade](/docs/services/personality-insights/numeric.html#percentiles) responde esta pergunta. Em resumo, o serviço calcula o percentual normalizado para cada dimensão e aspecto de forma independente. Nenhum relacionamento matemático existe entre uma dimensão e suas facetas.

1.  <span style="color:#003F69">Quando que eu uso o resultado bruto em vez da pontuação de percentil?</span>

    -   [pontuações para características da personalidade bruta](/docs/services/personality-insights/numeric.html#rawScores) fornece insight sobre esta opção. Resumidamente, é possível usar um resultado bruto quando você deseja desenvolver um normalização customizado para um cenário específico ou quando comparação com uma população de amostra não é necessário. Se você precisar de conhecimento de como os resultados de um autor comparar com uma população de amostra, use as pontuações de percentil.

1.  <span style="color:#003F69">Como normalizar um resultado bruto para uma pontuação de percentil?</span>

    -   [Pontuações brutas para características da personalidade](/docs/services/personality-insights/numeric.html#rawScores) fornecem uma orientação de alto nível para normalizar uma pontuação bruta e discutir a abordagem da {{site.data.keyword.IBM_notm}} para a normalização.

1.  <span style="color:#003F69">Como interpretar o {{site.data.keyword.personalityinsightsshort}} visualização?</span>

    -   [Interpretando os resultados numéricos](/docs/services/personality-insights/numeric.html) descreve como interpretar os resultados numéricos que são mostrados na visualização.
