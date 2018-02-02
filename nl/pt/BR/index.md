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

# Sobre
{: #about}

> **Serviço de atualização:** *O {{site.data.keyword.personalityinsightsshort}} serviço foi atualizado em 13 de outubro de 2017. Cada `Peculiaridade` objeto de um perfil de personalidade agora inclui um `significativo` campo para indicar se uma característica da personalidade é significativo para o idioma de entrada. O campo identifica as características para o qual os modelos do serviço são incapazes de gerar resultados significativos para entrada árabe e coreano. A versão da interface para a liberação é `2017-10-13`. Para obter mais informações sobre isso e todas as atualizações para o serviço, consulte o [Release notes](/docs/services/personality-insights/release-notes.html).*

O {{site.data.keyword.personalityinsightsfull}} serviço fornece uma Interface de Programação de Aplicativos (API) para derivar insights de mídias sociais, dados corporativos, ou outras comunicações digitais. O serviço usa análise linguística para indicar características intrínsecas da personalidade dos indivíduos de comunicações digitais, como e-mails, mensagens de texto, tweets, e posts do fórum.
{: shortdesc}

O inferirá serviço, de mídias sociais potencialmente ruidosas, retratos de indivíduos que refletem suas características da personalidade. Ele também pode determinar as preferências de consumo dos indivíduos, que indicam a probabilidade de que vários produtos, serviços e atividades.

## As características de personalidade
{: #models}

O serviço {{site.data.keyword.personalityinsightsshort}} infere características da personalidade com base em três modelos primárias:

-   As características da personalidade **Big
Five** representam o modelo mais amplamente usado para descrever
de forma geral como uma pessoa se envolve com o
mundo. O modelo inclui cinco dimensões primárias: *Afabilidade*, *inteligênica*, *Extroversão*, *Emotivas intervalo*, e *Openness*. Cada dimensão possui seis máscaras que caracterizam ainda mais um indivíduo, de acordo com a dimensão.
-   **Necessidades** descrevem quais
aspectos de um produto repercutirão com uma pessoa. O modelo inclui
12 necessidades características: *entusiasmo*, *harmonia*,
*curiosidade*, *ideal*, *proximidade*,
*autoexpressão*, *liberdade*, *amor*,
*praticidade*, *estabilidade*, *desafio*
e *estrutura*.
-   **Valores** descrevem os fatores de motivação que influenciam a tomada de decisão de uma pessoa. O modelo inclui cinco valores: *Auto-transcendência / Ajudar outros*, *hedonismo/ter prazer*, *prazer na vida*, *de sucesso*, e *Abrir para alterar / entusiasmo*.

Para obter mais informações, consulte [Personality modelos](/docs/services/personality-insights/models.html).

## Preferências de consumo
{: #preferences}

Com base nas características da personalidade inferido a partir do texto de entrada, o serviço também pode retornar uma indicação de preferências de consumo do autor. Consumo preferências indicam a probabilidade do autor buscar diferentes produtos, serviços e atividades. O serviço agrupa as preferências individuais em oito categorias: *Compras*, *Música*, *Filmes*, *Leitura e aprendizado*, *Saúde e atividade*, *Voluntariado*, *Preocupação ambiental* e *Empreendedorismo*. Cada categoria contém de um a mais de uma dúzia de preferências individuais.

Para obter mais informações, consulte [Consumo Preferências](/docs/services/personality-insights/preferences.html).

## Benefícios do serviço
{: #benefits}

Como um serviço principal do {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} plataforma, o {{site.data.keyword.personalityinsightsshort}} serviço pode fornecer insights que ajudam as empresas

-   Entenda seus clientes em um nível mais profundo por aprender as preferências dos clientes, melhorar a satisfação do cliente, e fortalecer as relações do cliente.
-   Melhore a aquisição de cliente, retenção e engajamento.
-   Guia compromissos e interações altamente personalizados para melhor ajustar seus produtos, serviços, campanhas e comunicações para clientes individuais.

Para obter mais informações sobre como você pode se beneficiar do serviço, consulte [Usar casos](/docs/services/personality-insights/usecases.html).

## Suporte de Idioma
{: #languages}

O serviço suporta os seguintes idiomas. É possível usar qualquer combinação de idiomas suportados para a solicitação e resposta, mas tudo texto de entrada devem estar no mesmo idioma. Para obter mais informações, consulte [Especificando de pedido e resposta idiomas](/docs/services/personality-insights/input.html#languages).

<table style="width:75%">
  <caption>Tabela 1. Idiomas Suportados</caption>
  <tr>
    <th style="width:50%; text-align:center">
      Solicitação de idiomas
    </th>
    <th style="width:50%; text-align:center">
Idiomas da resposta
    </th>
  </tr>
  <tr>
    <td style="text-align:center; vertical-align:top">
      Árabe<br/>
      Inglês<br/>
      Japonês<br/>
      Coreano<br/>
      Espanhol
    </td>
    <td style="text-align:center; vertical-align:top">
      Árabe<br/>
      Inglês<br/>
      Japonês<br/>
      Coreano<br/>
      Espanhol<br/>
      Português do Brasil<br/>
      França<br/>
      Alemanha<br/>
      Italiano<br/>
      Chinês Simplificado<br/>
      Chinês Tradicional
    </td>
  </tr>
</table>

## Saiba mais sobre o serviço
{: #learn}

-   Um [rápido demo ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://personality-insights-demo.ng.bluemix.net/){: new_window} do {{site.data.keyword.personalityinsightsshort}} serviço permite analisar texto de entrada para desenvolver um retrato personalidade que inclui preferências de consumo para o autor.
-   Aplicativos no {{site.data.keyword.watson}} Developer Cloud [Starter Kits ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://www.ibm.com/watson/developercloud/starter-kits.html){: new_window} demonstram o serviço.
-   [O serviço em ação](/docs/services/personality-insights/applied.html) e [A ciência por trás do serviço](/docs/services/personality-insights/science.html) fornecem informações sobre a pesquisa que suporta o serviço.
-   O [{{site.data.keyword.personalityinsightsshort}} serviços no {{site.data.keyword.Bluemix_short}} Catálogo do ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.ng.bluemix.net/catalog/services/personality-insights/){: new_window} descreve os planos de precificação que estão disponíveis para o serviço.
