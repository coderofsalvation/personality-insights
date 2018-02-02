---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-28"

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

# Comprensión de un perfil JSON
{: #output}

Cuando utiliza el método `POST /v3/profile` para analizar contenido, el servicio devuelve los resultados de su análisis como un objeto `Profile` de JSON de forma predeterminada o al especificar `application/json` con la cabecera `Accept` de una solicitud. El ámbito de la salida JSON depende de los parámetros que haya especificado con la solicitud y de si el texto de entrada representa datos con indicación de fecha y hora, como por ejemplo el texto asociado con un canal de Twitter.
{: shortdesc}

Las siguientes secciones describen el contenido de una respuesta en formato JSON. Toda la salida de ejemplo la produce el archivo JSON de ejemplo <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Icono de enlace externo" title="Icono de enlace externo" class="style-scope doc-content"></a> que se utiliza en la [Guía de aprendizaje de iniciación](/docs/services/personality-insights/getting-started.html). Para obtener información sobre la salida CSV, consulte [Comprensión de un perfil CSV](/docs/services/personality-insights/output-csv.html).

## El objeto Profile
{: #outputJSON}

El objeto `Profile` es el objeto JSON de nivel superior devuelto por el servicio. El objeto tiene los campos siguientes:

-   `word_count` (entero) proporciona el número de palabras del contenido de entrada que se utilizaron para generar el perfil. Puede ser menos que el número de palabras de la entrada si la solicitud ha enviado una gran cantidad de contenido. Si el número de palabras no cumple con un umbral mínimo, la salida también incluirá un campo `word_count_message` que proporciona orientación adicional.
-   `processed language` (serie) describe el modelo de idioma que ha utilizado el servicio para procesar la entrada: `ar` (árabe), `en` (inglés), `es` (español), `ja` (japonés), o `ko` (coreano).
-   `personality` es una matriz recursiva de objetos `Trait` que describe las cinco grandes dimensiones y facetas deducidas del texto de entrada.
-   `needs` es una matriz de objetos `Trait` que describe las necesidades deducidas del texto de entrada.
-   `values` es una matriz de objetos `Trait` que describe los valores deducidos del texto de entrada.
-   `behavior` es una matriz de objetos `Behavior` que describe la distribución del contenido en los días de la semana y en las horas del día. El servicio devuelve el campo solo para la entrada JSON que tiene indicación de fecha y hora.
-   `consumption_preferences` es una matriz de objetos `ConsumptionPreferencesCategory` que proporciona resultados para cada categoría de preferencias de consumo. Los elementos de la matriz proporcionan información para las preferencias individuales de dicha categoría. El servicio devuelve el campo solo si el parámetro de consulta `consumption_preferences` de la solicitud se establece en `true`.
-   `warnings` es una matriz de objetos `Warning` que proporciona mensajes asociados con el texto de entrada. La matriz está vacía si la entrada no ha generado avisos.

### Respuesta de ejemplo
{: #JSONExample}

La siguiente salida de ejemplo muestra la estructura de alto nivel de un objeto `Profile`. La salida siempre incluye los campos `personality`, `needs`, y `values`. Si la entrada es JSON con indicación de fecha y hora, la respuesta incluye el campo `behavior`. Y si la solicitud también pide preferencias de consumo, la respuesta incluirá el campo `consumption_preferences`. En este ejemplo, la entrada no genera avisos.

```javascript
{
  "word_count": 15223,
  "processed_language": "en",
  "personality": [
     . . .
  ],
  "needs": [
     . . .
  ],
  "values": [
     . . .
  ],
  "behavior": [
     . . .
  ],
  "consumption_preferences": [
     . . .
   ],
  "warnings": []
}
```
{: codeblock}

## Salida de características de personalidad
{: #traitJSON}

El objeto `Profile` siempre incluye los campos `personality`, `needs`, y `values` para todos los tipos de entrada. Cada uno de estos campos contiene una matriz de objetos `Trait` que describe las características de personalidad para los atributos de dicho tipo de característica. Para las características necesidades y valores, la matriz tiene un único nivel que describe las características. Para las cinco grandes características, una matriz de nivel superior describe las dimensiones, y las matrices de segundo nivel describen las facetas de cada dimensión.

-   `trait_id` (serie) es el ID exclusivo de la característica a la que pertenecen los resultados:
    -   `big5_characteristic` para las cinco grandes dimensiones de personalidad
    -   `facet_characteristic` para las cinco grandes facetas de personalidad
    -   `need_characteristic` para necesidades
    -   `value_characteristic` para valores
-   `name` (serie) es el nombre visible del usuario de la característica.
-   `category` (serie) es la categoría de la característica:
    -   `personality` para las cinco grandes características de personalidad
    -   `needs` para necesidades
    -   `values` para valores
-   `percentile` (doble) es la puntuación de percentil normalizada para la característica. Para obtener más información, consulte [Percentiles para características de personalidad](/docs/services/personality-insights/numeric.html#percentiles).
-   `raw_score` (doble) es la puntuación en bruto para la característica. El campo solo se devuelve si solicita puntuaciones en bruto estableciendo el parámetro de consulta `raw_scores` en `true`. Para obtener más información, consulte [Puntuaciones en bruto para las características de personalidad](/docs/services/personality-insights/numeric.html#rawScores).
-   `significant` (booleano) indica si la característica es significativa para el idioma de entrada. El campo es siempre `true` para todas las características de la entrada en inglés, español y japonés. El campo es `false` para el subconjunto de características de la entrada en árabe y coreano para la que los modelos de servicio no pueden generar resultados significativos. Para obtener más información, consulte [Limitaciones para entrada en árabe y coreano](/docs/services/personality-insights/numeric.html#limitations).
-   `children` es una matriz de objetos `Trait` que proporciona resultados más detallados para las facetas de cada dimensión de las cinco grandes, como se ha deducido del texto de entrada. La matriz solo se devuelve para las cinco grandes dimensiones.

### Respuesta de ejemplo
{: #traitExample}

La salida de ejemplo siguiente muestra fragmentos de la salida para las características cinco grandes, necesidades y valores. Tal como se describe, solo las cinco grandes características tienen una matriz de `children` para sus respectivas facetas.

```javascript
{
  . . .
  "personality": [
    {
      "trait_id": "big5_openness",
      "name": "Openness",
      "category": "personality",
      "percentile": 0.8011555009553,
      "raw_score": 0.77565404255038,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_adventurousness",
          "name": "Adventurousness",
          "category": "personality",
          "percentile": 0.89755869047319,
          "raw_score": 0.54990704031219,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_conscientiousness",
      "name": "Conscientiousness",
      "category": "personality",
      "percentile": 0.81001753184176,
      "raw_score": 0.66899984888815,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_achievement_striving",
          "name": "Achievement striving",
          "category": "personality",
          "percentile": 0.84613299226628,
          "raw_score": 0.74240118454888,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_extraversion",
      "name": "Extraversion",
      "category": "personality",
      "percentile": 0.64980796071382,
      "raw_score": 0.56817738781166,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_activity_level",
          "name": "Activity level",
          "category": "personality",
          "percentile": 0.88220584913965,
          "raw_score": 0.60106995926143,
          "significant": true
        },
      ]
    },
    {
      "trait_id": "big5_agreeableness",
      "name": "Agreeableness",
      "category": "personality",
      "percentile": 0.94786124793821,
      "raw_score": 0.80677815631809,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_altruism",
          "name": "Altruism",
          "category": "personality",
          "percentile": 0.99241983824205,
          "raw_score": 0.79028406290747,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_neuroticism",
      "name": "Emotional range",
      "category": "personality",
      "percentile": 0.5008224041628,
      "raw_score": 0.46748200007024,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_anger",
          "name": "Fiery",
          "category": "personality",
          "percentile": 0.17640022058508,
          "raw_score": 0.48490315691802,
          "significant": true
        },
        . . .
      ]
    }
  ],
  "needs": [
    {
      "trait_id": "need_challenge",
      "name": "Challenge",
      "category": "needs",
      "percentile": 0.67362332054511,
      "raw_score": 0.75196348037675,
      "significant": true
    },
    . . .
  ],
  "values": [
    {
      "trait_id": "value_conservation",
      "name": "Conservation",
      "category": "values",
      "percentile": 0.89268222856139,
      "raw_score": 0.72135308187423,
      "significant": true
    },
    . . .
  ],
  . . .
}
```
{: codeblock}

## Salida de comportamiento
{: #behaviorJSON}

Si la entrada al servicio es JSON que tiene indicaciones de fecha y hora para los elementos de contenido individual, el objeto `Profile` incluirá un campo `behavior`. El campo incluye un objeto `Behavior` para cada día de la semana y hora del día.

-   `trait_id` (serie) es el ID exclusivo de la característica a la que pertenecen los resultados:
    -   `behavior_day` para días de la semana (por ejemplo, `behavior_sunday`).
    -   `behavior_hour` para horas del día (por ejemplo, `behavior_0000`).
-   `name` (serie) es el nombre visible del usuario de la característica.
-   `category` (serie) es la categoría de la característica, que es siempre `behavior`.
-   `percentage` (doble) es el porcentaje de elementos de contenido que se ha producido durante dicho día de la semana u hora del día. Para obtener más información, consulte [Porcentajes para características de comportamiento](/docs/services/personality-insights/numeric.html#percentages).

### Respuesta de ejemplo
{: #behaviorExample}

La salida siguiente muestra fragmentos de la salida de comportamiento para características temporales.

```javascript
{
  . . .
  "behavior": [
    {
      "trait_id": "behavior_sunday",
      "name": "Sunday",
      "category": "behavior",
      "percentage": 0.21392532795156
    },
    {
      "trait_id": "behavior_monday",
      "name": "Monday",
      "category": "behavior",
      "percentage": 0.42583249243189
    },
    . . .
    {
      "trait_id": "behavior_saturday",
      "name": "Saturday",
      "category": "behavior",
      "percentage": 0.077699293642785
    },
    {
      "trait_id": "behavior_0000",
      "name": "0:00 am",
      "category": "behavior",
      "percentage": 0.4561049445005
    },
    {
      "trait_id": "behavior_0100",
      "name": "1:00 am",
      "category": "behavior",
      "percentage": 0.12209889001009
    },
    . . .
    {
      "trait_id": "behavior_2300",
      "name": "11:00 pm",
      "category": "behavior",
      "percentage": 0.12310797174571
    }
  ],
  . . .
}
```
{: codeblock}

## Salida de preferencias de consumo
{: #preferenceJSON}

Si el parámetro de consulta `consumption_preferences` se establece en `true`, el objeto `Profile` incluirá un campo `consumption_preferences`. El campo incluye un objeto `ConsumptionPreferencesCategory` para cada categoría de preferencias.

-   `consumption_preference_category_id` (serie) es el ID exclusivo de la categoría de preferencias de consumo a la que pertenecen los resultados en el formato `consumption_preferences_{category}`.
-   `name` (serie) es el nombre visible del usuario de la categoría de preferencias de consumo.
-   `consumption_preferences` es una matriz de objetos `ConsumptionPreferences` que proporciona resultados para las preferencias individuales de la categoría.

Cada preferencia individual para una categoría se describe mediante un objeto `ConsumptionPreferences`. Algunas categorías solo tienen una única preferencia, otras tienen muchas más.

-   `consumption_preference_id` (serie) es el ID exclusivo de la preferencia de consumo a la que pertenecen los resultados en el formato `consumption_preferences_preference`.
-   `name` (serie) es el nombre visible de usuario de la preferencia de consumo.
-   `score` (doble) es una puntuación que indica la probabilidad de que el autor prefiera el artículo. Para obtener más información, consulte [Puntuaciones para preferencias de consumo](/docs/services/personality-insights/numeric.html#scores).

### Respuesta de ejemplo
{: #preferenceExample}

La salida siguiente muestra fragmentos de la salida para las preferencias de consumo.

```javascript
{
  . . .
  "consumption_preferences": [
    {
      "consumption_preference_category_id": "consumption_preferences_shopping",
      "name": "Purchasing Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_automobile_ownership_cost",
          "name": "Likely to be sensitive to ownership cost when buying automobiles",
          "score": 0
        },
        . . .
      ]
    },
    {
      "consumption_preference_category_id": "consumption_preferences_health_and_activity",
      "name": "Health & Activity Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_eat_out",
          "name": "Likely to eat out frequently",
          "score": 1
        },
        . . .
      ]
    },
    . . .
    {
      "consumption_preference_category_id": "consumption_preferences_volunteering",
      "name": "Volunteering Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_volunteer",
          "name": "Likely to volunteer for social causes",
          "score": 0
        }
      ]
    }
  ],
  . . .
}
```
{: codeblock}
