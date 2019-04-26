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

# Modelos de personalidad
{: #models}

El servicio {{site.data.keyword.personalityinsightsshort}} se basa en la psicología del lenguaje, junto con algoritmos de análisis de datos. El servicio analiza el contenido que se envía y devuelve un perfil de personalidad para el autor de la entrada. El servicio deduce las características de personalidad basándose en tres modelos:
{: shortdesc}

-   Las *cinco grandes* características de personalidad representan el modelo más utilizado para describir de forma general cómo interactúa una persona con el mundo. El modelo incluye cinco dimensiones primarias:
    -   [*Simpatía*](/docs/services/personality-insights?topic=personality-insights-agreeableness) es la tendencia de una persona a ser compasiva y cooperadora con los demás.
    -   [*Responsabilidad*](/docs/services/personality-insights?topic=personality-insights-conscientiousness) es la tendencia de una persona a actuar de forma organizada o meticulosa.
    -   [*Extraversión*](/docs/services/personality-insights?topic=personality-insights-extraversion) es la tendencia de una persona a buscar la estimulación en compañía de los demás.
    -   [*Rango emocional*](/docs/services/personality-insights?topic=personality-insights-emotionalRange), también conocido como *Neurosis* o *Reacciones naturales*, es la magnitud a la que son sensibles las emociones de una persona a su entorno.
    -   [*Apertura*](/docs/services/personality-insights?topic=personality-insights-openness) es el punto hasta el que una persona está abierta a experimentar distintas actividades.

    Cada una de estas dimensiones de nivel superior tiene seis facetas que caracterizan más a un individuo según la dimensión.
-   [Necesidades](/docs/services/personality-insights?topic=personality-insights-needs) describe los aspectos de un producto con los que se identifica una persona. El modelo incluye doce necesidades de características.
-   [Valores](/docs/services/personality-insights?topic=personality-insights-values) describe los factores de motivación que influyen en la toma de decisiones de una persona. El modelo incluye cinco valores.

Para obtener más información sobre cómo se han desarrollado los modelos y cómo los utiliza el servicio, consulte [La ciencia detrás del servicio](/docs/services/personality-insights?topic=personality-insights-science).

## Descripciones de las cinco grandes características de personalidad
{: #bigFive}

Cada dimensión de los Cinco grandes se describe mediante tres tablas:

-   La tabla *Facetas* introduce las facetas de la dimensión y describe a los individuos que tienen una puntuación alta en cada faceta.
-   La tabla *Rango de características* presenta descripciones generales que pueden aplicarse a las personas cuyas puntuaciones muestran más o menos de cada faceta de la dimensión, junto con los términos que pueden describir a dichas personas. Para una tabla de página única conveniente que resuma las tablas *Rango de características* para las facetas de las cinco dimensiones, consulte <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Facet-Characteristics.pdf" download="Personality-Insights-Facet-Characteristics.pdf">Personality-Insights-Facet-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="Icono de enlace externo" title="Icono de enlace externo"></a>.
-   La tabla *Dimensiones primarias y secundarias* presenta información que relaciona la dimensión con otras dimensiones, describiendo combinaciones de características de personalidad. La tabla proporciona información interesante sobre cómo se pueden interrelacionar las características primarias y secundarias para representar la personalidad compuesta de un individuo. Para una tabla de página única conveniente que resuma las tablas *Características primarias y secundarias* para las cinco dimensiones, consulte <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Dimension-Characteristics.pdf" download="Personality-Insights-Dimension-Characteristics.pdf">Personality-Insights-Dimension-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="Icono de enlace externo" title="Icono de enlace externo"></a>.
