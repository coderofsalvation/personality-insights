---

copyright:
  years: 2015, 2017
lastupdated: "2017-08-13"

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

# Orientación de uso
{: #guidance}

Los usuarios están aplicando el servicio de {{site.data.keyword.personalityinsightsshort}} a un creciente número de casos de uso. Se han aplicado el servicio para ofrecer recomendaciones de producto personalizadas a los clientes a través de los quioscos de tienda. Han estudiado y analizado las diferencias en la personalidad de los presidentes estadounidenses como se deduce de sus Discursos del estado de la unión. Y han integrado el servicio con otro producto en la cartera de {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}}, {{site.data.keyword.watson}} Explorer, para demostrar cómo puede ofrecer un asesor de inversión opciones adecuadas basadas en los retratos de personalidad de los inversores. (Para obtener más información, consulte [Casos de uso](/docs/services/personality-insights/usecases.html)).
{: shortdesc}

Durante el desarrollo de estos y otros casos de uso futuros, {{site.data.keyword.IBM_notm}} ha tenido conversaciones con bancos, proveedores de salud, empresas de gestión de la experiencia del cliente y agencias federales. Estas conversaciones suelen generar preguntas sobre casos de uso aplicables. Algunas de estas preguntas y enlaces a sus respuestas están disponibles como preguntas frecuentes. A continuación se muestra la perspectiva de {{site.data.keyword.IBM_notm}} sobre varias preguntas adicionales:

