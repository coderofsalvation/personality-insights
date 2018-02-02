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

# Visión general para desarrolladores
{: #overviewDevelopers}

Puede utilizar el servicio de {{site.data.keyword.personalityinsightsshort}} mediante una API REST (Representational State Transfer) HTTP. Varios SDK (Software Development Kits) también están disponibles para simplificar el desarrollo de aplicaciones en varios idiomas y entornos.
{: shortdesc}

## Programación con el servicio
{: #programming}

Para producir un perfil de personalidad, envíe texto al método `POST /v3/profile` HTTP del servicio. Puede enviar texto sin formato, HTML, o contenido JSON. El servicio puede devolver su análisis en formato JSON o CSV

Para cada característica de personalidad, el servicio informa de un *percentil*, que es una puntuación normalizada que describe hasta qué punto la escritura del autor exhibe una característica dentro de una población de ejemplo. Si se solicita, el servicio también devuelve una *puntuación en bruto*, que es un valor absoluto no normalizado para una población de ejemplo. Si la entrada es una indicación de fecha y hora, el servicio proporciona un resumen de los hábitos de escritura del autor con respecto al día de la semana y a la hora del día. Y si se solicita, el servicio también devuelve una puntuación parecida para cada una de sus preferencias de consumo disponibles.

Para obtener más información sobre cómo utilizar el servicio, consulte:

-   [Solicitud de un perfil](/docs/services/personality-insights/input.html)
-   [Comprensión de un perfil JSON](/docs/services/personality-insights/output.html)
-   [Comprensión de un perfil CSV](/docs/services/personality-insights/output-csv.html)

### Visualización de un perfil
{: #visualize}

El servicio proporciona una recopilación de archivos JavaScript que permiten la visualización gráfica de un perfil. Los scripts facilitan el uso del servicio con redes de distribución en caché y contenido. Se basan en JavaScript, jQuery, HTML y SVG con la biblioteca de Documentos controlados por datos (`D3.js`) para mostrar los resultados. Para obtener información sobre estos archivos del lado del cliente, consulte las aplicaciones de ejemplo citadas en [Utilización de Software Development Kits](#sdks); para obtener más información sobre `D3.js`, consulte [d3js.org ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://d3js.org/){: new_window}.

### Soporte de CORS
{: #CORS}

El servicio da soporte a CORS (Cross-Origin Resource Sharing) para permitir que los clientes basados en navegador realicen solicitudes asíncronas directamente en el servicio desde los scripts frontales. CORS permite a los clientes solicitar recursos de un dominio que está fuera del dominio desde el que se ha originado la solicitud; permite a las aplicaciones web solucionar la política de seguridad de mismo origen, que de lo contrario impide tales solicitudes. Para obtener más información, consulte [enable-cors.org ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://enable-cors.org/){: new_window}.

## Utilización de Software Development Kits
{: #sdks}

El servicio de {{site.data.keyword.personalityinsightsshort}} da soporte a un número de SDK para el desarrollo de aplicaciones simplificado. Los SDK están disponibles para muchos lenguajes de programación y plataformas populares, como Node.js, Java, Python, y Apple&reg; iOS. Para obtener una lista completa de SDK e información sobre cómo utilizarlos, consulte [SDK de {{site.data.keyword.watson}}](/docs/services/watson/getting-started-sdks.html). Todos los SDK están disponibles en el [espacio de nombres de watson-developer-cloud ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/watson-developer-cloud){: new_window} en GitHub.

El servicio también ofrece las siguientes aplicaciones de ejemplo para ayudarle a empezar:

-   Puede acceder a una aplicación que utiliza el SDK Node.js en el [repositorio personality-insights-nodejs ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window}.
-   Puede acceder a una aplicación que utiliza el SDK de Java en el [repositorio personality-insights-java ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/watson-developer-cloud/personality-insights-java){: new_window}.

Para el desarrollo móvil, consulte el [SDK de {{site.data.keyword.watson}} Developer Cloud Swift ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://github.com/watson-developer-cloud/swift-sdk){: new_window}. Todos los SDK dan soporte a la autenticación utilizando las credenciales de servicio o una señal de autenticación.

## Más información sobre el desarrollo de aplicaciones
{: #learn}

El servicio de {{site.data.keyword.personalityinsightsshort}} da soporte a dos modelos de programación típicos: *Interacción directa*, en el que el cliente se comunica con el servicio directamente; y *transmisión mediante un proxy*, en el que el cliente y el servicio intercambian todos los datos (solicitudes y resultados) mediante una aplicación proxy que reside en {{site.data.keyword.Bluemix_short}}.

Para obtener más información sobre cómo trabajar con los servicios de {{site.data.keyword.watson}} Developer Cloud y {{site.data.keyword.Bluemix_notm}}, consulte lo siguiente:

-   Para obtener una introducción a cómo trabajar con los servicios de {{site.data.keyword.watson}} y {{site.data.keyword.Bluemix_notm}}, consulte [Iniciación a {{site.data.keyword.watson}} y {{site.data.keyword.Bluemix_notm}}](/docs/services/watson/index.html).
-   Para obtener una introducción independiente del lenguaje para desarrollar aplicaciones de servicios de {{site.data.keyword.watson}} en {{site.data.keyword.Bluemix_notm}}, consulte [enfoques de desarrollo de {{site.data.keyword.Bluemix_notm}}](/docs/services/watson/getting-started-bluemix.html).
-   Para obtener información sobre los dos modelos de programación disponibles para desarrollar aplicaciones de {{site.data.keyword.watson}}, consulte [Programación de modelos para los servicios de {{site.data.keyword.watson}}](/docs/services/watson/getting-started-develop.html):
    -   Con la transmisión a través de un proxy, el cliente se basa en un servidor proxy que reside en {{site.data.keyword.Bluemix_notm}} para comunicarse con el servicio; pasa todas las solicitudes a través de la aplicación proxy. La transmisión de solicitudes mediante un proxy se basa solo en las credenciales de servicio para autenticarse con el servicio; consulte [Credenciales de servicio para servicios de {{site.data.keyword.watson}}](/docs/services/watson/getting-started-credentials.html).
    -   Con la interacción directa, el cliente utiliza la aplicación de proxy en {{site.data.keyword.Bluemix_notm}} solo para obtener una señal de autenticación para el servicio, tras lo cual se comunica directamente con el servicio. La interacción directa utiliza las credenciales de servicio solo para obtener una señal; consulte [Señales de autenticación](/docs/services/watson/getting-started-tokens.html).
-   Para obtener información sobre el control del registro de solicitudes predeterminadas que se realiza para todos los servicios de {{site.data.keyword.watson}}, consulte [Control de registros de solicitudes para los servicios de {{site.data.keyword.watson}}](/docs/services/watson/getting-started-logging.html).
