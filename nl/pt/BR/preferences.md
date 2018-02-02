---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-12"

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

# Consumo preferências
{: #preferences}

O serviço {{site.data.keyword.personalityinsightsshort}} infere as características de personalidade de um autor para três modelos: Big Five, Necessidades e Valores. Com base em seus resultados para esses modelos, o serviço também pode produzir preferências de consumo para o autor do texto de entrada. Configure o `consumption_preferences` consulta parâmetro para `true` para uma solicitação para obter preferências de consumo.
{: shortdesc}

Agrupados em oito categorias de alto nível, as preferências mais de 40 do consumo indicam a probabilidade do autor preferir diferentes produtos, serviços e atividades. Por exemplo, o serviço pode identificar as inclinações do autor quando comprar roupas (conforto versus moda) e automóveis (custo versus segurança); suas inclinações para diferentes gêneros de música, filmes, e leitura; e suas atitudes em relação ao ambiente e voluntariado, entre outras coisas.

As empresas usam modelos de personalidade do serviço para entender melhor seus clientes e para projetar e desenvolver campanhas mais personalizadas e de destino, produtos e serviços. As preferências de consumo tornam ainda mais fácil a ação com base nos resultados do serviço. As empresas podem facilmente obter uma lista de preferências que estão associados com características dominantes do indivíduo e responder de forma apropriada. Para obter mais informações sobre aplicativos possíveis das preferências de consumo, consulte [Usar casos](/docs/services/personality-insights/usecases.html) e [O serviço em ação](/docs/services/personality-insights/applied.html).

As seções a seguir listam e descrevem as preferências de consumo que o serviço pode retornar. Para obter mais informações sobre como interpretar as preferências numéricos, consulte [Escores para consumo preferências](/docs/services/personality-insights/numeric.html#scores). Para obter informações sobre como o {{site.data.keyword.IBM_notm}} desenvolveu as preferências, consulte [A ciência por trás do serviço](/docs/services/personality-insights/science.html).

## Preferências de Compras
{: #shopping}

Preferências de Compra indicam interesse do autor em diferentes tipos de compras, a extensão na qual os hábitos de compra do autor são influenciados por diferentes origens externas, e hábitos de gastos do autor. O ID da categoria e o nome são `consumption_preferences_shopping` e `Preferências de Compra`. A categoria tem 12 preferências.

<table>
  <caption>Tabela 1. Preferências de Compras</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de Consumo de preferência
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
      A ser sensível ao custo de propriedade ao comprar automóveis
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_brand_name</code>
    </td>
    <td style="text-align:left">
Propenso a ser influenciado pelo nome da marca ao fazer compras de produtos
</td>
    <td style="text-align:center">
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_utility</code>
    </td>
    <td style="text-align:left">
      Propenso a ser influenciado pelo utilitário do produto ao fazer compras de produtos
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_online_ads</code>
    </td>
    <td style="text-align:left">
      Propenso a ser influenciado por anúncios on-line ao fazer compras de produtos
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_social_media</code>
    </td>
    <td style="text-align:left">
      Propenso a ser influenciado pela mídia social ao fazer compras de produtos
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_family_members</code>
    </td>
    <td style="text-align:left">
      Propenso a ser influenciado pela família ao fazer compras de produtos
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
</table>

## Preferências de Filme
{: #movie}

Filme preferências indicam interesse do autor em diferentes tipos de filmes. O ID da categoria e o nome são `consumption_preferences_movie` e `Filme Preferências`. A categoria tem 10 preferências.

<table>
  <caption>Tabela 2. Preferências de Filme</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de Consumo de preferência
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
</table>

## Música preferências
{: #music}

Música preferências indicam interesse do autor em diferentes tipos de música e se o autor gosta de tocar música. O ID de categoria e o nome são `consumption_preferences_music` e `Music Preferences`. A categoria tem nove preferências.

<table>
  <caption>Tabela 3. Música preferências</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de Consumo de preferência
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
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_r_b</code>
    </td>
    <td style="text-align:left">
      Propenso a gostar de música R &amp; B
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_live_event</code>
    </td>
    <td style="text-align:left">
      Propenso a assistir eventos musicais
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
</table>

## Lendo e aprendendo preferências
{: #reading}

Lendo e aprendendo preferências indicam a probabilidade do autor para ler, a motivação do autor para leitura, e os tipos de conteúdo o autor gosta de leitura. O ID da categoria e o nome são `consumption_preferences_reading` e `Lendo Preferências`. A categoria tem cinco preferências.

<table>
  <caption>Tabela 4. Lendo e aprendendo preferências</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de Consumo de preferência
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
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_non_fiction</code>
    </td>
    <td style="text-align:left">
      Propenso a ler livros de não-ficção
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
</table>

## Saúde e preferências de atividade
{: #health}

Saúde e preferências de atividade indicam interesse do autor em alimentos saudáveis e atividade física. O ID da categoria e o nome são `consumption_preferences_health_and_activity` e `Health & Activity Preferências`. A categoria tem três preferências.

<table>
  <caption>Tabela 5. Saúde e preferências de atividade</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de Consumo de preferência
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
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_gym_membership</code>
    </td>
    <td style="text-align:left">
      Propenso a ter uma associação de ginástica
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
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
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
</table>

## Preferências de Empreendedorismo
{: #entrepreneur}

Preferências de Empreendedorismo indicam interesse do autor em iniciar um negócio. O ID da categoria e o nome são `consumption_preferences_entrepreneurship` e `e Preferências`. A categoria tem uma preferência.

<table>
  <caption>Tabela 6. Preferências de Empreendedorismo</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de Consumo de preferência
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
      Propenso a considerar abrir um negócio nos próximos anos
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
</table>

## Preferências de preocupação ambiental
{: #environment}

Preferências de preocupação ambiental indicam interesse do autor no ambiente. O ID da categoria e o nome são `consumption_preferences_environmental_concern` e `Interesse Ambiental Preferências`. A categoria tem uma preferência.

<table>
  <caption>Tabela 7. Preferências de preocupação ambiental</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de Consumo de preferência
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
      <code>0,0</code> (improvável)<br/>
      <code>0,5</code> (neutro)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
</table>

## Preferências de Voluntariado
{: #volunteer}

Preferências de Voluntariado indicam interesse do autor no voluntário por causas sociais. O ID de categoria e o nome são `consumption_preferences_volunteering` e `Volunteering Preferences`. A categoria tem uma preferência.

<table>
  <caption>Tabela 8. Preferências de Voluntariado</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de Consumo de preferência
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
      A trabalhar como voluntário por causas sociais
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improvável)<br/>
      <code>1,0</code> (provavelmente)
    </td>
  </tr>
</table>
