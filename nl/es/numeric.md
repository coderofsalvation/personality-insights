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

# Interpretación de los resultados numéricos
{: #numeric}

El servicio de {{site.data.keyword.personalityinsightsshort}} devuelve resultados numéricos para cada una de las características de personalidad y de comportamiento y para cada una de las preferencias de consumo. Los valores difieren en la información que proporcionan.
{: shortdesc}

> **Nota:** Para la entrada en árabe y en coreano, el servicio no puede producir percentiles significativos ni puntuaciones en bruto para varias características de personalidad. Para obtener más información, consulte [Limitaciones para entrada en árabe y coreano](#limitations).

## Percentiles para las características de personalidad
{: #percentiles}

Para cada solicitud, el servicio siempre informa de una puntuación normalizada como un `percentil` para cada una de las características de personalidad de cinco grandes, valores y necesidades. Las puntuaciones normalizadas representan un rango de percentiles para cada característica basada en cualidades deducidas del texto de entrada. El servicio calcula puntuaciones normalizadas comparando la puntuación en bruto para el texto del autor con resultados de una población de ejemplo. El servicio informa de cada percentil como un doble en el rango de 0 a 1.

Por ejemplo, un percentil de `0,64980796071382` para la característica de personalidad `big5_extraversion` indica que el autor del texto ha puntuado en el percentil número 65 para dicha característica. El escrito del autor exhibe la tendencia a una medida que es superior al 64 por ciento e inferior del 34 por ciento de la población de ejemplo. La precisión del percentil depende del número de palabras enviadas como entrada con la solicitud; para obtener más información, consulte [Proporcionar suficiente entrada](/docs/services/personality-insights/input.html#sufficient).

> **Nota:** No existe ninguna relación matemática entre los percentiles de los que se ha informado para las cinco grandes dimensiones y facetas. El servicio calcula el percentil normalizado para cada dimensión y faceta, basado independientemente en las correlaciones entre las puntuaciones de los participantes de la encuesta para dicha dimensión o faceta y las palabras que utiliza. Por lo tanto, aunque las facetas proporcionen descripciones precisas de las dimensiones, la adición de las puntuaciones para las seis facetas de una dimensión no genera necesariamente el percentil para dicha dimensión. Lo mismo ocurre con las puntuaciones en bruto.

## Puntuaciones en bruto para características de personalidad
{: #rawScores}

Si especifica `true` para el parámetro de consulta `raw_scores` de la solicitud, el servicio informará de una `raw_score` para cada característica de personalidad. Las puntuaciones en bruto representan la puntuación para la característica específica basada exclusivamente en el texto del autor y en el modelo para dicha característica, sin comparar los resultados con una población de ejemplo. Las puntuaciones en bruto se pueden interpretar como las puntuaciones que recibiría el autor de realizar una prueba de personalidad.

El servicio informa de cada puntuación en bruto como un doble en el rango de 0 a 1. Una puntuación superior normalmente indica una probabilidad mayor de que el autor tenga dicha característica. Sin embargo, las puntuaciones en bruto deben considerarse en formato agregado: El rango de valores en la práctica podría ser mucho menor que de 0 a 1, por lo que debe considerarse una puntuación individual en el contexto de las puntuaciones generales y su rango. Pero en general, una puntuación en bruto, por ejemplo, de `0.56817738781166` para la característica de personalidad `big5_extraversion` indica que el autor probablemente haya conseguido esta puntuación en una prueba de personalidad. Compare esta puntuación en bruto con el percentil normalizado informado para el mismo autor y característica en la sección anterior.

El servicio convierte en disponibles puntuaciones en bruto para los usuarios que desean aplicar una normalización personalizada para un caso de ejemplo específico o para quienes no necesitan una comparación con una población de ejemplo. Los usuarios que desean conocer cómo se comparan las características del autor con una población de ejemplo grande pueden utilizar las puntuaciones normalizadas. Los usuarios que desean derivar sus propias puntuaciones de percentil normalizadas desde los datos en bruto pueden comparar las puntuaciones en bruto con una población de ejemplo distinta y aplicar un enfoque distinto a la normalización.

Para normalizar una puntuación en bruto con un percentil para una característica específica, compare la puntuación en bruto con una población de ejemplo para la que se conocen la desviación media y la estándar para la característica. Por ejemplo, {{site.data.keyword.IBM_notm}} realizó estudios para recopilar datos de una población de ejemplo grande de usuarios de Twitter. {{site.data.keyword.IBM_notm}} ha calculado las puntuaciones de los usuarios para cada una de las características de personalidad y, a continuación, estableció la desviación media y estándar para cada característica. Para calcular la puntuación de percentil para una puntuación en bruto deducida de su análisis de texto de entrada, el servicio utilizará la desviación media y estándar derivada de su población de Twitter de ejemplo para dicha característica.

## Porcentajes para características de comportamiento
{: #percentages}

Si envía datos JSON cuyos elementos de contenido tienen indicaciones de fecha y hora, el servicio informará de un `porcentaje` para cada característica de comportamiento. Las características de comportamiento identifican la distribución temporal de la entrada. El porcentaje indica cuántos de los elementos de contenido se han producido durante cada día de la semana y la hora del día. Por ejemplo, un porcentaje de `0,4561049445005` para la característica de comportamiento `behavior_0000` significa que se ha creado apenas un 46 por ciento de los elementos de contenido entre las horas de la medianoche y las 1:00 de la madrugada.

## Puntuaciones para preferencias de consumo
{: #scores}

Si especifica `true` para el parámetro de consulta `consumption_preferences` de la solicitud, el servicio informará de preferencias de consumo que incluyan una `puntuación` para cada preferencia. El servicio obtiene la puntuación de las características de personalidad que deduce del texto de entrada. La puntuación es un doble que indica la probabilidad de que el autor del texto prefiera el artículo. Es una indicación de preferencia, no un porcentaje normalizado.

Para algunas preferencias, la puntuación es uno de los siguientes tres valores:

-   `0,0`: Es muy improbable que el autor prefiera el artículo. Para algunas preferencias, puede interpretar el valor como significativo de que el autor tiene un muy bajo nivel de interés.
-   `0,5`: El autor es neutro con respecto al artículo. Para algunas preferencias, el valor puede significar que el autor tiene un nivel medio de interés.
-   `1,0`: Es muy probable que el autor prefiera el artículo. Para algunas preferencias, el valor indica un nivel alto de interés.

Para otras preferencias, la puntuación representa un valor binario. El autor del texto de entrada no es probable (`0,0`) o es probable (`1,0`) que tenga interés en el artículo, o el autor tiene un nivel de interés bajo o alto. En algunos casos, la puntuación puede representar una simple respuesta sí o no (por ejemplo, ¿es probable que el autor tenga experiencia de voluntariado para causas sociales?).

Para obtener una lista completa de todas las preferencias por categoría y el rango de sus resultados, consulte [Preferencias de consumo](/docs/services/personality-insights/preferences.html).

## Limitaciones para entrada en árabe y coreano
{: #limitations}

Para la entrada en árabe y coreano, los modelos del servicio no pueden producir resultados significativos para un subconjunto de características de personalidad. Para las características siguientes, las puntuaciones de los percentiles normalizados son siempre `0,5`, y las puntuaciones en bruto son siempre la media de la distribución original. El campo `significant` para cada una de estas características es siempre `false`. *No* se base en los resultados para estas características como parte del perfil de personalidad del autor.

<table>
  <caption>Tabla 1. Características cuyos resultados no son significativos</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      Características
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      Resultados de árabe que<br/>no son significativos
    </th>
    <th style="text-align:left; vertical-align:bottom; width:40%">
      Resultados de coreano que<br/>no son significativos
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Cinco grandes dimensiones
    </td>
    <td style="text-align:left; vertical-align:top">
      Rango emocional
    </td>
    <td style="text-align:left; vertical-align:top">
      Ninguno
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Cinco grandes facetas
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; line-height:110%; padding:0px">
          *Simpatía*: Altruismo, Cooperación, Modestia y Confianza
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Responsabilidad*: Consecución de logros y Obediencia
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Extraversión*: Alegría y Amigabilidad (Extrovertido)
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Rango emocional*: Ira (Fogoso), Tendencia a la preocupación, Falta de
          moderación, y Conciencia de uno mismo
        </li>
        <li style="margin:10px 0px 0px 0px; line-height:110%; padding:0px">
          *Apertura*: Osadía, Imaginación, e Intelecto
        </li>
      </ul>
    </td>
    <td style="text-align:left; vertical-align:top">
      <ul style="margin:0px 0px 0px 15px; padding:0px">
        <li style="margin:0px; padding:0px">
          *Extraversión*: Búsqueda de emociones
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Necesidades
    </td>
    <td style="text-align:left; vertical-align:top">
      Ideal, Libertad, Amor, Uso práctico, y Estructura
    </td>
    <td style="text-align:left; vertical-align:top">
      Libertad y Estabilidad
    </td>
  </tr>
  </tr>
    <td style="text-align:left; vertical-align:top">
      Valores
    </td>
    <td style="text-align:left; vertical-align:top">
      Superación personal
    </td>
    <td style="text-align:left; vertical-align:top">
      Conservación
    </td>
  </tr>
</table>
