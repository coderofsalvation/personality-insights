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

# Interpretando os resultados numéricos
{: #numeric}

O {{site.data.keyword.personalityinsightsshort}} serviço retorna resultados numéricos para cada personalidade e características comportamentais e para cada preferência consumo. Os valores diferem nas informações que eles fornecem.
{: shortdesc}

> **Nota:** Para entrada árabe e coreano, o serviço é incapaz de produzir percentis significativas e pontuações brutos para um número de características da personalidade. Para obter mais informações, consulte [Limitações para entrada árabe e coreano](#limitations).

## Percentis para as características de personalidade
{: #percentiles}

Para cada pedido, o serviço sempre relata uma pontuação normalizada como um `percentual` para cada Big Five, Valores e Necessidades, características de personalidade. Pontuações normalizadas representam uma classificação de percentil para cada característica com base nas qualidades inferidas a partir do texto de entrada. O serviço calcula as pontuações normalizadas comparando o resultado bruto para texto do autor com resultados de uma população de amostra. O serviço relata cada percentis como um duplo no intervalo de 0 1.

Por exemplo, um percentil de `0,64980796071382` para a personalidade característica `big5_extraversion` indica que o autor do texto marcou no 65º percentil para essa característica. A escrita do autor exibe a tendência de uma extensão que seja maior que 64 e menor que 34 da população de amostra. A precisão do percentual depende do número de palavras que foram enviados como entrada com o pedido; para obter mais informações, consulte [Fornecendo suficiente de entrada](/docs/services/personality-insights/input.html#sufficient).

> **Nota:** Nenhum relacionamento matemático existe entre os percentis relatados para dimensões e aspectos Big Five. O serviço calcula o percentual normalizado para cada dimensão e aspecto de forma independente com base em correlações entre as pontuações de pesquisa participantes ' para essa dimensão ou aspecto e as palavras que eles usam. Portanto, mesmo que os aspectos forneçam descrições de dimensões mais finas, a adição das pontuações para os seis aspectos de uma dimensão não produz necessariamente o percentil para essa dimensão. O mesmo é verdadeiro para pontuações brutos.

## Pontuações brutas para características de personalidade
{: #rawScores}

Se você especificar `true` para o `raw_scores` parâmetro de consulta da solicitação, o serviço relata um `raw_score` para cada característica personalidade. Pontuações brutos representam a pontuação para a característica específica baseada somente em texto do autor e o modelo para essa característica, sem comparar os resultados para uma população de amostra. Pontuações bruto pode ser interpretado como o pontuações a autora receberia de tomar um teste de personalidade.

O serviço relata cada pontuação bruto como um duplo no intervalo de 0 1. Uma pontuação maior geralmente indica uma probabilidade maior que o autor tem essa característica. No entanto, pontuações brutos devem ser considerados no agregado: O intervalo de valores em prática pode ser muito menor que 0 e 1, então uma pontuação individual deve ser considerado no contexto das pontuações geral e seu intervalo. Mas em geral, uma pontuação bruto, por exemplo, `0,56817738781166` para a personalidade característica `big5_extraversion` indica que o autor deve ter conseguido esta pontuação em um teste de personalidade. Compare esse resultado bruto com o percentil normalizado relatado para o mesmo autor e característica na seção anterior.

O serviço faz pontuações brutos disponíveis para usuários que desejam aplicar uma normalização customizado para um cenário específico ou que não requerem uma comparação com uma população de amostra. Os usuários que querem saber como as características do autor comparar com uma população grande amostra pode usar as pontuações normalizadas. Os usuários que desejam obter seus próprios índices de percentil normalizados dos dados brutos podem comparar as pontuações brutas com uma população de amostra diferente e aplicar uma abordagem diferente à normalização.

Para normalizar uma pontuação bruto para um percentil para uma característica específica, comparar o resultado bruto com uma população de amostra para o qual a média e o desvio padrão para a característica são conhecidos. Por exemplo, {{site.data.keyword.IBM_notm}} realizou estudos para reunir dados de uma população grande amostra de usuários do Twitter. {{site.data.keyword.IBM_notm}} calcular as pontuações dos usuários para cada uma das características da personalidade e, em seguida, estabeleceu a média e desvio padrão para cada característica. Para calcular a pontuação de percentil para uma pontuação bruto deduzido da análise de texto de entrada, o serviço usa o média e desvio padrão derivado da população no Twitter sua amostra para essa característica.

## Porcentagens de características comportamentais
{: #percentages}

Se você enviar dados JSON cujos itens de conteúdo têm os registros, o serviço relata um `porcentagem` para cada característica comportamental. As características comportamentais identificam a distribuição temporal da entrada. A porcentagem indica quantos dos itens de conteúdo ocorreu durante cada dia da semana e hora do dia. Por exemplo, uma porcentagem de `0,4561049445005` para o comportamento característica `behavior_0000` significa que cerca de 46 dos itens de conteúdo foram criados entre os horários de meia-noite e 1:00 a:m:

## Pontuações para as preferências de consumo
{: #scores}

Se você especificar `true` para o `consumption_preferences` parâmetro de consulta da solicitação, o serviço relata preferências de consumo que incluem um `score` para cada preferência. O serviço obtém a pontuação do características de personalidade que deduz do texto de entrada. A pontuação é um duplo que indica a probabilidade do autor do texto preferir o item. Não é uma indicação de preferência, não uma porcentagem normalizada.

Para algumas preferências, a pontuação é um dos três valores a seguir:

-   `0,0`: O autor é muito improvável que preferir o item. Para algumas preferências, você pode interpretar o valor como significa que o autor tem um nível muito baixo de interesse.
-   `0,5`: O autor é neutra com relação ao item. Para algumas preferências, o valor pode significar que o autor tem um nível médio de interesse.
-   `1,0`: O autor é muito provável que preferir o item. Para algumas preferências, o valor indica um alto nível de interesse.

Para outras preferências, o resultado representa um valor binário. O autor do texto de entrada é improvável ou (`0,0`) ou provável (`1,0`) para ter um interesse no item, ou o autor tem também um nível baixo ou alto de interesse. Em alguns casos, o resultado pode representar um simples sim ou não resposta (por exemplo, é o autor deve ter experiência como voluntário por causas sociais).

Para obter uma lista completa de todas as preferências por categoria e o intervalo de seus resultados, consulte [Consumo Preferências](/docs/services/personality-insights/preferences.html).

## Limitações para entrada árabe e coreano
{: #limitations}

Para entrada árabe e coreano, modelos de serviço são incapazes de produzir resultados significativos para um subconjunto de características da personalidade. Para as seguintes características, pontuações de percentil normalizados são sempre `0,5` e pontuações brutos são sempre assim da distribuição original. O campo `significant` para cada uma dessas características é sempre `false`. Você *não* contam com os resultados para essas características como parte do perfil personalidade do autor.

<table>
  <caption>Tabela 1. Características cujos resultados não são significativos</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      Características
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      Resultados árabe que<br/>Não são significativos
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      Coreano que resultados<br/>Não são significativos
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Grande cinco dimensões
    </td>
    <td style="text-align:left; vertical-align:top">
      Faixa emocional
    </td>
    <td style="text-align:left; vertical-align:top">
      Nenhum
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Big Five Aspectos
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; line-height:110%; padding:0px">
          *Afabilidade*: Altruísmo, Cooperação, Modéstia e Confiança
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Estado consciente*: liderança de conquista e obediência
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Extroversão*: alegria e simpatia (de saída)
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Emotivas intervalo*: Raiva (Chamas), Propenso a se preocupar, Immoderation e auto-consciência
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Openness*: Adventurousness, imaginação e intelecto
        </li>
      </ul>
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; padding:0px">
          *Extroversão*: busca de excitação
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Necessidades
    </td>
    <td style="text-align:left; vertical-align:top">
      Ideal, Liberty, amor, praticidade, e Estrutura
    </td>
    <td style="text-align:left; vertical-align:top">
      Liberty e Estabilidade
    </td>
  </tr>
  </tr>
    <td style="text-align:left; vertical-align:top">
      Valores
    </td>
    <td style="text-align:left; vertical-align:top">
      Aprimoramento de Autoatendimento
    </td>
    <td style="text-align:left; vertical-align:top">
      Conservação
    </td>
  </tr>
</table>
