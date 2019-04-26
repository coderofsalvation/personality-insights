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

# Comprensión de un perfil CSV
{: #outputCSV}

El servicio devuelve los resultados de su análisis en formato CSV (comma-separated values) al especificar `text/csv` con la cabecera `Accept` de una solicitud. La salida CSV proporciona información similar a la proporcionada por la salida JSON. Como con JSON, la información de la salida CSV depende de si los datos de entrada llevan indicación de fecha y hora y de si se solicitan puntuaciones en bruto y preferencias de consumo.
{: shortdesc}

La salida CSV, a diferencia de JSON, se devuelve como un número fijo de columnas. La primera fila de la salida consta de etiquetas de columna opcionales, incluidas solo si se establece el parámetro de consulta `csv_headers` de la solicitud en `true`. La segunda fila de la salida, que está siempre presente, contiene los resultados del análisis.

Las secciones siguientes listan y describen brevemente todas las columnas de la salida CSV en el orden exacto en el que aparecen en los resultados. Las tablas describen las columnas por agrupación lógica, incluido el número de columnas de cada grupo y sus etiquetas opcionales. Aparte del recuento de palabras, todos los datos numéricos se devuelven como valores dobles.

Para obtener más información sobre el significado de las columnas CSV, consulte [Comprensión de un perfil JSON](/docs/services/personality-insights?topic=personality-insights-output) e [Interpretación de los resultados numéricos](/docs/services/personality-insights?topic=personality-insights-numeric).

## Características básicas y metadatos
{: #basicCSV}

Las siguientes columnas están siempre presentes en la salida CSV para todas las solicitudes.

<table>
  <caption>Tabla 1. Columnas CSV para características básicas y
    metadatos</caption>
  <tr>
    <th style="width:25%; text-align:left; vertical-align:bottom">Agrupación<br/>(Número de columnas)</th>
    <th style="width:25%; text-align:left; vertical-align:bottom">Etiquetas opcionales</th>
    <th style="text-align:left; vertical-align:bottom">Descripción</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentiles de simpatía - Cinco Grandes<br/>(Siete columnas)
    </td>
    <td style="vertical-align:top">
      big5_agreeableness<br/>facet_altruism<br/>
      facet_cooperation<br/>facet_modesty<br/>
      facet_morality<br/>facet_sympathy<br/>
      facet_trust
    </td>
    <td style="vertical-align:top">
      Puntuación de percentil normalizada del autor del texto
      respecto a la dimensión o faceta mencionada.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentiles de responsabilidad - Cinco Grandes<br/>(Siete columnas)
    </td>
    <td style="vertical-align:top">
      big5_conscientiousness<br/>facet_achievement_striving
      <br/>facet_cautiousness<br/>facet_dutifulness<br/>
      facet_orderliness<br/>facet_self_discipline<br/>
      facet_self_efficacy
    </td>
    <td style="vertical-align:top">
      Puntuación de percentil normalizada del autor del texto
      respecto a la dimensión o faceta mencionada.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentiles de extraversión - Cinco Grandes<br/>(Siete columnas)
    </td>
    <td style="vertical-align:top">
      big5_extraversion<br/>facet_activity_level
      <br/>facet_assertiveness<br/>facet_cheerfulness<br/>
      facet_excitement_seeking<br/>facet_friendliness<br/>
      facet_gregariousness
    </td>
    <td style="vertical-align:top">
      Puntuación de percentil normalizada del autor del texto
      respecto a la dimensión o faceta mencionada.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentiles de rango emocional - Cinco Grandes<br/>(Siete columnas)
    </td>
    <td style="vertical-align:top">
      big5_neuroticism<br/>facet_anger<br/>
      facet_anxiety<br/>facet_depression<br/>
      facet_immoderation<br/>facet_self_consciousness<br/>
      facet_vulnerability
    </td>
    <td style="vertical-align:top">
      Puntuación de percentil normalizada del autor del texto
      respecto a la dimensión o faceta mencionada.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentiles de apertura - Cinco Grandes<br/>(Siete columnas)
    </td>
    <td style="vertical-align:top">
      big5_openness<br/>facet_adventurousness<br/>
      facet_artistic_interests<br/>facet_emotionality<br/>
      facet_imagination<br/>facet_intellect<br/>
      facet_liberalism
    </td>
    <td style="vertical-align:top">
      Puntuación de percentil normalizada del autor del texto
      respecto a la dimensión o faceta mencionada.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentiles de Necesidades<br/>(Doce columnas)
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
      Puntuación de percentil normalizada del autor del texto
      respecto a la necesidad mencionada.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentiles de Valores<br/>(Cinco columnas)
    </td>
    <td style="vertical-align:top">
      value_conservation<br/>value_hedonism<br/>
      value_openness_to_change<br/>value_self_enhancement<br/>
      value_self_transcendence
    </td>
    <td style="vertical-align:top">
      Puntuación de percentil normalizada del autor del texto
      respecto al valor mencionado.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Porcentajes de días de la semana<br/>(Siete columnas)
    </td>
    <td style="vertical-align:top">
      behavior_sunday<br/>behavior_monday<br/>
      behavior_tuesday<br/>behavior_wednesday<br/>
      behavior_thursday<br/>behavior_friday<br/>
      behavior_saturday
    </td>
    <td style="vertical-align:top">
      <em>Si el texto de entrada tiene indicación de fecha y hora,</em> el porcentaje de la
      entrada que está asociado a cada día de la semana. De lo contrario,
      todos los porcentajes son <code>0.0</code>.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Porcentajes de horas del día<br/>(Veinticuatro columnas)
    </td>
    <td style="vertical-align:top">
      behavior_0000 <em>through</em> behavior_2300
    </td>
    <td style="vertical-align:top">
      <em>Si el texto de entrada tiene indicación de fecha y hora,</em> el porcentaje de la
      entrada que está asociado a cada hora del día. De lo contrario,
      todos los porcentajes son <code>0.0</code>.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Recuento de palabras e idioma<br/>(Dos columnas)
    </td>
    <td style="vertical-align:top">
      word_count<br/>processed_language
    </td>
    <td style="vertical-align:top">
      Un entero que indica el número de palabras presentes en el texto de entrada,
      y un identificador de dos letras para el modelo de idioma que ha utilizado el
      servicio para analizar el texto.
    </td>
  </tr>
</table>

## Puntuaciones en bruto
{: #rawCSV}

Las columnas siguientes solo están presentes si solicita las puntuaciones en bruto estableciendo el parámetro de consulta `raw_scores` en `true`. En todos los casos, la columna es un valor doble que proporciona la puntuación en bruto del autor para la dimensión, la faceta, la necesidad o el valor.

<table>
  <caption>Tabla 2. Columnas CSV para puntuaciones en bruto</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Agrupación<br/>(Número de columnas)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Etiquetas opcionales</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Puntuaciones en bruto de simpatía - Cinco Grandes<br/>(Siete columnas)
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
      Puntuaciones en bruto de responsabilidad - Cinco Grandes<br/>(Siete columnas)
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
      Puntuaciones en bruto de extraversión - Cinco Grandes<br/>(Siete columnas)
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
      Puntuaciones en bruto de rango emocional - Cinco Grandes<br/>(Siete columnas)
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
      Puntuaciones en bruto de apertura - Cinco Grandes<br/>(Siete columnas)
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
      Puntuaciones en bruto de Necesidades<br/>(Doce columnas)
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
      Puntuaciones en bruto de Valores<br/>(Cinco columnas)
    </td>
    <td>
      value_conservation_raw<br/>value_hedonism_raw<br/>
      value_openness_to_change_raw<br/>value_self_enhancement_raw<br/>
      value_self_transcendence_raw
    </td>
  </tr>
</table>

## Significancia
{: #significantCSV}

Las siguientes columnas están siempre presentes en la salida CSV para todas las solicitudes. En todos los casos, la columna es un valor booleano que indica si la dimensión, la faceta, la necesidad o el valor es significativo para el idioma de entrada procesado.

<table>
  <caption>Tabla 3. Columnas CSV para significancia</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Agrupación<br/>(Número de columnas)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Etiquetas opcionales</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Significancia de simpatía - Cinco Grandes<br/>(Siete columnas)
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
      Significancia de responsabilidad - Cinco Grandes<br/>(Siete columnas)
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
      Significancia de extraversión - Cinco Grandes<br/>(Siete columnas)
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
      Significancia de rango emocional - Cinco Grandes<br/>(Siete columnas)
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
      Significancia de apertura - Cinco Grandes<br/>(Siete columnas)
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
      Significancia bruta de Necesidades<br/>(Doce columnas)
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
      Significancia de Valores<br/>(Cinco columnas)
    </td>
    <td>
      value_conservation_significant<br/>value_hedonism_significant<br/>
      value_openness_to_change_significant<br/>
      value_self_enhancement_significant<br/>
      value_self_transcendence_significant
    </td>
  </tr>
</table>

## Preferencias de consumo
{: #preferenceCSV}

Las columnas siguientes solo están presentes si solicita las preferencias de consumo estableciendo el parámetro de consulta `consumption_preferences` en `true`. En todos los casos, la columna es un valor doble que informa de la probabilidad de que el autor prefiera el tema de consumo denominado.

<table style="width:90%">
  <caption>Tabla 4. Columnas CSV para las preferencias de consumo</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Agrupación<br/>(Número de columnas)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Etiquetas opcionales</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Puntuaciones de categorías de preferencias de compras<br/>(Doce columnas)
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
      Puntuaciones de categorías de preferencias musicales<br/>(Nueve columnas)
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
      Puntuaciones de categorías de preferencias de salud y actividad<br/>(Tres columnas)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_gym_membership<br/>
      consumption_preferences_outdoor<br/>
      consumption_preferences_eat_out
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Puntuaciones de categorías de preferencias de películas<br/>(Diez columnas)
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
      Puntuaciones de categorías de preferencias de lectura<br/>(Cinco columnas)
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
      Puntuaciones de categorías de preferencias de voluntariado<br/>(Una columna)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_volunteer
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Puntuaciones de categorías de preferencias de interés en cuestiones ambientales<br/>(Una columna)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_concerned_environment
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Puntuaciones de categorías de preferencias de emprendimiento<br/>(Una columna)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_start_business
    </td>
  </tr>
</table>
