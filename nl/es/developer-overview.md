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

# Visión general para desarrolladores
{: #overviewDevelopers}

Puede utilizar el servicio {{site.data.keyword.personalityinsightsshort}} mediante una API REST (Representational State Transfer) HTTP. También hay disponibles varios kits de desarrollo de software (SDK) para simplificar el desarrollo de aplicaciones en varios idiomas.
{: shortdesc}

## Programación con el servicio
{: #programming}

Para producir un perfil de personalidad, envíe texto al método `POST /v3/profile` HTTP del servicio. Puede enviar texto sin formato, HTML, o contenido JSON. El servicio puede devolver su análisis en formato JSON o CSV

Para cada característica de la personalidad, el servicio da un *percentil*. El percentil es una puntuación normalizada que describe hasta qué punto la escritura del autor exhibe una característica dentro de una población de ejemplo. Si se solicita, el servicio también devuelve una *puntuación en bruto*, que es un valor absoluto no normalizado para una población de ejemplo. Si la entrada es una indicación de fecha y hora, el servicio proporciona un resumen de los hábitos de escritura del autor por día de la semana y hora del día. Y si se solicita, el servicio también devuelve una puntuación parecida para cada una de sus preferencias de consumo disponibles.

Para obtener más información sobre cómo utilizar el servicio, consulte:

-   [Solicitud de un perfil](/docs/services/personality-insights?topic=personality-insights-input)
-   [Comprensión de un perfil JSON](/docs/services/personality-insights?topic=personality-insights-output)
-   [Comprensión de un perfil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV)

### Visualización de un perfil
{: #visualize}

El servicio proporciona una recopilación de archivos JavaScript que permiten la visualización gráfica de un perfil. Los scripts facilitan el uso del servicio con redes de distribución en caché y contenido. Se basan en JavaScript, jQuery, HTML y SVG con la biblioteca de Documentos controlados por datos (`D3.js`) para mostrar los resultados. Para obtener más información sobre `D3.js`, consulte [d3js.org ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://d3js.org/){: new_window}.

### Soporte de CORS
{: #CORS}

El servicio da soporte a CORS (Cross-Origin Resource Sharing). CORS permite que los clientes basados en navegador realicen solicitudes asíncronas directamente al servicio desde los scripts frontales. CORS omite la política de seguridad del mismo origen, que de lo contrario impide tales solicitudes.

Utilizando CORS, las páginas web pueden solicitar recursos de un dominio foráneo, que esté fuera del dominio de donde se ha originado la solicitud. Para obtener más información, consulte [enable-cors.org ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://enable-cors.org/){: new_window}.

## Utilización de kits de desarrollo de software (SDK)
{: #sdks}

Hay SDK disponibles para el servicio {{site.data.keyword.personalityinsightsshort}} para simplificar el desarrollo de aplicaciones. Hay SDK de {{site.data.keyword.ibmwatson}} disponibles para muchos lenguajes de programación y plataformas ampliamente utilizados.

-   Para obtener una lista completa de los SDK y los enlaces a los SDK de GitHub, consulte [Utilización de SDK](/docs/services/watson?topic=watson-using-sdks).
-   Para obtener información detallada sobre todos los métodos de los SDK de Node, Java, Python, Ruby y Go para el servicio {{site.data.keyword.personalityinsightsshort}}, consulte la [referencia de API ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/apidocs/personality-insights){: new_window}.

## Más información sobre el desarrollo de aplicaciones
{: #learn-overview}

Para obtener más información sobre cómo trabajar con los servicios de {{site.data.keyword.watson}} y {{site.data.keyword.cloud}}, consulte las secciones siguientes:

-   Para obtener una introducción de cómo trabajar con los servicios de {{site.data.keyword.watson}} y {{site.data.keyword.cloud_notm}}, consulte [Iniciación a {{site.data.keyword.watson}} y {{site.data.keyword.cloud_notm}}](/docs/services/watson?topic=watson-about).
-   Todas las instancias de servicio nuevas utilizan {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) para la autenticación. Las instancias de servicio más antiguas pueden seguir utilizando `{username}` y `{password}` de sus credenciales de servicio de Cloud Foundry existentes para la autenticación. Para obtener más información sobre cómo autenticarse para el servicio, consulte [actualización de servicio del 30 de octubre de 2018](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018) en las notas del release.
-   El registro de solicitudes está inhabilitado para el servicio {{site.data.keyword.personalityinsightsshort}}. El servicio no registra ni retiene datos de solicitudes y respuestas, independientemente de si se ha establecido la cabecera de la solicitud `X-Watson-Learning-Opt-Out`.
