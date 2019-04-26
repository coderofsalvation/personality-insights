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

# Notas del release
{: #release-notes}

En las siguientes secciones se documentan las nuevas características y los cambios que se han incluido para cada release del servicio {{site.data.keyword.personalityinsightsshort}}. A menos que se indique lo contrario, todos los cambios son compatibles con releases anteriores y están disponibles de forma automática y transparente para todas las aplicaciones nuevas y existentes.
{: shortdesc}

Las notas de release documentan la *versión de servicio* y la *versión de interfaz* para todas las actualizaciones recientes. La *versión de la interfaz* se especifica con el parámetro de consulta `version` y sirve para utilizar las nuevas características y funciones disponibles con dicha actualización. El servicio devuelve ambas versiones con la cabecera de respuesta `X-Service-Api-Version`.
{: note}

## 21 de diciembre de 2018
{: #December2018}

**Versión de servicio** - `3.4.5`<br/> **Versión de interfaz** - `2017-10-13`

La versión 2 de la API de {{site.data.keyword.personalityinsightsshort}} se ha eliminado del servicio. La versión 3 del servicio se publicó el 19 de octubre de 2016. En ese momento, se recomendó a los usuarios migrar de la versión 2 lo antes posible.

## 18 de noviembre de 2018
{: #November2018b}

**Versión de servicio** - `3.4.5`<br/> **Versión de interfaz** - `2017-10-13`

El servicio {{site.data.keyword.personalityinsightsshort}} está ahora disponible en la {{site.data.keyword.cloud}} ubicación de Londres (**eu-gb**). Al igual que todas las ubicaciones, Londres utiliza la autenticación de Identity and Access Management (IAM) basada en señales. Todas las nuevas instancias de servicios que cree en esta ubicación utilizarán la autenticación de IAM.

## 7 de noviembre de 2018
{: #November2018a}

**Versión de servicio** - `3.4.5`<br/> **Versión de interfaz** - `2017-10-13`

El servicio {{site.data.keyword.personalityinsightsshort}} está ahora disponible en la {{site.data.keyword.cloud_notm}} ubicación de Tokio(**jp-tok**). Al igual que todas las ubicaciones, Tokio utiliza la autenticación de Identity and Access Management (IAM) basada en señales. Todas las nuevas instancias de servicios que cree en esta ubicación utilizarán la autenticación de IAM.

## Releases anteriores
{: #older}

-   [30 de octubre de 2018](#October2018)
-   [11 de junio de 2018](#June2018b)
-   [4 de junio de 2018](#June2018a)
-   [23 de marzo de 2018](#March2018)
-   [13 de octubre de 2017](#October2017)
-   [18 de septiembre de 2017](#September2017)
-   [10 de abril de 2017](#April2017)
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

### 30 de octubre de 2018
{: #October2018}

**Versión de servicio** - `3.4.5`<br/> **Versión de interfaz** - `2017-10-13`

El servicio {{site.data.keyword.personalityinsightsshort}} se ha migrado a la autenticación de Identity and Access Management (IAM) basada en señales para todas las ubicaciones. Todos los servicios de {{site.data.keyword.cloud_notm}} ahora utilizan la autenticación de IAM. El servicio {{site.data.keyword.personalityinsightsshort}} se ha migrado de cada ubicación en las fechas siguientes:

-   Dallas (**us-south**): 30 de octubre de 2018
-   Frankfurt (**eu-de**): 30 de octubre de 2018
-   Washington, DC (**us-east**): 11 de junio de 2018
-   Sídney (**au-syd**): 4 de junio de 2018

La migración a la autenticación de IAM afecta de forma distinta a las instancias de servicio nuevas y existentes:

-   *Todas las instancias de servicio nuevas que se crean en cualquier ubicación* ahora utilizan la autenticación de IAM para acceder al servicio. Puede pasar una señal portadora o una clave de API: las señales admiten solicitudes autenticadas sin incluir credenciales de servicio en cada llamada; las claves de API utilizan la autenticación básica HTTP. Cuando se utiliza cualquier SFK de {{site.data.keyword.watson}}, se puede pasar la clave de API y dejar que SDK gestione el ciclo de vida de las señales.
-   *Las instancias de servicio existentes que ha creado en una ubicación antes de la fecha de migración indicada* siguen utilizando el `{username}` y la `{password}` de sus credenciales de servicio de Cloud Foundry para la autenticación hasta que las actualice para utilizar la autenticación de IAM. Debido a que el servicio {{site.data.keyword.personalityinsightsshort}} es sin estado, puede realizar los pasos siguientes para convertir una instancia de servicio existente a utilizar la autenticación de IAM:

    1.  Suprima y vuelva a crear la instancia de servicio.
    1.  Modifique el código de la aplicación para que utilice la autenticación de IAM.

Para obtener más información, consulte la documentación siguiente:

-   Para saber qué mecanismo de autenticación utiliza la instancia de servicio, consulte las credenciales de servicio pulsando la instancia en el [panel de control de {{site.data.keyword.cloud_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/dashboard/apps){: new_window}.
-   Para obtener más información sobre el uso de las señales IAM con los servicios de Watson, consulte [Autenticación con señales IAM](/docs/services/watson?topic=watson-iam).
-   Para obtener más información sobre el uso de las claves de API de IAM con los servicios de Watson, consulte [Claves de API de servicio de IAM](/docs/services/watson?topic=watson-api-key-bp).
-   Para obtener ejemplos que utilicen la autenticación de IAM, consulte la publicación [Referencia de la API ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/apidocs/personality-insights){: new_window}.

### 11 de junio de 2018
{: #June2018b}

**Versión de servicio** - `3.4.5`<br/> **Versión de interfaz** - `2017-10-13`

Para las instancias de servicio y las aplicaciones alojadas en Washington, DC (**us-east**), el servicio ahora admite un nuevo proceso de autenticación de API. Para obtener más información, consulte la [actualización de servicio del 30 de octubre de 2018](#October2018).

### 4 de junio de 2018
{: #June2018a}

**Versión de servicio** - `3.4.5`<br/> **Versión de interfaz** - `2017-10-13`

Para las instancias de servicio y las aplicaciones alojadas en Sídney (**au-syd**), el servicio ahora da soporte a un nuevo proceso de autenticación de API. Para obtener más información, consulte la [actualización de servicio del 30 de octubre de 2018](#October2018).

### 23 de marzo de 2018
{: #March2018}

**Versión de servicio** - `3.4.4`<br/> **Versión de interfaz** - `2017-10-13`

-   El servicio se ha actualizado con pequeños arreglos de defectos. Los cambios son específicos para los idiomas árabe, japonés y coreano.
-   La cabecera de solicitud `Accept` ahora es obligatoria con el método `POST /v3/profile`. Debe especificar `application/json` o `text/csv`.

### 13 de octubre de 2017
{: #October2017}

**Versión de servicio** - `3.4.0`<br/> **Versión de interfaz** - `2017-10-13`

-   El objeto `Rasgo` de un perfil de personalidad ahora incluye un campo `significant`. Otro objeto `Rasgo` informa de los resultados para cada dimensión de los Cinco grandes, cada faceta de los Cinco grandes, cada Necesidad y cada Valor. El campo `significant` de cada instancia del objeto identifica si los resultados para dicha característica son significativos para el idioma de entrada (`Content-Language`) de la solicitud:

    -   Para inglés, español y japonés, el campo es siempre `true` para todas las características de personalidad.
    -   Para árabe y coreano, el campo es `true` para la mayoría de las características de personalidad, pero es `false` para las características para las que los modelos del servicio no pueden producir resultados significativos. El campo es `false` para un conjunto constante de características. Para obtener una lista completa, consulte [Limitaciones para entrada en árabe y coreano](/docs/services/personality-insights?topic=personality-insights-numeric#limitations). No se base en los resultados para cualquier característica para la que el campo es `false`.

    Para obtener más información sobre el contenido de la respuesta JSON del servicio, consulte [Comprensión de un perfil JSON](/docs/services/personality-insights?topic=personality-insights-output).
-   La salida CSV también incluye ahora columnas cuyas cabeceras se denominan `*_significant`. Cada columna proporciona un valor booleano para indicar si una característica es significativa. Para obtener más información sobre el contenido de respuesta CSV del servicio, consulte [Comprensión de un perfil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV).
-   Para utilizar esta versión más reciente de la interfaz, especifique la versión de interfaz `2017-10-13` con el parámetro `version`.

### 18 de septiembre de 2017
{: #September2017}

**Versión de servicio** - `3.3.0`<br/> **Versión de interfaz** - `2016-10-19`

El servicio ahora da soporte a contenido de entrada en coreano (`ko`). Para obtener más información sobre el MAE (Error absoluto medio promedio) y la correlación promedio para la entrada en coreano, consulte [MAE promedio por idioma y correlación](/docs/services/personality-insights?topic=personality-insights-science#precisePerLanguage).

Los modelos del servicio no pueden producir percentiles significativos ni puntuaciones en bruto para algunas características de personalidad de la entrada en coreano. Para obtener más información sobre los resultados para estas características, consulte [Limitaciones para entrada en árabe y coreano](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).

### 10 de abril de 2017
{: #April2017}

**Versión de servicio** - `3.1.7`<br/> **Versión de interfaz** - `2016-10-19`

-   El servicio ha cambiado la forma de manejar solicitudes con grandes cantidades de contenido de entrada. El servicio acepta un máximo de 20 MB de contenido. Sin embargo, para los modelos basados en *GloVe*, los niveles de precisión se desactivaron a alrededor de las 3000 palabras de entrada. Este comportamiento es distinto del de los modelos anteriores, donde más texto producía una mayor precisión. En general, el servicio ya no necesita tanto contenido para producir un perfil preciso. Pero más contenido requiere más tiempo de proceso, lo que puede provocar que una solicitud finalice el tiempo de espera antes de que se complete.

    Por lo tanto, el servicio ahora extrae y utiliza solo los primeros 250 KB de contenido, sin contar la marcación HTML o JSON, de solicitudes grandes. Esta cifra no se correlaciona con un número exacto de palabras, que varía en función del idioma y de la naturaleza del texto. En inglés, por ejemplo, la longitud de palabra promedio está entre cuatro y cinco caracteres, por lo que esta cifra proporciona alrededor de 50.000 palabras, lo que es al menos 15 veces más palabras de lo que el servicio necesita. El campo `word_count` del JSON de respuesta indica el número de palabras que el servicio utiliza para una solicitud, lo que puede ser inferior al número de palabras de la entrada.

    Puesto que sigue basando un perfil en muchas más palabras de lo estrictamente necesario para la precisión máxima, el servicio genera un perfil que es tan preciso como anteriormente. Sin embargo, el servicio responde mucho más rápido que antes. Para las solicitudes para las que solo utiliza una parte del contenido de entrada, el servicio devuelve el siguiente mensaje de aviso `CONTENT_TRUNCATED` para que el usuario conozca el hecho:

    `Para la máxima precisión al optimizar también el tiempo de proceso, solo se han analizado los primeros 250 KB de texto de entrada (excluida la marcación). Los niveles de precisión se desactivaron a las aproximadamente 3.000 palabras para que no afectara a la precisión del perfil.`

    Para obtener más información, consulte [Proporcionar suficiente entrada](/docs/services/personality-insights?topic=personality-insights-input#sufficient).
-   El servicio se ha actualizado con pequeños arreglos de seguridad.

### 1 de marzo de 2017
{: #March2017}

**Versión de servicio** - `3.1.6`<br/> **Versión de interfaz** - `2016-10-19`

El servicio se ha actualizado con pequeñas mejoras en el registro.

### 20 de febrero de 2017
{: #February2017b}

**Versión de servicio** - `3.1.5.1`<br/> **Versión de interfaz** - `2016-10-19`

El servicio se ha actualizado con pequeños arreglos de seguridad y de defectos, y para mejorar la medición de llamadas de API.

### 13 de febrero de 2017
{: #February2017}

**Versión de servicio** - `3.1.4`<br/> **Versión de interfaz** - `2016-10-19`

-   La lista de preferencias de consumo se ha mejorado. Ahora la lista incluye solo las preferencias más importantes para entender los hábitos de estilo de vida dominantes de una persona y las características del consumidor. La lista de preferencias de consumo se ha reducido de 51 a 42. el resto de las preferencias expresan de forma más precisa la probabilidad de que el autor prefiera diversos productos, servicios y actividades, facilitando aún más actuar sobre los resultados.

    El servicio ya no devuelve las siguientes nueve preferencias de consumo:

    -   La categoría <code>consumption_preferences_shopping</code> ya no incluye
        -   <code>consumption_preferences_automobile_resale_value</code>
    -   La categoría <code>consumption_preferences_reading</code> ya no incluye
        -   <code>consumption_preferences_read_motive_enjoyment</code><br/>
        -   <code>consumption_preferences_read_motive_information</code><br/>
        -   <code>consumption_preferences_read_motive_mandatory</code><br/>
        -   <code>consumption_preferences_read_motive_relaxation</code>
    -   La categoría <code>consumption_preferences_health_and_activity</code> ya no incluye
        -   <code>consumption_preferences_adventurous_sports</code>
        -   <code>consumption_preferences_fast_food_frequency</code>
    -   La categoría <code>consumption_preferences_volunteering</code> ya no incluye
        -   <code>consumption_preferences_volunteering_time</code>
        -   <code>consumption_preferences_volunteer_learning</code>

    Para obtener más información sobre las preferencias restantes, consulte [Preferencias de consumo](/docs/services/personality-insights?topic=personality-insights-preferences).
-   *Para la entrada en árabe*, la información sobre el Error absoluto medio promedio (MAE, Average Mean Absolute Error) y la correlación promedio está disponible ahora en [MAE promedio por idioma y correlación](/docs/services/personality-insights?topic=personality-insights-science#precisePerLanguage). Además, los modelos del servicio no pueden producir percentiles significativos ni puntuaciones en bruto para una recopilación de características de personalidad. Para obtener más información sobre los resultados para estas características, consulte [Limitaciones para entrada en árabe y coreano](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).

### 13 de enero de 2017
{: #January2017}

**Versión de servicio** - `3.1.2.1`<br/> **Versión de interfaz** - `2016-10-19`

El servicio de Personality Insights se ha actualizado con algunos pequeños arreglos de defectos.

### 15 de diciembre de 2016
{: #December2016}

**Versión de servicio** - `3.1.1`<br/> **Versión de interfaz** - `2016-10-19`

Para el texto de entrada en árabe, el servicio {{site.data.keyword.personalityinsightsshort}} utiliza ahora *GloVe* para desarrollar un perfil de personalidad. El servicio ya no utiliza el diccionario de psicolingüística LIWC (Linguistic Inquiry and Word Count) para cualquier idioma. Para obtener más información sobre cómo desarrolla el servicio un retrato de personalidad, consulte [Cómo se deducen las características de personalidad](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).

### 15 de noviembre de 2016
{: #November2016}

**Versión de servicio** - `3.1.0`<br/> **Versión de interfaz** - `2016-10-19`

-   Para el texto de entrada en japonés, el servicio {{site.data.keyword.personalityinsightsshort}} utiliza ahora *GloVe* para desarrollar un perfil de personalidad. El servicio ya no utiliza el diccionario de psicolingüística LIWC (Linguistic Inquiry and Word Count) para entrada en japonés. Para obtener más información, consulte [Cómo se deducen las características de personalidad](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).
-   Los campos `name` de los objetos `ConsumptionPreferencesCategory` y `ConsumptionPreferences` se devuelven ahora con series localizadas en el idioma que se especifica en la cabecera de solicitud `Accept-Language`.
-   La actualización incluye unos pequeños arreglos de defectos.

### 20 de octubre de 2016
{: #October2016b}

**Versión de servicio** - `3.0.0`<br/> **Versión de interfaz** - `2016-10-19`

El servicio {{site.data.keyword.personalityinsightsshort}} y sus API se han actualizado significativamente. La API se incrementa de la versión 2 a la versión 3 y ofrece nuevas características. Las secciones restantes de esta nota de release describen los cambios en detalle.

La versión 3 no es compatible con la versión 2. Se recomienda migrar a la versión 3 para aprovechar las nuevas características y cambios. La migración a la versión 3 consta solo de actualizar y redesplegar las aplicaciones para utilizar los cambios que se describen en estas notas de release para la nueva versión. No es necesario que cree una nueva instancia del servicio en {{site.data.keyword.cloud_notm}}; sólo es necesario llamar a la API de la `v3`.

La versión 2 de la API de {{site.data.keyword.personalityinsightsshort}} se va a eliminar del servicio pronto. Se recomienda encarecidamente migrar a la versión 3 lo antes posible.
{: note}

#### Más información sobre la versión 3

Esta documentación ahora describe la versión 3 de la API de {{site.data.keyword.personalityinsightsshort}}. Las secciones siguientes resumen los cambios para la nueva versión de la interfaz:

-   Para obtener más información sobre la llamada al método `/v3/profile`, consulte [Solicitud de un perfil](/docs/services/personality-insights?topic=personality-insights-input).
-   Para obtener más información sobre la respuesta del método `/v3/profile`, consulte [Comprensión de un perfil JSON](/docs/services/personality-insights?topic=personality-insights-output) y [Comprensión de un perfil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV).
-   Para obtener más información sobre la interfaz de la versión 3, consulte la [Referencia de API ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/apidocs/personality-insights){: new_window}.

#### Cambios en los parámetros del método <code>/v3/profile</code>

Parámetros del método `/v3/profile` modificados:

-   La API ofrece ahora un parámetro de consulta opcional denominado `consumption_preferences`. El parámetro acepta un valor booleano que indica si la información que se deduzca sobre las preferencias de consumo se debe devolver con los resultados. De forma predeterminada, la información no está incluida en la respuesta. Para obtener más información, consulte [Nueva característica de preferencias de consumo](#cp).
-   La API incluye ahora el parámetro de consulta obligatorio `version`. El parámetro acepta una serie que identifica la versión solicitada de la API y el formato de respuesta como una fecha en el formato `AAAA-MM-DD`; por ejemplo, especifique `2016-10-19` para el 19 de octubre de 2016. Este parámetro permite al servicio actualizar su API o formato de respuesta para versiones nuevas sin romper los clientes existentes. La serie inicial para la versión 3 de la API es `2016-10-19`.

    La fecha que especifique no tiene que coincidir exactamente con una versión del servicio. El servicio utiliza la versión que no sea posterior a la fecha que proporcione. Si especifica una fecha anterior a la fecha de release de la versión 3, el servicio utilizará la versión 3 de la API. Si especifica una fecha que está en el futuro o que es posterior a la versión más reciente, el servicio utilizará la última versión.
-   El nombre del parámetro de consulta `include_raw` es ahora `raw_scores`.
-   El nombre del parámetro de consulta `headers` es ahora `csv_headers`.

#### Nueva característica de preferencias de consumo
{: #cp}

La característica de preferencias de consumo proporciona una indicación de la tendencia del autor por exhibir distintas tendencias del consumidor. Cuando pase el parámetro de consulta `consumption_preferences` con un valor de `true` al método `/v3/profile`, el servicio devolverá resultados extra con el objeto `Profile`:

-   Un campo `consumption_preferences` que proporciona una matriz de objetos `ConsumptionPreferencesCategory`.
-   Cada objeto `ConsumptionPreferencesCategory` incluye los campos siguientes:
    -   `consumption_preference_category_id`: El ID de una de las categorías de preferencias de consumo.
    -   `name`: El nombre visible de usuario de la categoría.
    -   `consumption_preferences`: Una matriz de objetos `ConsumptionPreferences` que proporciona resultados que se deducen del texto de entrada para las preferencias individuales de la categoría.
-   Cada objeto `ConsumptionPreferences` incluye los campos siguientes:
    -   `consumption_preference_id`: El ID de una de las preferencias de consumo.
    -   `name`: El nombre visible de usuario de la preferencia de consumo.
    -   `score`: La puntuación de la preferencia de consumo:

        -   `0.0` indica poco probable
        -   `0,5` indica neutralidad
        -   `1.0` indica probable

        Las puntuaciones para algunas preferencias son binarias y no permiten un valor neutral. La puntuación es una indicación de preferencia basada en los resultados que se deducen del texto de entrada, no un percentil normalizado.

Para obtener más información sobre las preferencias de consumo, consulte [Preferencias de consumo](/docs/services/personality-insights?topic=personality-insights-preferences).

El campo `name` para ambos objetos de preferencias de consumo siempre se devuelve en inglés, independientemente del idioma especificado con la cabecera de solicitud `Accept-Language`.
{: note}

#### Cambios en objetos y campos JSON

Los objetos de entrada y salida JSON y sus campos se han simplificado y clarificado:

-   Los campos siguientes se han eliminado de los objetos `ContentItem` JSON que puede pasar al método `/v3/profile` con una solicitud:
    -   `userid`
    -   `sourceid`
    -   `charset` (anteriormente en desuso)

    Pase estos objetos del cuerpo de una solicitud JSON como elementos de la matriz `contentItems` del objeto `Content`.
-   Los siguientes campos del objeto `Profile` JSON devueltos por el método `/v3/profile` se han modificado:
    -   Los campos siguientes se han eliminado:
        -   `id`
        -   `source`
    -   El campo `tree` se ha eliminado. Se ha sustituido por cuatro nuevos campos:
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

    El servicio ahora informa de un Error absoluto medio promedio (MAE, Average Mean Absolute Error) que califica la precisión de sus resultados. Para obtener más información sobre el MAE para cantidades distintas de texto de entrada, consulte [Proporcionar suficiente entrada](/docs/services/personality-insights?topic=personality-insights-input#sufficient).
-   Los objetos `Trait` JSON se siguen devolviendo para los campos `personality`, `needs`, y `values` del objeto `Profile`. Pero el campo `behavior` devuelve una matriz de objetos JSON denominada `Behavior` que tiene los campos siguientes:
    -   `trait_id`
    -   `name`
    -   `categoría`
    -   `percentage`

    Además, la información de comportamiento ya no se devuelve como un árbol de valores. La salida consta de una matriz única que enumera todas las características temporales (día de la semana y hora del día).
-   El nombre del campo `id` del objeto `Warnings` JSON que se puede devolver mediante el método `/v3/profile` es ahora `warnings_id`.

#### Cambios en los ID JSON
{: #ids}

Los ID JSON que devuelve el servicio para el campo `trait_id` (anteriormente `id`) del objeto `Trait` y el nuevo `Behavior` han cambiado:

-   Los ID para las dimensiones de los cinco grandes empiezan ahora con la serie `big5_`.
-   Los ID para las facetas de los Cinco grandes empiezan ahora con la serie `facet_`.
-   Los ID para necesidades empiezan ahora con la serie `need_`.
-   Los ID para valores empiezan ahora con la serie `value_`.
-   Los ID para todas las características temporales empiezan ahora con la serie `behavior_`.
-   Los ID para las características temporales relacionadas con la hora del día utilizan ahora el formato de hora de 24 horas de cuatro dígitos (por ejemplo, `behavior_0000`) en lugar del formato de hora de 12 horas (por ejemplo, `0:00 am`).
-   Todos los caracteres están ahora en minúscula.
-   Los espacios y los guiones están ahora subrayados.

#### Cambios en las cabeceras CSV
{: #headers}

Las cabeceras de columna opcionales que el servicio puede devolver para la salida CSV han cambiado:

-   Todos los cambios que se describen para el `trait_id` de la salida JSON también se aplican a las cabeceras CSV.
-   Las cabeceras para puntuaciones en bruto para las dimensiones de los Cinco grandes empiezan ahora con la serie `big5_`.
-   Las cabeceras para puntuaciones en bruto para las facetas de los Cinco grandes empiezan ahora con la serie `facet_`.
-   Las cabeceras para puntuaciones en bruto para necesidades empiezan ahora con la serie `need_`.
-   Las cabeceras para puntuaciones en bruto para valores empiezan ahora con la serie `value_`.
-   La cabecera para la columna de idioma procesado es ahora `processed_language` en lugar de `processed_lang`.
-   Las columnas `user` y `source_id` ya no son devueltas.
-   Todos los caracteres están ahora en minúscula.
-   Los espacios y los guiones están ahora subrayados.

#### Eliminación del método <code>visualize</code>

La versión 2 de la API del servicio incluía un método `visualize` en desuso utilizado en un release anterior para visualizar los resultados de una llamada en el método `/v3/profile`. El método `visualize` se ha eliminado de la API de servicio. El servicio sigue proporcionando una colección de archivos JavaScript que permiten la visualización gráfica de un perfil. Para obtener más información, consulte
[Visualización de un perfil](/docs/services/personality-insights?topic=personality-insights-overviewDevelopers#visualize).

### 12 de octubre de 2016
{: #October2016a}

Para el texto de entrada en español, el servicio {{site.data.keyword.personalityinsightsshort}} utiliza ahora *GloVe*
para desarrollar un perfil de personalidad. El servicio ya no utiliza el diccionario de psicolingüística LIWC (Linguistic Inquiry and Word Count) para entrada en español. El servicio empezó a utilizar el modelo nuevo para el texto de entrada en inglés el 31 de agosto. Está previsto aplicar el nuevo modelo al resto de los idiomas de entrada en el futuro próximo. Para obtener más información sobre el nuevo modelo, consulte [Cómo se deducen las características de personalidad](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).

### 31 de agosto de 2016
{: #August2016}

El servicio utiliza ahora *GloVe*
para desarrollar un perfil de personalidad. *GloVe* es una técnica de inclusión de palabras de código abierto. Para obtener más información, consulte [Cómo se deducen las características de personalidad](/docs/services/personality-insights?topic=personality-insights-science#researchInfer). El servicio utiliza el nuevo método solo para el texto en inglés. Para otros idiomas, el servicio seguirá utilizando el diccionario de psicolingüística LIWC (Linguistic Inquiry and Word Count). El servicio tiene previsto utilizar el método de vocabulario abierto para todos los idiomas en el futuro.

Para el modelo nuevo utilizado para la entrada en inglés, el servicio informará del Error absoluto medio promedio (MAE, Average Mean Absolute Error) de los resultados para su modelo formado. Para obtener más información sobre cómo cambia el MAE con distintas cantidades de texto de entrada, consulte [Proporcionar suficiente entrada](/docs/services/personality-insights?topic=personality-insights-input#sufficient).

{{site.data.keyword.IBM_notm}} tiene previsto informar sobre el MAE para los modelos no ingleses en el futuro. {{site.data.keyword.IBM_notm}} tiene previsto utilizar el MAE en lugar de los errores de muestreo para determinar cómo cambia la precisión del servicio en función de la cantidad de texto de entrada que proporcione.

### 14 de julio de 2016
{: #July2016b}

-   Para entrada en árabe, el servicio puede ahora reducir la cantidad de texto de entrada por motivos de rendimiento. En un umbral determinado, la precisión de los resultados para árabe no mejora con más palabras. Si el servicio recorta el texto de entrada en árabe, devolverá un aviso `PARTIAL_TEXT_USED` con el mensaje siguiente:

    `El texto proporcionado para calcular el perfil se ha reducido por motivos de rendimiento. Esta acción no afecta la precisión de la salida, ya que no se necesitaba todo el texto de entrada.`
-   La actualización incluye arreglos de defectos y mejoras internas.

### 1 de julio de 2016
{: #July2016a}

-   Los planes de precios del servicio ahora ofrecen precios más bajos para los usuarios de {{site.data.keyword.personalityinsightsshort}}. Para obtener más información, consulte el servicio {{site.data.keyword.personalityinsightsshort}} en el [Catálogo de {{site.data.keyword.cloud_notm}}
![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/catalog/services/personality-insights/){: new_window}.
-   La lista de idiomas de respuesta soportados que puede especificar con la cabecera `Accept-Language` ahora incluye:
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

    Para obtener más información, consulte [Especificación de idiomas de solicitud y respuesta](/docs/services/personality-insights?topic=personality-insights-input#languages-input).
-   El método `/v2/profile` ahora puede devolver los siguientes códigos de estado HTTP:
    -   429 *Demasiadas solicitudes*: El servicio está procesando demasiadas solicitudes para el idioma del contenido. Espere un poco y vuelva a intentar la solicitud. Si está enviando muchas solicitudes para el idioma, considere la posibilidad de regular la velocidad a la que envía las solicitudes.
    -   504 *Tiempo de espera excedido de pasarela*: La solicitud ha superado el tiempo de espera o ha tardado demasiado en procesarse. Espere un poco y vuelva a intentar la solicitud. Si la entrada contenía demasiadas palabras (por ejemplo, más de 20.000), considere la posibilidad de reducir el número de palabras, manteniendo el significado de la entrada.

    El método ya no devuelve 503 *Servicio no disponible*. Para obtener más información sobre posibles códigos de respuesta, consulte la [Referencia de API ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/apidocs/personality-insights){: new_window}.
-   La actualización incluye arreglos de defectos y mejoras internas.

### 7 de junio de 2016
{: #June2016b}

-   El servicio ahora da soporte a CORS (Cross-Origin Resource Sharing) para permitir que los clientes basados en navegador llamen al servicio directamente. Para obtener más información, consulte [Soporte de CORS](/docs/services/personality-insights?topic=personality-insights-overviewDevelopers#CORS).
-   El rendimiento del servicio para texto en japonés ha mejorado considerablemente.
-   La actualización incluye arreglos de defectos y mejoras internas.

### 1 de junio de 2016
{: #June2016a}

El servicio se ha actualizado para arreglos de defectos y mejoras internas. También se ha añadido un campo de nivel superior nuevo, `warnings`, a los resultados JSON que devuelve el servicio. Para obtener más información, consulte la [Referencia de API ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/apidocs/personality-insights){: new_window}.

### 17 de mayo de 2016
{: #May2016}

El servicio se ha actualizado para arreglos de defectos y mejoras internas.

### 18 de marzo de 2016
{: #March2016}

El servicio ahora da soporte a los idiomas siguientes:

-   El servicio admite cuatro idiomas para el texto de entrada: árabe (`ar`), inglés (`en`), español (`es`) y japonés (`ja`). Para especificar el idioma, utilice la cabecera `Content-Language` HTTP para texto sin formato y entrada HTML o la propiedad `language` del objeto `ContentItem` para entrada JSON.
-   El servicio admite los mismos cuatro idiomas para las respuestas. Para especificar el idioma de la respuesta, utilice la cabecera `Accept-Language`.

Puede utilizar cualquier combinación de idiomas para la entrada y la respuesta. Si no indica un idioma, el servicio tomará como valor predeterminado el inglés. Para obtener más información, consulte [Especificación de idiomas de solicitud y respuesta](/docs/services/personality-insights?topic=personality-insights-input#languages-input). También puede consultar la publicación del blog [El soporte para árabe y japonés está ahora disponible para {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.personalityinsightsshort}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/blogs/watson/2016/04/arabic-japanese-support-now-available-ibm-watson-personality-insights/){: new_window}.

Dado que requiere significativamente más ciclos de cálculo para analizar que otros idiomas, el contenido en árabe toma mucho más tiempo en procesarse. Aunque el servicio da soporte a la misma restricción de 20 MB en la cantidad de texto de entrada para todos los idiomas, el límite práctico para el contenido en árabe puede ser inferior para evitar que se exceda el tiempo de espera. El contenido en japonés también lleva más tiempo en procesarse, pero los retrasos son menos significativos que los del árabe.
{: note}

### 9 de julio de 2015
{: #July2015}

-   *Soporte de idiomas.* Puede analizar contenido tanto en inglés como en español. Puede indicar el idioma del texto de entrada con la cabecera `Content-Language` del método `/v2/profile`. Para obtener más información sobre la especificación de un idioma, consulte [Especificación de idiomas de solicitud y respuesta](/docs/services/personality-insights?topic=personality-insights-input#languages-input).
-   *Puntuaciones en bruto.* Puede solicitar puntuaciones en bruto y errores de muestreo en bruto que se calculan a partir del texto de entrada y los modelos de servicio. Los valores no se normalizan ni se comparan con una población de ejemplo. Las puntuaciones en bruto son útiles para clientes que desean aplicar una normalización personalizada para un caso de ejemplo específico o que no necesitan una comparación con una población de ejemplo. Solicite puntuaciones en bruto estableciendo el parámetro de consulta `include_raw` del método `/v2/profile` en `true`. Para obtener más información, consulte [Interpretación de los resultados numéricos](/docs/services/personality-insights?topic=personality-insights-numeric).
-   *Mejoras de modelos.* Según sus estudios más recientes, {{site.data.keyword.IBM_notm}} ha mejorado más algunos de sus planteamientos para deducir las características de personalidad. Los cambios son transparentes para los usuarios del servicio; no invalidan ningún resultado anterior obtenido del servicio. Para obtener más información sobre los estudios y el enfoque del servicio para deducir, consulte [Cómo se deducen las características de personalidad](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).

### 23 de febrero de 2015
{: #February2015}

A partir del 23 de febrero de 2015, el servicio {{site.data.keyword.personalityinsightsshort}} es la versión generalmente disponible (GA) del servicio de User Modeling anterior, que estaba disponible como un release beta. El release GA requiere que los usuarios migren a una instancia del nuevo servicio. Existen las siguientes diferencias entre las versiones beta y GA del servicio.

-   El servicio {{site.data.keyword.personalityinsightsshort}} es compatible con el servicio de User Modeling. Las diferencias que se describen proporcionan más flexibilidad y resultados mejorados sin afectar a las aplicaciones actuales.
-   Los parámetros con los que crea el servicio en {{site.data.keyword.cloud_notm}} han cambiado. Ahora se utiliza el nombre de servicio `personality_insights` en lugar de `user_modeling` y el plan de servicio `"IBM Watson Personality Insights Monthly Plan"` en lugar de `user_modeling_free_plan`.
-   El método `/v2/profile` acepta dos nuevos formatos de entrada. La cabecera `Content-Type` ahora acepta el texto sin formato de formatos de entrada (`text/plain`), que es el valor predeterminado, y HTML (`text/html`), además de JSON (`application/json`).
-   El método `/v2/profile` ahora devuelve un nuevo formato de salida. La cabecera `Accept` ahora acepta el CSV de formato de salida (`text/csv`) además de JSON (`application/json`), que es el valor predeterminado.
-   El método `/v2/profile` ahora incluye un nuevo elemento de salida, `sampling_error`, para cada característica para la que informa de un valor de porcentaje. El error de muestreo se devuelve como un valor doble que indica el nivel de confianza del servicio en el percentil del autor basado en el texto de entrada.
-   El modelo Necesidades emplea simbolización y proceso mejorados para normalizar mejor la distribución de valores para sus características. Se recomienda volver a calcular los resultados generados por la API de User Modeling.
-   El método `visualize` ahora está en desuso y se eliminará completamente en un release futuro. Puede utilizar el archivo JavaScript `personality.js` que se proporciona con la aplicación de ejemplo para lograr resultados similares del cliente. El archivo JavaScript `textsummary.js` proporciona formateo extra para los resultados del servicio.
