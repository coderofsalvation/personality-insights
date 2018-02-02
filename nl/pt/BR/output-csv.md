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

# Entendendo um perfil CSV
{: #outputCSV}

O serviço retorna os resultados de suas análises em formato de valores separados por vírgula (CSV) quando você especificar `text/csv` com o `Aceitar` cabeçalho de uma solicitação. Saída CSV fornece informações que são semelhantes às informações fornecidas pela saída JSON. Assim como JSON, as informações na saída CSV depende se a entrada representa dados de data e se as solicitações do usuário pontuações brutos e preferências de consumo.
{: shortdesc}

No entanto, Diferentemente de JSON, a saída CSV é retornado como um número fixo de colunas. A primeira linha da saída consiste em rótulos de coluna opcionais, que são incluídos apenas se você configurar o `csv_headers` parâmetro de consulta da solicitação para `true`. A segunda linha da saída, que está sempre presente, contém os resultados da análise.

As seções a seguir listam e descreva brevemente todas as colunas da saída CSV na ordem exata na qual eles aparecem nos resultados. As tabelas descrevem as colunas de agrupamento lógico, incluindo o número de colunas em cada grupo e seus rótulos opcionais. Além de contar palavras, todos os dados numéricos são retornados como valores duplos.

Para obter mais informações sobre o significado das colunas CSV, consulte [Entendendo um perfil JSON](/docs/services/personality-insights/output.html) e [Interpretando os resultados numéricos](/docs/services/personality-insights/numeric.html).

## As características básicas e metadados
{: #basicCSV}

As colunas a seguir são sempre presente na saída CSV para todas as solicitações.

<table>
  <caption>Tabela 1. Colunas CSV para características básicas e metadados</caption>
  <tr>
    <th style="width:25%; text-align:left; vertical-align:bottom">Agrupamento<br/>(número de colunas)</th>
    <th style="width:25%; text-align:left; vertical-align:bottom">Etiquetas Opcional</th>
    <th style="text-align:left; vertical-align:bottom">Descrição</th>
  </tr>
  <tr>
    <td>
      Afabilidade Big Five<br/>Percentis<br/>(7 colunas)
    </td>
    <td>
      Big5_agreeableness<br/>Facet_altruism<br/>
      Facet_cooperation<br/>Facet_modesty<br/>
      Facet_morality<br/>Facet_sympathy<br/>
      Facet_trust
    </td>
    <td>
      Pontuação de percentil normalizado para o autor do texto com relação ao chamado dimensão ou aspecto.
    </td>
  </tr>
  <tr>
    <td>
      Big Five consciente<br/>Percentis<br/>(7 colunas)
    </td>
    <td>
      Big5_conscientiousness<br/>Facet_achievement_striving
      <br/>Facet_cautiousness<br/>Facet_dutifulness<br/>
      Facet_orderliness<br/>Facet_self_discipline<br/>
      Facet_self_efficacy
    </td>
    <td>
      Pontuação de percentil normalizado para o autor do texto com relação ao chamado dimensão ou aspecto.
    </td>
  </tr>
  <tr>
    <td>
      Big Five Extroversão<br/>Percentis<br/>(7 colunas)
    </td>
    <td>
      Big5_extraversion<br/>Facet_activity_level
      <br/>Facet_assertiveness<br/>Facet_cheerfulness<br/>
      Facet_excitement_seeking<br/>facet_friendliness<br/>
      Facet_gregariousness
    </td>
    <td>
      Pontuação de percentil normalizado para o autor do texto com relação ao chamado dimensão ou aspecto.
    </td>
  </tr>
  <tr>
    <td>
      Big Five intervalo emocional<br/>Percentis<br/>(7 colunas)
    </td>
    <td>
      Big5_neuroticism<br/>Facet_anger<br/>
      Facet_anxiety<br/>Facet_depression<br/>
      Facet_immoderation<br/>Facet_self_consciousness<br/>
      Facet_vulnerability
    </td>
    <td>
      Pontuação de percentil normalizado para o autor do texto com relação ao chamado dimensão ou aspecto.
    </td>
  </tr>
  <tr>
    <td>
      Big Five Openness<br/>Percentis<br/>(7 colunas)
    </td>
    <td>
      big5_openness<br/>Facet_adventurousness<br/>
      Facet_artistic_interests<br/>Facet_emotionality<br/>
      Facet_imagination<br/>facet_intellect<br/>
      Facet_liberalism
    </td>
    <td>
      Pontuação de percentil normalizado para o autor do texto com relação ao chamado dimensão ou aspecto.
    </td>
  </tr>
  <tr>
    <td>
      Necessidades percentis<br/>(12 colunas)
    </td>
    <td>
      Need_liberty<br/>Need_ideal<br/>
      Need_love<br/>Need_practicality<br/>
      Need_self_expression<br/>Need_stability<br/>
      Need_structure<br/>Need_challenge<br/>
      Need_closeness<br/>Need_curiosity<br/>
      need_excitement<br/>Need_harmony
    </td>
    <td>
      Pontuação de percentil normalizado para o autor do texto com relação à necessidade nomeado.
    </td>
  </tr>
  <tr>
    <td>
      Valores percentuais<br/>(5 colunas)
    </td>
    <td>
      Value_conservation<br/>Value_hedonism<br/>
      Value_openness_to_change<br/>value_self_enhancement<br/>
      Value_self_transcendence
    </td>
    <td>
Pontuação percentil normalizada para o autor do texto com respeito ao valor nomeado.
    </td>
  </tr>
  <tr>
    <td>
      Dias da semana<br/>Porcentagens<br/>(7 colunas)
    </td>
    <td>
      Behavior_sunday<br/>Behavior_monday<br/>
      Behavior_tuesday<br/>Behavior_wednesday<br/>
      Behavior_thursday<br/>Behavior_friday<br/>
      Behavior_saturday
    </td>
    <td>
      Se o texto de entrada é data, a porcentagem de entrada associada a cada dia da semana; se a entrada não for data, as porcentagens são todos <code>0,0</code>.
    </td>
  </tr>
  <tr>
    <td>
      Horas do dia<br/>Porcentagens<br/>(24 colunas)
    </td>
    <td>
      Behavior_0000<br/><em>por meio</em><br/>Behavior_2300
    </td>
    <td>
      Se o texto de entrada é data, a porcentagem de entrada associados a cada hora do dia; se a entrada não for data, as porcentagens são todos <code>0,0</code>.
    </td>
  </tr>
  <tr>
    <td>
      Spark-Wordcount e<br/>linguagem<br/>(2 colunas)
    </td>
    <td>
      Word_count<br/>Processed_language
    </td>
    <td>
      Um número inteiro que indica o número de palavras presentes no texto de entrada e um identificador de duas letras para o modelo de linguagem que o serviço utilizado para analisar o texto.
    </td>
  </tr>
</table>

## Pontuações Brutos
{: #rawCSV}

As colunas a seguir estão presentes somente se você solicitar notas brutas configurando o `raw_scores` parâmetro de consulta para `true`. Em todos os casos, a coluna é um valor duplo que fornece pontuação bruto do autor para a dimensão, aspecto, precisa, ou valor.

<table>
  <caption>Tabela 2. Colunas CSV para pontuações brutos</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Agrupamento<br/>(número de colunas)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Etiquetas Opcional</th>
  </tr>
  <tr>
    <td>
      Afabilidade Big Five<br/>Pontuações brutos<br/>(7 colunas)
    </td>
    <td>
      Big5_agreeableness_raw<br/>Facet_altruism_raw<br/>
      Facet_cooperation_raw<br/>facet_modesty_raw<br/>
      Facet_morality_raw<br/>Facet_sympathy_raw<br/>
      Facet_trust_raw
    </td>
  </tr>
  <tr>
    <td>
      Big Five consciente<br/>Pontuações brutos<br/>(7 colunas)
    </td>
    <td>
      Big5_conscientiousness_raw<br/>Facet_achievement_striving_raw<br/>
      Facet_cautiousness_raw<br/>Facet_dutifulness_raw<br/>
      Facet_orderliness_raw<br/>Facet_self_discipline_raw<br/>
      Facet_self_efficacy_raw
    </td>
  </tr>
  <tr>
    <td>
      Big Five Extroversão<br/>Pontuações brutos<br/>(7 colunas)
    </td>
    <td>
      Big5_extraversion_raw<br/>Facet_activity_level_raw<br/>
      Facet_assertiveness_raw<br/>facet_cheerfulness_raw<br/>
      Facet_excitement_seeking_raw<br/>Facet_friendliness_raw<br/>
      Facet_gregariousness_raw
    </td>
  </tr>
  <tr>
    <td>
      Big Five intervalo emocional<br/>Pontuações brutos<br/>(7 colunas)
    </td>
    <td>
      Big5_neuroticism_raw<br/>Facet_anger_raw<br/>
      Facet_anxiety_raw<br/>Facet_depression_raw<br/>
      Facet_immoderation_raw<br/>Facet_self_consciousness_raw<br/>
      Facet_vulnerability_raw
    </td>
  </tr>
  <tr>
    <td>
      Big Five Openness<br/>Pontuações brutos<br/>(7 colunas)
    </td>
    <td>
      Big5_openness_raw<br/>Facet_adventurousness_raw<br/>
      Facet_artistic_interests_raw<br/>facet_emotionality_raw<br/>
      Facet_imagination_raw<br/>Facet_intellect_raw<br/>
      Facet_liberalism_raw
    </td>
  </tr>
  <tr>
    <td>
      Precisa de pontuações brutas<br/>(12 colunas)
    </td>
    <td>
      Need_liberty_raw<br/>Need_ideal_raw<br/>
      Need_love_raw<br/>Need_practicality_raw<br/>
      Need_self_expression_raw<br/>Need_stability_raw<br/>
      Need_structure_raw<br/>Need_challenge_raw<br/>
      Need_closeness_raw<br/>Need_curiosity_raw<br/>
      Need_excitement_raw<br/>Need_harmony_raw
    </td>
  </tr>
  <tr>
    <td>
      Valores pontuações brutos<br/>(5 colunas)
    </td>
    <td>
      Value_conservation_raw<br/>value_hedonism_raw<br/>
      Value_openness_to_change_raw<br/>Value_self_enhancement_raw<br/>
      value_self_transcendence_raw
    </td>
  </tr>
</table>

## Significância
{: #significantCSV}

As colunas a seguir são sempre presente na saída CSV para todas as solicitações. Em todos os casos, a coluna é um valor booleano que indica se a dimensão, aspecto, precisa, ou valor é significativo para o idioma de entrada processado.

<table>
  <caption>Tabela 3. Colunas CSV para significância</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Agrupamento<br/>(número de colunas)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Etiquetas Opcional</th>
  </tr>
  <tr>
    <td>
      Afabilidade Big Five<br/>Significância<br/>(7 colunas)
    </td>
    <td>
      Big5_agreeableness_significant<br/>Facet_altruism_significant<br/>
      Facet_cooperation_significant<br/>Facet_modesty_significant<br/>
      Facet_morality_significant<br/>facet_sympathy_significant<br/>
      Facet_trust_significant
    </td>
  </tr>
  <tr>
    <td>
      Big Five consciente<br/>Significância<br/>(7 colunas)
    </td>
    <td>
      Big5_conscientiousness_significant<br/>
      facet_achievement_striving_significant<br/>
      Facet_cautiousness_significant<br/>Facet_dutifulness_significant<br/>
      Facet_orderliness_significant<br/>Facet_self_discipline_significant<br/>
      Facet_self_efficacy_significant
    </td>
  </tr>
  <tr>
    <td>
      Big Five Extroversão<br/>Significância<br/>(7 colunas)
    </td>
    <td>
      Big5_extraversion_significant<br/>Facet_activity_level_significant<br/>
      Facet_assertiveness_significant<br/>Facet_cheerfulness_significant<br/>
      Facet_excitement_seeking_significant<br/>
      Facet_friendliness_significant<br/>Facet_gregariousness_significant
    </td>
  </tr>
  <tr>
    <td>
      Big Five intervalo emocional<br/>Significância<br/>(7 colunas)
    </td>
    <td>
      big5_neuroticism_significant<br/>Facet_anger_significant<br/>
      Facet_anxiety_significant<br/>Facet_depression_significant<br/>
      Facet_immoderation_significant<br/>
      Facet_self_consciousness_significant<br/>Facet_vulnerability_significant
    </td>
  </tr>
  <tr>
    <td>
      Big Five Openness<br/>Significância<br/>(7 colunas)
    </td>
    <td>
      Big5_openness_significant<br/>Facet_adventurousness_significant<br/>
      Facet_artistic_interests_significant<br/>
      Facet_emotionality_significant<br/>Facet_imagination_significant<br/>
      Facet_intellect_significant<br/>Facet_liberalism_significant
    </td>
  </tr>
  <tr>
    <td>
      Precisa de importância bruto<br/>(12 colunas)
    </td>
    <td>
      need_liberty_significant<br/>Need_ideal_significant<br/>
      Need_love_significant<br/>Need_practicality_significant<br/>
      Need_self_expression_significant<br/>Need_stability_significant<br/>
      Need_structure_significant<br/>Need_challenge_significant<br/>
      Need_closeness_significant<br/>Need_curiosity_significant<br/>
      Need_excitement_significant<br/>Need_harmony_significant
    </td>
  </tr>
  <tr>
    <td>
      Valores de importância<br/>(5 colunas)
    </td>
    <td>
      Value_conservation_significant<br/>Value_hedonism_significant<br/>
      Value_openness_to_change_significant<br/>
      Value_self_enhancement_significant<br/>
      value_self_transcendence_significant
    </td>
  </tr>
</table>

## Consumo preferências
{: #preferenceCSV}

As colunas a seguir estão presentes somente se você solicitar preferências de consumo configurando o `consumption_preferences` parâmetro de consulta para `true`. Em todos os casos, a coluna é um valor duplo que relata a probabilidade de que o autor prefere o tópico consumo nomeado.

<table style="width:90%">
  <caption>Tabela 4. Colunas CSV para as preferências de consumo</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Agrupamento<br/>(número de colunas)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Etiquetas Opcional</th>
  </tr>
  <tr>
    <td>
      Preferências de Compra<br/>Pontuações de categoria<br/>(12 colunas)
    </td>
    <td>
      Consumption_preferences_spur_of_moment<br/>
      Consumption_preferences_credit_card_payment<br/>
      Consumption_preferences_influence_brand_name<br/>
      Consumption_preferences_influence_utility<br/>
      Consumption_preferences_online_ads<br/>
      Consumption_preferences_social_media<br/>
      Consumption_preferences_family_members<br/>
      consumption_preferences_clothes_quality<br/>
      Consumption_preferences_clothes_style<br/>
      Consumption_preferences_clothes_comfort<br/>
      Consumption_preferences_automobile_ownership_cost<br/>
      Consumption_preferences_automobile_safety
    </td>
  </tr>
  <tr>
    <td>
      Música preferências<br/>Pontuações de categoria<br/>(9 colunas)
    </td>
    <td>
      Consumption_preferences_music_rap<br/>
      Consumption_preferences_music_country<br/>
      Consumption_preferences_music_r_b<br/>
      Consumption_preferences_music_hip_hop<br/>
      consumption_preferences_music_live_event<br/>
      Consumption_preferences_music_playing<br/>
      Consumption_preferences_music_latin<br/>
      Consumption_preferences_music_rock<br/>
      Consumption_preferences_music_classical
    </td>
  </tr>
  <tr>
    <td>
      Saúde e preferências de atividade<br/>Pontuações de categoria<br/>(3 colunas)
    </td>
    <td>
      Consumption_preferences_gym_membership<br/>
      Consumption_preferences_outdoor<br/>
      Consumption_preferences_eat_out
    </td>
  </tr>
  <tr>
    <td>
      Preferências de Filme<br/>Pontuações de categoria<br/>(10 colunas)
    </td>
    <td>
      consumption_preferences_movie_romance<br/>
      Consumption_preferences_movie_adventure<br/>
      Consumption_preferences_movie_horror<br/>
      Consumption_preferences_movie_musical<br/>
      Consumption_preferences_movie_historical<br/>
      Consumption_preferences_movie_science_fiction<br/>
      Consumption_preferences_movie_war<br/>
      Consumption_preferences_movie_drama<br/>
      Consumption_preferences_movie_action<br/>
      Consumption_preferences_movie_documentary
    </td>
  </tr>
  <tr>
    <td>
      Preferências de leitura<br/>Pontuações de categoria<br/>(5 colunas)
    </td>
    <td>
      Consumption_preferences_read_frequency<br/>
      Consumption_preferences_books_entertainment_magazines<br/>
      Consumption_preferences_books_non_fiction<br/>
      Consumption_preferences_books_financial_investing<br/>
      Consumption_preferences_books_autobiographies
    </td>
  </tr>
  <tr>
    <td>
      Preferências de Voluntariado<br/>Pontuações de categoria<br/>(1 coluna)
    </td>
    <td>
      Consumption_preferences_volunteer
    </td>
  </tr>
  <tr>
    <td>
      Preferências de preocupação ambiental<br/>Pontuações de categoria<br/>(1 coluna)
    </td>
    <td>
      Consumption_preferences_concerned_environment
    </td>
  </tr>
  <tr>
    <td>
      Preferências de Empreendedorismo<br/>Pontuações de categoria<br/>(1 coluna)
    </td>
    <td>
      Consumption_preferences_start_business
    </td>
  </tr>
</table>
