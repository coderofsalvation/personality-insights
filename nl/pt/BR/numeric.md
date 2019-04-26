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

# Interpretando os resultados numéricos
{: #numeric}

O serviço do {{site.data.keyword.personalityinsightsshort}} retorna resultados numéricos para cada uma das características de personalidade e comportamentais e para cada preferência de consumo. Os valores diferem nas informações que fornecem.
{: shortdesc}

Para entrada em árabe e coreano, o serviço é incapaz de produzir percentis significativos e pontuações brutas para um número de características de personalidade. Para obter mais informações, veja [Limitações para entrada em árabe e coreano](#limitations).
{: note}

## Percentis para características da personalidade
{: #percentiles}

Para cada solicitação, o serviço sempre relata uma pontuação normalizada como um `percentile` para característica da personalidade do Big Five, Valores e Necessidades. Pontuações normalizadas representam uma classificação de percentil para cada característica que é baseada em qualidades que o serviço infere do texto de entrada. O serviço calcula as pontuações normalizadas comparando a pontuação bruta do texto do autor com resultados de uma população de amostra. O serviço relata cada percentil como um duplo no intervalo de 0 a 1.

Por exemplo, um percentil de `0.64980796071382` para a característica da personalidade `big5_extraversion` indica que a pontuação do autor para essa característica está no 65º percentil. A composição do autor exibe a tendência de uma extensão maior que 64 por cento e menor que 34 por cento da população de amostra. A precisão do percentil depende do número de palavras que foram enviadas como entrada com a solicitação. Para obter mais informações, consulte [Fornecendo entrada suficiente](/docs/services/personality-insights?topic=personality-insights-input#sufficient).

Não existe nenhum relacionamento matemático entre os percentis que são relatados para dimensões e aspectos do Big Five. O serviço calcula o percentil normalizado para cada dimensão e aspecto independentemente com base nas correlações entre pontuações dos participantes da pesquisa de opinião para essa dimensão ou esse aspecto e as palavras que eles usam. Portanto, embora aspectos forneçam descrições de dimensões com granulação mais fina, somar as pontuações dos seis aspectos de uma dimensão não mostra como resultado necessariamente o percentil dessa dimensão. O mesmo é verdadeiro para pontuações brutas.
{: note}

## Pontuações brutas para características da personalidade
{: #rawScores-numeric}

Se você especificar `true` para o parâmetro de consulta `raw_scores` da solicitação, o serviço relatará um `raw_score` para cada característica da personalidade. Pontuações brutas representam a pontuação para uma característica que é baseada exclusivamente no texto do autor e no modelo para essa característica. Quando ele gera pontuações brutas, o serviço não compara os resultados com uma população de amostra. Pontuações brutas podem ser interpretadas como as pontuações que o autor receberia se fizesse um teste de personalidade.

O serviço relata cada pontuação bruta como um duplo no intervalo de 0 a 1. Uma pontuação mais alta geralmente indica que o autor tem mais probabilidade de ter essa característica. No entanto, pontuações brutas devem ser consideradas em agregado: o intervalo de valores na prática pode ser muito menor que 0 a 1; portanto, uma pontuação individual deve ser considerada no contexto das pontuações gerais e seu intervalo. Mas, em geral, uma pontuação bruta, por exemplo, `0.56817738781166` para a característica da personalidade `big5_extraversion` indica que o autor provavelmente teria atingido essa pontuação em um teste de personalidade. Compare essa pontuação bruta ao percentil normalizado relatado para o mesmo autor e característica na seção anterior.

O serviço disponibiliza pontuações brutas para usuários que desejam aplicar uma normalização customizada para um cenário específico ou que não requerem uma comparação com uma população de amostra. Os usuários que desejam saber como as características do autor se comparam a uma grande população de amostra podem usar as pontuações normalizadas. Os usuários que desejam derivar suas próprias pontuações em percentil normalizadas com base nos dados brutos podem comparar as pontuações brutas a uma população de amostra diferente e aplicar uma abordagem diferente à normalização.

Para normalizar uma pontuação bruta a um percentil para uma característica específica, compare a pontuação bruta a uma população de amostra para a qual a média e o desvio padrão da característica são conhecidos. Por exemplo, a {{site.data.keyword.IBM_notm}} realizou estudos para reunir dados de uma grande população de amostra de usuários do Twitter. A {{site.data.keyword.IBM_notm}} calculou as pontuações dos usuários para cada uma das características da personalidade e, em seguida, estabeleceu a média e o desvio padrão para cada característica. Para calcular a pontuação do percentil para uma pontuação bruta que ele infere de sua análise do texto de entrada, o serviço usa o desvio médio e padrão que ele derivou de sua população do Twitter de amostra para essa característica.

## Porcentagens de características comportamentais
{: #percentages}

Se você enviar dados JSON cujos itens de conteúdo têm os registros de data e hora, o serviço relatará um `percentage` para cada característica comportamental. As características comportamentais identificam a distribuição temporal da entrada. A porcentagem indica quantos dos itens de conteúdo ocorreram durante cada dia da semana e hora do dia. Por exemplo, uma porcentagem de `0.4561049445005` para a característica comportamental `behavior_0000` significa que cerca de 46 dos itens de conteúdo foram criados entre meia-noite e 1h.

## Pontuações para preferências de consumo
{: #scores}

Se você especificar `true` para o parâmetro de consulta `consumption_preferences` da solicitação, o serviço relatará preferências de consumo que incluem um `score` para cada preferência. O serviço deriva a pontuação das características da personalidade que infere do texto de entrada. A pontuação é um duplo que indica a probabilidade de o autor do texto preferir o item. É uma indicação de preferência, não uma porcentagem normalizada.

Para algumas preferências, a pontuação é um dos três valores:

-   `0.0`: o autor muito improvavelmente prefere o item. Para algumas preferências, é possível interpretar o valor como significando que o autor tem um nível baixo de interesse.
-   `0.5`: O autor é neutro sobre o item. Para algumas preferências, o valor pode significar que o autor tem um nível médio de interesse.
-   `1.0`: o autor muito provavelmente prefere o item. Para algumas preferências, o valor indica um alto nível de interesse.

Para outras preferências, a pontuação representa um valor binário. O autor do texto de entrada improvavelmente (`0.0`) ou provavelmente (`1.0`) tem interesse no item ou o autor tem um nível de interesse baixo ou alto. Em alguns casos, a pontuação pode representar uma simples resposta de sim ou não (por exemplo, se o autor provavelmente terá experiência como voluntário de causas sociais).

Para obter uma lista completa de todas as preferências por categoria e do intervalo de seus resultados, consulte [Preferências de consumo](/docs/services/personality-insights?topic=personality-insights-preferences).

## Limitações para entrada em árabe e coreano
{: #limitations}

Para entrada em árabe e coreano, os modelos do serviço são incapazes de produzir resultados significativos para um subconjunto de características da personalidade. Para as características a seguir, pontuações em percentil normalizadas sempre são `0.5` e pontuações brutas sempre são a média da distribuição original. O campo `significant` de cada uma dessas características sempre é `false`. *Não* se baseie nos resultados dessas características como parte do perfil da personalidade do autor.

<table>
  <caption>Tabela 1. Características cujos resultados não são significativos</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      Características
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      Resultados do árabe que<br/>não são significativos
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      Resultados do coreano que<br/>não são significativos
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Cinco principais dimensões
    </td>
    <td style="text-align:left; vertical-align:top">
      Escala emocional
    </td>
    <td style="text-align:left; vertical-align:top">
      Nenhum
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Cinco principais aspectos
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; line-height:110%; padding:0px">
          *Afabilidade*: Altruísmo, Cooperação, Modéstia e Confiança
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Estado consciente*: Esforço para realização e Obediência
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Extroversão*: Alegria e Simpatia (Extrovertido)
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Escala emocional*: Raiva (Explosivo), Propenso a se preocupar, Sem moderação e Autoconsciência
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Abertura*: Aventura, Imaginação e Intelecto
        </li>
      </ul>
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; padding:0px">
          *Extroversão*: Busca por entusiasmo
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Necessidades
    </td>
    <td style="text-align:left; vertical-align:top">
      Ideal, Liberdade, Amor, Praticidade e Estrutura
    </td>
    <td style="text-align:left; vertical-align:top">
      Liberdade e Estabilidade
    </td>
  </tr>
  </tr>
    <td style="text-align:left; vertical-align:top">
      Valores
    </td>
    <td style="text-align:left; vertical-align:top">
      Autoaprimoramento
    </td>
    <td style="text-align:left; vertical-align:top">
      Conservação
    </td>
  </tr>
</table>
