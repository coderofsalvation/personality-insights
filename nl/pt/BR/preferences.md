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

# Preferências de consumo
{: #preferences}

O serviço do {{site.data.keyword.personalityinsightsshort}} infere as características de personalidade de um autor para três modelos: Big Five, Necessidades e Valores. Com base em seus resultados para esses modelos, o serviço também pode produzir preferências de consumo para o autor do texto de entrada. Configure o parâmetro de consulta `consumption_preferences` para `true` para que uma solicitação obtenha preferências de consumo.
{: shortdesc}

O serviço agrupa as mais de 40 preferências de consumo em oito categorias de alto nível. As preferências indicam a probabilidade do autor de preferir diferentes produtos, serviços e atividades. Por exemplo, o serviço pode identificar

-   As inclinações do autor para roupas (conforto versus moda) e automóveis (custo versus segurança).
-   As inclinações do autor em direção a diferentes gêneros de música, filmes e leitura.
-   As atitudes do autor sobre o ambiente e o voluntariado.

Os negócios usam modelos de personalidade do serviço para entender melhor seus clientes e projetar e desenvolver campanhas, produtos e serviços mais personalizados e direcionados. As preferências de consumo tornam ainda mais fácil agir sobre os resultados do serviço. As empresas podem facilmente obter e responder a uma lista de preferências que estão associadas às características dominantes de um indivíduo. Para obter mais informações sobre possíveis usos das preferências de consumo, consulte [Casos de uso](/docs/services/personality-insights?topic=personality-insights-usecases) e [O serviço em ação](/docs/services/personality-insights?topic=personality-insights-applied).

As seções a seguir listam e descrevem as preferências de consumo que o serviço pode retornar. Para obter mais informações sobre como interpretar as preferências numéricas, consulte [Pontuações para preferências de consumo](/docs/services/personality-insights?topic=personality-insights-numeric#scores). Para obter informações sobre como a {{site.data.keyword.IBM_notm}} desenvolveu as preferências, consulte [A ciência por trás do serviço](/docs/services/personality-insights?topic=personality-insights-science).

## Preferências de compras
{: #shopping}

Preferências de compras indicam o interesse do autor em diferentes tipos de compras, até que ponto os hábitos de compra do autor são influenciados por diferentes fontes externas e os hábitos de gastos do autor. O ID e o nome da categoria são `consumption_preferences_shopping` e `Purchasing Preferences`. A categoria tem 12 preferências.

<table>
  <caption>Tabela 1. Preferências de compras</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferência de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Pontuações
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_ownership_cost</code>
    </td>
    <td style="text-align:left">
      Propenso a ser sensível ao custo de propriedade ao comprar automóveis
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_safety</code>
    </td>
    <td style="text-align:left">
      Propenso a preferir segurança ao comprar automóveis
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_quality</code>
    </td>
    <td style="text-align:left">
      Propenso a preferir qualidade ao comprar roupas
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_style</code>
    </td>
    <td style="text-align:left">
      Propenso a preferir estilo ao comprar roupas
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_comfort</code>
    </td>
    <td style="text-align:left">
      Propenso a preferir conforto ao comprar roupas
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_brand_name</code>
    </td>
    <td style="text-align:left">
      Propenso a ser influenciado pelo nome da marca ao comprar produtos
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_utility</code>
    </td>
    <td style="text-align:left">
      Propenso a ser influenciado pela utilidade do produto ao comprar produtos
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_online_ads</code>
    </td>
    <td style="text-align:left">
      Propenso a ser influenciado por anúncios on-line ao comprar produtos
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_social_media</code>
    </td>
    <td style="text-align:left">
      Propenso a ser influenciado pela mídia social ao comprar produtos
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_family_members</code>
    </td>
    <td style="text-align:left">
      Propenso a ser influenciado pela família ao comprar produtos
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_spur_of_moment</code>
    </td>
    <td style="text-align:left">
      Propenso a fazer compras por impulso
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_credit_card_payment</code>
    </td>
    <td style="text-align:left">
      Propenso a preferir usar cartões de crédito para fazer compras
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
</table>

## Preferências de filme
{: #movie}

As preferências de filme indicam o interesse do autor em diferentes tipos de filmes. O ID e o nome da categoria são `consumption_preferences_movie` e `Preferências de filme`. A categoria tem 10 preferências.

<table>
  <caption>Tabela 2. Preferências de filme</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferência de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Pontuações
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_romance</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de filmes românticos
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_adventure</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de filmes de aventura
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_horror</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de filmes de terror
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_musical</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de filmes musicais
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_historical</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de filmes históricos
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_science_fiction</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de filmes de ficção científica
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_war</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de filmes de guerra
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_drama</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de filmes dramáticos
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_action</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de filmes de ação
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_documentary</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de filmes documentários
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
</table>

## Preferências de música
{: #music}

As preferências de música indicam o interesse do autor em diferentes tipos de música e se o autor gosta de tocar música. O ID e o nome da categoria são `consumption_preferences_music` e `Preferências de música`. A categoria tem nove preferências.

<table>
  <caption>Tabela 3. Preferências de música</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferência de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Pontuações
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rap</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de rap
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_country</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de música country
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_r_b</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de música R&amp;B
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_hip_hop</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de hip hop
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_live_event</code>
    </td>
    <td style="text-align:left">
      Propenso a assistir eventos musicais ao vivo
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_playing</code>
    </td>
    <td style="text-align:left">
      Propenso a ter experiência tocando música
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_latin</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de música latina
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rock</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de rock
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_classical</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de música clássica
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
</table>

## Preferências de leitura e aprendizado
{: #reading}

As preferências de leitura e aprendizado indicam a probabilidade de o autor ler, a motivação do autor para leitura e os tipos de conteúdo que o autor gosta de ler. O ID e o nome da categoria são `consumption_preferences_reading` e `Preferências de leitura`. A categoria tem cinco preferências.

<table>
  <caption>Tabela 4. Preferências de leitura e aprendizado</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferência de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Pontuações
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_read_frequency</code>
    </td>
    <td style="text-align:left">
      Propenso a ler frequentemente
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_entertainment_magazines</code>
    </td>
    <td style="text-align:left">
      Propenso a ler revistas de entretenimento
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_non_fiction</code>
    </td>
    <td style="text-align:left">
      Propenso a ler livros de não ficção
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_financial_investing</code>
    </td>
    <td style="text-align:left">
      Propenso a ler livros de investimento financeiro
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_autobiographies</code>
    </td>
    <td style="text-align:left">
      Propenso a ler livros autobiográficos
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
</table>

## Preferências de saúde e atividade
{: #health}

As preferências de saúde e atividade indicam o interesse do autor em alimentos saudáveis e atividade física. O ID e o nome da categoria são `consumption_preferences_health_and_activity` e `Preferências de saúde e atividade`. A categoria tem três preferências.

<table>
  <caption>Tabela 5. Preferências de saúde e atividade</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferência de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Pontuações
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_eat_out</code>
    </td>
    <td style="text-align:left">
      Propenso a comer fora frequentemente
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_gym_membership</code>
    </td>
    <td style="text-align:left">
      Propenso a estar matriculado em uma academia de ginástica
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_outdoor</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de atividades ao ar livre
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
</table>

## Preferências de empreendedorismo
{: #entrepreneur}

As preferências de empreendedorismo indicam o interesse do autor em iniciar um negócio. O ID e o nome da categoria são `consumption_preferences_entrepreneurship` e `Preferências de empreendedorismo`. A categoria tem uma preferência.

<table>
  <caption>Tabela 6. Preferências de empreendedorismo</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferência de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Pontuações
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_start_business</code>
    </td>
    <td style="text-align:left">
      Propenso a considerar iniciar um negócio nos próximos anos
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
</table>

## Preferências de preocupação ambiental
{: #environment}

As preferências de preocupação ambiental indicam o interesse do autor no ambiente. O ID e o nome da categoria são `consumption_preferences_environmental_concern` e `Preferências de preocupação ambiental`. A categoria tem uma preferência.

<table>
  <caption>Tabela 7. Preferências de preocupação ambiental</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferência de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Pontuações
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_concerned_environment</code>
    </td>
    <td style="text-align:left">
      Propenso a se preocupar com o ambiente
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>0.5</code> (neutro)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
</table>

## Preferências de voluntariado
{: #volunteer}

As preferências de voluntariado indicam o interesse do autor no voluntariado para causas sociais. O ID e o nome da categoria são `consumption_preferences_volunteering` e `Preferências de voluntariado`. A categoria tem uma preferência.

<table>
  <caption>Tabela 8. Preferências de voluntariado</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferência de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nome
    </th>
    <th style="text-align:center">
      Pontuações
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_volunteer</code>
    </td>
    <td style="text-align:left">
      Propenso a trabalhar como voluntário para causas sociais
    </td>
    <td style="text-align:center">
      <code>0.0</code> (improvável)<br/>
      <code>1.0</code> (provável)
    </td>
  </tr>
</table>
