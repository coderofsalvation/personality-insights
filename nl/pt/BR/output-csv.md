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

# Entendendo um perfil CSV
{: #outputCSV}

O serviço retorna os resultados de suas análises em formato de valores separados por vírgula (CSV) quando você especifica `text/csv` com o cabeçalho `Accept` de uma solicitação. A saída em CSV fornece informações que são semelhantes às informações fornecidas pela saída em JSON. Como com JSON, as informações na saída de CSV dependem de os dados de entrada serem registrados com data e hora e se você solicita pontuações brutas e preferências de consumo.
{: shortdesc}

A saída de CSV, diferente de JSON, é retornada como um número fixo de colunas. A primeira linha da saída consiste em rótulos de coluna opcionais, que serão incluídos apenas se você configurar o parâmetro de consulta `csv_headers` da solicitação para `true`. A segunda linha da saída, que sempre está presente, contém os resultados da análise.

As seções a seguir listam e descrevem brevemente todas as colunas da saída em CSV na ordem exata na qual elas aparecem nos resultados. As tabelas descrevem as colunas por agrupamento lógico, incluindo o número de colunas em cada grupo e seus rótulos opcionais. Além da contagem de palavras, todos os dados numéricos são retornados como valores duplos.

Para obter mais informações sobre o significado das colunas de CSV, consulte [Entendendo um perfil JSON](/docs/services/personality-insights?topic=personality-insights-output) e [Interpretando os resultados numéricos](/docs/services/personality-insights?topic=personality-insights-numeric).

## Características básicas e metadados
{: #basicCSV}

As colunas a seguir estão sempre presentes na saída CSV para todas as solicitações.

<table>
  <caption>Tabela 1. Colunas de CSV para características básicas e metadados</caption>
  <tr>
    <th style="width:25%; text-align:left; vertical-align:bottom">Agrupamento<br/>(Número de colunas)</th>
    <th style="width:25%; text-align:left; vertical-align:bottom">Rótulos opcionais</th>
    <th style="text-align:left; vertical-align:bottom">Descrição</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentis de Afabilidade do Big Five<br/>(Sete colunas)
    </td>
    <td style="vertical-align:top">
      big5_agreeableness<br/>facet_altruism<br/>
      facet_cooperation<br/>facet_modesty<br/>
      facet_morality<br/>facet_sympathy<br/>
      facet_trust
    </td>
    <td style="vertical-align:top">
      Pontuação de percentil normalizada para o autor do texto para a
      dimensão ou o aspecto nomeado.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentis de Estado consciente do Big Five<br/>(Sete colunas)
    </td>
    <td style="vertical-align:top">
      big5_conscientiousness<br/>facet_achievement_striving
      <br/>facet_cautiousness<br/>facet_dutifulness<br/>
      facet_orderliness<br/>facet_self_discipline<br/>
      facet_self_efficacy
    </td>
    <td style="vertical-align:top">
      Pontuação de percentil normalizada para o autor do texto para a
      dimensão ou o aspecto nomeado.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentis de Extroversão do Big Five<br/>(Sete colunas)
    </td>
    <td style="vertical-align:top">
      big5_extraversion<br/>facet_activity_level
      <br/>facet_assertiveness<br/>facet_cheerfulness<br/>
      facet_excitement_seeking<br/>facet_friendliness<br/>
      facet_gregariousness
    </td>
    <td style="vertical-align:top">
      Pontuação de percentil normalizada para o autor do texto para a
      dimensão ou o aspecto nomeado.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentis de escala emocional do Big Five<br/>(Sete colunas)
    </td>
    <td style="vertical-align:top">
      big5_neuroticism<br/>facet_anger<br/>
      facet_anxiety<br/>facet_depression<br/>
      facet_immoderation<br/>facet_self_consciousness<br/>
      facet_vulnerability
    </td>
    <td style="vertical-align:top">
      Pontuação de percentil normalizada para o autor do texto para a
      dimensão ou o aspecto nomeado.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentis de Abertura do Big Five<br/>(Sete colunas)
    </td>
    <td style="vertical-align:top">
      big5_openness<br/>facet_adventurousness<br/>
      facet_artistic_interests<br/>facet_emotionality<br/>
      facet_imagination<br/>facet_intellect<br/>
      facet_liberalism
    </td>
    <td style="vertical-align:top">
      Pontuação de percentil normalizada para o autor do texto para a
      dimensão ou o aspecto nomeado.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentis de necessidades<br/>(Doze colunas)
    </td>
    <td style="vertical-align:top">
      need_liberty<br/>need_ideal<br/>
      need_love<br/>need_practicality<br/>
      need_self_expression<br/>need_stability<br/>
      need_structure<br/>need_challenge<br/>
      need_closeness<br/>need_curiosity<br/>
      need_excitement<br/>need_harmony
    </td>
    <td style="vertical-align:top">
      Pontuação de percentil normalizada para o autor do texto para a
      necessidade nomeada.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentis de valores<br/>(Cinco colunas)
    </td>
    <td style="vertical-align:top">
      value_conservation<br/>value_hedonism<br/>
      value_openness_to_change<br/>value_self_enhancement<br/>
      value_self_transcendence
    </td>
    <td style="vertical-align:top">
      Pontuação de percentil normalizada para o autor do texto para o
      valor nomeado.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Porcentagens dos dias da semana<br/>(Sete colunas)
    </td>
    <td style="vertical-align:top">
      behavior_sunday<br/>behavior_monday<br/>
      behavior_tuesday<br/>behavior_wednesday<br/>
      behavior_thursday<br/>behavior_friday<br/>
      behavior_saturday
    </td>
    <td style="vertical-align:top">
      <em>Se o texto de entrada é registrado com data e hora,</em> a porcentagem da
      entrada que está associada a cada dia da semana. Caso contrário,
      todas as porcentagens serão <code>0.0</code>.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Horas dos porcentagens do dia<br/>(Vinte e quatro colunas)
    </td>
    <td style="vertical-align:top">
      behavior_0000 <em>through</em> behavior_2300
    </td>
    <td style="vertical-align:top">
      <em>Se o texto de entrada for timestampado,</em>a porcentagem de
      que está associado a cada hora do dia. Caso contrário,
      todas as porcentagens serão <code>0.0</code>.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Contagem de palavras e idioma<br/>(Duas colunas)
    </td>
    <td style="vertical-align:top">
      word_count<br/>processed_language
    </td>
    <td style="vertical-align:top">
      Um número inteiro que indica o número de palavras presentes no texto de entrada e um identificador de duas letras para o modelo de idioma que o serviço usou para analisar o texto.
    </td>
  </tr>
</table>

## Pontuações brutas
{: #rawCSV}

As colunas a seguir estarão presentes somente se você solicitar pontuações brutas configurando o parâmetro de consulta `raw_scores` para `true`. Em todos os casos, a coluna é um valor duplo que fornece pontuação bruta do autor para a dimensão, o aspecto, a necessidade ou o valor.

<table>
  <caption>Tabela 2. Colunas de CSV para pontuações brutas</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Agrupamento<br/>(Número de colunas)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Rótulos opcionais</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações brutas de Afabilidade do Big Five<br/>(Sete colunas)
    </td>
    <td>
      big5_agreeableness_raw<br/>facet_altruism_raw<br/>
      facet_cooperation_raw<br/>facet_modesty_raw<br/>
      facet_morality_raw<br/>facet_sympathy_raw<br/>
      facet_trust_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações brutas de Estado consciente do Big Five<br/>(Sete colunas)
    </td>
    <td>
      big5_conscientiousness_raw<br/>facet_achievement_striving_raw<br/>
      facet_cautiousness_raw<br/>facet_dutifulness_raw<br/>
      facet_orderliness_raw<br/>facet_self_discipline_raw<br/>
      facet_self_efficacy_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações brutas de Extroversão do Big Five<br/>(Sete colunas)
    </td>
    <td>
      big5_extraversion_raw<br/>facet_activity_level_raw<br/>
      facet_assertiveness_raw<br/>facet_cheerfulness_raw<br/>
      facet_excitement_seeking_raw<br/>facet_friendliness_raw<br/>
      facet_gregariousness_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações brutas de escala emocional do Big Five<br/>(Sete colunas)
    </td>
    <td>
      big5_neuroticism_raw<br/>facet_anger_raw<br/>
      facet_anxiety_raw<br/>facet_depression_raw<br/>
      facet_immoderation_raw<br/>facet_self_consciousness_raw<br/>
      facet_vulnerability_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações brutas de Abertura do Big Five<br/>(Sete colunas)
    </td>
    <td>
      big5_openness_raw<br/>facet_adventurousness_raw<br/>
      facet_artistic_interests_raw<br/>facet_emotionality_raw<br/>
      facet_imagination_raw<br/>facet_intellect_raw<br/>
      facet_liberalism_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações brutas de necessidades<br/>(Doze colunas)
    </td>
    <td>
      need_liberty_raw<br/>need_ideal_raw<br/>
      need_love_raw<br/>need_practicality_raw<br/>
      need_self_expression_raw<br/>need_stability_raw<br/>
      need_structure_raw<br/>need_challenge_raw<br/>
      need_closeness_raw<br/>need_curiosity_raw<br/>
      need_excitement_raw<br/>need_harmony_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações brutas de valores<br/>(Cinco colunas)
    </td>
    <td>
      value_conservation_raw<br/>value_hedonism_raw<br/>
      value_openness_to_change_raw<br/>value_self_enhancement_raw<br/>
      value_self_transcendence_raw
    </td>
  </tr>
</table>

## Significância
{: #significantCSV}

As colunas a seguir estão sempre presentes na saída CSV para todas as solicitações. Em todos os casos, a coluna é um valor booleano que indica se a dimensão, o aspecto, a necessidade ou o valor é significativo para o idioma de entrada processado.

<table>
  <caption>Tabela 3. Colunas de CSV para significância</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Agrupamento<br/>(Número de colunas)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Rótulos opcionais</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Importância de Afabilidade do Big Five<br/>(Sete colunas)
    </td>
    <td>
      big5_agreeableness_significant<br/>facet_altruism_significant<br/>
      facet_cooperation_significant<br/>facet_modesty_significant<br/>
      facet_morality_significant<br/>facet_sympathy_significant<br/>
      facet_trust_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Importância de Estado consciente do Big Five<br/>(Sete colunas)
    </td>
    <td>
      big5_conscientiousness_significant<br/>
      facet_achievement_striving_significant<br/>
      facet_cautiousness_significant<br/>facet_dutifulness_significant<br/>
      facet_orderliness_significant<br/>facet_self_discipline_significant<br/>
      facet_self_efficacy_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five significância de Extraversão<br/>(Sete colunas)
    </td>
    <td>
      big5_extraversion_significant<br/>facet_activity_level_significant<br/>
      facet_assertiveness_significant<br/>facet_cheerfulness_significant<br/>
      facet_excitement_seeking_significant<br/>
      facet_friendliness_significant<br/>facet_gregariousness_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Importância de escala emocional do Big Five<br/>(Sete colunas)
    </td>
    <td>
      big5_neuroticism_significant<br/>facet_anger_significant<br/>
      facet_anxiety_significant<br/>facet_depression_significant<br/>
      facet_immoderation_significant<br/>
      facet_self_consciousness_significant<br/>facet_vulnerability_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Importância de Abertura do Big Five<br/>(Sete colunas)
    </td>
    <td>
      big5_openness_significant<br/>facet_adventurousness_significant<br/>
      facet_artistic_interests_significant<br/>
      facet_emotionality_significant<br/>facet_imagination_significant<br/>
      facet_intellect_significant<br/>facet_liberalism_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Significância bruta de necessidades<br/>(Doze colunas)
    </td>
    <td>
      need_liberty_significant<br/>need_ideal_significant<br/>
      need_love_significant<br/>need_practicality_significant<br/>
      need_self_expression_significant<br/>need_stability_significant<br/>
      need_structure_significant<br/>need_challenge_significant<br/>
      need_closeness_significant<br/>need_curiosity_significant<br/>
      need_excitement_significant<br/>need_harmony_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Significância de valores<br/>(Cinco colunas)
    </td>
    <td>
      value_conservation_significant<br/>value_hedonism_significant<br/>
      value_openness_to_change_significant<br/>
      value_self_enhancement_significant<br/>
      value_self_transcendence_significant
    </td>
  </tr>
</table>

## Preferências de consumo
{: #preferenceCSV}

As colunas a seguir estarão presentes somente se você solicitar preferências de consumo configurando o parâmetro de consulta `consumption_preferences` para `true`. Em todos os casos, a coluna é um valor duplo que relata a probabilidade de que o autor prefere o tópico de consumo denominado.

<table style="width:90%">
  <caption>Tabela 4. Colunas de CSV para preferências de consumo</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Agrupamento<br/>(Número de colunas)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Rótulos opcionais</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações de categoria de preferências de compras<br/>(Doze colunas)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_spur_of_moment<br/>
      consumption_preferences_credit_card_payment<br/>
      consumption_preferences_influence_brand_name<br/>
      consumption_preferences_influence_utility<br/>
      consumption_preferences_online_ads<br/>
      consumption_preferences_social_media<br/>
      consumption_preferences_family_members<br/>
      consumption_preferences_clothes_quality<br/>
      consumption_preferences_clothes_style<br/>
      consumption_preferences_clothes_comfort<br/>
      consumption_preferences_automobile_ownership_cost<br/>
      consumption_preferences_automobile_safety
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações de categoria de preferências de música<br/>(Nove colunas)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_music_rap<br/>
      consumption_preferences_music_country<br/>
      consumption_preferences_music_r_b<br/>
      consumption_preferences_music_hip_hop<br/>
      consumption_preferences_music_live_event<br/>
      consumption_preferences_music_playing<br/>
      consumption_preferences_music_latin<br/>
      consumption_preferences_music_rock<br/>
      consumption_preferences_music_classical
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações de categoria de preferências de funcionamento e atividade<br/>(Três colunas)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_gym_membership<br/>
      consumption_preferences_outdoor<br/>
      consumption_preferences_eat_out
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações de categoria de preferências de filme<br/>(Dez colunas)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_movie_romance<br/>
      consumption_preferences_movie_adventure<br/>
      consumption_preferences_movie_horror<br/>
      consumption_preferences_movie_musical<br/>
      consumption_preferences_movie_historical<br/>
      consumption_preferences_movie_science_fiction<br/>
      consumption_preferences_movie_war<br/>
      consumption_preferences_movie_drama<br/>
      consumption_preferences_movie_action<br/>
      consumption_preferences_movie_documentary
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações de categoria de preferências de leitura<br/>(Cinco colunas)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_read_frequency<br/>
      consumption_preferences_books_entertainment_magazines<br/>
      consumption_preferences_books_non_fiction<br/>
      consumption_preferences_books_financial_investing<br/>
      consumption_preferences_books_autobiographies
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações de categoria de preferências de voluntariado<br/>(Uma coluna)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_volunteer
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações de categoria de preferências de preocupação ambiental<br/>(Uma coluna)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_concerned_environment
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Pontuações da categoria de preferências do empreendedorismo<br/>(Uma coluna)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_start_business
    </td>
  </tr>
</table>