-   ¿Qué tipo de texto es mejor para deducir la personalidad de una persona? ¿El texto se refleja en la naturaleza? Si es así, ¿cómo de reflexivo y cómo se mide la reflexión? Consulte [¿Qué tipo de texto es óptimo para deducir la personalidad?](#optimal)
-   ¿Cómo se interpreta un texto escrito por una persona sobre otra persona? ¿Se puede deducir la personalidad de un autor de las obras de ficción del autor? ¿Puede combinarse el texto escrito por varias personas para obtener un retrato de personalidad? Consulte [Cómo interpretar los resultados de diferentes tipos de texto](#interpreting).
-   ¿Se pueden deducir los retratos de personalidad de texto que se genera mediante transcripción o servicios de traducción? Consulte [Cómo deducir la personalidad de texto generado](#inferring).
-   ¿Pueden aplicarse los retratos de personalidad a aplicaciones como el emparejamiento de personas, la supervisión y la predicción de salud mental, y la supervisión de elementos radicales y criminales mediante las redes sociales? Consulte [Cómo utilizar los retratos de personalidad para aplicaciones específicas](#applying).
-   ¿Evoluciona la personalidad de los individuos a medida que envejecen? Consulte [¿Cambia la personalidad de una persona a lo largo del tiempo?](#evolve)

## ¿Qué tipo de texto es óptimo para deducir la personalidad?
{: #optimal}

¿Qué tipo de texto es ideal para deducir la personalidad? ¿Tiene que ser el texto reflexivo, autorreflexivo, formal, o informal? ¿Cómo se miden las palabras que se utilizan en la vida diaria? ¿Se reflejan tales palabras en la naturaleza? Las respuestas a estas preguntas pueden ayudarle a seleccionar la entrada más adecuada para aplicar el servicio de forma más eficaz.

El trabajo de {{site.data.keyword.IBM_notm}} en el servicio de {{site.data.keyword.personalityinsightsshort}} se basa en la premisa fundamental de que las palabras que se utilizan en la vida diaria revelan la personalidad de alguien ([Pennebaker et al., 2001](/docs/services/personality-insights/references.html#pennebaker2001), y [Pennebaker et al., 2007](/docs/services/personality-insights/references.html#pennebaker2007)). El servicio puede analizar palabras escritas por individuos sobre sí mismos o sobre cualquier tema, pero el individuo debe elegir y escribir las palabras para el servicio para generar un retrato de personalidad preciso.

{{site.data.keyword.IBM_notm}} cree que, idealmente, el texto que se utiliza para deducir la personalidad de un individuo debe ser reflexivo. El escrito reflexivo expone las experiencias personales y las respuestas del autor; requiere que el autor piense en cierta medida las palabras elegidas. Por ejemplo, el texto puede incluir las opiniones, las actitudes, los sentimientos y las observaciones del escritor sobre alguien o algo, o puede expresar lo que le gusta y lo que no le gusta al escritor, pero debe reflejar la selección de palabras del escritor.

{{site.data.keyword.IBM_notm}} no ha encontrado referencias explícitas en la bibliografía psicolingüística sobre la necesidad de reflexión en el texto que se utiliza para deducir la personalidad. Sin embargo, {{site.data.keyword.IBM_notm}} observó que algunos estudios utilizan palabras de texto recopilado en un entorno de laboratorio en el que se pide a las personas que escriban redacciones cortas sobre temas específicos. Este tipo de escritura exige implícitamente una cierta reflexión. Otros estudios utilizaron texto de muestra natural como blogs sobre diversos temas, tuits en Twitter, correo electrónico, o incluso la comunicación que se extrae del juego *World of Warcraft*. Todos estos estudios presuponen que las palabras utilizadas en la vida diaria revelan la personalidad porque tienden a reflejar los pensamientos del escritor.

Otros estudios muestran que la escritura emocional, la escritura con control, los blogs y las transcripciones de voz se adaptan a la perfección para deducir la personalidad. Los artículos científicos, por el contrario, solo se ajustan marginalmente para deducir la personalidad. Además, la bibliografía indica que llegar a una medida precisa de personalidad es más complicado mediante un texto que

-   Carece de autenticidad, como sarcasmo, ironía, edición intensa, o varios autores
-   Incluye errores ortográficos, palabras técnicas, significados alternativos para palabras, negación, y frases en lugar de solo palabras
-   Incluye grupos de comparación inapropiados, como escritura profesional frente a personal y escritura técnica frente a emocional

## Cómo interpretar los resultados de diferentes tipos de texto
{: #interpreting}

El tipo de texto que debe analizarse puede tener un efecto significativo en la calidad de los resultados del servicio de {{site.data.keyword.personalityinsightsshort}}. Las secciones siguientes tratan sobre cómo interpretar los resultados obtenidos de distintas fuentes:

-   [Cómo interpretar los resultados de texto escrito sobre otros](#writingaboutothers)
-   [Cómo interpretar los resultados de obras de ficción](#fictionalworks)
-   [Cómo interpretar los resultados de texto escrito por varias personas](#multipleindividuals)

### Cómo interpretar los resultados de texto escrito sobre otros
{: #writingaboutothers}

Para deducir de forma fiable la personalidad de un individuo, ¿el texto tiene que estar escrito *por* la persona o puede estar escrito *sobre* la persona por otra persona? Cuando una persona escribe sobre otra persona, ¿qué personalidad se deduce del texto?

La intuición de {{site.data.keyword.IBM_notm}} en que la escritura siempre refleja la personalidad del autor, independientemente del asunto. Por ejemplo, si una persona A escribe texto sobre una persona B, un análisis del texto deduce la personalidad de la persona A. Aunque la persona A esté escribiendo sobre la persona B, es la persona A la que está eligiendo las palabras para expresar cosas sobre la persona B. Sin embargo, {{site.data.keyword.IBM_notm}} no ha realizado estudios para probar explícitamente este caso de ejemplo.

### Cómo interpretar los resultados de obras de ficción
{: #fictionalworks}

{{site.data.keyword.IBM_notm}} no recomienda deducir la personalidad de un autor de su obra de ficción. Cuando escriben ficción, los autores describen cada personaje de forma deliberadamente diferente, construyen diálogo para reflejar las personalidades de sus personajes, y predefinen la personalidad de cada personaje en sus mentes.

Es cuestionable el uso de texto que pretende reflejar la personalidad de un personaje ficticio personificado para deducir la personalidad del creador de dicho personaje. Aunque cada autor tiene un estilo único, los personajes siguen decididamente preconfigurados. La personalidad de un autor puede, sin embargo, deducirse de los ensayos de no ficción del autor, de transcripciones de entrevistas, o de otros trabajos como introducciones, prólogos, agradecimientos o dedicatorias.

### Cómo interpretar los resultados de texto escrito por varias personas
{: #multipleindividuals}

Un caso de uso común del servicio de {{site.data.keyword.personalityinsightsshort}} es analizar a los seguidores de una marca o de una empresa. Los seguidores se definen como personas que siguen a una empresa en Twitter o en una página pública de Facebook. En este caso de ejemplo, el objetivo es obtener la personalidad general de los seguidores de una empresa. Un método preferido es recopilar suficiente texto escrito por los miembros de un grupo para calcular la personalidad de cada miembro individual, y luego agrupar las personalidades en grupos distintos. Estos grupos representan las personas con características de personalidad distintivas que siguen a la empresa.

Si no hay disponible texto suficiente de los miembros de un grupo, el texto que escriben muchos miembros se puede combinar y analizar para crear un retrato de personalidad promedio o compuesto para el grupo en su conjunto. Este enfoque puede dar una indicación de las cualidades dominantes del grupo, pero la precisión de este método disminuye con la diversidad de la población. Tenga cuidado al interpretar los retratos que se obtienen de agregar el texto de varias personas. El trabajo de {{site.data.keyword.IBM_notm}} en este ámbito todavía está en sus etapas iniciales; {{site.data.keyword.IBM_notm}} informará de sus conclusiones a medida que obtenga resultados convincentes.

## Cómo deducir la personalidad de texto generado
{: #inferring}

El análisis de texto generado por servicios de transcripción o de traducción puede afectar a la fiabilidad de los resultados del servicio de {{site.data.keyword.personalityinsightsshort}}. Las siguientes secciones tratan sobre los efectos de deducir la personalidad de texto generado:

-   [Cómo deducir la personalidad de transcripciones de voz](#transcription)
-   [Cómo deducir la personalidad de texto traducido](#translation)

### Cómo deducir la personalidad de transcripciones de voz
{: #transcription}

Los motores de transcripción de voz, como por ejemplo el servicio de {{site.data.keyword.IBM_notm}} {{site.data.keyword.speechtotextshort}}, generan texto escrito de palabras habladas. Dado que los distintos motores de transcripción tienen distintos rangos de precisión, los clientes que transcriban voz a texto para utilizarlo como entrada para el servicio de {{site.data.keyword.personalityinsightsshort}} deben ser conscientes de que los resultados varían mucho dependiendo del rendimiento del motor. Específicamente, {{site.data.keyword.IBM_notm}} aconseja a los clientes y a los socios comerciales que determinen la calidad de la transcripción frente a dos tipos de errores:

-   *Descartar:* Una palabra hablada se omite de la transcripción.
-   *Sustitución:* Una palabra hablada se transcribe de forma incorrecta.

La sustitución puede ser un problema más serio porque puede introducir palabras que no se dijeron pero que coinciden con las palabras utilizadas para determinar la personalidad. Antes de utilizar texto transcrito, considere la posibilidad de corregir manualmente el texto de un corpus de prueba y contar los errores que encuentre. A continuación, compare los resultados del texto generado automáticamente con la versión corregida manualmente para determinar la variación de resultados debida a errores de transcripción.

### Cómo deducir la personalidad de texto traducido
{: #translation}

Los servicios de traducción de idiomas traducen texto escrito en otro idioma a otro idioma. Al igual que con la transcripción de voz, surge la pregunta de si el texto traducido se puede utilizar como entrada para el servicio de {{site.data.keyword.personalityinsightsshort}}. {{site.data.keyword.IBM_notm}} no recomienda utilizar texto obtenido de servicios de traducción como entrada para el servicio de {{site.data.keyword.personalityinsightsshort}}. Dependiendo del servicio de traducción, los resultados de la traducción y de la deducción de personalidad pueden variar ampliamente. Las palabras, sus sentidos y las particularidades culturales tienden a perderse en la traducción, lo que da lugar a resultados no válidos.

{{site.data.keyword.IBM_notm}} recomienda utilizar como entrada solo texto escrito en idiomas en los que esté habilitado el servicio de {{site.data.keyword.personalityinsightsshort}}. Las versiones habilitadas para el idioma del servicio analizan el texto de entrada en su idioma nativo, utilizan diccionarios de idioma nativo para identificar características de personalidad, y utilizan modelos calibrados para el idioma nativo para producir resultados estadísticos. Si debe analizar texto traducido, {{site.data.keyword.IBM_notm}} le recomienda que primero traduzca manualmente algunos ejemplos de texto utilizando los servicios de un experto en lenguaje humano. A continuación, puede comparar los resultados que obtiene el servicio de {{site.data.keyword.personalityinsightsshort}} de texto traducido manual y automáticamente para comprender la diferencia en los resultados.

{{site.data.keyword.IBM_notm}} seguirá añadiendo más idiomas a medida que aumente la demanda empresarial. {{site.data.keyword.IBM_notm}} entiende que el servicio de {{site.data.keyword.personalityinsightsshort}} puede que no dé soporte a su idioma nativo lo suficientemente rápido para sus objetivos. {{site.data.keyword.IBM_notm}} está realizando pruebas para comparar los resultados que se obtienen de la habilitación del idioma nativo con los resultados obtenidos de los servicios de traducción de idiomas e informará de sus conclusiones a medida que estén disponibles.

## Cómo utilizar los retratos de personalidad para aplicaciones específicas
{: #applying}

El servicio de {{site.data.keyword.personalityinsightsshort}} se puede aplicar a innumerables casos de uso. Las siguientes secciones describen el uso de los retratos de personalidad para algunos objetivos específicos:

-   [Emparejamiento de personas](#matching)
-   [Supervisión y predicción de salud mental](#mentalhealth)
-   [Supervisión de elementos radicales y criminales mediante las redes sociales](#monitoring)

### Emparejamiento de personas
{: #matching}

Hacer un buen emparejamiento entre personas puede mejorar la interacción y los resultados en las relaciones. Este es el caso de la construcción del equipo dentro de una empresa y de la interacción con clientes a través de una amplia gama de sectores. En un estudio de emparejamiento médico-paciente, los investigadores descubrieron que los pacientes prefieren médicos que sean parecidos a ellos mismos. Efectivamente, emparejar médicos y pacientes crea confianza y alienta la comunicación, lo que puede mejorar el cumplimiento y dar como resultado un tratamiento más exitoso ([Godager, 2012](/docs/services/personality-insights/references.html#godager2012)).

La personalidad también influye en las preferencias de interacción entre profesionales y clientes. Por ejemplo, los pacientes con un alto grado de responsabilidad y de apertura prefieren implicarse de forma activa a la hora de decidir su curso de tratamiento. Los pacientes con altos niveles de simpatía o neurosis prefieren que sean los médicos los que tomen la iniciativa a la hora de tomar decisiones de salud importantes ([Flynn &amp; Smith, 2007](/docs/services/personality-insights/references.html#flynn2007)).

### Supervisión y predicción de salud mental
{: #mentalhealth}

{{site.data.keyword.IBM_notm}} cree que el diagnóstico de la enfermedad lo realiza mejor un profesional médico capacitado. Podría ser posible detectar algunos signos de estado mental de las personas a partir del uso de vocabulario. Pero {{site.data.keyword.IBM_notm}} no ha realizado investigaciones en este espacio como para realizar estudios de datos de campo ni para explorar la posibilidad de establecer una base científica para ese trabajo.

Los clientes y los socios empresariales interesados en adquirir el uso del servicio de {{site.data.keyword.personalityinsightsshort}} para el diagnóstico de salud mental son bienvenidos para diseñar y realizar experimentos de datos de campo para tales casos de uso. La investigación activa y continua en este ámbito incluye trabajo que relaciona la personalidad con los resultados médicos ([Israel et al., 2014](/docs/services/personality-insights/references.html#israel2014)) y que trata de predecir el postparto y otras formas de depresión a partir de las redes sociales ([De Choudhury et al., 2013a](/docs/services/personality-insights/references.html#dechoudhury2013a), y [De Choudhury et al., 2013b](/docs/services/personality-insights/references.html#dechoudhury2013b)).

### Supervisión de elementos radicales y criminales mediante las redes sociales
{: #monitoring}

Las agencias gubernamentales de todo el mundo están constantemente buscando maneras de detectar señales iniciales de la radicalización de personas o grupos de personas a través de canales de las redes sociales. La deducción de la personalidad de la escritura de individuos es una aplicación tradicional del servicio de {{site.data.keyword.personalityinsightsshort}}. Por lo tanto, no es sorprendente que utilizar el servicio para deducir elementos radicales y criminales mediante las redes sociales sea un caso de uso viable. Las deducciones fiables requieren no solo las características de personalidad, sino un conjunto de otros atributos como género, edad y geografía. {{site.data.keyword.IBM_notm}} no ha realizado ningún estudio para validar o invalidar este caso de uso. Los clientes y los socios comerciales son bienvenidos a realizar estudios para explorar este caso de uso basado en sus objetivos y requisitos específicos.

## ¿Cambia la personalidad de una persona a lo largo del tiempo?
{: #evolve}

¿Evoluciona la personalidad de una persona a lo largo del tiempo? Si es así, ¿con cuánta frecuencia se debería utilizar el servicio de {{site.data.keyword.personalityinsightsshort}} para deducir la personalidad de una persona? Distintos estudios informan de pruebas a favor y en contra de la teoría de que la personalidad de una persona se estabiliza en la edad adulta. En su trabajo seminal de 1890 sobre cómo medir la estabilidad de la personalidad, *Principios de psicología*, el psicólogo de Harvard William James señaló que "En la mayoría de nosotros, a los treinta años de edad, el carácter se queda como el yeso, y no se volverá a suavizar". Pero informes más recientes informan de que la personalidad evoluciona con el tiempo:

-   [Helson et al. (2002)](/docs/services/personality-insights/references.html#helson2002) informan de que "la idea de que el cambio de personalidad es más pronunciado antes de la edad de 30 y que luego se estabiliza no ha recibido ningún soporte". Los autores realizaron un estudio longitudinal en dos grupos durante un periodo de 40 años. Señalan que el periodo de vida y de clima social son factores significativos en el cambio de personalidad durante la edad adulta. Comentan que "Las puntuaciones en dominación e independencia alcanzaron el punto más alto en la edad media de ambos grupos, y las puntuaciones en responsabilidad fueron las menores durante los años punta de la cultura del individualismo".
-   [Scollon and Diener (2006)](/docs/services/personality-insights/references.html#scollon2006) se propusieron examinar las diferencias individuales en el cambio en extraversión, neurosis, y satisfacción con el trabajo y las relaciones a lo largo del tiempo. Los autores señalan que la satisfacción aumentada con el trabajo y las relaciones se asociaba con descensos en neurosis y aumentos en extraversión a lo largo del tiempo.
-   [Roberts and Mroczek (2008)](/docs/services/personality-insights/references.html#roberts2008) comentan que existen pruebas para "el cambio de nivel medio en los rasgos de personalidad, así como para las diferencias individuales en el cambio a lo largo de toda la vida". Los autores señalan que las personas muestran una confianza en uno mismo, una calidez, un autocontrol y una estabilidad emocional aumentados con la edad. Estos cambios predominan en la adultez joven (de los 20 a los 40 años). Además, el cambio de nivel medio en las características de personalidad se produce en la mitad de la tercera edad, lo que muestra que las características de personalidad pueden cambiar a cualquier edad.

Basándose en estos estudios, {{site.data.keyword.IBM_notm}} recomienda que los usuarios del servicio de {{site.data.keyword.personalityinsightsshort}} trabajen siempre con los datos más recientes y con tantos datos disponibles como sea posible. {{site.data.keyword.IBM_notm}} recomienda además que los usuarios renueven los retratos de personalidad en intervalos regulares para capturar las personalidades en evolución de las personas. Mientras que {{site.data.keyword.IBM_notm}} tiende a creer que la personalidad evoluciona dentro de determinados límites, no ha realizado ningún estudio para examinar los bordes superiores e inferiores de esta evolución.

Alguien podría preguntarse con cuánta frecuencia hay que renovar los retratos de personalidad de los individuos. {{site.data.keyword.IBM_notm}} recomienda buscar la disponibilidad de datos y texto nuevo de un individuo determinado. Si una persona ha creado una cantidad sustancial de texto nuevo desde que se obtuvo su retrato de personalidad, podría valer la pena renovar el retrato. Este enfoque captura la naturaleza evolutiva de la personalidad, si alguien elige aceptar que la personalidad evoluciona, y da al servicio de {{site.data.keyword.personalityinsightsshort}} el beneficio de trabajar con más palabras, lo que a su vez puede aumentar la precisión de los resultados del servicio.
