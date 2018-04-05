---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-18"

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
{:download: .download}

# Guía de aprendizaje de iniciación
{: #gettingStarted}

El servicio de {{site.data.keyword.personalityinsightsfull}} obtiene información sobre las características de personalidad de las redes sociales, los datos empresariales, u otras comunicaciones digitales. Esta guía de aprendizaje puede ayudarle a comenzar rápidamente con el servicio de {{site.data.keyword.personalityinsightsshort}}. Los ejemplos muestran cómo llamar al método `POST /v3/profile` del servicio con distintos tipos de entrada y cómo solicitar distintos tipos de salida y de formatos de salida.
{: shortdesc}

## Antes de empezar
{: #before-you-begin}

- Cree una instancia del servicio:
    - {: download} Si está viendo esto, ha creado la instancia de servicio. Ahora obtiene sus credenciales.
    - Crear un proyecto desde un servicio:
        1.  Vaya a la página {{site.data.keyword.watson}} Developer Console [Services ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://console.{DomainName}/developer/watson/services){: new_window}.
        1.  Seleccione {{site.data.keyword.personalityinsightsshort}}, pulse **Añadir servicios**, y regístrese para una cuenta gratuita de {{site.data.keyword.Bluemix_notm}} o inicie sesión.
        1.  Escriba `personality-tutorial` como nombre de proyecto y pulse **Crear proyecto**.
- Copie las credenciales para autenticarse con la instancia de servicio:
    - {: download} Desde el panel de control de servicio (lo que está viendo):
        1.  Pulse el separador **Credenciales de servicio**.
        1.  Pulse **Ver credenciales** bajo **Acciones**.
        1.  Copie los valores `username`, `password` y `url`.
        {: download}
    - Desde el proyecto **personality-tutorial** de la Developer Console, copie los valores `username`, `password` y `url` para `"personality_insights"` desde la sección **Credenciales**.
- Asegúrese de que dispone de cURL:
    - Los ejemplos utilizan cURL para llamar a métodos de la interfaz HTTP. Instale la versión para el sistema operativo desde [curl.haxx.se ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://curl.haxx.se/){: new_window}. Instale la versión que da soporte al protocolo Secure Sockets Layer (SSL). Asegúrese de incluir el archivo binario instalado en la variable de entorno `PATH`.

<!-- Remove this text after dedicated instances have the Developer Console: begin -->

Si utiliza {{site.data.keyword.Bluemix_dedicated_notm}}, cree una instancia de servicio desde la página [{{site.data.keyword.personalityinsightsshort}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://console.{DomainName}/catalog/services/personality-insights/){: new_window} del Catálogo. Para obtener detalles sobre cómo encontrar las credenciales de servicio, consulte [Credenciales de servicio para servicios de Watson ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](/docs/services/watson/getting-started-credentials.html#getting-credentials-manually){: new_window}.

<!-- Remove this text after dedicated instances have the Developer Console: end -->

## Paso 1: Enviar entrada de texto sin formato y recibir salida JSON básica
{: #example1}

El primer ejemplo pasa el archivo de texto sin formato `profile.txt` al método `POST /v3/profile` e implícitamente solicita la respuesta JSON predeterminada.

1.  Descargue el archivo de ejemplo <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="Icono de enlace externo" title="Icono de enlace externo" class="style-scope doc-content"></a>.
1.  Emita el mandato siguiente para enviar el archivo al método `/v3/profile` y solicitar la respuesta JSON predeterminada. El parámetro `charset` incluido con la cabecera `Content-Type` especifica la codificación de caracteres del texto de entrada.
    -   Sustituya `{username}` y `{password}` por las credenciales de servicio del paso anterior.
    -   Modifique `{path_to_file}` para especificar la ubicación del archivo `profile.txt`.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --data-binary "@{path_to_file}profile.txt" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
    ```
    {: pre}

El servicio devuelve un objeto `Perfil` de JSON que incluye metadatos básicos como el número de palabras de la entrada, el modelo de lenguaje con el que se ha procesado la entrada, y cualquier advertencia asociada con la entrada. Para obtener más información, consulte [El objeto Perfil](/docs/services/personality-insights/output.html#outputJSON).

El perfil incluye información sobre las cinco grandes características de personalidad, necesidades y valores para el autor, como se infirieron del texto de entrada. El servicio informa de un `percentil`, o de una puntuación normalizada, para cada característica. El servicio calcula el percentil comparando los resultados del autor con los resultados de una población de ejemplo. Para obtener más información, consulte [Resultado de las características de personalidad](/docs/services/personality-insights/output.html#traitJSON).

## Paso 2: Enviar entrada JSON y recibir salida JSON detallada
{: #example2}

El segundo ejemplo pasa el archivo JSON `profile.json` al método `/v3/profile`, aceptando de nuevo la respuesta JSON predeterminada. El ejemplo solicita preferencias de consumo y puntuaciones en bruto para un análisis más detallado de la entrada.

1.  Descargue el archivo de ejemplo <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Icono de enlace externo" title="Icono de enlace externo" class="style-scope doc-content"></a>, que contiene una recopilación de mensajes de Twitter.
1.  Emita el siguiente mandato para enviar el archivo al método `/v3/profile`. El ejemplo especifica `application/json` para la cabecera `Content-Type`; el parámetro `charset` no es necesario para la entrada JSON. El ejemplo establece los parámetros de consulta `consumption_preferences` y `raw_scores` en `true`.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --data-binary "@{path_to_file}profile.json" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"
    ```
    {: pre}

El servicio devuelve un perfil JSON que incluye los metadatos y las características devueltas con el ejemplo anterior. Para cada característica, el servicio también incluye una `raw_score`, que representa la puntuación del autor para la característica basada exclusivamente en el texto de entrada, sin comparar los resultados con una población de ejemplo.

Dado que el contenido de entrada incluye las indicaciones de fecha y hora, el servicio también informa de características de comportamiento. Estas son características temporales que indican el `porcentaje` de los elementos de contenido creados en cada día de la semana y hora del día. Para obtener más información, consulte [Salida de comportamiento](/docs/services/personality-insights/output.html#behaviorJSON).

El servicio también informa de puntuaciones para su recopilación de preferencias de consumo. Las puntuaciones indican la probabilidad del autor para preferir distintos productos, servicios y actividades en función de las características deducidas. Para obtener más información, consulte [Salida de preferencias de consumo](/docs/services/personality-insights/output.html#preferenceJSON).

## Paso 3: Enviar entrada JSON y recibir salida CSV detallada
{: #example3}

El tercer ejemplo es similar al segundo: pasa el mismo contenido JSON y solicita los mismos resultados. Pero este ejemplo especifica `text/csv` para la cabecera `Accept` para solicitar la respuesta en formato CSV (comma-separated values). Utiliza la opción `--output` del mandato cURL para dirigir los resultados a un archivo llamado `profile.csv`. El ejemplo establece el parámetro de consulta `csv_headers` en `true` para solicitar que las cabeceras de columna se devuelvan con la salida.

1.  Emita el mandato siguiente para enviar el archivo JSON al método `/v3/profile`.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary "@{path_to_file}profile.json" \
    --output profile.csv \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"
    ```
    {: pre}

Para obtener una descripción detallada de la respuesta y las cabeceras CSV, consulte [Comprensión de un perfil CSV](/docs/services/personality-insights/output-csv.html).

## Pasos siguientes

-   Más información sobre [Solicitud de un perfil](/docs/services/personality-insights/input.html) y sobre [Comprensión de un perfil JSON](/docs/services/personality-insights/output.html) y [Comprensión de un perfil CSV](/docs/services/personality-insights/output-csv.html).
-   Más información sobre los [modelos de personalidad](/docs/services/personality-insights/models.html) de los cinco grandes, necesidades y valores.
-   Más información sobre la API en la [referencia de la API ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}
-   Interactúe con la API en el [Explorador de API![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v3){: new_window}.
-   Explore la [aplicación de ejemplo Node.js ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} para obtener más información sobre el desarrollo de aplicaciones con el servicio.
