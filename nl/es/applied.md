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

# El servicio en acción
{: #applied}

{{site.data.keyword.IBM_notm}} y otros investigadores han validado muchas hipótesis relacionadas con aplicaciones reales de las características de personalidad. Estos estudios han ayudado a impulsar el desarrollo del servicio de {{site.data.keyword.personalityinsightsshort}}. Sus hallazgos proporcionarán información sobre algunas de las muchas formas en que se puede aplicar el servicio a sus objetivos de negocio y de comunicaciones. Para obtener más información sobre la investigación que subyace en el servicio de {{site.data.keyword.personalityinsightsshort}}, consulte [La ciencia detrás del servicio](/docs/services/personality-insights/science.html).
{: shortdesc}

## Estudios de investigadores de IBM
{: #appliedIBM}

Los siguientes estudios realizados por investigadores de {{site.data.keyword.IBM_notm}} indican que la aplicación de los resultados del servicio puede producir resultados tangibles en varios dominios. Los estudios han contribuido directamente al desarrollo del servicio. La tabla incluye enlaces a secciones con más información sobre cada estudio.

<table>
  <caption>Tabla 3. Estudios de IBM</caption>
  <tr>
    <th style="text-align:left; width:25%">Estudio</th>
    <th style="text-align:center; width:25%">Sujetos</th>
    <th style="text-align:left; width:50%">Efecto de las características
    de personalidad</th>
  </tr>
  <tr>
    <td>
      <a href="#IBMrespond"><strong>Respuesta a los tuits</strong></a>
      <br/>(recopilación de información)
    </td>
    <td style="text-align:center">2000 usuarios de Twitter</td>
    <td>
      <strong>Más probable que respondan:</strong> Puntuación alta en las cinco grandes dimensiones
      y facetas de búsqueda de emociones, amigabilidad, nivel de actividad,
      sociabilidad, confianza, moralidad, extraversión y
      afabilidad<br/><br/>
      <strong>Menos probable que respondan:</strong> Puntuación alta en las cinco grandes facetas       de cautela y ansiedad
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMretweet"><strong>Retuiteo</strong></a>
      <br/>(difusión de información)
    </td>
    <td style="text-align:center">3500 usuarios de Twitter</td>
    <td>
      <strong>Más probable que retuiteen:</strong> Puntuación alta en las cinco grandes
      dimensiones y facetas de modestia, apertura y amigabilidad
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMtarget"><strong>Publicidad personalizada</strong></a>
      <br/>(publicidad no solicitada)
    </td>
    <td style="text-align:center">Más de 6000 usuarios de Twitter
    </td>
    <td>
      <strong>Respuesta más favorablemente:</strong> Puntuación alta en las cinco grandes dimensiones de apertura, y puntuación baja en las cinco grandes dimensiones de rango emocional
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMcampaign"><strong>Campañas de marketing</strong></a>
      <br/>(canje de cupones)
    </td>
    <td style="text-align:center">Miles de clientes minoristas</td>
    <td>
      <strong>Más probable que respondan:</strong> Puntuación alta en las cinco grandes facetas
      de orden, autodisciplina y prudencia, y puntuación baja
      en las cinco grandes facetas de falta de moderación
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMbrand"><strong>Preferencia de marca</strong></a>
      <br/>(afinidad de marca)
    </td>
    <td style="text-align:center">600 usuarios de Twitter</td>
    <td>
      <strong>Predictores de preferencia de marca:</strong> cinco grandes dimensiones
      y facetas de responsabilidad, conservación, superación personal
      y afabilidad; necesita amor y un ideal; y valor de hedonismo
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMmember"><strong>Satisfacción de los miembros</strong></a>
      <br/>(satisfacción de la comunidad)
    </td>
    <td style="text-align:center">Más de 3000 miembros de la comunidad</td>
    <td>
      <strong>Predictores de satisfacción de los miembros:</strong> características como
      la ira, ansiedad, trabajo, ocio, inhibición, aceptación, y uso del pronombre
      de primera persona
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMreading"><strong>Preferencia de lectura</strong></a>
      <br/>(interés del contenido)
    </td>
    <td style="text-align:center">Más de 200 participantes</td>
    <td>
      <strong>Interés en artículos ambientales:</strong> puntuación alta en el valor de
      la autotrascendencia<br/><br/>
      <strong>Interés en artículos relacionados con el trabajo:</strong> puntuación alta en el valor de superación personal
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMpreferences"><strong>Predicción de preferencias de consumo
      </strong></a><br/>(compra de consumidores)
    </td>
    <td style="text-align:center">Cientos de miles de registros de datos</td>
    <td>
      <strong>Predicción de las preferencias del consumidor:</strong> datos demográficos y características de personalidad
    </td>
  </tr>
</table>

### Respuesta a los tuits
{: #IBMrespond}

{{site.data.keyword.IBM_notm}} ha descubierto que las personas con características de personalidad específicas responden más fácilmente a las tareas de recogida de información. {{site.data.keyword.IBM_notm}} ha realizado recientemente un estudio de más de 2000 usuarios de Twitter para comprender los factores que influyen en la probabilidad de respuesta a tales tareas y para desarrollar modelos para predecir las respuestas a las preguntas ([Mahmud et al., 2013](/docs/services/personality-insights/references.html#mahmud2013), y [Mahmud et al., 2014](/docs/services/personality-insights/references.html#mahmud2014)).

{{site.data.keyword.IBM_notm}} ha entrenado el modelo utilizado en el estudio a partir de dos conjuntos de datos de preguntas y respuestas en los que se preguntó a los usuarios de Twitter preguntas relacionadas con su ubicación o relacionadas con el producto. Las preguntas dependen de si los usuarios informaron estar presentes en una ubicación o tener un producto. Como características en el modelo de predicción, {{site.data.keyword.IBM_notm}} incluyó el comportamiento social (por ejemplo, tasa de respuesta y actividad en Twitter pasadas), la predisposición (por ejemplo, por cuánto tiempo está inactivo el usuario), las características de categoría del diccionario de psicolingüística LIWC (Linguistic Inquiry and Word Count), y las cinco grandes dimensiones y facetas.

{{site.data.keyword.IBM_notm}} ha descubierto un conjunto de cinco grandes características de personalidad que son significativas a la hora de predecir la probabilidad de respuesta. Específicamente, {{site.data.keyword.IBM_notm}} ha descubierto que las personas que tienen un valor elevado en las dimensiones y facetas de búsqueda de emociones, amigabilidad, nivel de actividad, sociabilidad, confianza, moralidad, extraversión y simpatía es más probable que respondan a los tuits. Alternativamente, las personas que tienen una puntuación alta en las facetas de precaución y ansiedad es menos probable que respondan. Se ha descubierto que estos resultados son estadísticamente significativos (valor p &lt; 0,05).

### Retuiteo
{: #IBMretweet}

Asimismo, {{site.data.keyword.IBM_notm}} también ha descubierto que las personas con características de personalidad específicas responden en mayor número a las tareas de difusión de la información. {{site.data.keyword.IBM_notm}} ha realizado recientemente otro estudio entre más de 3500 usuarios de Twitter para comprender los factores que aumentan la probabilidad para retuitear información y para desarrollar modelos para predecir el comportamiento del reenvío de tuits ([Lee et al., 2014](/docs/services/personality-insights/references.html#lee2014)).

Como características en el modelo que se ha utilizado en el estudio, {{site.data.keyword.IBM_notm}} incluía actividad anterior de las redes sociales, información del perfil de las redes sociales, la preparación, el diccionario LIWC, y las cinco grandes dimensiones y facetas. El estudio ha descubierto que un conjunto de cinco grandes características es significativo a la hora de predecir la tendencia para retuitear. Por ejemplo, los resultados indican que las personas con puntuación elevada en las dimensiones y facetas de modestia, apertura y amigabilidad son más propensas a difundir información. Los resultados fueron estadísticamente significativos (valor p &lt; 0,05).

### Publicidad personalizada
{: #IBMtarget}

{{site.data.keyword.IBM_notm}} ha descubierto que las personas con características de personalidad específicas responden más favorablemente a la publicidad dirigida. Recientemente, {{site.data.keyword.IBM_notm}} ha creado un servicio de información de viajes basado en Twitter para probar la hipótesis de que determinados usuarios de Twitter responderían más favorablemente a publicidad no solicitada del servicio. La hipótesis predijo que tales usuarios serían más proclives a pulsar un enlace para un anuncio o a seguir una cuenta. {{site.data.keyword.IBM_notm}} ha realizado dos estudios basados en este caso de uso y los efectos hipotetizados de la personalidad ([Chen et al., 2015](/docs/services/personality-insights/references.html#chen2015)).

En un estudio, {{site.data.keyword.IBM_notm}} pidió a 133 usuarios de Twitter que informaran de su respuesta probable a un tuit que anunciara un servicio de información de viajes. {{site.data.keyword.IBM_notm}} a continuación utilizó cuestionarios tradicionales para medir las personalidades de los usuarios. En un estudio de campo, {{site.data.keyword.IBM_notm}} envió tuits anunciando el servicio a más de 5900 usuarios de viajes de Twitter. {{site.data.keyword.IBM_notm}} a continuación utilizó el servicio de {{site.data.keyword.personalityinsightsshort}} para deducir las características de personalidad de los usuarios de sus tuits pasados.

Los dos estudios dieron resultados coherentes: las personas con una puntuación alta en la dimensión de apertura y con una puntuación baja en la dimensión de rango emocional (neurosis) responden más favorablemente a los anuncios. Estos resultados son verdaderos a pesar de los distintos enfoques utilizados por los estudios para obtener las características de personalidad de los usuarios. Dirigirse al 10 por ciento principal de usuarios con una alta apertura y con un bajo rango emocional aumentó la tasa de pulsación de 6,8 a 11,3 por ciento y la tasa de seguimiento de 4,7 a 8,8 por ciento. Los resultados fueron estadísticamente significativos (valor p &lt; 0,05).

### Campañas de marketing
{: #IBMcampaign}

{{site.data.keyword.IBM_notm}} recientemente trabajó con un gran minorista para deducir características para miles de sus clientes implicados en campañas de marketing. El minorista envió cupones a sus clientes. Una respuesta positiva se definió como canjear cualquier cupón. Según la teoría de psicología, quienes obtienen una alta puntuación en las cinco grandes facetas de orden, autodisciplina y cautela y una puntuación baja en la faceta de falta de moderación son más propensos a canjear cupones.

{{site.data.keyword.IBM_notm}} ha validado la hipótesis utilizando datos del cliente y características de personalidad deducidas. {{site.data.keyword.IBM_notm}} primero segmentó la población de clientes en cuartiles basándose en características de personalidad individuales. Al utilizar puntuaciones de percentiles normalizadas para las características (con una escala de 1 a 100), {{site.data.keyword.IBM_notm}} ha utilizado la combinación lineal para calcular una puntuación combinada para cada cliente:

*Orden + autodisciplina + cautela + (100 - falta de moderación)*

{{site.data.keyword.IBM_notm}} a continuación comparó los resultados para los clientes en el cuartil más alto con los del cuartil más bajo, ignorando la mitad de la población. El estudio descubrió que las personas con las características hipotetizadas tienen el 40 por ciento de más probabilidad de responder a los cupones que las personas de la población aleatoria.

### Preferencia de marca
{: #IBMbrand}

{{site.data.keyword.IBM_notm}} realizó un estudio de más de 600 usuarios de Twitter para comprender si las cinco grandes características de personalidad de valores y necesidades pueden predecir las preferencias de los usuarios para distintas marcas (ya sea que les guste una marca o no). El estudio evaluó 22 marcas de seis categorías: coches de lujo, bebidas, comida rápida, minorista, champús y teléfonos inteligentes. {{site.data.keyword.IBM_notm}} estableció unos datos de campo para la preferencia de marca realizando una encuesta entre los usuarios.

El estudio descubrió que las características de personalidad pueden predecir la preferencia de marca con una exactitud del 65 por ciento. Concretamente, el estudio determinó que las cinco grandes dimensiones y facetas de responsabilidad, conservación, superación personal y simpatía, las necesidades de amor e ideal, y el valor hedonismo están entre las características más probables para predecir la preferencia de marca.

### Satisfacción de los miembros
{: #IBMmember}

{{site.data.keyword.IBM_notm}} ha realizado un estudio entre sus empleados que son miembros de las comunidades de trabajo en línea para investigar si el idioma que utilizan en las comunidades está relacionado con su nivel de satisfacción con las comunidades ([Matthews et al., 2015](/docs/services/personality-insights/references.html#matthews2015)). {{site.data.keyword.IBM_notm}} ha medido la satisfacción de la comunidad mediante autoencuestas. {{site.data.keyword.IBM_notm}} ha examinado 142 comunidades de trabajo; en función del tamaño de la comunidad, {{site.data.keyword.IBM_notm}} encuestó de 20 a 26 miembros de cada comunidad.

El estudio estableció que el uso del idioma en las comunidades, según el diccionario LIWC, se correlaciona con la satisfacción de los miembros. Concretamente, el estudio halló que las categorías LIWC como ira, ansiedad, trabajo, ocio, inhibición, aprobación y pronombre de primera persona son buenos predictores de satisfacción de los miembros. {{site.data.keyword.IBM_notm}} espera las características que se calculan desde el texto en una comunidad para correlacionar bien con la satisfacción de los miembros para la comunidad.

### Preferencia de lectura
{: #IBMreading}

{{site.data.keyword.IBM_notm}} realizó un estudio para comprender la relación entre los valores y los intereses de lectura ([Hsieh et al., 2014](/docs/services/personality-insights/references.html#hsieh2014)). {{site.data.keyword.IBM_notm}} realizó la hipótesis de que

1.  Las personas con un valor de autotrascendencia superior demostrarán un interés en la lectura de artículos sobre el entorno.
1.  Las personas con un valor de superación personal superior mostrarán un interés en la lectura de artículos sobre el trabajo.
1.  Las personas con un valor de hedonismo superior manifestarán un interés mayor en contenido sobre ocio.

{{site.data.keyword.IBM_notm}} reclutó a más de 200 participantes para el estudio desde el mercado de Amazon Mechanical Turk. Los participantes completaron una encuesta de valores y respondieron a preguntas sobre su nivel de interés en la lectura de distintos artículos.

El estudio ha validado las primeras dos hipótesis: los participantes con una puntuación superior en el valor de autotrascendencia demostraron un interés en la lectura de artículos sobre el entorno, y los participantes con una puntuación más alta en el valor de superación personal mostraron un interés en la lectura de artículos sobre trabajo. Estos resultados fueron estadísticamente significativos (valor p &lt; 0,05).

Sin embargo, el estudio observa una débil correlación entre el valor de hedonismo y un interés en la lectura de artículos de ocio. Este enlace débil puede indicar que las personas no consideran la lectura como una actividad hedonista, sin importar el tema del artículo.

### Predicción de preferencias de consumo
{: #IBMpreferences}

{{site.data.keyword.IBM_notm}} ha colaborado con [Acxiom ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://www.acxiom.com/){: new_window} para investigar si el retrato de la personalidad de un individuo puede mejorar la precisión predictiva de las preferencias de consumo de los individuos en comparación con las predicciones basadas únicamente en atributos demográficos. El estudio examinó 133 preferencias de consumo para alrededor de 785.000 individuos de EE.UU. La adición de características de Personality Insights a la demografía ha mejorado la precisión predictiva para 115 preferencias (86,5 por ciento), y para 23 de las preferencias, utilizando solo Personality Insights se proporciona una mejor precisión que utilizando solo la demografía.

El estudio se basó en dos tecnologías: los resultados del servicio de {{site.data.keyword.IBM_notm}} {{site.data.keyword.personalityinsightsshort}} y del producto Acxiom InfoBase, específicamente los elementos de datos de InfoBase Customer Enhancement&trade;. Acxiom es un proveedor líder del sector de datos demográficos para las necesidades de marketing de los clientes. Los datos demográficos de Acxiom, como edad, género, ingresos, tamaño familiar, rango de ingresos, etc., pueden ayudar a analizar y mejorar los datos de clientes para identificar oportunidades de venta y de retención, a llenar las lagunas en la información de contacto del cliente, a ayudar a analizar la información del cliente, y a identificar las perspectivas, entre otras cosas.

El estudio ha analizado 133 atributos de consumo de comportamiento basados en 22 características de {{site.data.keyword.personalityinsightsshort}} y en cuatro categorías demográficas (género, educación, ingresos del hogar, y edad). Los resultados muestran que 115 de las 133 preferencias de consumo mostraron mejor predicción predictiva cuando la demografía aumentó con las características de personalidad. Además, la falta de mejora en las 18 preferencias restantes puede deberse a la naturaleza de la comparación y a cómo se han calculado los datos. Los experimentos futuros intentarán comparaciones más complejas para ver si un enfoque distinto mejora la precisión.

Los resultados generales revelan que las características de {{site.data.keyword.personalityinsightsshort}} son útiles para predecir varias preferencias de consumo. El uso de la demografía y de las características de personalidad genera mejor precisión predictiva. Pero {{site.data.keyword.personalityinsightsshort}} solo es una buena alternativa cuando demografía no está disponible.

Para obtener más información sobre el estudio, consulte <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Improving-Consumption-Preferences-Accuracy.pdf" download="Improving-Consumption-Preferences-Accuracy.pdf">Improving-Consumption-Preferences-Accuracy.pdf <img src="../../icons/launch-glyph.svg" alt="Icono de enlace externo" title="Icono de enlace externo" class="style-scope doc-content"></a>. Para obtener más información sobre el modelo de preferencias de consumo utilizado en el estudio, consulte [Liu et al. (2016)](/docs/services/personality-insights/references.html#liu2016).

## Estudios de otros investigadores
{: #appliedOthers}

Muchos estudios realizados por investigadores de fuera de {{site.data.keyword.IBM_notm}} indican que la personalidad se correlaciona con y puede predecir varios resultados. Las siguientes secciones describen estos estudios, que corroboran y aumentan la búsqueda descrita en la sección anterior.

### Preferencias del consumidor
{: #otherConsumer}

-   [Hirsh et al. (2012)](/docs/services/personality-insights/references.html#hirsh2012) ha encuestado a personas sobre varios mensajes de marketing. Descubrieron que las personas responden más positivamente a los mensajes adaptados a su personalidad.
-   [Chen (2011)](/docs/services/personality-insights/references.html#chen2011) descubrió que en el contexto del marketing en línea, las personas con una gran apertura son más curiosos intelectualmente y abiertos a nuevas ideas. Tales personas son, por lo tanto, más proclives a intentar cosas nuevas.
-   [Westfall (1962)](/docs/services/personality-insights/references.html#westfall1962) descubrió que existen diferencias de personalidad entre los propietarios de coches convertibles y de coches estándares o compactos. Los consumidores con una alta puntuación en la dimensión de simpatía y en la faceta de orden de la dimensión de responsabilidad prefieren coches tradicionales. Los consumidores con una alta puntuación en la dimensión de apertura, por otro lado, podrían convertir un coche convertible en su primera elección.
-   [Choo and Mokhtarian (2002)](/docs/services/personality-insights/references.html#choo2002) examinaron la relación entre la elección del tipo de vehículo y factores como personalidad, estilo de vida, actitud y demografía. Descubrieron que las personas con una alta puntuación en las facetas de osadía, búsqueda de emociones y desafiante a la autoridad podrían preferir coches de gran rendimiento. Sin embargo, a las personas con una alta puntuación en la dimensión de simpatía podrían no gustarle los coches potentes.
-   [Kassarjian (1971)](/docs/services/personality-insights/references.html#kassarjian1971) ha descubierto que los propietarios de coches normalmente tienden a percibir los tipos de coches que compran como extensiones de su personalidad. [Conciencia ambiental](#otherEnvironment) describe cómo puede influir la personalidad de un individuo en su preferencia de vehículos de bajas emisiones.
-   [Myszkowski and Storme (2012)](/docs/services/personality-insights/references.html#myszkowski2012) han descubierto que la apertura predice significativamente la tendencia de los individuos para preferir y responder a productos bien diseñados. Su estudio sugiere que las personas con una apertura *baja* tienden a responder más intensamente al aspecto de un producto, amplificando las opciones del producto gestionadas por el diseño. Por el contrario, las personas con una apertura *alta* tienden a centrarse más en otros aspectos del producto, lo que les lleva a características estéticas de omisión.
-   [Lin (2002)](/docs/services/personality-insights/references.html#lin2002) y [Sarli and Tat (2011)](/docs/services/personality-insights/references.html#sarli2011) han informado de que las características de personalidad afectan a la preferencia de marca.

### Preferencias personales
{: #otherPersonal}

-   [Hu and Pu (2011)](/docs/services/personality-insights/references.html#hu2011) han descubierto que, en el dominio de la música, las recomendaciones tienen más éxito cuando aprovechan las correlaciones entre la personalidad de la gente y sus preferencias musicales.
-   [Chamorro-Premuzic and Furnham (2007)](/docs/services/personality-insights/references.html#chamorro2007) también han informado de que las diferencias individuales en la personalidad y en la capacidad cognitiva pueden determinar cómo experimentan la música las personas. [Rentfrow and Gosling (2003)](/docs/services/personality-insights/references.html#rentfrow2003) informaron de hallazgos similares en un estudio anterior.
-   [Golbeck and Norris (2013)](/docs/services/personality-insights/references.html#golbeck2013) han encontrado correlaciones entre la personalidad y las preferencias de películas entre los usuarios de Netflix&trade;.

### Hábitos de gasto
{: #otherSpending}

-   [Pirog and Roberts (2007)](/docs/services/personality-insights/references.html#pirog2007) han revelado la relación entre los hábitos de gasto y la personalidad. Se centran en el "mal uso" (o "abuso") de las tarjetas de crédito entre los estudiantes universitarios. Han descubierto que los estudiantes con una alta puntuación en responsabilidad tienden a utilizar tarjetas de débito o efectivo y no tienen a abusar de las tarjetas de crédito. Por el contrario, una neurosis alta (rango emocional) es probable que esté asociada con un uso excesivo de tarjetas de crédito.

### Perfiles de riesgo
{: #otherRisk}

-   [Lauriola and Levin (2001)](/docs/services/personality-insights/references.html#lauriola2001) ha demostrado que la personalidad influencia la toma de decisiones arriesgadas de las personas en inversiones financieras. Concluyeron que las personas con una puntuación alta en apertura a experiencias tienden a realizar inversiones arriesgadas. Sin embargo, la neurosis (rango emocional) puede convertir a las personas en menos dispuestas a asumir esos riesgos.
-   [Nicholson et al. (2001)](/docs/services/personality-insights/references.html#nicholson2001) han desarrollado más la correlación entre las cinco grandes características y perfiles de riesgo. Sus descubrimientos revelan que la simpatía y la responsabilidad reducen la disposición de las personas a tomar riesgos, en general. En contraste, las personas con una puntuación alta en extraversión son más proclives a asumir decisiones arriesgadas.
-   [Tok (2011)](/docs/services/personality-insights/references.html#tok2011) identificó la relación entre las cinco grandes características de personalidad y la participación en deportes de aventura de riesgo como el esquí, el ciclismo de montaña, vuelo, vuelo sin motor, parasailing, y submarinismo. Cuatro de las cinco grandes características influyen directamente en la participación en deportes de riesgo: las puntuaciones altas en extraversión, apertura, y neurosis (rango emocional) aumentan la probabilidad de participación en estos deportes; una puntuación alta en meticuloso reduce la probabilidad de participación.
-   [Hymbaugh and Garrett (1974)](/docs/services/personality-insights/references.html#hymbaugh1974) estudiaron las características de personalidad de los paracaidistas. Descubrieron que los paracaidistas normalmente tienen mayor búsqueda de emociones y osadía que la población en general.

### Rendimiento profesional
{: #otherProfessional}

-  [Barrick and Mount (1991)](/docs/services/personality-insights/references.html#barrick1991) exploraron la relación de las cinco grandes dimensiones de personalidad con el rendimiento de trabajo. Descubrieron que las dimensiones de personalidad como la responsabilidad están relacionadas con el rendimiento de trabajo para todos los grupos de trabajo que han estudiado (profesionales, gestores, ventas, policías, calificados y semicalificados).
-   [Hurtz and Donovan (2000)](/docs/services/personality-insights/references.html#hurtz2000) han informado de que la responsabilidad es la característica de personalidad más predictiva del rendimiento del trabajo.
-   [Lim and Ployhart (2004)](/docs/services/personality-insights/references.html#lim2004) han descubierto que la extraversión está positivamente correlacionada con las capacidades de liderazgo.
-   [Judge et al. (2002)](/docs/services/personality-insights/references.html#judge2002) han hallado que las personas extravertidas están más satisfechas en el trabajo; el trabajo les da una oportunidad para experimentar un nivel óptimo de excitación. Por el contrario, las personas introvertidas están menos satisfechas en el trabajo debido a demasiada estimulación.
-   [van Vianen et al. (2012)](/docs/services/personality-insights/references.html#vanvianen2012) han informado de diferencias individuales en la adaptabilidad y sus causas, correlaciones y consecuencias. Descubrieron que la responsabilidad, la extraversión y la apertura se correlacionan positivamente con la adaptabilidad de la carrera.

### Rendimiento académico
{: #otherAcademic}

-   [Chamorro-Premuzic and Furnham (2003)](/docs/services/personality-insights/references.html#chamorro2003) informaron de un estudio longitudinal en el que encontraron que las características de personalidad afectan al rendimiento académico. Específicamente, encontraron que la neurosis (rango emocional) puede afectar al rendimiento académico y que la responsabilidad podría llevar a un logro académico superior.
-   [Komarraju and Karau (2005)](/docs/services/personality-insights/references.html#komarraju2005) descubrieron que algunas características de personalidad producen un impacto en el comportamiento individual con respecto al aprendizaje de superación personal. El estudio revela que una apertura y responsabilidad altas a menudo dan lugar a un mayor interés en el aprendizaje de superación personal y que una neurosis mayor (rango emocional) disminuye la motivación para tal aprendizaje.

### Relaciones profesionales
{: #otherProRelations}

-   [Flynn and Smith (2007)](/docs/services/personality-insights/references.html#flynn2007) han descubierto que la personalidad influye en las preferencias de interacción entre profesionales y clientes. Por ejemplo, los pacientes con un alto grado de responsabilidad y de apertura prefieren estar activamente implicados a la hora de decidir el curso del tratamiento. Los pacientes con niveles altos de simpatía o de rango emocional (neurosis) prefieren médicos que tomen la iniciativa a la hora de decidir sobre cuestiones de salud importantes.
-   [Duberstein et al. (2007)](/docs/services/personality-insights/references.html#duberstein2007) han informado de forma similar que las personalidades de los médicos afectan al nivel de satisfacción de sus pacientes. Por ejemplo, los pacientes se mostraron más satisfechos con médicos que tuvieran una puntuación relativamente alta en apertura y una media en responsabilidad.

### Relaciones personales
{: #otherPerRelations}

-   [Botwin et al. (1997)](/docs/services/personality-insights/references.html#botwin1997) han descubierto que la personalidad afecta a las relaciones románticas. Las características de personalidad de una pareja predice de forma significativa el descontento conyugal, especialmente cuando la pareja tiene una puntuación menor en simpatía, rango emocional y apertura de la deseada.

### Estado
{: #otherHealth}

-   [Turiano et al. (2012)](/docs/services/personality-insights/references.html#turiano2012) han creado un estudio longitudinal durante un lapso de tiempo de 10 años en el que han descubierto que las cinco grandes características predecían resultados relacionados con la salud. Por ejemplo, todas las características, excepto la apertura, predecían estados físicos autoevaluados, y todas las características, excepto la simpatía, predecían el número de días laborables limitado debido a la salud física.
-   [Masui et al. (2006)](/docs/services/personality-insights/references.html#masui2006) han descubierto que las puntuaciones altas en las características de personalidad específicas de responsabilidad, extraversión y apertura están asociadas con la longevidad. Otros investigadores también han descubierto una relación entre las cinco grandes características de personalidad y la esperanza de vida.
-   [Roberts et al. (2007)](/docs/services/personality-insights/references.html#roberts2007) han descubierto que las características de personalidad específicas predicen resultados vitales importantes, como mortalidad, divorcio y éxito en el trabajo.

### Dieta y ejercicio
{: #otherDiet}

-   [Shepherd and Sparks (1994)](/docs/services/personality-insights/references.html#shepherd1994) han desarrollado la relación entre personalidad y elección de alimentos. Su estudio revela que las personas con altas puntuaciones en rango emocional (neurosis), especialmente en la faceta de falta de moderación, tienden a consumir alimentos con mucha grasa.
-   [Elfhag and Morey (2008)](/docs/services/personality-insights/references.html#elfhag2008) han revelado que la responsabilidad está relacionada de forma positiva con una preferencia por los alimentos con poca grasa. Concretamente, las facetas de autodisciplina y de obediencia de la dimensión de responsabilidad influencian de forma positiva el consumo de alimentos con poca grasa y (ya que la gestión del peso está íntimamente relacionada con la elección de alimentos) el control del peso normal.
-   [Heaven et al. (2001)](/docs/services/personality-insights/references.html#heaven2001) hallaron que el consumo de alimentos sanos está relacionado con dos de las cinco grandes dimensiones. Las personas con alta neurosis (rango emocional) son normalmente menos propensos a elegir alimentos sanos, mientras que las personas con una alta responsabilidad prefieren alimentos sanos. El documento también cita varias facetas que se relacionan sutilmente con la elección de alimentos: intereses artísticos (de la dimensión de apertura) y autodisciplina (de la dimensión de responsabilidad) se correlacionan positivamente con un mayor consumo de alimentos sanos; de lo contrario, ser susceptible al estrés tiene una correlación negativa en cierto grado con el consumo de alimentos sanos.
-   [Lusk (2012)](/docs/services/personality-insights/references.html#lusk2012) ha descubierto que los amantes de la comida tienen una puntuación alta en la apertura a la experiencia. La apertura puede motivar a las personas a probar comidas distintas y ayudarles a convertirse en expertos de los alimentos.
-   [Courneya and Hellsten (1998)](/docs/services/personality-insights/references.html#courneya1998) han hallado que la personalidad influencia la tendencia de los individuos a la hora de aspirar a hábitos asociados con un estilo de vida sano, incluido el ejercicio físico. La extraversión y la responsabilidad se correlacionan positivamente con más frecuencia de ejercicio físico, mientras que la neurosis (rango emocional) puede influir negativamente con la frecuencia de ejercicio.

### Cenar fuera
{: #otherDining}

-   [Kim et al. (2010)](/docs/services/personality-insights/references.html#kim2010) han probado que la apertura a la experiencia se correlaciona positivamente con más frecuencia de cenas fuera. Las personas que tienen una puntuación baja en la apertura normalmente cenan fuera con menos frecuencia.
-   [van Trijp and Steenkamp (1992)](/docs/services/personality-insights/references.html#vantrijp1992) han descubierto que cenar fuera se correlaciona con la faceta de búsqueda de emociones (búsqueda de sensaciones) de la dimensión de extraversión.

### Conciencia ambiental
{: #otherEnvironment}

-   [Griskevicius et al. (2010)](/docs/services/personality-insights/references.html#griskevicius2010) han descubierto que la personalidad de una persona influencia su interés en cuestiones ambientales. Han estudiado la relación entre personalidad y comportamiento proambiental, como por ejemplo el uso de vehículos de bajas emisiones y el interés por la vida ecológica, la jardinería, el reciclaje, etc. Para la mayoría de las personas, unos niveles más elevados de simpatía, apertura y responsabilidad están asociados con una mayor inclinación por el comportamiento proambiental.
-   [Fraj and Martinez (2006)](/docs/services/personality-insights/references.html#fraj2006) han descubierto que la personalidad influencia la decisión de comprar productos respetuosos con el medio ambiente. Las personas caracterizadas por características de personalidad como la extraversión, la simpatía y la responsabilidad son más proclives a comprar tales productos.

### Servicio comunitario
{: #otherCommunity}

-   [Penner et al. (2005)](/docs/services/personality-insights/references.html#penner2005) han hallado que la personalidad de un individuo afecta a su compromiso al servicio comunitario. En un documento de revisión, los autores resumen los diversos factores de personalidad que influyen el comportamiento prosocial. Descubrieron que la extraversión y la simpatía tienen influencias positivas a la hora de interactuar en el servicio comunitario. En particular, las facetas de altruismo y cooperación de la dimensión de simpatía pueden tener el máximo impacto, mientras que la faceta de sociabilidad de la dimensión de extraversión tiene una correlación positiva más sutil para el servicio comunitario.

### Religión y espiritualidad
{: #otherReligion}

-   [Adorno et al. (1950)](/docs/services/personality-insights/references.html#adorno1950), en su libro clásico *La personalidad autoritaria*, informa de una posible correlación entre las características de personalidad y la religión. Sugieren que las personas que tienen una alta puntuación en simpatía son más religiosas, mientras que aquellas que tienen una puntuación alta en desafiantes a la autoridad están menos motivadas para participar en prácticas religiosas y espirituales.
