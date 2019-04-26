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
{:go: .ph data-hd-programlang='go'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}
{:download: .download}
{:apikey: data-credential-placeholder='apikey'}
{:url: data-credential-placeholder='url'}
{:hide-dashboard: .hide-dashboard}

# Guía de aprendizaje de iniciación
{: #gettingStarted}

El servicio {{site.data.keyword.personalityinsightsfull}} obtiene información sobre las características de personalidad de las redes sociales, los datos empresariales, u otras comunicaciones digitales. Esta guía de aprendizaje puede ayudarle a comenzar rápidamente con el servicio {{site.data.keyword.personalityinsightsshort}}. Los ejemplos muestran cómo llamar al método `POST /v3/profile` del servicio con distintos tipos de entrada y cómo solicitar distintos tipos de salida y de formatos de salida.
{: shortdesc}

La guía de aprendizaje utiliza las teclas de API de {{site.data.keyword.cloud}} Identity and Access Management (IAM) para la autenticación. Las instancias de servicio más antiguas pueden seguir utilizando `{username}` y `{password}` de sus credenciales de servicio de Cloud Foundry existentes para la autenticación. Realice la autenticación utilizando el método correcto para su instancia de servicio. Para obtener más información sobre la autenticación de IAM, consulte [actualización de servicio del 30 de octubre de 2018](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018) en las notas del release.
{: important}

## Antes de empezar
{: #before-you-begin}

-   {: hide-dashboard} Cree una instancia del servicio:
    1.  {: hide-dashboard} Vaya a la página [{{site.data.keyword.personalityinsightsshort}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/catalog/services/personality-insights){: new_window} en el catálogo de {{site.data.keyword.cloud_notm}}.
    1.  {: hide-dashboard} Regístrese para obtener una cuenta de {{site.data.keyword.cloud_notm}} gratuita o inicie sesión.
    1.  {: hide-dashboard} Pulse **Crear**.
-   Copie las credenciales para autenticarse en la instancia de servicio:
    1.  {: hide-dashboard} En el panel de control de [{{site.data.keyword.cloud_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/dashboard/apps){: new_window}, pulse en la instancia de servicio de {{site.data.keyword.personalityinsightsshort}} para ir a la página de panel de control del servicio {{site.data.keyword.personalityinsightsshort}}.
    1.  En la página **Gestionar**, pulse **Mostrar** para visualizar las credenciales.
    1.  Copie los valores de `Clave de API` y `URL`.
-   Asegúrese de tener el mandato `curl`.
    -   Los ejemplos utilizan el mandato `curl` para llamar a métodos de la interfaz HTTP. Instale la versión correspondiente a su sistema operativo desde [curl.haxx.se ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://curl.haxx.se/){: new_window}. Instale la versión que da soporte al protocolo SSL (Secure Sockets Layer). Asegúrese de incluir el archivo binario instalado en la variable de entorno `PATH`.

Cuando especifique un mandato, sustituya `{apikey}` y `{url}` por la clave de API y el URL reales. Omita las llaves, que indican un valor variable, en el mandato. Un valor real se asemeja al ejemplo siguiente:
{: hide-dashboard}

```bash
curl -X POST -u "apikey:L_HALhLVIksh1b73l97LSs6R_3gLo4xkujAaxm7i-b9x"
. . .
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{:pre}
{: hide-dashboard}

## Paso 1: Enviar entrada de texto sin formato y recibir salida JSON básica
{: #example1}

El primer ejemplo pasa el archivo de texto sin formato `profile.txt` al método `POST /v3/profile` y solicita una respuesta JSON.

1.  Descargue el archivo de ejemplo <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="Icono de enlace externo" title="Icono de enlace externo"></a>.
1.  Emita el mandato siguiente para enviar el archivo al método `/v3/profile` y solicite una respuesta JSON.
    -   La cabecera `Content-Type` especifica que la entrada es texto sin formato, `text/plain`. El parámetro `charset` incluido en la cabecera identifica la codificación de caracteres del texto de entrada.
    -   La cabecera `Accept` especifica `application/json` para indicar que se solicita una salida JSON.
    -   {: hide-dashboard} Sustituya `{apikey}` y `{url}` por su información.
    -   Modifique `{path_to_file}` para especificar la ubicación del archivo `profile.txt`.

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.txt \
    "{url}/v3/profile?version=2017-10-13"{: url}
    ```
    {: pre}

El servicio devuelve un objeto `Perfil` de JSON que incluye metadatos básicos como el número de palabras de la entrada, el modelo de lenguaje con el que se ha procesado la entrada, y cualquier advertencia asociada con la entrada. Para obtener más información, consulte [El objeto Perfil](/docs/services/personality-insights?topic=personality-insights-output#outputJSON).

El perfil incluye información sobre las características de los Cinco grandes de personalidad, de las Necesidades y de los Valores para el autor, como se han deducido del texto de entrada. El servicio reporta un `percentil`, o una puntuación normalizada, para cada característica. El servicio calcula el percentil comparando los resultados del autor con los resultados de una población de ejemplo. Para obtener más información, consulte [Resultado de las características de personalidad](/docs/services/personality-insights?topic=personality-insights-output#traitJSON).

## Paso 2: Enviar entrada JSON y recibir salida JSON detallada
{: #example2}

El segundo ejemplo pasa el archivo JSON `profile.json` al método `/v3/profile`, solicitando de nuevo una respuesta JSON. El ejemplo solicita preferencias de consumo y puntuaciones en bruto para un análisis más detallado de la entrada.

1.  Descargue el archivo de ejemplo <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Icono de enlace externo" title="Icono de enlace externo"></a>, que contiene una recopilación de mensajes de Twitter.
1.  Emita el siguiente mandato para enviar el archivo al método `/v3/profile`. El ejemplo especifica `application/json` para las cabeceras `Content-Type` y `Accept`; el parámetro `charset` no es necesario para la entrada JSON. El ejemplo establece los parámetros de consulta `consumption_preferences` y `raw_scores` en `true`.

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.json \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"{: url}
    ```
    {: pre}

El servicio devuelve un perfil JSON que incluye los metadatos y las características devueltas con el ejemplo anterior. Para cada característica, el servicio también incluye una `raw_score`, que representa la puntuación del autor para la característica basada exclusivamente en el texto de entrada, sin comparar los resultados con una población de ejemplo.

Dado que el contenido de entrada incluye las indicaciones de fecha y hora, el servicio también informa de características de comportamiento. Estas son características temporales que indican el `porcentaje` de los elementos de contenido creados en cada día de la semana y hora del día. Para obtener más información, consulte [Salida de comportamiento](/docs/services/personality-insights?topic=personality-insights-output#behaviorJSON).

El servicio también informa de puntuaciones para su recopilación de preferencias de consumo. Las puntuaciones indican la probabilidad del autor para preferir distintos productos, servicios y actividades en función de las características deducidas. Para obtener más información, consulte [Salida de preferencias de consumo](/docs/services/personality-insights?topic=personality-insights-output#preferenceJSON).

## Paso 3: Enviar entrada JSON y recibir salida CSV detallada
{: #example3}

El tercer ejemplo es similar al segundo: pasa el mismo contenido JSON y solicita los mismos resultados. Pero este ejemplo especifica `text/csv` para la cabecera `Accept` para solicitar la respuesta en formato CSV (comma-separated values). Utiliza la opción `--output` del mandato `curl` para dirigir los resultados a un archivo llamado `profile.csv`. El ejemplo establece el parámetro de consulta `csv_headers` en `true` para solicitar que las cabeceras de columna se devuelvan con la salida.

1.  Emita el mandato siguiente para enviar el archivo JSON al método `/v3/profile`. La cabecera `Content-Type` identifica el contenido de entrada como `application/json`, y la cabecera `Accept` solicita una salida CSV, `text/csv`.

    ```bash
    curl -X POST -u "apikey:{apikey}"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary @{path_to_file}profile.json \
    --output profile.csv \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"{: url}
    ```
    {: pre}

Para obtener una descripción detallada de la respuesta y las cabeceras CSV, consulte [Comprensión de un perfil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV).

## Siguientes pasos
{: #gsns}

-   Más información sobre [Solicitud de un perfil](/docs/services/personality-insights?topic=personality-insights-input) y sobre [Comprensión de un perfil JSON](/docs/services/personality-insights?topic=personality-insights-output) y [Comprensión de un perfil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV).
-   Más información sobre los [modelos de personalidad](/docs/services/personality-insights?topic=personality-insights-models) de Los Cinco Grandes, Necesidades y Valores.
-   Más información sobre la API en la [referencia de la API ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/apidocs/personality-insights){: new_window}
-   Explore la [aplicación de ejemplo Node.js ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} para obtener más información sobre el desarrollo de aplicaciones con el servicio.
