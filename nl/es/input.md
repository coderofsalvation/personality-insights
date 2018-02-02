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

# Solicitud de un perfil
{: #input}

Para analizar el contenido, utilice el método de solicitud `POST` HTTP para llamar al método `/v3/profile` del servicio de {{site.data.keyword.personalityinsightsshort}}. Puede pasar al servicio un máximo de 20 MB de contenido para ser analizado mediante el cuerpo de la solicitud, pero el servicio necesita mucha menos entrada para producir un perfil de personalidad preciso; para obtener más información, consulte [Proporcionar suficiente entrada](#sufficient).
{: shortdesc}

El método `/v3/profile` incluye parámetros que le permiten especificar el tipo de contenido que el servicio pasará y devolverá, así como el idioma de cada tipo de contenido. El servicio siempre devuelve un perfil que proporciona información sobre las características de personalidad del autor del texto de entrada. También puede solicitar que el servicio devuelva puntuaciones en bruto y preferencias de consumo.

En las secciones siguientes se describen los parámetros del método `/v3/profile`. Para obtener información sobre los resultados de una solicitud, consulte [Comprensión de un perfil JSON](/docs/services/personality-insights/output.html) y [Comprensión de un perfil CSV](/docs/services/personality-insights/output-csv.html). Para obtener información detallada sobre el método `/v3/profile`, consulte la [Referencia de API ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

## Cómo especificar formatos de solicitud y de respuesta
{: #formats}

Puede utilizar los parámetros de cabecera `Content-Type` y `Accept` para indicar el formato del contenido que está pasando al método y al formato de la respuesta del servicio. Puede utilizar cualquier combinación de formatos soportados para la solicitud y la respuesta.

<table>
  <caption>Tabla 1. Cómo especificar formatos de solicitud y de respuesta</caption>
  <tr>
    <th style="width:10%; text-align:left; vertical-align:bottom">
      Formato
    </th>
    <th style="width:26%; text-align:center; vertical-align:bottom">
      Argumento
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      Soportado por<br/>
      <code>Content-Type</code>
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      Soportado por<br/>
      <code>Accept</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Texto sin formato
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/plain</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Sí (valor predeterminado)<br/><br/>
      El servicio procesa texto sin formato sin modificación.
    </td>
    <td style="text-align:center; vertical-align:top">
      No
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      HTML
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/html</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Sí<br/><br/>
      El servicio separa las etiquetas del contenido antes de procesarlo.
    </td>
    <td style="text-align:center; vertical-align:top">
      No
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      JSON
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>application/json</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Sí<br/><br/>
      El contenido debe ajustarse al modelo definido por el objeto
      <code>Content</code>, que es una matriz
      de los objetos <code>ContentItem</code>.
    </td>
    <td style="text-align:center; vertical-align:top">
      Sí (valor predeterminado)<br/><br/>
      El servicio devuelve sus resultados como un objeto <code>Profile</code>.

    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      CSV
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/csv</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      No
    </td>
    <td style="text-align:center; vertical-align:top">
      Sí<br/><br/>
      De forma predeterminada, el servicio devuelve una sola fila de resultados numéricos.
      Establezca el parámetro de consulta <code>csv_headers</code> opcional en
      <code>true</code> para solicitar cabeceras para cada columna de la solicitud.
    </td>
  </tr>
</table>

### Cómo especificar el juego de caracteres
{: #charset}

De forma predeterminada, el servicio utiliza los juegos de caracteres siguientes para el contenido de entrada:

-   *Para texto sin formato y contenido HTML,* el servicio utiliza el juego de caracteres International Standards Organization (ISO)-8859-1 (efectivamente, el juego de caracteres ASCII) por especificación HTTP versión 1.1.
-   *Para contenido JSON,* el servicio efectivamente siempre utiliza el juego de caracteres Unicode Transformation Format (UTF)-8 por Sección 8.1 de la International Engineering Task Force (IETF) [Request for Comment (RFC) 7159 ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://tools.ietf.org/html/rfc7159#section-8.1){: new_window}.

Al presentar el texto sin formato o el contenido HTML, incluya el parámetro `charset` con la cabecera `Content-Type` para indicar la codificación de caracteres del texto de entrada. El ejemplo siguiente especifica la codificación de caracteres UTF-8 para la entrada de texto sin formato:

```
Content-Type: text/plain;charset=utf-8
```
{: codeblock}

Al utilizar el parámetro `charset`, puede evitar posibles problemas asociados con caracteres no ASCII o no imprimibles. Si pasa datos UTF-8 sin especificar el juego de caracteres, los caracteres especiales pueden dar lugar a resultados incorrectos o a errores 4*nn* o 5*nn* HTTP.

### Cómo utilizar cURL
{: #charsetCurl}

Para evitar errores cuando se utiliza cURL, pase siempre el contenido a través de la opción `--data-binary` del mandato `curl` para preservar cualquier codificación UTF-8 para el contenido. Si utiliza la opción `--data` para pasar el contenido como ASCII, el mandato puede procesar la entrada, lo que puede provocar problemas para los datos codificados en UTF-8.

Por ejemplo, el mandato `curl` siguiente utiliza correctamente la opción `--data-binary` para publicar el contenido del *filename* especificado sin proceso adicional. El mandato también utiliza el parámetro `charset` con la cabecera `Content-Type`, y solicita explícitamente el formato de respuesta JSON predeterminado.

```bash
curl -X POST --user {username}:{password}
--header "Content-Type: text/plain;charset=utf-8"
--header "Accept: application/json"
--data-binary @{filename}
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{: pre}

Para obtener ejemplos adicionales de cómo llamar al servicio con distintos formatos de solicitud y de respuesta, consulte la [Guía de aprendizaje de iniciación](/docs/services/personality-insights/getting-started.html).

## Cómo especificar entrada JSON
{: #json}

Para pasar entrada JSON, utilice el objeto `Content`. El objeto incluye una matriz de objetos `ContentItem`, cada uno de los cuales contiene un elemento del contenido. El único campo necesario del objeto es `content`, que proporciona el texto que debe analizarse. Otros campos opcionales le permiten especificar lo siguiente:

-   `id` (serie) es un ID exclusivo para el elemento de contenido.
-   `created` (entero) es una indicación de fecha y hora de UNIX que indica cuándo se ha creado el elemento de contenido.
-   `updated` (entero) es una indicación de fecha y hora de UNIX que indica cuándo se ha actualizado por última vez el elemento de contenido.
-   `contenttype` (serie) indica el tipo de elemento de contenido, `text/plain` o `text/html`.
-   `language` (serie) indica el idioma del elemento de contenido: `ar` (árabe), `en` (inglés), `es` (español), `ja` (japonés) o `ko` (coreano). Consulte [Especificación de idiomas de solicitud y respuesta](#languages).
-   `parentid` (serie) es el `id` del elemento padre del elemento de contenido.
-   `reply` (booleano) indica si el elemento de contenido es una respuesta a otro elemento.
-   `forward` (booleano) indica si el elemento de contenido es un reenvío o una copia de otro elemento.

La entrada de JSON es muy adecuada para el contenido de Twitter o de otras redes sociales que constan de varias conversaciones o publicaciones. En lugar de concatenar todo el texto del autor en una serie única, puede utilizar JSON para enviar los datos tal como existen. Esto tiene la ventaja adicional de permitir que el servicio sepa qué partes del texto están relacionadas.

### Entrada JSON de ejemplo
{: jsonExample}

Los ejemplos de la [Guía de aprendizaje de iniciación](/docs/services/personality-insights/getting-started.html) utilizan el archivo JSON de ejemplo <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Icono de enlace externo" title="Icono de enlace externo" class="style-scope doc-content"></a>. El archivo incluye una serie de mensajes de Twitter. El ejemplo siguiente muestra los primeros tuits del archivo.

```javascript
{
  "contentItems": [
    {
      "content": "Wow, I liked @TheRock before, now I really SEE how special he is. The daughter story was IT for me. So great! #MasterClass",
      "contenttype": "text/plain",
      "created": 1447639154000,
      "id": "666073008692314113",
      "language": "en"
    },
    {
      "content": ".@TheRock how did you Know to listen to your gut and Not go back to football? #Masterclass",
      "contenttype": "text/plain",
      "created": 1447638226000,
      "id": "666069114889179136",
      "language": "en"
    },
    . . .
  ]
}
```
{: codeblock}

## Especificación de idiomas de solicitud y respuesta
{: #languages}

Puede utilizar los parámetros de cabecera `Content-Language` y `Accept-Language` para indicar el idioma del contenido de entrada y el idioma de la respuesta del servicio. Puede utilizar cualquier combinación de idiomas soportados para la solicitud y la respuesta. Si no indica un idioma, el servicio utilizará sus modelos entrenados en inglés para su análisis y el inglés para sus resultados. La tabla siguiente enumera los idiomas de entrada y de salida soportados e identifica los argumentos que utiliza con los parámetros relacionados con el idioma.

<table style="width:90%">
  <caption>Tabla 2. Especificación de idiomas de solicitud y respuesta</caption>
  <tr>
    <th style="width:28%; text-align:left; vertical-align:bottom">
      Idioma
    </th>
    <th style="width:12%; text-align:center; vertical-align:bottom">
      Argumento
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      Soportado por<br/>
      <code>Content-Language</code>
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      Soportado por<br/>
      <code>Accept-Language</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      Árabe
    </td>
    <td style="text-align:center">
      <code>ar</code>
    </td>
    <td style="text-align:center">
      Sí
    </td>
    <td style="text-align:center">
      Sí
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Inglés
    </td>
    <td style="text-align:center">
      <code>en</code>
    </td>
    <td style="text-align:center">
      Sí
    </td>
    <td style="text-align:center">
      Sí
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Japonés
    </td>
    <td style="text-align:center">
      <code>ja</code>
    </td>
    <td style="text-align:center">
      Sí
    </td>
    <td style="text-align:center">
      Sí
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Coreano
    </td>
    <td style="text-align:center">
      <code>ko</code>
    </td>
    <td style="text-align:center">
      Sí
    </td>
    <td style="text-align:center">
      Sí
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Español
    </td>
    <td style="text-align:center">
      <code>es</code>
    </td>
    <td style="text-align:center">
      Sí
    </td>
    <td style="text-align:center">
      Sí
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Portugués de Brasil
    </td>
    <td style="text-align:center">
      <code>pt-br</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Sí
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Francés
    </td>
    <td style="text-align:center">
      <code>fr</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Sí
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Alemán
    </td>
    <td style="text-align:center">
      <code>de</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Sí
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Italiano
    </td>
    <td style="text-align:center">
      <code>it</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Sí
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Chino simplificado
    </td>
    <td style="text-align:center">
      <code>zh-cn</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Sí
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Chino tradicional
    </td>
    <td style="text-align:center">
      <code>zh-tw</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Sí
    </td>
  </tr>
</table>

Envíe todo el texto en el mismo idioma; no mezcle varios idiomas en la misma solicitud. Para los argumentos de idioma de dos caracteres, el servicio trata variantes regionales como su idioma padre; por ejemplo, se interpreta `en-US` como `en`.

### Cómo especificar un idioma para contenido JSON
{: #languageJSON}

Para texto sin formato y entrada HTML, la cabecera `Content-Language` es la única forma de especificar el idioma. Para la entrada JSON, también puede especificar el idioma de cada elemento de contenido individual mediante el parámetro `language` del objeto `ContentItem`. Sin embargo, un idioma especificado con la cabecera `Content-Language` altera un idioma especificado para un elemento de contenido; el servicio ignora los elementos de contenido que especifican un idioma distinto.

Omita la cabecera `Content-Type` para basar el idioma únicamente en la especificación de los elementos de contenido. El servicio utiliza el idioma principal de entre los elementos de contenido, lo que genera los mejores resultados posibles. Se cuenta el número de elementos de contenido para cada idioma y se selecciona el idioma con la mayor frecuencia. Si varios idiomas tienen la misma frecuencia máxima, el servicio utilizará el idioma que llega a ese valor en primer lugar. De nuevo, el servicio ignora elementos de contenido que especifican un idioma distinto.

### Consideraciones sobre el idioma
{: #languageNotes}

Tenga en cuenta lo siguiente al enviar texto de entrada:

-   *Para inglés,* los resultados se basan en las normas culturales de los EE.UU. Si analiza texto en inglés desde una cultura distinta, es posible que necesite ajustar los resultados en consecuencia.
-   *Para árabe,* el servicio puede reducir la cantidad de texto de entrada por motivos de rendimiento. En un umbral determinado, la precisión de los resultados en árabe no mejora con más palabras. Si el servicio reduce la entrada de árabe, devolverá un mensaje de aviso para informarle de que ha reducido la cantidad de texto de entrada utilizado para el perfil.
-   *Para árabe y coreano,* el servicio no puede devolver resultados significativos para un subconjunto de características. Para obtener más información, consulte [Limitaciones para entrada en árabe y coreano](/docs/services/personality-insights/numeric.html#limitations).

Para obtener información general sobre el uso de texto traducido, consulte [Cómo deducir la personalidad de texto traducido](/docs/services/personality-insights/guidance.html#translation).

## Proporcionar suficiente entrada
{: #sufficient}

Un perfil de personalidad significativa puede crearse sólo cuando se proporcionan suficientes datos de cantidad y calidad adecuados. Dado que el uso del idioma varía naturalmente de un documento a otro y de vez en cuando, una pequeña muestra de texto podría no ser representativa de los patrones de idioma generales de un individuo. Además, características y redes distintas convergen en tasas algo diferentes.

Hasta cierto punto, más palabras pueden producir mejores resultados, mejorando la precisión del servicio reduciendo la desviación entre los resultados previstos y la puntuación real del autor. Puede enviar el servicio hasta a 20 MB de contenido de entrada, pero los niveles de precisión se desactivan a alrededor de 3000 palabras de entrada; el contenido adicional no contribuye más a la exactitud del perfil. Por lo tanto, el servicio extrae y utiliza solo los primeros 250 KB de contenido, sin contar ninguna marcación HTML ni JSON, de solicitudes grandes.

Esta cifra no se correlaciona con un número exacto de palabras, que varía en función del idioma y de la naturaleza del texto. En inglés, por ejemplo, la longitud de palabra promedio está entre cuatro y cinco caracteres, por lo que esta cifra proporciona alrededor de 50.000 palabras, lo que es al menos 15 veces más palabras de las que el servicio necesita para producir un perfil preciso. Al truncar la entrada larga, el servicio mejora el tiempo de respuesta sin sacrificar la precisión. El campo `word_count` del JSON de respuesta indica el número de palabras que el servicio utiliza realmente para una solicitud, lo que puede ser inferior que el número de palabras enviadas.

### Directrices y recomendaciones
{: #sufficientGuidelines}

La tabla siguiente informa de dos valores para distintas cantidades de texto de entrada:

-   *Error absoluto medio promedio (MAE, Average Mean Absolute Error)* en todas las características basadas en el número de palabras proporcionadas como entrada. Cuando más pequeño sea el MAE, más cerca estarán los resultados del servicio a las puntuaciones que el autor recibiría realizando una prueba de personalidad real.
-   *Correlación promedio* entre las puntuaciones deducidas y reales en todas las características. Cuando más cercana es la correlación a 1, mejores serán las predicciones, aunque las correlaciones por encima de 0,2 se consideran aceptables y las superiores a 0,4 son raras.

La información se basa en los datos en inglés, pero las directrices generales se aplican a todos los idiomas. Para obtener más información sobre MAE y correlación promedio, incluyendo estadísticas específicas del idioma, consulte [Cómo de preciso es el servicio](/docs/services/personality-insights/science.html#researchPrecise).

<table style="width:80%">
  <caption>Tabla 3. MAE y correlación promedio</caption>
  <tr>
    <th style="text-align:center; vertical-align:bottom; width:24%">Número de palabras</th>
    <th style="text-align:center; width:38%">MAE promedio<br/>en todas
      las características</th>
    <th style="text-align:center; width:38%">Correlación promedio<br/>en todas las
      características</th>
  </tr>
  <tr>
    <td style="text-align:center">3000</td>
    <td style="text-align:center">12,1%</td>
    <td style="text-align:center">0,257</td>
  </tr>
  <tr>
    <td style="text-align:center">1200</td>
    <td style="text-align:center">12,2%</td>
    <td style="text-align:center">0,237</td>
  </tr>
  <tr>
    <td style="text-align:center">600</td>
    <td style="text-align:center">12,3%</td>
    <td style="text-align:center">0,212</td>
  </tr>
  <tr>
    <td style="text-align:center">300</td>
    <td style="text-align:center">12,5%</td>
    <td style="text-align:center">0,175</td>
  </tr>
  <tr>
    <td style="text-align:center">100</td>
    <td style="text-align:center">12,7%</td>
    <td style="text-align:center">0,095</td>
  </tr>
</table>

Como indican las directrices siguientes, {{site.data.keyword.IBM_notm}} recomienda proporcionar al menos 1200 palabras, pero proporcionar al menos 600 palabras se producen resultados aceptables:

-   3000 palabras son suficientes para conseguir la máxima precisión del servicio.
-   Al menos 1200 palabras da como resultado un MAE que está dentro del dos por ciento del mejor MAE que puede devolver el servicio.
-   Entre 600 y 1200 palabras da como resultado un MAE que está dentro del tres por ciento del mejor MAE que puede devolver el servicio.
-   Menos de 600 palabras generan un aviso, pero el servicio sigue analizando la entrada.
-   Menos de 100 palabras generan un error.

Estas directrices pueden ayudarle a acomodar la fiabilidad de los resultados a la aplicación. Por ejemplo, para una aplicación casual que recomienda películas, podría estar cómodo con menos precisión; para una aplicación que realiza recomendaciones más críticas, es posible que requiera resultados más precisos. Para obtener más información sobre cómo deduce el servicio las características de personalidad, consulte [Cómo se deducen las características de personalidad](/docs/services/personality-insights/science.html#researchInfer).

## Solicitud de puntuaciones en bruto
{: #rawScores}

El servicio siempre devuelve puntuaciones normalizadas para cada característica de personalidad (dimensión y faceta de los cinco grandes, necesidad y valor) como parte de su respuesta. El servicio también puede informar de una `raw_score` para cada característica si establece el parámetro de consulta `raw_scores` en `true`. Las puntuaciones en bruto representan las puntuaciones para las características basadas únicamente en el texto del autor y en el modelo para dicha característica, sin comparar los resultados con una población de ejemplo. Para obtener más información sobre cómo utilizar las puntuaciones en bruto, consulte [Puntuaciones en bruto para características de personalidad](/docs/services/personality-insights/numeric.html#rawScores).

## Cómo solicitar preferencias de consumo
{: #preferences}

El servicio siempre devuelve resultados para los modelos de personalidad. Al establecer el parámetro de consulta `consumption_preferences` en `true`, el servicio también devuelve `scores` para una variedad de preferencias de consumo basadas en las características de personalidad que deduce del texto de entrada. Estos resultados indican la tendencia del autor para preferir distintos productos, servicios y actividades. Las empresas pueden utilizar los resultados para comprender mejor las inclinaciones del autor y personalizar las comunicaciones y ofertas para el autor.

Para obtener más información sobre las diferentes preferencias de consumo, consulte [Preferencias de consumo](/docs/services/personality-insights/preferences.html). Para obtener información sobre la interpretación de los resultados numéricos para una preferencia, consulte [Puntuaciones para preferencias de consumo](/docs/services/personality-insights/numeric.html#scores).

## Cómo especificar la versión de la interfaz
{: #version}

Todas las llamadas al método `/v3/profile` deben incluir el parámetro de consulta `version` para indicar la versión de la API de servicio y el formato de respuesta que desea utilizar. Especifique la versión como una fecha en el formato `AAAA-MM-DD`; por ejemplo, especifique `2017-10-13` para el 13 de octubre de 2017. El parámetro permite al servicio actualizar su API y su formato de respuesta para versiones nuevas sin romper los clientes existentes.

La fecha que especifique no tiene que coincidir exactamente con una versión del servicio; el servicio utiliza la versión que no sea posterior a la fecha que proporcione. Si especifica una fecha anterior al release inicial de la versión 3, el servicio utilizará la versión 3 de la API. Si especifica una fecha que está en el futuro o que es posterior a la versión más reciente, el servicio utilizará la última versión.
