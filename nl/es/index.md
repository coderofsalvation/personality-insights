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

# Acerca de
{: #about}

> **Actualización de servicio:** *El servicio de {{site.data.keyword.personalityinsightsshort}} se ha actualizado el 13 de octubre de 2017. Cada objeto `Rasgo` de un perfil de personalidad ahora incluye un campo `significant` para indicar si una característica de personalidad es significativa para el idioma de entrada. El campo identifica las características para las que los modelos del servicio no pueden generar resultados significativos para la entrada en árabe y coreano. La versión de la interfaz para el release es `2017-10-13`. Para obtener más información sobre esta y todas las actualizaciones del servicio, consulte las [Notas de release](/docs/services/personality-insights/release-notes.html).*

El servicio de {{site.data.keyword.personalityinsightsfull}} proporciona una API (Application Programming Interface) para obtener información de las redes sociales, los datos empresariales, u otras comunicaciones digitales. El servicio utiliza análisis lingüístico para deducir las características de personalidad intrínsecas del individuo de las comunicaciones digitales como correo electrónico, mensajes de texto, tuits y publicaciones de foros.
{: shortdesc}

El servicio deduce, desde las redes sociales potencialmente ruidosas, retratos de individuos que reflejan sus características de personalidad. También puede determinar las preferencias de consumo de los individuos, lo que indica su probabilidad de preferir varios productos, servicios y actividades.

## Características de personalidad
{: #models}

El servicio de {{site.data.keyword.personalityinsightsshort}} deduce características de personalidad basándose en tres modelos primarios:

-   Las **cinco grandes** características de personalidad representan el modelo más utilizado para describir de forma general cómo interactúa una persona con el mundo. El modelo incluye cinco dimensiones primarias: *Simpatía*, *Responsabilidad*, *Extraversión*, *Rango emocional*, y *Apertura*. Cada dimensión tiene seis facetas que caracterizan más a un individuo según la dimensión.
-   **Necesidades** describe los aspectos de un producto con los que se identificará una persona. El modelo incluye doce necesidades características: *Entusiasmo*, *Armonía*, *Curiosidad*, *Ideal*, *Proximidad*, *Autoexpresión*, *Libertad*, *Amor*, *Uso práctico*, *Estabilidad*, *Reto* y *Estructura*.
-   **Valores** describe los factores de motivación que influyen en la toma de decisiones de una persona. El modelo incluye cinco valores: *Autotrascendencia/Ayuda a los demás*, *Conservación/Tradición*, *Hedonismo/Disfrutar de la vida*, *Superación personal/Tener éxito*, y *Apertura al cambio/Emoción*.

Para obtener más información, consulte [Modelos de personalidad](/docs/services/personality-insights/models.html).

## Preferencias de consumo
{: #preferences}

Basándose en las características de personalidad deducidas del texto de entrada, el servicio también puede devolver una indicación de las preferencias de consumo del autor. Las preferencias de consumo indican la probabilidad del autor para perseguir distintos productos, servicios y actividades. El servicio agrupa las preferencias individuales en ocho categorías: *Comprar*, *Música*, *Películas*, *Leer y aprender*, *Salud y actividad*, *Voluntariado*, *Interés en cuestiones ambientales*, y *Emprendimiento*. Cada categoría contiene de una a doce preferencias individuales.

Para obtener más información, consulte [Preferencias de consumo](/docs/services/personality-insights/preferences.html).

## Ventajas del servicio
{: #benefits}

Como servicio principal de la plataforma de {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}}, el servicio de {{site.data.keyword.personalityinsightsshort}} puede proporcionar información que ayudará a las empresas a

-   Comprender a sus clientes en un nivel más profundo, aprendiendo sus preferencias, mejorando la satisfacción del cliente y fortaleciendo las relaciones con el cliente.
-   Mejorar la adquisición, la retención y el compromiso de los clientes.
-   Guiar compromisos e interacciones muy personalizados para adaptarse mejor a sus productos, servicios, campañas y comunicaciones para los clientes individuales.

Para obtener más información sobre cómo puede beneficiarse del servicio, consulte [Casos de uso](/docs/services/personality-insights/usecases.html).

## Soporte de idiomas
{: #languages}

El servicio da soporte a los siguientes idiomas. Puede utilizar cualquier combinación de idiomas soportados para la solicitud y la respuesta, pero todo el texto de entrada debe estar en el mismo idioma. Para obtener más información, consulte [Especificación de idiomas de solicitud y respuesta](/docs/services/personality-insights/input.html#languages).

<table style="width:75%">
  <caption>Tabla 1. Idiomas soportados</caption>
  <tr>
    <th style="width:50%; text-align:center">
      Idiomas de solicitud
    </th>
    <th style="width:50%; text-align:center">
      Idiomas de respuesta
    </th>
  </tr>
  <tr>
    <td style="text-align:center; vertical-align:top">
      Árabe<br/>
      Inglés<br/>
      Japonés<br/>
      Coreano<br/>
      Español
    </td>
    <td style="text-align:center; vertical-align:top">
      Árabe<br/>
      Inglés<br/>
      Japonés<br/>
      Coreano<br/>
      Español<br/>
      Portugués de Brasil<br/>
      Francés<br/>
      Alemán<br/>
      Italiano<br/>
      Chino simplificado<br/>
      Chino tradicional
    </td>
  </tr>
</table>

## Más información sobre el servicio
{: #learn}

-   Una demostración rápida de [ ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://personality-insights-demo.ng.bluemix.net/){: new_window} del servicio de {{site.data.keyword.personalityinsightsshort}} le permite analizar el texto de entrada para desarrollar un retrato de personalidad que incluya las preferencias de consumo para el autor.
-   Las aplicaciones de {{site.data.keyword.watson}} Developer Cloud [Starter Kits ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://www.ibm.com/watson/developercloud/starter-kits.html){: new_window} muestran el servicio.
-   [El servicio en acción](/docs/services/personality-insights/applied.html) y [La ciencia detrás del servicio](/docs/services/personality-insights/science.html) proporcionan información sobre la búsqueda que subyace en el servicio.
-   El servicio de [{{site.data.keyword.personalityinsightsshort}} del Catálogo de {{site.data.keyword.Bluemix_short}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://console.ng.bluemix.net/catalog/services/personality-insights/){: new_window} describe los planes de precios disponibles para el servicio.
