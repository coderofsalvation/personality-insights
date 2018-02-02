---

copyright:
  years: 2015, 2017
lastupdated: "2017-09-13"

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

# Comprensión de un perfil
{: #output}

1.  <span style="color:#003F69">¿Cómo puedo interpretar los resultados devueltos por el servicio?</span>

    -   [Interpretación de los resultados numéricos](/docs/services/personality-insights/numeric.html) describe cómo interpretar el percentil que devuelve el servicio. También incluye información sobre porcentajes de comportamiento y la puntuación en bruto opcional y las preferencias de consumo que el servicio puede devolver.

1.  <span style="color:#003F69">¿Por qué añadir los resultados de las facetas de una dimensión no cede la puntuación para dicha dimensión?</span>

    -   [Percentiles para las características de personalidad](/docs/services/personality-insights/numeric.html#percentiles) responde a esta pregunta. En resumen, el servicio calcula el percentil normalizado para cada dimensión y faceta de forma independiente. No existe ninguna relación matemática entre una dimensión y sus facetas.

1.  <span style="color:#003F69">¿Cuándo debo utilizar la puntuación en bruto en lugar de la puntuación del percentil?</span>

    -   [Puntuaciones en bruto para características de personalidad](/docs/services/personality-insights/numeric.html#rawScores) proporciona información sobre esta opción. Brevemente, puede utilizar una puntuación en bruto cuando desee desarrollar una normalización personalizada para un caso de ejemplo específico o cuando no se necesite la comparación con una población de ejemplo. Si necesita conocimientos sobre como se comparan los resultados de un autor con una población de ejemplo, utilice las puntuaciones de los percentiles.

1.  <span style="color:#003F69">¿Cómo puedo normalizar una puntuación en bruto con una puntuación de percentiles?</span>

    -   [Puntuaciones en bruto para características de personalidad](/docs/services/personality-insights/numeric.html#rawScores) proporciona orientación de alto nivel para normalizar una puntuación en bruto y discute el enfoque de {{site.data.keyword.IBM_notm}} con la normalización.

1.  <span style="color:#003F69">¿Cómo puedo interpretar la visualización de {{site.data.keyword.personalityinsightsshort}}?</span>

    -   [Interpretación de los resultados numéricos](/docs/services/personality-insights/numeric.html) describe cómo interpretar los resultados numéricos que se muestran en la visualización.
