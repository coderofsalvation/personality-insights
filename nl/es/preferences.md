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

# Preferencias de consumo
{: #preferences}

El servicio {{site.data.keyword.personalityinsightsshort}} deduce las características de personalidad de un autor para tres modelos: cinco grandes, necesidades y valores. Según sus resultados para estos modelos, el servicio también puede producir preferencias de consumo para el autor del texto de entrada. Establezca el parámetro de consulta `consumption_preferences` en `true` para que una solicitud obtenga las preferencias de consumo.
{: shortdesc}

El servicio agrupa las más de 40 preferencias de consumo en ocho categorías de alto nivel. Las preferencias indican la probabilidad del autor para preferir distintos productos, servicios y actividades. Por ejemplo, el servicio puede identificar

-   Las inclinaciones del autor en cuanto a ropa (confort frente a moda) y automóviles (coste frente a seguridad).
-   Las inclinaciones del autor hacia diferentes géneros de música, películas y lectura.
-   Las actitudes del autor sobre el medio ambiente y el voluntariado.

Las empresas utilizan los modelos de personalidad del servicio para comprender mejor a sus clientes y para diseñar y desarrollar campañas, productos y servicios más personalizados y selectivos. Las preferencias de consumo facilitan aún más actuar sobre los resultados del servicio. Las empresas pueden obtener fácilmente una lista de preferencias que están asociadas con las características dominantes de una persona y responder en consecuencia. Para obtener más información sobre posibles aplicaciones de las preferencias de consumo, consulte [Casos prácticos](/docs/services/personality-insights?topic=personality-insights-usecases) y [El servicio en acción](/docs/services/personality-insights?topic=personality-insights-applied).

Las secciones siguientes enumeran y describen las preferencias de consumo que puede devolver el servicio. Para obtener más información sobre la interpretación de las preferencias numéricas, consulte [Puntuaciones para preferencias de consumo](/docs/services/personality-insights?topic=personality-insights-numeric#scores). Para obtener información sobre cómo {{site.data.keyword.IBM_notm}} ha desarrollado las preferencias, consulte [La ciencia detrás del servicio](/docs/services/personality-insights?topic=personality-insights-science).

## Preferencias de compra
{: #shopping}

Las preferencias de compra indican el interés del autor en distintos tipos de compras, hasta qué punto están influenciados los hábitos de compra del autor por distintas fuentes externas, y los hábitos de gasto del autor. El ID y el nombre de categoría son `consumption_preferences_shopping` y `Preferencias de compra`. La categoría tiene 12 preferencias.

<table>
  <caption>Tabla 1. Preferencias de compra</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferencia de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nombre
    </th>
    <th style="text-align:center">
      Puntuaciones
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_ownership_cost</code>
    </td>
    <td style="text-align:left">
      Es probable que se muestre receptivo al coste de propiedad al comprar automóviles
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_safety</code>
    </td>
    <td style="text-align:left">
      Es probable que prefiera la seguridad al comprar automóviles
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_quality</code>
    </td>
    <td style="text-align:left">
      Es probable que prefiera la calidad al comprar ropa
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_style</code>
    </td>
    <td style="text-align:left">
      Es probable que prefiera el estilo al comprar ropa
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_comfort</code>
    </td>
    <td style="text-align:left">
      Es probable que prefiera la comodidad al comprar ropa
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_brand_name</code>
    </td>
    <td style="text-align:left">
      Es probable que le influya la marca al adquirir un producto
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_utility</code>
    </td>
    <td style="text-align:left">
      Es probable que le influya la utilidad del producto al adquirir un producto
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_online_ads</code>
    </td>
    <td style="text-align:left">
      Es probable que le influya la publicidad en línea al adquirir un producto
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_social_media</code>
    </td>
    <td style="text-align:left">
      Es probable que le influyan las redes sociales al adquirir un producto
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
     <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_family_members</code>
    </td>
    <td style="text-align:left">
      Es probable que le influya la familia al adquirir un producto
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_spur_of_moment</code>
    </td>
    <td style="text-align:left">
      Es probable que se dé algún capricho en el momento de hacer las compras
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_credit_card_payment</code>
    </td>
    <td style="text-align:left">
      Es probable que prefiera utilizar tarjetas de crédito para las compras
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
</table>

## Preferencias de películas
{: #movie}

Las preferencias de películas indican el interés del autor en distintos tipos de películas. El ID y el nombre de categoría son `consumption_preferences_movie` y `Preferencias de películas`. La categoría tiene 10 preferencias.

<table>
  <caption>Tabla 2. Preferencias de películas</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferencia de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nombre
    </th>
    <th style="text-align:center">
      Puntuaciones
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_romance</code>
    </td>
    <td style="text-align:left">
      Es probable que les gusten las películas románticas
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_adventure</code>
    </td>
    <td style="text-align:left">
      Es probable que le gusten las películas de aventuras
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_horror</code>
    </td>
    <td style="text-align:left">
      Es probable que le gusten las películas de terror
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_musical</code>
    </td>
    <td style="text-align:left">
      Es probable que le gusten las películas musicales
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_historical</code>
    </td>
    <td style="text-align:left">
      Es probable que le gusten las películas históricas
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_science_fiction</code>
    </td>
    <td style="text-align:left">
      Es probable que le gusten las películas de ciencia ficción
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_war</code>
    </td>
    <td style="text-align:left">
      Es probable que le gusten las películas bélicas
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_drama</code>
    </td>
    <td style="text-align:left">
      Es probable que les gusten las películas dramáticas
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_action</code>
    </td>
    <td style="text-align:left">
      Es probable que le gusten las películas de acción
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_documentary</code>
    </td>
    <td style="text-align:left">
      Es probable que le gusten los documentales
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
</table>

## Preferencias musicales
{: #music}

Las preferencias musicales indican el interés del autor en distintos tipos de música y si el autor disfruta interpretando música. El ID y el nombre de categoría son `consumption_preferences_music` y `Preferencias musicales`. La categoría tiene nueve preferencias.

<table>
  <caption>Tabla 3. Preferencias musicales</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferencia de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nombre
    </th>
    <th style="text-align:center">
      Puntuaciones
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rap</code>
    </td>
    <td style="text-align:left">
      Es probable que le guste el rap
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_country</code>
    </td>
    <td style="text-align:left">
      Es probable que le guste el country
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_r_b</code>
    </td>
    <td style="text-align:left">
      Es probable que le guste el R&amp;B
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_hip_hop</code>
    </td>
    <td style="text-align:left">
      Es probable que le guste el hip hop
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_live_event</code>
    </td>
    <td style="text-align:left">
      Es probable que asista a eventos de música en directo
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_playing</code>
    </td>
    <td style="text-align:left">
      Es probable que tenga experiencia interpretando música
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_latin</code>
    </td>
    <td style="text-align:left">
      Es probable que le guste la música latina
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rock</code>
    </td>
    <td style="text-align:left">
      Es probable que le guste el rock
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_classical</code>
    </td>
    <td style="text-align:left">
      Probabilidad de que le guste la música clásica
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
</table>

## Preferencias de lectura y aprendizaje
{: #reading}

Las preferencias de lectura y aprendizaje indican la probabilidad del autor para leer, la motivación del autor para leer, y los tipos de contenido que el autor disfruta leer. El ID y el nombre de categoría son `consumption_preferences_reading` y `Preferencias de lectura`. La categoría tiene cinco preferencias.

<table>
  <caption>Tabla 4. Preferencias de lectura y aprendizaje</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferencia de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nombre
    </th>
    <th style="text-align:center">
      Puntuaciones
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_read_frequency</code>
    </td>
    <td style="text-align:left">
      Probabilidad de leer con frecuencia
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_entertainment_magazines</code>
    </td>
    <td style="text-align:left">
      Probabilidad de que lea revistas de entretenimiento
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_non_fiction</code>
    </td>
    <td style="text-align:left">
      Probabilidad de que lea libros que no sean de ficción
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_financial_investing</code>
    </td>
    <td style="text-align:left">
      Probabilidad de que lea libros sobre inversión financiera
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_autobiographies</code>
    </td>
    <td style="text-align:left">
      Probabilidad de que lea libros autobiográficos
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
</table>

## Preferencias de salud y actividad
{: #health}

Las preferencias de salud y actividad indican el interés del autor en alimentos saludables y actividad física. El ID y el nombre de categoría son `consumption_preferences_health_and_activity` y `Preferencias de salud y actividad`. La categoría tiene tres preferencias.

<table>
  <caption>Tabla 5. Preferencias de salud y actividad</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferencia de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nombre
    </th>
    <th style="text-align:center">
      Puntuaciones
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_eat_out</code>
    </td>
    <td style="text-align:left">
      Probabilidad de que coma fuera con frecuencia
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_gym_membership</code>
    </td>
    <td style="text-align:left">
      Probabilidad de que esté inscrito en un gimnasio
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_outdoor</code>
    </td>
    <td style="text-align:left">
      Probabilidad de que le gusten las actividades al aire libre
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
</table>

## Preferencias de emprendimiento
{: #entrepreneur}

Las preferencias de emprendimiento indican el interés del autor en iniciar un negocio. El ID y el nombre de categoría son `consumption_preferences_entrepreneurship` y `Preferencias de emprendimiento`. La categoría tiene una preferencia.

<table>
  <caption>Tabla 6. Preferencias de emprendimiento</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferencia de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nombre
    </th>
    <th style="text-align:center">
      Puntuaciones
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_start_business</code>
    </td>
    <td style="text-align:left">
      Es probable que considere iniciar un negocio en los próximos años
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
</table>

## Preferencias de interés en cuestiones ambientales
{: #environment}

Las preferencias de interés en cuestiones ambientales indican el interés del autor en el entorno. El ID y el nombre de categoría son `consumption_preferences_environmental_concern` y `Preferencias de interés en cuestiones ambientales`. La categoría tiene una preferencia.

<table>
  <caption>Tabla 7. Preferencias de interés en cuestiones ambientales</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferencia de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nombre
    </th>
    <th style="text-align:center">
      Puntuaciones
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_concerned_environment</code>
    </td>
    <td style="text-align:left">
      Es probable que le preocupe el medioambiente
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>0,5</code> (neutral)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
</table>

## Preferencias de voluntariado
{: #volunteer}

Las preferencias de voluntariado indican el interés del autor en el voluntariado para causas sociales. El ID y el nombre de categoría son `consumption_preferences_volunteering` y `Preferencias de voluntariado`. La categoría tiene una preferencia.

<table>
  <caption>Tabla 8. Preferencias de voluntariado</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID de preferencia de consumo
    </th>
    <th style="width:30%; text-align:left">
      Nombre
    </th>
    <th style="text-align:center">
      Puntuaciones
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_volunteer</code>
    </td>
    <td style="text-align:left">
      Es probable que realice tareas de voluntario para obras sociales
    </td>
    <td style="text-align:center">
      <code>0,0</code> (improbable)<br/>
      <code>1,0</code> (probable)
    </td>
  </tr>
</table>
