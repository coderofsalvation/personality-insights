---

copyright:
  years: 2015, 2017
lastupdated: "2017-11-28"

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

# Notas del release
{: #release-notes}

Las secciones siguientes documentan las nuevas características y los cambios incluidos para cada release del servicio de {{site.data.keyword.personalityinsightsshort}}. A menos que se indique lo contrario, todos los cambios eran compatibles y estaban disponibles de forma automática y transparente para todas las aplicaciones nuevas y existentes.
{: shortdesc}

> **Nota:** Las notas de release documentan la *versión de servicio* y la *versión de interfaz* para todas las actualizaciones recientes. Especifique la *versión de interfaz* con el parámetro de consulta `versión` para utilizar nuevas características y la funcionalidad disponible con dicha actualización. El servicio devuelve ambas versiones con la cabecera de respuesta `X-Service-Api-Version`.

## 13 de octubre de 2017
{: #October2017}

**Versión de servicio:** `3.4.0`<br/> **Versión de interfaz:** `2017-10-13`

-   El objeto `Rasgo` de un perfil de personalidad ahora incluye un campo `significant` adicional. Otro objeto `Rasgo` informa de los resultados para cada dimensión y faceta de cinco grandes, necesidad y valor. El campo `significant` de cada instancia del objeto identifica si los resultados para dicha característica son significativos para el idioma de entrada (`Content-Language`) de la solicitud:

    -   Para inglés, español y japonés, el campo es siempre `true` para todas las características de personalidad.
    -   Para árabe y coreano, el campo es `true` para la mayoría de las características de personalidad, pero es `false` para aquellas para las que los modelos del servicio no pueden producir resultados significativos. El campo es `false` para un conjunto constante de características; para obtener una lista completa, consulte [Limitaciones para entrada en árabe y coreano](/docs/services/personality-insights/numeric.html#limitations). No se base en los resultados para cualquier característica para la que el campo es `false`.

    Para obtener información sobre el contenido de la respuesta JSON del servicio, consulte [Comprensión de un perfil JSON](/docs/services/personality-insights/output.html).
-   La salida CSV también incluye ahora columnas adicionales cuyas cabeceras se denominan `*_significant`. Cada columna proporciona un valor booleano para indicar si una característica es significativa. Para obtener información sobre el contenido de respuesta CSV del servicio, consulte [Comprensión de un perfil CSV](/docs/services/personality-insights/output-csv.html).
-   La versión de interfaz especificada con el parámetro `version` es `2017-10-13` para utilizar esta versión más reciente de la interfaz.

## 18 de septiembre de 2017
{: #September2017}

**Versión de servicio:** `3.3.0`<br/> **Versión de interfaz:** `2016-10-19`

El servicio ahora da soporte a contenido de entrada en coreano (`ko`). Para obtener información sobre el MAE (Error absoluto medio promedio) y la correlación promedio para la entrada en coreano, consulte [MAE promedio por idioma y correlación](/docs/services/personality-insights/science.html#precisePerLanguage).

Los modelos del servicio no pueden producir percentiles significativos ni puntuaciones en bruto para algunas características de personalidad de la entrada en coreano. Para obtener más información sobre los resultados para estas características, consulte [Limitaciones para entrada en árabe y coreano](/docs/services/personality-insights/numeric.html#limitations).

## 10 de abril de 2017
{: #April2017}

**Versión de servicio:** `3.1.7`<br/> **Versión de interfaz:** `2016-10-19`

-   El servicio ha cambiado la forma de manejar solicitudes con grandes cantidades de contenido de entrada. El servicio acepta un máximo de 20 MB de contenido. Sin embargo, con los modelos basados en *GloVe*, los niveles de precisión se desactivaron a alrededor de las 3000 palabras de entrada. Esto es distinto a los modelos anteriores, donde más texto producía una mayor precisión. En general, el servicio ya no necesita tanto contenido para producir un perfil preciso. Pero el contenido adicional requiere tiempo de proceso adicional, lo que puede provocar que una solicitud finalice el tiempo de espera antes de que se complete.

    Por lo tanto, el servicio ahora extrae y utiliza solo los primeros 250 KB de contenido, sin contar la marcación HTML o JSON, de solicitudes grandes. Esta cifra no se correlaciona con un número exacto de palabras, que varía en función del idioma y de la naturaleza del texto. En inglés, por ejemplo, la longitud de palabra promedio está entre cuatro y cinco caracteres, por lo que esta cifra proporciona alrededor de 50.000 palabras, lo que es al menos 15 veces más palabras de lo que el servicio necesita. El campo `word_count` del JSON de respuesta indica el número de palabras que el servicio utiliza realmente para una solicitud, lo que puede ser inferior al número de palabras de la entrada.

    Puesto que sigue basando un perfil en muchas más palabras de lo estrictamente necesario para la precisión máxima, el servicio genera un perfil que es tan preciso como anteriormente. Sin embargo, el servicio responde mucho más rápido que antes. Para las solicitudes para las que solo utiliza una parte del contenido de entrada, el servicio devuelve el siguiente mensaje de aviso `CONTENT_TRUNCATED` para que el usuario conozca el hecho:

    `Para la máxima precisión al optimizar también el tiempo de proceso, solo se han analizado los primeros 250 KB de texto de entrada (excluida la marcación). Los niveles de precisión se desactivaron a las aproximadamente 3.000 palabras para que no afectara a la precisión del perfil.`

    Para obtener más información, consulte [Proporcionar suficiente entrada](/docs/services/personality-insights/input.html#sufficient).
-   El servicio se ha actualizado con pequeños arreglos de seguridad.

## Releases anteriores
{: #older}

-   [1 de marzo de 2017](#March2017)
-   [20 de febrero de 2017](#February2017b)
-   [13 de febrero de 2017](#February2017)
-   [13 de enero de 2017](#January2017)
-   [15 de diciembre de 2016](#December2016)
-   [15 de noviembre de 2016](#November2016)
-   [20 de octubre de 2016](#October2016b)
-   [12 de octubre de 2016](#October2016a)
-   [31 de agosto de 2016](#August2016)
-   [14 de julio de 2016](#July2016b)
-   [1 de julio de 2016](#July2016a)
-   [7 de junio de 2016](#June2016b)
-   [1 de junio de 2016](#June2016a)
-   [17 de mayo de 2016](#May2016)
-   [18 de marzo de 2016](#March2016)
-   [9 de julio de 2015](#July2015)
-   [23 de febrero de 2015](#February2015)

### 1 de marzo de 2017
{: #March2017}

**Versión de servicio:** `3.1.6`<br/> **Versión de interfaz:** `2016-10-19`

El servicio de {{site.data.keyword.personalityinsightsshort}} se ha actualizado con pequeñas mejoras en el registro.

### 20 de febrero de 2017
{: #February2017b}

**Versión de servicio:** `3.1.5.1`<br/> **Versión de interfaz:** `2016-10-19`

El servicio de Personality Insights se ha actualizado con pequeños arreglos de seguridad y de defectos, y para mejorar la medición de llamadas de API.

### 13 de febrero de 2017
{: #February2017}

**Versión de servicio:** `3.1.4`<br/> **Versión de interfaz:** `2016-10-19`

-   La lista de preferencias de consumo se ha perfeccionado para incluir solo las más importantes para entender los hábitos de estilo de vida dominantes de una persona y las características del consumidor. La lista de preferencias de consumo se ha reducido de 51 a 42; el resto de las preferencias expresan la probabilidad del autor para que prefiera distintos productos, servicios y actividades de forma más concisa, lo que facilita tomar medidas basadas en los resultados. El servicio ya no devuelve las siguientes nueve preferencias de consumo. Para obtener más información sobre las preferencias restantes, consulte [Preferencias de consumo](/docs/services/personality-insights/preferences.html).

    <table>
      <caption>Tabla 1. Cambios en las preferencias de consumo</caption>
      <tr>
        <th style="text-align:left">Categoría</th>
        <th style="text-align:left">Preferencias de consumo eliminadas</th>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_shopping</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_automobile_resale_value</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_reading</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_read_motive_enjoyment</code>
            <code>consumption_preferences_read_motive_information</code>
            <code>consumption_preferences_read_motive_mandatory</code>
            <code>consumption_preferences_read_motive_relaxation</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_health_and_activity</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_adventurous_sports</code>
            <code>consumption_preferences_fast_food_frequency</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_volunteering</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_volunteering_time</code>
            <code>consumption_preferences_volunteer_learning</code>
          </p>
        </td>
      </tr>
    </table>

-   *Para la entrada en árabe*, la información sobre el Error absoluto medio promedio (MAE, Average Mean Absolute Error) y la correlación promedio está disponible ahora en [MAE promedio por idioma y correlación](/docs/services/personality-insights/science.html#precisePerLanguage). Además, los modelos del servicio no pueden producir percentiles significativos ni puntuaciones en bruto para una recopilación de características de personalidad. Para obtener más información sobre los resultados para estas características, consulte [Limitaciones para entrada en árabe y coreano](/docs/services/personality-insights/numeric.html#limitations).

### 13 de enero de 2017
{: #January2017}

**Versión de servicio:** `3.1.2.1`<br/> **Versión de interfaz:** `2016-10-19`

El servicio de Personality Insights se ha actualizado con algunos pequeños arreglos de defectos.

### 15 de diciembre de 2016
{: #December2016}

**Versión de servicio:** `3.1.1`<br/> **Versión de interfaz:** `2016-10-19`

Para el texto de entrada en árabe, el servicio de {{site.data.keyword.personalityinsightsshort}} utiliza ahora la técnica de inclusión de palabras de código abierto llamada *GloVe* para desarrollar un perfil de personalidad. El servicio ya no utiliza el diccionario de psicolingüística LIWC (Linguistic Inquiry and Word Count) para cualquier idioma. Para obtener más información sobre cómo desarrolla el servicio un retrato de personalidad, consulte [Cómo se deducen las características de personalidad](/docs/services/personality-insights/science.html#researchInfer).

### 15 de noviembre de 2016
{: #November2016}

**Versión de servicio:** `3.1.0`<br/> **Versión de interfaz:** `2016-10-19`

-   Para el texto de entrada en japonés, el servicio de {{site.data.keyword.personalityinsightsshort}} utiliza ahora la técnica de inclusión de palabras de código abierto llamada *GloVe* para desarrollar un perfil de personalidad; el servicio ya no utiliza el diccionario de psicolingüística LIWC (Linguistic Inquiry and Word Count) para la entrada en japonés. Para obtener más información, consulte [Cómo se deducen las características de personalidad](/docs/services/personality-insights/science.html#researchInfer).
-   Los campos `name` de los objetos `ConsumptionPreferencesCategory` y `ConsumptionPreferences` se devuelven ahora con series localizadas en el idioma especificado con la cabecera de solicitud `Accept-Language`.
-   La actualización incluye unos pequeños arreglos de defectos.

### 20 de octubre de 2016
{: #October2016b}

**Versión de servicio:** `3.0.0`<br/> **Versión de interfaz:** `2016-10-19`

El servicio de {{site.data.keyword.personalityinsightsshort}} y sus API se han actualizado significativamente. La API se incrementa de la versión 2 a la versión 3 y ofrece nuevas características. Las secciones restantes de esta nota de release describen los cambios en detalle.

La versión 3 no es compatible con la versión 2. Se recomienda migrar a la versión 3 para aprovechar las nuevas características y cambios. La migración a la versión 3 consta solo de actualizar y redesplegar las aplicaciones para utilizar los cambios descritos en estas notas de release para la nueva versión. No es necesario crear una nueva instancia del servicio en {{site.data.keyword.Bluemix_notm}}; solo necesita llamar a la API de `v3`.

> **Nota:** La versión 2 de la API de {{site.data.keyword.personalityinsightsshort}} se eliminará del servicio en el futuro próximo. Se recomienda encarecidamente migrar a la versión 3 lo antes posible. Por ahora, puede acceder a la documentación de referencia para la versión 2 en [Referencia de API para v2 ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/watson/developercloud/personality-insights/api/v2/){: new_window}; también puede acceder a la herramienta interactiva para probar llamadas en la versión 2 y visualizar respuestas en directo del servicio en [Explorador de API para v2 ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v2){: new_window}.

#### Más información sobre la versión 3

Esta documentación ahora describe la versión 3 de la API de {{site.data.keyword.personalityinsightsshort}}. Las secciones siguientes resumen los cambios para la nueva versión de la interfaz:

-   Para obtener información sobre la llamada al método `/v3/profile`, consulte [Solicitud de un perfil](/docs/services/personality-insights/input.html).
-   Para obtener información sobre la respuesta del método `/v3/profile`, consulte [Comprensión de un perfil JSON](/docs/services/personality-insights/output.html) y [Comprensión de un perfil CSV](/docs/services/personality-insights/output-csv.html).
-   Para obtener información detallada sobre la interfaz de versión 3, consulte la [Referencia de API ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

#### Cambios en los parámetros del método <code>/v3/profile</code>

Los parámetros del método `/v3/profile` han cambiado de la manera siguiente:

-   La API ofrece ahora un parámetro de consulta opcional denominado `consumption_preferences`. El parámetro acepta un valor booleano que indica si la información deducida sobre las preferencias de consumo se devolverá con los resultados. De forma predeterminada, la información no está incluida en la respuesta. Para obtener más información, consulte [Nueva característica de preferencias de consumo](#cp).
-   La API incluye ahora un parámetro de consulta necesario denominado `version`. El parámetro acepta una serie que identifica la versión solicitada de la API y el formato de respuesta como una fecha en el formato `AAAA-MM-DD`; por ejemplo, especifique `2016-10-19` para el 19 de octubre de 2016. Este parámetro permite al servicio actualizar su API o formato de respuesta para versiones nuevas sin romper los clientes existentes. La serie inicial para la versión 3 de la API es `2016-10-19`.

    La fecha que especifique no tiene que coincidir exactamente con una versión del servicio; el servicio utiliza la versión que no sea posterior a la fecha que proporcione. Si especifica una fecha anterior a la fecha de release de la versión 3, el servicio utilizará la versión 3 de la API. Si especifica una fecha que está en el futuro o que es posterior a la versión más reciente, el servicio utilizará la última versión.
-   El nombre del parámetro de consulta `include_raw` es ahora `raw_scores`.
-   El nombre del parámetro de consulta `headers` es ahora `csv_headers`.

#### Nueva característica de preferencias de consumo
{: #cp}

La característica de preferencias de consumo proporciona una indicación de la tendencia del autor por exhibir distintas tendencias del consumidor. Cuando pase el parámetro de consulta `consumption_preferences` con un valor de `true` al método `/v3/profile`, el servicio devolverá los siguientes resultados adicionales con el objeto `Profile`:

-   Un campo `consumption_preferences` que proporciona una matriz de objetos `ConsumptionPreferencesCategory`.
-   Cada objeto `ConsumptionPreferencesCategory` incluye los campos siguientes:
    -   `consumption_preference_category_id`: El ID de una de las categorías de preferencias de consumo.
    -   `name`: El nombre visible de usuario de la categoría.
    -   `consumption_preferences`: Una matriz de objetos `ConsumptionPreferences` que proporciona resultados deducidos del texto de entrada para las preferencias individuales de la categoría.
-   Cada objeto `ConsumptionPreferences` incluye los campos siguientes:
    -   `consumption_preference_id`: El ID de una de las preferencias de consumo.
    -   `name`: El nombre visible de usuario de la preferencia de consumo.
    -   `score`: La puntuación para la preferencia de consumo. Para muchas preferencias, `0,0` indica improbabilidad, `0,5` indica neutralidad, y `1,0` indica probabilidad. Las puntuaciones para algunas preferencias son binarias y no permiten un valor neutral. La puntuación es una indicación de preferencia basada en los resultados deducidos del texto de entrada, no un percentil normalizado.

Para obtener más información sobre las preferencias de consumo, consulte [Preferencias de consumo](/docs/services/personality-insights/preferences.html).

> **Nota:** Actualmente, el campo `name` para ambos objetos de preferencias de consumo siempre se devuelve en inglés, independientemente del idioma especificado con la cabecera de solicitud `Accept-Language`.

#### Cambios en objetos y campos JSON

Los objetos de entrada y salida JSON y sus campos se han simplificado y aclarado de la forma siguiente:

-   Los campos siguientes se han eliminado de los objetos `ContentItem` JSON que puede pasar al método `/v3/profile` con una solicitud:
    -   `userid`
    -   `sourceid`
    -   `charset` (anteriormente en desuso)

    Pase estos objetos del cuerpo de una solicitud JSON como elementos de la matriz `contentItems` del objeto `Content`.
-   Los siguientes campos del objeto `Profile` JSON devueltos por el método `/v3/profile` se han modificado:
    -   Los campos siguientes se han eliminado:
        -   `id`
        -   `source`
    - El campo `tree` se ha eliminado. Se ha sustituido por cuatro nuevos campos:
        -   `personality` para las cinco grandes características de personalidad.
        -   `needs` para las características necesidades.
        -   `values` para las características valores.
        -   `behavior` para los resultados temporales sobre la distribución del contenido en los días de la semana y las horas del día. Este campo solo se devuelve para la entrada JSON que tiene indicación de fecha y hora.

    Este cambio mueve efectivamente los resultados a un nivel superior en el objeto `Profile` JSON, eliminando un nivel de recurrencia.
    -   El nombre del campo `processed_lang` es ahora `processed_language`.
-   Los siguientes campos de objetos `Trait` JSON devueltos por el método `/v3/profile` han cambiado de nombre:
    -   El nombre del campo `id` del objeto `Trait` JSON es ahora `trait_id`.
    -   El nombre del campo `percentage` del objeto `Trait` JSON es ahora `percentile`.
-   Los campos siguientes de los objetos `Trait` JSON devueltos por el método `/v3/profile` se han eliminado:
    -   `sampling_error`
    -   `raw_sampling_error`

    El servicio ahora informa de un Error absoluto medio promedio (MAE, Average Mean Absolute Error) que califica la precisión de sus resultados. Para obtener más información sobre el MAE para cantidades distintas de texto de entrada, consulte [Proporcionar suficiente entrada](/docs/services/personality-insights/input.html#sufficient).
-   Los objetos `Trait` JSON se siguen devolviendo para los campos `personality`, `needs`, y `values` del objeto `Profile`. Pero el campo `behavior` devuelve una matriz de objetos JSON denominada `Behavior` que tiene los campos siguientes:
    -   `trait_id`
    -   `name`
    -   `categoría`
    -   `percentage`

    Además, la información de comportamiento ya no se devuelve como un árbol de valores. La salida consta de una matriz única que enumera todas las características temporales (día de la semana y hora del día).
-   El nombre del campo `id` del objeto `Warnings` JSON que se puede devolver mediante el método `/v3/profile` es ahora `warnings_id`.

#### Cambios en los ID JSON
{: #ids}

Los ID JSON que devuelve el servicio para el campo `trait_id` (anteriormente `id`) del objeto `Trait` y el nuevo `Behavior` han cambiado de la forma siguiente:

-   Los ID para las cinco grandes dimensiones empiezan ahora por la serie `big5_`.
-   Los ID para las cinco grandes facetas empiezan ahora por la serie `facet_`.
-   Los ID para necesidades empiezan ahora por la serie `need_`.
-   Los ID para valores empiezan ahora por la serie `value_`.
-   Los ID para todas las características temporales empiezan ahora por la serie `behavior_`.
-   Los ID para las características temporales relacionadas con la hora del día utilizan ahora el formato de hora de 24 horas de cuatro dígitos (por ejemplo, `behavior_0000`) en lugar del formato de hora de 12 horas (por ejemplo, `0:00 am`).
-   Todos los caracteres están ahora en minúscula.
-   Los espacios y los guiones están ahora subrayados.

#### Cambios en las cabeceras CSV
{: #headers}

Las cabeceras de columna opcionales que el servicio puede devolver para la salida CSV han cambiado de la forma siguiente:

-   Todos los cambios descritos para el `trait_id` de la salida JSON también se aplican a las cabeceras CSV.
-   Las cabeceras para puntuaciones en bruto para las cinco grandes dimensiones empiezan ahora por la serie `big5_`.
-   Las cabeceras para puntuaciones en bruto para las cinco grandes facetas empiezan ahora por la serie `facet_`.
-   Las cabeceras para puntuaciones en bruto para necesidades empiezan ahora por la serie `need_`.
-   Las cabeceras para puntuaciones en bruto para valores empiezan ahora por la serie `value_`.
-   La cabecera para la columna de idioma procesado es ahora `processed_language` en lugar de `processed_lang`.
-   Las columnas `user` y `source_id` ya no son devueltas.
-   Todos los caracteres están ahora en minúscula.
-   Los espacios y los guiones están ahora subrayados.

#### Eliminación del método <code>visualize</code>

La versión 2 de la API del servicio incluía un método `visualize` en desuso utilizado en un release anterior para visualizar los resultados de una llamada en el método `/v3/profile`. El método `visualize` se ha eliminado de la API de servicio. El servicio sigue proporcionando una colección de archivos JavaScript que permiten la visualización gráfica de un perfil; para obtener más información, consulte [Visualización de un perfil](/docs/services/personality-insights/developer-overview.html#visualize).

### 12 de octubre de 2016
{: #October2016a}

Para el texto de entrada en español, el servicio de {{site.data.keyword.personalityinsightsshort}} utiliza ahora la técnica de inclusión de palabras de código abierto llamada *GloVe* para desarrollar un perfil de personalidad; el servicio ya no utiliza el diccionario de psicolingüística LIWC (Linguistic Inquiry and Word Count) para la entrada en español. El servicio empezó a utilizar el modelo nuevo para el texto de entrada en inglés el 31 de agosto; se aplicará el nuevo modelo al resto de los idiomas de entrada en el futuro próximo. Para obtener más información sobre el nuevo modelo, consulte [Cómo se deducen las características de personalidad](/docs/services/personality-insights/science.html#researchInfer).

### 31 de agosto de 2016
{: #August2016}

El servicio de {{site.data.keyword.personalityinsightsshort}} utiliza ahora una técnica de inclusión de palabras de código abierto llamada *GloVe* para desarrollar un perfil de personalidad; para obtener más información, consulte [Cómo se deducen las características de personalidad](/docs/services/personality-insights/science.html#researchInfer). En este momento, el servicio utiliza el nuevo enfoque solo para el texto en inglés. Para otros idiomas, el servicio seguirá utilizando el diccionario de psicolingüística LIWC (Linguistic Inquiry and Word Count). Las versiones futuras del servicio utilizarán el enfoque de vocabulario abierto para todos los idiomas.

Para el modelo nuevo utilizado para la entrada en inglés, el servicio informará del Error absoluto medio promedio (MAE, Average Mean Absolute Error) de los resultados para su modelo formado. Para obtener información sobre cómo cambia el MAE con distintas cantidades de texto de entrada, consulte [Proporcionar suficiente entrada](/docs/services/personality-insights/input.html#sufficient). Las versiones futuras del servicio informarán del MAE para modelos que no estén en inglés y recomendarán que lo utilice, en contraposición a errores de muestreo, para determinar cómo cambia la precisión del servicio en función de la cantidad de texto de entrada que proporcione.

### 14 de julio de 2016
{: #July2016b}

-   Para entrada en árabe, el servicio puede ahora reducir la cantidad de texto de entrada por motivos de rendimiento. En un umbral determinado, la precisión de los resultados para árabe no mejora con más palabras. Si el servicio recorta el texto de entrada en árabe, devolverá un aviso `PARTIAL_TEXT_USED` con el mensaje siguiente:

    `El texto proporcionado para calcular el perfil se ha reducido por motivos de rendimiento. Esta acción no afecta la precisión de la salida, ya que no se necesitaba todo el texto de entrada.`
-   La actualización incluye arreglos de defectos adicionales y mejoras internas.

### 1 de julio de 2016
{: #July2016a}

-   Los planes de precios del servicio han cambiado para ofrecer precios más bajos para los usuarios de {{site.data.keyword.personalityinsightsshort}}. Para obtener más información, consulte el servicio de [{{site.data.keyword.personalityinsightsshort}} en el Catálogo de {{site.data.keyword.Bluemix_short}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://console.ng.bluemix.net/catalog/services/personality-insights/){: new_window}.
-   La lista de idiomas de respuesta soportados que puede especificar con la cabecera `Accept-Language` ahora incluye lo siguiente:
    -   `ar` (Árabe)
    -   `de` (Alemán)
    -   `en` (Inglés, el valor predeterminado)
    -   `es` (Español)
    -   `fr` (Francés)
    -   `it` (Italiano)
    -   `ja` (Japonés)
    -   `ko` (Coreano)
    -   `pt-br` (Portugués de Brasil)
    -   `zh-cn` (Chino simplificado)
    -   `zh-tw` (Chino tradicional)

    Para obtener más información, consulte [Especificación de idiomas de solicitud y respuesta](/docs/services/personality-insights/input.html#languages).
-   El método `/v2/profile` ahora puede devolver los siguientes códigos de estado HTTP:
    -   429 *Demasiadas solicitudes*: El servicio está procesando en este momento demasiadas solicitudes para el idioma del contenido. Espere un poco y vuelva a intentar la solicitud. Si está enviando muchas solicitudes para el idioma, considere la posibilidad de regular la velocidad a la que envía las solicitudes.
    -   504 *Tiempo de espera excedido de pasarela*: La solicitud ha superado el tiempo de espera o ha tardado demasiado en procesarse. Espere un poco y vuelva a intentar la solicitud. Si la entrada contenía un gran número de palabras (por ejemplo, más de 20.000), considere la posibilidad de reducir el número de palabras mientras mantiene las directrices para la entrada significativa.

    El método ya no devuelve 503 *Servicio no disponible*. Para obtener más información sobre posibles códigos de respuesta, consulte la [Referencia de API ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.
-   La actualización incluye arreglos de defectos adicionales y mejoras internas.

### 7 de junio de 2016
{: #June2016b}

-   El servicio ahora da soporte a CORS (Cross-Origin Resource Sharing) para permitir que los clientes basados en navegador llamen al servicio directamente. Para obtener más información, consulte [Soporte de CORS](/docs/services/personality-insights/developer-overview.html#CORS).
-   El rendimiento del servicio al procesar texto en japonés ha mejorado considerablemente.
-   La actualización incluye arreglos de defectos adicionales y mejoras internas.

### 1 de junio de 2016
{: #June2016a}

El servicio de {{site.data.keyword.personalityinsightsshort}} se ha actualizado para arreglos de defectos y mejoras internas. También se ha añadido un campo de nivel superior adicional, `warnings`, a los resultados JSON devueltos por el servicio; para obtener más información, consulte la [Referencia de API ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

### 17 de mayo de 2016
{: #May2016}

El servicio de {{site.data.keyword.personalityinsightsshort}} se ha actualizado para arreglos de defectos y mejoras internas. 

### 18 de marzo de 2016
{: #March2016}

El servicio ahora da soporte a los idiomas siguientes:

-   Cuatro idiomas para su texto de entrada: árabe (`ar`), inglés (`en`), español (`es`) y japonés (`ja`). Para especificar el idioma, utilice la cabecera `Content-Language` HTTP para texto sin formato y entrada HTML o la propiedad `language` del objeto `ContentItem` para entrada JSON.
-   Los mismos cuatro idiomas para su respuesta. Para especificar el idioma de la respuesta, utilice la cabecera `Accept-Language`.

Puede utilizar cualquier combinación de idiomas para la entrada y la respuesta. En ambos casos, si no indica un idioma, el servicio tomará como valor predeterminado el inglés. Para obtener más información, consulte [Especificación de idiomas de solicitud y respuesta](/docs/services/personality-insights/input.html#languages). Consulte también la publicación del blog [El soporte para árabe y japonés está ahora disponible para {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.personalityinsightsshort}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/blogs/watson/2016/04/arabic-japanese-support-now-available-ibm-watson-personality-insights/){: new_window} para obtener información adicional.

> **Nota:** Dado que requiere significativamente más ciclos de cálculo para analizar que otros idiomas, el contenido en árabe toma mucho más tiempo en procesarse. Aunque el servicio da soporte a la misma restricción de 20 MB en la cantidad de texto de entrada para todos los idiomas, el límite práctico para el contenido en árabe puede ser inferior para evitar que se exceda el tiempo de espera. El contenido en japonés también lleva más tiempo en procesarse, pero los retrasos son menos significativos que los del árabe.

### 9 de julio de 2015
{: #July2015}

-   *Soporte de idiomas.* El servicio ahora permite analizar tanto el contenido en inglés como en español. Puede indicar el idioma del texto de entrada con la cabecera `Content-Language` del método `/v2/profile`. Para obtener información sobre la especificación de un idioma, consulte [Especificación de idiomas de solicitud y respuesta](/docs/services/personality-insights/input.html#languages).
-   *Puntuaciones en bruto.* El servicio ahora le permite solicitar puntuaciones en bruto y errores de muestreo en bruto calculados desde el texto de entrada y los modelos del servicio. Los valores no se normalizan ni se comparan con una población de ejemplo. Las puntuaciones en bruto son útiles para clientes que desean aplicar una normalización personalizada para un caso de ejemplo específico o que no necesitan una comparación con una población de ejemplo. Solicite puntuaciones en bruto estableciendo el parámetro de consulta `include_raw` del método `/v2/profile` en `true`. Para obtener más información, consulte [Interpretación de los resultados numéricos](/docs/services/personality-insights/numeric.html).
-   *Mejoras de modelos.* Según sus estudios más recientes, {{site.data.keyword.IBM_notm}} ha mejorado más algunos de sus planteamientos para deducir las características de personalidad. Los cambios son transparentes para los usuarios del servicio y no invalidan ningún resultado anterior obtenido desde el servicio. Para obtener más información sobre los estudios y el enfoque del servicio para deducir, consulte [Cómo se deducen las características de personalidad](/docs/services/personality-insights/science.html#researchInfer).

### 23 de febrero de 2015
{: #February2015}

A partir del 23 de febrero de 2015, el servicio de {{site.data.keyword.personalityinsightsshort}} es la versión generalmente disponible (GA) del servicio de User Modeling anterior, que estaba disponible como un release beta. El release GA requiere que los usuarios migren a una instancia del nuevo servicio. Existen las siguientes diferencias entre las versiones beta y GA del servicio.

-   El servicio de {{site.data.keyword.personalityinsightsshort}} es compatible con el servicio de User Modeling. Las diferencias que se describen en esta sección proporcionan más flexibilidad y resultados mejorados sin afectar a las aplicaciones actuales.
-   Los parámetros con los que crea el servicio en {{site.data.keyword.Bluemix_short}} han cambiado. Utilice ahora un nombre de servicio de `personality_insights` en lugar de `user_modeling` y un plan de servicio de `"IBM Watson Personality Insights Monthly Plan"` en lugar de `user_modeling_free_plan`.
-   El método `/v2/profile` acepta dos nuevos formatos de entrada. La cabecera `Content-Type` ahora acepta el texto sin formato de formatos de entrada (`text/plain`), que es el valor predeterminado, y HTML (`text/html`), además de JSON (`application/json`).
-   El método `/v2/profile` ahora devuelve un nuevo formato de salida. La cabecera `Accept` ahora acepta el CSV de formato de salida (`text/csv`) además de JSON (`application/json`), que es el valor predeterminado.
-   El método `/v2/profile` ahora incluye un nuevo elemento de salida, `sampling_error`, para cada característica para la que informa de un valor de porcentaje. El error de muestreo se devuelve como un valor doble que indica el nivel de confianza del servicio en el percentil del autor basado en el texto de entrada.
-   El modelo Necesidades emplea simbolización y proceso mejorados para normalizar mejor la distribución de valores para sus características. Se recomienda volver a calcular los resultados generados por la API de User Modeling.
-   El método `visualize` ahora está en desuso y se eliminará completamente en un release futuro. Puede utilizar el archivo JavaScript `personality.js` que se proporciona con la aplicación de ejemplo para lograr resultados similares del cliente. El archivo JavaScript `textsummary.js` proporciona formateo adicional para los resultados del servicio.
