---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-27"

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

# Sobre
{: #about}

> **Atualização de serviço:** *o serviço {{site.data.keyword.personalityinsightsshort}} foi atualizado em 18 de novembro de 2018. O serviço agora está disponível no local de Londres do {{site.data.keyword.cloud}}. Para obter mais informações, consulte a [atualização de serviço de 18 de novembro de 2018](/docs/services/personality-insights?topic=personality-insights-release-notes#November2018b) nas notas sobre a liberação.*

O serviço {{site.data.keyword.personalityinsightsfull}} fornece uma interface de programação de aplicativos (API) para derivar insights de mídias sociais, dados corporativos ou outras comunicações digitais. O serviço usa análise linguística para inferir características intrínsecas da personalidade dos indivíduos com base em comunicações digitais, como e-mails, mensagens de texto, tweets e posts do fórum.
{: shortdesc}

O serviço infere, de mídia social potencialmente ruidosa, perfis de indivíduos que refletem suas características da personalidade. Ele também pode determinar as preferências de consumo dos indivíduos, que indicam a probabilidade de preferirem vários produtos, serviços e atividades.

## Características da personalidade
{: #models-index}

O serviço do {{site.data.keyword.personalityinsightsshort}} infere características da personalidade com base em três modelos primários:

-   As características da personalidade **Big
Five** representam o modelo mais amplamente usado para descrever
de forma geral como uma pessoa se envolve com o
mundo. O modelo inclui cinco dimensões principais: *Afabilidade*, *Estado consciente*, *Extroversão*, *Escala emocional* e *Abertura*. Cada dimensão tem seis aspectos que caracterizam ainda mais um indivíduo de acordo com a dimensão.
-   **Necessidades** descrevem quais aspectos de um produto são propensos a ressoarem com uma pessoa. O modelo inclui
12 necessidades características: *entusiasmo*, *harmonia*,
*curiosidade*, *ideal*, *proximidade*,
*autoexpressão*, *liberdade*, *amor*,
*praticidade*, *estabilidade*, *desafio*
e *estrutura*.
-   **Valores** descrevem os fatores de motivação que influenciam a tomada de decisão de uma pessoa. O modelo inclui cinco valores: *Autotranscendência / Ajudando os outros*, *Conservação / Tradição*, *Hedonismo / Desfrutando do prazer da vida*, *Autoaprimoramento / Alcançando o sucesso* e *Aberto à mudança / Entusiasmo*.

Para obter mais informações, consulte [Modelos de personalidade](/docs/services/personality-insights?topic=personality-insights-models).

## Preferências de consumo
{: #preferences-index}

Com base nas características de personalidade inferidas por meio do texto de entrada, o serviço também poderá retornar uma indicação das preferências de consumo do autor. As preferências de consumo indicam a probabilidade de o autor em buscar diferentes produtos, serviços e atividades. O serviço agrupa as preferências individuais em oito categorias: *Compras*, *Música*, *Filmes*, *Leitura e aprendizado*, *Saúde e atividade*, *Voluntariado*, *Preocupação ambiental* e *Empreendedorismo*. Cada categoria contém no mínimo uma e no máximo uma dúzia de preferências individuais.

Para obter mais informações, consulte [Preferências de consumo](/docs/services/personality-insights?topic=personality-insights-preferences).

## Benefícios do serviço
{: #benefits}

Como um serviço principal da plataforma {{site.data.keyword.ibmwatson}}, o serviço do {{site.data.keyword.personalityinsightsshort}} pode fornecer insights que ajudam os negócios

-   A entender seus clientes em um nível mais profundo conhecendo as preferências de seus clientes, melhorando a satisfação dos clientes e fortalecendo as relações com os clientes.
-   A melhorar aquisição, retenção e engajamento dos cientes.
-   A guiar engajamentos e interações altamente personalizados para melhor customizar seus produtos, serviços, campanhas e comunicações para clientes individuais.

Para obter mais informações sobre como você pode se beneficiar do serviço, consulte [Casos de uso](/docs/services/personality-insights?topic=personality-insights-usecases).

## Suporte ao idioma
{: #languages-index}

O serviço suporta os idiomas a seguir. É possível usar qualquer combinação dos idiomas suportados para a solicitação e a resposta, mas todo o texto de entrada deve estar no mesmo idioma. Para obter mais informações, veja [Especificando linguagens de solicitação e resposta](/docs/services/personality-insights?topic=personality-insights-input#languages-input).

<table style="width:75%">
  <caption>Tabela 1. Idiomas suportados</caption>
  <tr>
    <th style="width:50%; text-align:center">
      Idiomas da solicitação
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
      Francês<br/>
      Alemão<br/>
      Italiano<br/>
      Chinês Simplificado<br/>
      Chinês Tradicional
    </td>
  </tr>
</table>

## HIPAA
{: hipaa}

O suporte ao Health Insurance Portability and Accountability Act (HIPAA) dos EUA não se aplica ao serviço {{site.data.keyword.personalityinsightsshort}}. O serviço é sem estado. Ele não armazena dados do usuário no {{site.data.keyword.cloud_notm}}.

## Saiba mais sobre o serviço
{: #learn-index}

-   Uma [demo rápida do ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://personality-insights-demo.ng.bluemix.net/){: new_window}do serviço {{site.data.keyword.personalityinsightsshort}}analisa o texto de entrada para desenvolver um retrato de personalidade que inclui preferências de consumo para o autor.
-   Os aplicativos em {{site.data.keyword.watson}} [Kits do iniciador ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://www.ibm.com/watson/developercloud/starter-kits.html){: new_window} demonstram o serviço.
-   [O serviço em ação](/docs/services/personality-insights?topic=personality-insights-applied) e [A ciência por trás do serviço](/docs/services/personality-insights?topic=personality-insights-science) fornecem informações sobre a pesquisa que embasa o serviço.
-   O serviço {{site.data.keyword.personalityinsightsshort}} no [Catálogo do {{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/catalog/services/personality-insights/){: new_window} descreve os planos de precificação que estão disponíveis para o serviço.
