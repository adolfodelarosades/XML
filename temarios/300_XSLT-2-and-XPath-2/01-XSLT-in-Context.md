# 1. XSLT en contexto
* 1.1. ¿Qué es XSLT?
   * 1.1.1. ¿Por qué la versión 2.0?
   * 1.1.2. Un escenario: transformar la música
* 1.2. ¿Cómo XSLT transforma XML?
   * 1.2.1. XSLT y SQL: una analogía
   * 1.2.2. Procesadores XSLT
   * 1.2.3. Una hoja de estilo XSLT simple
   * 1.2.4. Una hoja de estilo XSLT 2.0
* 1.3. El lugar de XSLT en la familia XML
   * 1.3.1. Objetos de formato XSLT y XSL
   * 1.3.2. XSLT y XPath
   * 1.3.3. Espacios de nombres XSLT y XML
   * 1.3.4. XSLT y CSS
   * 1.3.5. Esquemas XSLT y XML
   * 1.3.6. XSLT y XQuery
* 1.4. La historia de XSL
   * 1.4.1. Prehistoria
   * 1.4.2. La primera propuesta XSL
   * 1.4.3. sajón
   * 1.4.4. Más allá de XSLT 1.0
   * 1.4.5. Convergencia con XQuery
   * 1.4.6. El desarrollo de XSLT 2.0 y XPath 2.0
* 1.5. XSLT 2.0 como lenguaje
   * 1.5.1. Uso de sintaxis XML
   * 1.5.2. Sin efectos secundarios
   * 1.5.3. Basado en reglas
   * 1.5.4. Tipos basados en esquema XML
   * 1.5.5. Un sistema de dos idiomas: XSLT y XPath
* 1.6. Resumen


Este capítulo está diseñado para poner XSLT en contexto. Se trata del propósito de XSLT y la tarea para la que fue diseñado. Se trata de qué tipo de lenguaje es, cómo llegó a ser así y cómo ha cambiado en la versión 2.0; y se trata de cómo XSLT encaja con todas las demás tecnologías que probablemente usará en una aplicación típica basada en Web (incluido, por supuesto, XPath, que forma un componente vital de XSLT). No diré mucho en este capítulo sobre cómo se ve realmente una hoja de estilo XSLT o cómo funciona: eso vendrá más adelante, en los Capítulos 2 y 3.

El capítulo comienza describiendo la tarea para la que está diseñado XSLT (transformación) y por qué es necesario transformar los documentos XML. A continuación, presentaré un ejemplo trivial de transformación para explicar lo que esto significa en la práctica.

A continuación, analizo la relación de XSLT con otros estándares en la creciente familia XML, para poner su función en contexto y explicar cómo complementa los otros estándares.

Describiré qué tipo de lenguaje es XSLT y profundizaré un poco en la historia de cómo llegó a ser así. Si estás impaciente, es posible que desees saltarte la historia y seguir usando el lenguaje, pero tarde o temprano te preguntarás "¿por qué diablos lo diseñaron así?" y en esa etapa espero que vuelva atrás y lea sobre el proceso por el cual XSLT llegó a existir.

## 1.1. ¿Qué es XSLT?

XSLT (Extensible Stylesheet Language: Transformations) es un lenguaje que, de acuerdo con la primera oración de la especificación (que se encuentra en http://www.w3.org/TR/xslt20/), está diseñado principalmente para transformar un documento XML en otro. Sin embargo, XSLT también es capaz de transformar XML a HTML y muchos otros formatos basados en texto, por lo que una definición más general podría ser la siguiente:

XSLT es un lenguaje para transformar la estructura y el contenido de un documento XML.

¿Por qué debería querer hacer eso? Para responder correctamente a esta pregunta, primero debemos recordarnos por qué XML ha tenido tanto éxito y ha generado tanto entusiasmo.

XML es una forma simple y estándar de intercambiar datos textuales estructurados entre programas de computadora. Parte de su éxito se debe a que también es legible y escribible por humanos, sin usar nada más complicado que un editor de texto, pero esto no altera el hecho de que está destinado principalmente a la comunicación entre sistemas de software. Como tal, XML satisface dos requisitos convincentes:

* **Separar los datos de la presentación:** la necesidad de separar la información (como un pronóstico del tiempo) de los detalles de la forma en que se presentará en un dispositivo en particular. La motivación inicial para esto surgió de la necesidad de entregar información no solo al navegador web tradicional basado en PC (que a su vez viene en muchos sabores), sino también a televisores y dispositivos portátiles, sin mencionar la necesidad continua de producir impresiones -papel. Hoy en día, para muchos proveedores de información, un factor aún más importante es la oportunidad de distribuir contenido a otras organizaciones que pueden volver a publicarlo con su propia apariencia.

* **Transmisión de datos entre aplicaciones:** la necesidad de transmitir información (como pedidos y facturas) de una organización a otra sin invertir en proyectos únicos de integración de software. A medida que el comercio electrónico se acelera, la cantidad de datos intercambiados entre empresas aumenta a diario, y esta necesidad se vuelve cada vez más urgente.

Por supuesto, estas dos formas de utilizar XML no se excluyen mutuamente. Se puede presentar una factura en la pantalla, así como ingresar a un paquete de aplicación financiera, y el destinatario puede resumir, indexar y agregar las previsiones meteorológicas en lugar de mostrarlas directamente. Otro de los beneficios clave de XML es que unifica el mundo de los documentos y los datos, proporcionando una forma única de representar la estructura, independientemente de si la información está destinada al consumo humano o de máquinas. El punto principal es que, ya sea que los datos XML sean utilizados en última instancia por personas o por una aplicación de software, muy raramente se utilizarán directamente en la forma en que llegan: primero hay que transformarlos en otra cosa.

Para comunicarse con un lector humano, esta otra cosa podría ser un documento que se puede mostrar o imprimir: por ejemplo, un archivo HTML, un archivo PDF o incluso un sonido audible. La conversión de XML a HTML para visualización sigue siendo probablemente la aplicación más común de XSLT, y es la que usaré en la mayoría de los ejemplos de este libro. Una vez que tenga los datos en formato HTML, podrá visualizarlos en cualquier navegador.

Para transferir datos entre diferentes aplicaciones, necesitamos poder transformar la información del modelo de datos utilizado por una aplicación al modelo utilizado por otra. Para cargar los datos en una aplicación, el formato requerido puede ser un archivo de valores separados por comas, un script SQL, un mensaje HTTP o una secuencia de llamadas en una interfaz de programación en particular. Alternativamente, podría ser otro archivo XML con un vocabulario diferente al original. A medida que el comercio electrónico basado en XML se generaliza, el papel de XSLT en la conversión de datos entre aplicaciones también se vuelve cada vez más importante. El hecho de que todo el mundo esté usando XML no significa que desaparecerá la necesidad de conversión de datos.

Siempre habrá múltiples estándares en uso. Mientras escribo, existe un intenso debate entre los protagonistas de dos representaciones XML diferentes de documentos de Office: la especificación ODF de la comunidad Open Office y la especificación OOXML de Microsoft y sus amigos. Independientemente de cómo se resuelva esto, las perspectivas de un solo formato XML para todos los documentos de procesador de texto son remotas, por lo que siempre será necesario transformar entre múltiples formatos.

Incluso dentro del dominio de un único estándar, existe la necesidad de extraer información de un tipo de documento e insertarla en otro. Por ejemplo, un fabricante de PC que diseñe una solución para el problema de un cliente deberá extraer datos de los informes de problemas e insertarlos en los documentos emitidos a los ingenieros de campo para que puedan reconocer y solucionar el problema cuando otros clientes lo encuentren. Los ingenieros de campo, por supuesto, probablemente estén trabajando para una empresa diferente, no para el fabricante original. Por lo tanto, vincular empresas para hacer comercio electrónico se convertirá cada vez más en un caso de definir cómo extraer y combinar datos de un conjunto de documentos XML para generar otro conjunto de documentos XML, y XSLT es la herramienta ideal para el trabajo.

Durante el transcurso de este capítulo, volveremos a ejemplos específicos de cuándo debería usarse XSLT para transformar XML. Por ahora, solo quería establecer una idea de la importancia y la utilidad de transformar XML. Si ya está utilizando XSLT, por supuesto, esto puede ser una noticia obsoleta. Así que echemos un vistazo ahora a lo que la versión 2.0 de XSLT trae a la fiesta.

### 1.1.1. ¿Por qué la versión 2.0?

XSLT 1.0 salió a la luz en noviembre de 1999 y fue un gran éxito. Por lo tanto, era casi inevitable que se comenzara a trabajar en una versión 2.0. Como veremos más adelante, el proceso de creación de la versión 2.0 estuvo lejos de ser sencillo y tomó más tiempo de lo que algunas personas esperaban. Sin embargo, XSLT 2.0 finalmente se publicó como una Recomendación del W3C (es decir, una especificación final) en enero de 2007, y la reacción de los usuarios ha sido muy favorable.

Es tentador mirar la versión 2.0 y verla como una colección de características atornilladas al lenguaje, parches para compensar las debilidades de la versión 1.0. Al igual que con una nueva versión de cualquier otro idioma o paquete de software, la mayoría de los usuarios encontrarán aquí algunas características que han estado pidiendo a gritos y otras adiciones que parecen exceder los requisitos.

Pero creo que la versión 2.0 es más que una bolsa de golosinas; hay algunos temas subyacentes que han guiado el diseño y la selección de funciones. Puedo identificar cuatro temas principales:

* **Integración en toda la familia de estándares XML:** los grupos de trabajo del W3C no trabajan aislados unos de otros; dedican mucho tiempo a asegurarse de que sus esfuerzos estén coordinados. Gran parte de lo que hay en XSLT 2.0 está influenciado por una agenda más amplia de hacer lo correcto para toda la serie de estándares XML, no solo para XSLT considerado de forma aislada.

* **Ampliación del ámbito de aplicación:** XSLT 1.0 fue bastante bueno para representar documentos XML para mostrarlos como HTML en la pantalla y para convertirlos en objetos de formato XSL para la publicación impresa. Pero hay muchas otras tareas de transformación para las que resultó menos adecuado. En comparación con los redactores de informes (incluso los de la década de 1980, y mucho menos con las herramientas modernas de visualización de datos), sus capacidades de manejo de datos eran muy débiles. El lenguaje era bastante bueno para realizar conversiones de documentos XML si el marcado original estaba bien diseñado, pero era mucho más débil para reconocer patrones en el texto o marcado que representan una estructura oculta. Un objetivo importante de XSLT 2.0 era aumentar la gama de aplicaciones que puede abordar con XSLT.

* **Ingeniería de software más robusta:** XSLT siempre se diseñó para usarse tanto en el lado del cliente como en el lado del servidor, pero en muchos sentidos XSLT 1.0 optimizó el lenguaje para su uso en el navegador. Sin embargo, las personas escriben aplicaciones grandes en XSLT, que contienen 100K o más líneas de código, y esto necesita un enfoque más riguroso y sólido para cosas como el manejo de errores y la verificación de tipos.

* **Mejoras en la usabilidad táctica**: aquí estamos en el ámbito de las ventajas adicionales. El objetivo aquí es lograr beneficios de productividad, facilitando las tareas que son difíciles o propensas a errores en la versión 1.0. Estas son probablemente las características que los usuarios actuales reconocerán de inmediato como las más beneficiosas, pero a largo plazo, los otros temas probablemente tengan un significado más estratégico para el futuro del idioma.

Antes de discutir XSLT con más detalle y echar un primer vistazo a cómo funciona, estudiemos un escenario que demuestre claramente la variedad de formatos a los que podemos transformar XML, usando XSLT.

### 1.1.2. Un Escenario: Transformar Música

Como una indicación de hasta dónde ha penetrado XML, el índice de Robin Cover de estándares de aplicaciones basados en XML en http://xml.coverpages.org/xmlApplications.html alcanza actualmente 594 entradas. (El último se titula Lenguaje de marcado de lectura mental, pero hasta donde puedo decir, todas las demás entradas son serias).

Seguiré solo uno de estos 594 enlaces, XML y Música, que nos lleva a http://xml.coverpages.org/xmlMusic.html. En esta página encontramos una lista de no menos de 18 estándares, propuestas o iniciativas que utilizan XML para marcar música.

Esta diversidad es claramente innecesaria y muchas de estas iniciativas ya están muertas o agonizantes. Incluso los nombres de los estándares son caóticos: hay un Music Markup Language, un MusicML, un MusicXML y un MusiXML, todos sin relación alguna. Hay al menos tres contendientes realmente serios: Music Encoding Initiative (MEI), Standard Music Description Language (SMDL) y MusicXML. El MEI se inspira en la Iniciativa de codificación de texto y tiene un enfoque particular en las necesidades de los estudiosos de la música (por ejemplo, la capacidad de capturar características que se encuentran en diferentes manuscritos de la misma partitura), mientras que SMDL está relacionado con los estándares hipermedia de HyTime. y tiene en cuenta requisitos como la necesidad de sincronizar la música con el video o con un guión de iluminación (no se ha implementado ampliamente, pero tiene sus entusiastas). MusicXML, por el contrario, se centra principalmente en las necesidades de los compositores y editores de partituras.

Dada la variedad de requisitos, es poco probable que la cantidad de estándares en uso se reduzca aún más. Las diferentes notaciones se inventaron con diferentes propósitos en mente: un lenguaje de marcado utilizado por un editor para imprimir partituras tiene diferentes requisitos del diseñado para permitirle escuchar la música desde un navegador.

En la primera edición de este libro, allá por 2001, presenté la idea de usar XSLT para transformar la música como una posibilidad teórica, algo para hacer pensar a mis lectores sobre el abanico de posibilidades que se abren al lenguaje. Cuando publiqué la segunda edición, los estudiantes de doctorado estaban demostrando que realmente se podía hacer. Hoy en día, MusicXML es una parte estándar de más de 80 aplicaciones de software, incluidos líderes de la industria como Sibelius y Finale, y XSLT se usa habitualmente para manipular la salida. El sitio web de MEI publica hojas de estilo XSLT para convertir entre MEI y MusicXML en cualquier dirección.

![image](https://user-images.githubusercontent.com/23094588/114019619-ee7e2100-986e-11eb-81b0-768c41476c0b.png)

Da la casualidad de que MusicXML en sí proporciona dos formas de representar una partitura. En uno, la subdivisión de nivel superior en la jerarquía XML es por parte instrumental o voz; en el otro, la estructura de nivel superior es la línea de tiempo de la música. Se proporcionan hojas de estilo XSLT para convertir entre los dos formatos. 

La Figura 1-1 muestra algunas de las posibilidades. Puede usar XSLT para:

* Convertir música de una representación a otra, por ejemplo de MEI a SMDL. 
* Convertir música de cualquiera de estas representaciones en notación musical visual, generando el formato de gráficos vectoriales basado en XML SVG. 
* Reproducir la música en un sintetizador, generando un archivo MIDI (Musical Instrument Digital Interface).
* Realice una transformación musical, como transponer la música a una clave diferente o extrayendo partes para diferentes instrumentos o voces.
* Extraiga la letra, en HTML o en un documento XML de solo texto. 
* Capture música de formatos que no sean XML y tradúzcala a XML (XSLT 2.0 es especialmente útil aquí). 

Como puede ver, XSLT no es solo para convertir documentos XML a HTML.

## 1.2. ¿Cómo XSLT Transforma XML?

A estas alturas, probablemente se esté preguntando exactamente cómo XSLT procesa un documento XML para convertirlo en la salida requerida. Por lo general, hay dos aspectos en este proceso:

1. La primera etapa es una transformación estructural, en la que los datos se convierten de la estructura del documento XML entrante a una estructura que refleja la salida deseada.

2. La segunda etapa es el formateo, en el que la nueva estructura se genera en el formato requerido, como HTML o PDF.

La segunda etapa cubre el terreno que discutimos en la sección anterior; la estructura de datos que resulta de la primera etapa se puede generar como HTML, como un archivo de texto o como XML. La salida HTML permite que la información sea vista directamente en un navegador por un usuario humano o ingresada en cualquier procesador de texto moderno. La salida de texto sin formato permite formatear los datos de la forma en que una aplicación existente puede aceptar, por ejemplo, valores separados por comas o uno de los muchos formatos de intercambio de datos basados en texto que se desarrollaron antes de que XML llegara a la escena. Finalmente, la salida XML permite que los datos se proporcionen a aplicaciones que aceptan XML directamente. Normalmente, se utilizará un vocabulario de etiquetas XML diferente al del documento original: por ejemplo, una transformación XSLT podría tomar las cifras de ventas mensuales como entrada XML y producir un histograma como salida XML, utilizando el estándar SVG basado en XML para vectores. gráficos. O bien, puede utilizar una transformación XSLT para generar una salida XML de voz, para una reproducción auditiva de sus datos.

Puede encontrar información sobre VoiceXML en http://www.voicexml.org/.

Profundicemos ahora en la primera etapa, la transformación, la etapa en la que XSLT se ocupa principalmente y que hace posible proporcionar resultados en todos estos formatos. Esta etapa puede implicar seleccionar datos, agregarlos y agruparlos, ordenarlos o realizar conversiones aritméticas, como cambiar centímetros a pulgadas.

XSLT no es la única forma de procesar o transformar XML. Por ejemplo, puede escribir aplicaciones en Java o C # que construyan una representación en forma de árbol de un documento XML (utilizando el Modelo de objetos de documento definido por W3C u otros modelos similares como JDOM o XOM). Su programa podría interrogar esta estructura de árbol para encontrar la información específica necesaria. Lo haría definiendo una secuencia específica de pasos a seguir para producir el resultado requerido.

Entonces, ¿cómo es mejor usar XSLT para realizar transformaciones en XML que escribir aplicaciones personalizadas? Bueno, el diseño de XSLT se basa en el reconocimiento de que estos programas son todos muy similares y, por lo tanto, debería ser posible describir lo que hacen utilizando un lenguaje declarativo de alto nivel en lugar de escribir cada programa desde cero en Java o C #. La transformación requerida se puede expresar como un conjunto de reglas. Estas reglas se basan en definir qué salida se debe generar cuando se producen patrones particulares en la entrada. El lenguaje es declarativo en el sentido de que usted describe la transformación que necesita, en lugar de proporcionar una secuencia de instrucciones de procedimiento para lograrla. XSLT describe la transformación requerida y luego se basa en el procesador XSLT para decidir la forma más eficiente de hacerlo.

XSLT todavía se basa en un analizador XML (puede ser un analizador DOM o uno compatible con SAX, o uno de la nueva generación de "analizadores de extracción") para convertir el documento XML en una estructura de árbol. Es la estructura de esta representación de árbol del documento lo que XSLT manipula, no el documento en sí. Si está familiarizado con el DOM, estará satisfecho con la idea de tratar cada elemento de un documento XML (elementos, atributos, instrucciones de procesamiento, etc.) como un nodo en un árbol. Con XSLT tenemos un lenguaje de alto nivel que puede navegar alrededor de un árbol de nodos, seleccionar nodos específicos y realizar manipulaciones complejas en estos nodos.

El modelo de árbol XSLT es similar en concepto al DOM, pero no es el mismo. El modelo de procesamiento XSLT completo se analiza en el Capítulo 2.

La descripción de XSLT dada hasta ahora (un lenguaje declarativo que puede navegar y seleccionar datos específicos y luego manipular esos datos) puede parecerle similar a la del lenguaje estándar de consulta de bases de datos, SQL. Echemos un vistazo más de cerca a esta comparación.

### 1.2.1. XSLT y SQL: una Analogía

En una base de datos relacional, los datos constan de un conjunto de tablas. Por sí mismas, las tablas no son de mucha utilidad, los datos también podrían almacenarse en archivos planos en formato de valores separados por comas. El poder de una base de datos relacional no proviene de su estructura de datos; proviene del lenguaje que procesa los datos, SQL. De la misma manera, XML por sí solo define una estructura de datos. Es un poco más rico que las tablas del modelo relacional, pero por sí solo no hace nada muy útil. Es cuando obtenemos un lenguaje de alto nivel diseñado expresamente para manipular la estructura de datos que comenzamos a encontrar que tenemos algo interesante en nuestras manos, y para los datos XML, el lenguaje principal que lo hace es XSLT.

Superficialmente, SQL y XSLT son lenguajes muy diferentes. Pero si miras debajo de la superficie, en realidad tienen mucho en común. Para empezar, para procesar datos específicos, ya sea en una base de datos relacional o en un documento XML, el lenguaje de procesamiento debe incorporar una sintaxis de consulta declarativa para seleccionar los datos que necesitan ser procesados. En SQL, esa es la declaración `SELECT`. En XSLT, el equivalente es la ***expresión XPath***.

El lenguaje de expresión XPath forma una parte esencial de XSLT, aunque en realidad se define en una Recomendación W3C separada (http://www.w3.org/TR/xpath) porque también se puede usar independientemente de XSLT (la relación entre XPath y XSLT se analiza con más detalle en la página 22).

La sintaxis XPath está diseñada para recuperar nodos de un documento XML, basándose en una ruta a través del documento XML o el contexto en el que aparece el nodo. Permite el acceso a nodos específicos, conservando la jerarquía y estructura del documento. Las instrucciones XSLT se utilizan para manipular los resultados de estas consultas, por ejemplo, reorganizando los nodos seleccionados y construyendo nuevos nodos.

Hay más similitudes entre XSLT y SQL:

* Ambos lenguajes aumentan las facilidades de consulta básicas con adiciones útiles para realizar operaciones aritméticas, manipulación de cadenas y comparación.

* Ambos lenguajes complementan la sintaxis de consulta declarativa con facilidades semiprocedimiento para describir el procesamiento a realizar, y también proporcionan ganchos para escapar a lenguajes de programación convencionales donde los algoritmos comienzan a volverse demasiado complejos.

* Ambos lenguajes tienen una propiedad importante llamada ***closure***, lo que significa que la salida tiene la misma estructura de datos que la entrada. Para SQL, esta estructura son tablas, para XSLT son árboles, la representación en árbol de documentos XML. La propiedad closure es extremadamente valiosa porque significa que las operaciones realizadas usando el lenguaje se pueden combinar de un extremo a otro para definir operaciones más grandes y complejas: simplemente toma la salida de una operación y la convierte en la entrada de la siguiente operación. En SQL, puede hacer esto definiendo vistas o subconsultas; en XSLT puede hacerlo pasando sus datos a través de una serie de hojas de estilo, o capturando el árbol producido por una fase de transformación en una variable y usando esa variable como entrada de otra fase de transformación. Esta última característica es nueva en XSLT 2.0, aunque la mayoría de los procesadores XSLT 1.0 ofrecen una capacidad similar a la extensión del lenguaje.

En el mundo real, por supuesto, XSLT y SQL deben coexistir. Hay muchas relaciones posibles, pero por lo general, los datos se almacenan en bases de datos relacionales y se transmiten entre sistemas en XML. Los dos lenguajes no encajan tan bien como a uno le gustaría, porque los modelos de datos son muy diferentes. Pero las transformaciones XSLT pueden desempeñar un papel importante a la hora de cerrar la brecha. Todos los principales proveedores de bases de datos relacionales han lanzado extensiones que permiten almacenar y manipular datos XML directamente dentro de lo que todavía es nominalmente una base de datos relacional.

Antes de ver un ejemplo de trabajo simple de una transformación XSLT, deberíamos discutir brevemente algunos de los procesadores XSLT que están disponibles para efectuar estas transformaciones.

### 1.2.2. Procesadores XSLT

El trabajo de un procesador XSLT es aplicar una hoja de estilo XSLT a un documento de origen XML y producir un documento de resultado.

Con XSLT 1.0, hay bastantes buenos procesadores XSLT para elegir, y muchos de ellos se pueden descargar de forma gratuita (pero lea las condiciones de licencia).

Si utiliza tecnología de Microsoft, puede elegir entre dos productos. La opción más utilizada es MSXML (Google para "Descargar MSXML" para encontrarlo; la versión actual es MSXML 6). Por lo general, no soy el mayor fanático de Microsoft, pero con este procesador en general se acepta que han hecho un excelente trabajo. Este producto viene de serie con Internet Explorer y, por lo tanto, es la opción preferida para ejecutar transformaciones en el navegador. Sin embargo, para el entorno .NET, Microsoft desarrolló un nuevo procesador. Esto no tiene un nombre de producto propio, aparte del nombre del paquete dentro del marco .NET, que es `System.Xml.Xsl`. Inicialmente se dijo que este procesador era significativamente más lento que el producto MSXML, pero eso parece que ya no es cierto, y si está escribiendo su aplicación usando tecnologías .NET como C # y ASP.NET, probablemente sea el que usted ' Encontrarás más conveniente.

En el mundo de Java, hay una variedad de productos XSLT 1.0. Existe mi propio producto Saxon (la versión 6.5.5 es la versión que admite XSLT 1.0) disponible en http://saxon.sf.net/, y está el producto Xalan-J que se incluye con el software Java JDK de Sun desde JDK 1.4 en adelante. También hay una implementación de Oracle y un nuevo procesador de Intel.

Para C y C ++, el procesador más popular es el motor libxslt (http://xmlsoft.org/XSLT/).

La mayoría de estos productos son intérpretes XSLT, pero hay dos compiladores XSLT bien conocidos: XSLTC, que se distribuye como parte del paquete Xalan-J mencionado anteriormente, y Gregor, de Jacek Ambroziak (http://www.ambrosoft.com /gregor.html). En el extremo superior del mercado, para aquellos con un gran presupuesto, también puede obtener motores acelerados por hardware de IBM e Intel.

Con XSLT 2.0, en el momento de escribir este artículo, la elección es más limitada. Actualmente hay tres procesadores XSLT 2.0 disponibles:

* Mi propio producto Saxon. Está disponible en dos variantes, correspondientes a los dos niveles de conformidad definidos en la especificación W3C: Saxon-B 9.x (http://saxon.sf.net/) es una implementación de código abierto de un procesador XSLT 2.0 básico, y Saxon-SA 9.x (http://www.saxonica.com/) es una implementación comercial de un procesador XSLT con reconocimiento de esquemas. Ambas variantes están disponibles para las plataformas Java y .NET. Puede ejecutar la mayoría de los ejemplos de este libro utilizando un procesador XSLT básico, pero el Capítulo 4 y el Capítulo 11 se centran en la capacidad adicional de XSLT cuando se utiliza con esquemas XML, con ejemplos que solo se ejecutarán con un procesador XSLT con reconocimiento de esquemas.

* Saxon, tal como se entrega, ofrece una interfaz de línea de comandos y una API Java o .NET. Varios conjuntos de herramientas proporcionan interfaces gráficas de usuario en la parte superior: el más simple es el producto Kernow de código abierto (kernowforsaxon.sourceforge.net); otras opciones son el completo entorno de desarrollo Stylus Studio (www.stylusstudio.com) y el editor XML oXygen (www.oxygenxml.com), los cuales admiten la depuración Saxon paso a paso.

* Altova (www.altova.com) ha lanzado su propio procesador XSLT 2.0, que está disponible como un componente COM independiente con una interfaz de línea de comandos y API de Windows, o integrado en el popular entorno de desarrollo XML Spy. Como componente independiente, el producto es gratuito (pero no de código abierto) y ofrece un procesamiento con y sin reconocimiento de esquemas. El nivel de conformidad del producto Altova ha mejorado con cada versión y casi todos los ejemplos de este libro se ejecutan correctamente con la edición 2008 de este producto.

* Gestalt es un procesador XSLT 2.0 de código abierto escrito en el lenguaje Eiffel por Colin Adams (http://sourceforge.net/projects/gestalt). El producto está en progreso y, aunque el software está en desarrollo activo, la documentación es un poco incompleta y es poco probable que esta implementación le atraiga a menos que sea un entusiasta de Eiffel. No hemos probado los ejemplos de este libro con el procesador Gestalt.

Al leer los artículos publicados en las conferencias de investigación y las publicaciones en blogs de los empleados, puede hacer una suposición fundamentada de que las implementaciones están en marcha dentro de IBM, Oracle y Microsoft, pero ninguna de estas compañías ha anunciado planes de productos oficiales o fechas de lanzamiento al momento de escribir este artículo. y, por supuesto, no todo lo que esas empresas hacen en sus laboratorios de investigación ve la luz como un producto.

Creo que es un poco improbable que haya tantos procesadores XSLT 2.0 como para XSLT 1.0 (seguramente habrá una sacudida en un mercado en maduración), pero estoy seguro de que habrá cuatro o cinco, lo que debería bastar.

Mientras tanto, puede utilizar Altova o Saxon, y esos son los vehículos principales que utilizaré para todos los ejemplos de este libro.

### 1.2.3. Una Hoja de Estilo XSLT Simple

Ahora estamos listos para echar un vistazo a un ejemplo del uso de XSLT para transformar un documento XML muy simple.

#### 💻 "Hello, world!" XSLT Stylesheet

Kernighan y Ritchie en su clásico *El lenguaje de programación C* (Prentice-Hall, 1988) originaron la idea de presentar un programa trivial pero completo justo al comienzo del libro, y desde entonces el programa `Hello world` ha sido una tradición honrada. Por supuesto, no es posible una descripción completa de cómo funciona este ejemplo hasta que se hayan definido todos los conceptos, por lo que si cree que no lo estoy explicando completamente, no se preocupe, las explicaciones vendrán más adelante.

**Input**

¿Qué tipo de transformación nos gustaría hacer? Intentemos transformar el siguiente documento XML.

`hello.xml`

```xml
<?xml version="1.0" encoding="iso-8859-1"?>
<?xml-stylesheet type="text/xsl" href="hello.xsl"?>
<greeting>Hello, world!</greeting>
```

Este documento está disponible como archivo `hello.xml` en el directorio de descarga de este capítulo.

En la Figura 1-2 se muestra una representación simple de árbol de nodos de este documento.

![image](https://user-images.githubusercontent.com/23094588/114033299-6ce1bf80-987d-11eb-8af8-e7948af42370.png)

Hay cuatro nodos en este árbol: un nodo de documento que representa el documento como un todo; una instrucción de procesamiento `<?xml-stylesheet?>` que identifica la hoja de estilo que se utilizará; el elemento `<greeting>`; y el texto dentro del elemento `<greeting>`.

El nodo del documento en el modelo XSLT realiza la misma función que el nodo del documento en el modelo DOM (se lo llamó nodo raíz en XSLT 1.0, pero la nomenclatura se ha alineado con el DOM). La declaración XML no es visible para el procesador XSLT y, por lo tanto, no se incluye en el árbol.

Lo he facilitado deliberadamente al incluir una instrucción de procesamiento `<?xml-stylesheet?>` en el archivo XML de origen. Muchos procesadores XSLT usarán esto para identificar la hoja de estilo si no especifica una hoja de estilo diferente para usar. El atributo `href` proporciona el URI relativo de la hoja de estilo predeterminada para este documento.

**Output**

Nuestro resultado requerido es el siguiente HTML, que simplemente cambiará el título del navegador a "Today's Greeting" y mostrará el saludo que esté en el archivo XML de origen:


```html
<html>
<head>
   <title>Today's greeting</title>
</head>
<body>
   <p>Hello, world!</p>
</body>
</html>
```

**XSLT Stylesheet**

Sin más preámbulos, aquí está la hoja de estilo XSLT `hello.xsl` para efectuar la transformación. Esta es una hoja de estilo XSLT 1.0, de ahí la `«versión =" 1.0 "»` en el elemento `<xsl:stylesheet>`.

```xsl
<?xml version="1.0" encoding="iso-8859-1"?>
<xsl:stylesheet
   version="1.0"
   xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

<xsl:template match="/">
   <html>
   <head>
      <title>Today's greeting</title>
   </head>
   <body>
      <p><xsl:value-of select="greeting"/></p>
   </body>
   </html>
</xsl:template>

</xsl:stylesheet>
```

**Ejecución de la Stylesheet(hoja de estilo)**

Hay varias formas de ejecutar esta hoja de estilo, que veremos en las siguientes secciones. Puede valer la pena probar varios de los diferentes enfoques para descubrir con cuál se siente más cómodo: la familiaridad con las herramientas lo ayudará a dominar los ejemplos del resto del libro, además de convertirlo en un desarrollador XSLT más competente.

Cualquiera que sea el enfoque que utilice, la primera etapa es descargar el código de muestra para este libro del sitio web de Wrox (www.wrox.com), como se explica en la Introducción. El código está organizado por capítulos, por lo que encontrará los dos archivos `hello.xml` y `hello.xsl` en el directorio `ch01`.

Si es un desarrollador serio de XSLT, es posible que su empresa haya invertido en un entorno de desarrollo XML como XML Spy, Stylus Studio u oXygen. Todos estos productos tienen la capacidad de ejecutar hojas de estilo XSLT 2.0: XML Spy usa el procesador XSLT 2.0 de Altova (aunque también se puede configurar para ejecutar Saxon), mientras que Stylus Studio y oXygen usan Saxon. No cubriremos el uso de estos entornos de desarrollo en este libro.

**Usando el Navegador**

La forma más sencilla de ejecutar este ejemplo es simplemente cargar el archivo XML `hello.xml` en cualquier versión reciente de Internet Explorer o Firefox (haga clic con el botón derecho en el archivo y seleccione `Open With...`). El navegador reconocerá la instrucción de procesamiento `<?xml-stylesheet?>` Y la usará para buscar la hoja de estilo y ejecutarla. El resultado es una pantalla como la de la Figura 1-3.


![image](https://user-images.githubusercontent.com/23094588/114035537-78ce8100-987f-11eb-98db-e06317638873.png)

![image](https://user-images.githubusercontent.com/23094588/114035683-a0254e00-987f-11eb-849d-c3e359809f2b.png)

El archivo debe cargarse en un un Servidor para evitar el error del Cors, en Chrome la salida es:

![image](https://user-images.githubusercontent.com/23094588/114036060-06aa6c00-9880-11eb-9728-acc840fa56e7.png)![image](https://user-images.githubusercontent.com/23094588/114048115-8d644680-988a-11eb-96c1-202ad7ff14b0.png)

Podemos ejecutar este ejemplo en el navegador porque en realidad es una hoja de estilo XSLT 1.0. La mayoría de los navegadores modernos admiten el procesamiento XSLT 1.0 de esta manera, pero en el momento de redactar este artículo, ninguno es compatible con XSLT 2.0.

**Usando Saxon de Kernow**

Ejecutaremos la mayoría de los ejemplos de XSLT 2.0 en este libro usando Saxon, y una de las formas más fáciles de ejecutar Saxon es usando un interfaz gráfico llamado Kernow. Puede descargar Kernow desde http://kernowforsaxon.sourceforge.net/. Incluye los archivos JAR de Saxon, por lo que el único requisito previo es que Java esté instalado. Necesitará Java Standard Edition 6 o posterior, que puede obtener en http://java.sun.com/. (El propio Saxon funciona con JDK 1.4 o posterior, el requisito para Java SE 6 proviene de Kernow).

Para instalar Kernow, lo único que debe hacer es descomprimir el archivo de descarga en un directorio adecuado y, si está ejecutando Windows, puede iniciar el producto haciendo doble clic en el archivo `Run.bat`. En el cuadro de diálogo que aparece, seleccione la pestaña `"Single File"` y busque los archivos de origen y de hoja de estilo. Luego haga clic en Ejecutar para ejecutar la transformación. La salida es como se muestra en la Figura 1-4.

Tenga en cuenta que esta vez, el resultado se muestra en términos de HTML sin procesar. Si desea ver cómo se ve el HTML en un navegador, siempre puede guardarlo en un archivo y luego abrir el archivo en su navegador. Pero Kernow está diseñado para desarrolladores, no para usuarios finales, y como desarrollador necesita ver el HTML que ha generado. No recomendaría a nadie que haga un desarrollo XSLT serio probando directamente en un navegador, porque es difícil ver qué salió mal cuando comete un error.

![image](https://user-images.githubusercontent.com/23094588/114036819-aec03500-9880-11eb-98ab-be391063bfdd.png)

![image](https://user-images.githubusercontent.com/23094588/114053747-8429a880-988f-11eb-811d-8a9aab5399f8.png)


**Usando Saxon en Java desde la Línea de Comandos**

Si es un desarrollador de software profesional, probablemente no sea reacio a ejecutar utilidades desde la línea de comandos, que es la forma natural de probar sus hojas de estilo cuando usa Saxon "listo para usar". Los pasos son los siguientes:

1. Asegúrese de tener Java instalado en su máquina. Saxon funcionará con JDK 1.4 o posterior. Saxon es código Java puro, por lo que se ejecutará en cualquier plataforma que admita Java, pero por lo general supongo que está utilizando una máquina con Windows.

2. Descargue el procesador Saxon-B de http://sf.net/saxon. Elija la versión más reciente de Saxon-B para Java y descomprima el archivo de descarga en un directorio adecuado, por ejemplo, c: \ saxon.

3. Abra una ventana de consola estilo MSDOS (use Start

![image](https://user-images.githubusercontent.com/23094588/114037149-01015600-9881-11eb-8a92-fb69e3682edb.png)

4. Escriba lo siguiente en el símbolo del sistema:

```sh
java -jar c:\saxon\saxon9.jar -a -s:hello.xml
```

5. Admire el HTML que se muestra en la salida estándar.

Si desea ver la salida usando su navegador, simplemente guarde la salida de la línea de comando como un archivo HTML, de la siguiente manera:

```sh
java -jar c:\saxon\saxon8.jar -a -s:hello.xml -o:hello.html
```

(Usar el símbolo del sistema en Windows no es muy divertido. Si eres un fanático de Unix, instala Cygwin. La mayoría de los editores tienen la capacidad de invocar un procesador de línea de comandos que generalmente es mucho más utilizable que el proporcionado por el sistema operativo. Utilizo UltraEdit, pero hay muchas otras opciones disponibles).

**Uso del procesador XSLT de Altova**

Puede obtener el producto independiente AltovaXML en www.altova.com. La versión actual en el momento de escribir este artículo es AltovaXML 2008. Incluye procesadores XSLT 1.0 y 2.0 independientes y un motor XQuery. El producto se instala de forma predeterminada en `c:\Program Files\Altova\AltovaXML2008`. Suponiendo que este directorio está en su PATH, puede ejecutar nuestra transformación de ejemplo con la línea de comando:

```sh
AltovaXML -in hello.xml -xslt2 hello.xsl -out hello.html
```

**Usando XMLSpy**

Si ha instalado XMLSpy, use File

![image](https://user-images.githubusercontent.com/23094588/114043068-41af9e00-9886-11eb-80ce-9d79fa55665e.png)

**Usando Stylus Studio**

Stylus Studio utiliza su propio procesador XSLT integrado de forma predeterminada. Esto solo es compatible con XSLT 1.0, pero está bien para este ejemplo.

Primero abra la hoja de estilo usando File

Si desea usar XSLT 2.0 con Stylus Studio, elija la pestaña Procesador en el cuadro de diálogo Crear escenario y elija la versión más reciente de Saxon de la lista de procesadores ofrecidos (una de las características interesantes de Stylus es que puede usarlo para pruebe que su código sea portátil en una variedad de procesadores diferentes). Luego puede hacer clic en Setting . . . para seleccionar entre una gama de opciones específicas de Saxon (por ejemplo, puede elegir si desea utilizar o no el procesamiento con reconocimiento de esquema). Estos corresponden a opciones que están disponibles en la línea de comandos de Saxon.

![image](https://user-images.githubusercontent.com/23094588/114043303-76bbf080-9886-11eb-99ba-64bbdea31310.png)

**Cómo funciona**

Si ha tenido éxito al ejecutar este ejemplo, o incluso si solo quiere seguir leyendo el libro, querrá saber cómo funciona. Vamos a diseccionarlo.

```xml
<?xml version="1.0" encoding="iso-8859-1"?>
```

Este es solo el encabezado XML estándar. El punto interesante es que una hoja de estilo XSLT es en sí misma un documento XML. Tendré más que decir sobre esto más adelante en el capítulo. He usado la codificación de caracteres `iso-8859-1` (que es el nombre oficial del juego de caracteres que Microsoft a veces llama "ANSI") porque en Europa Occidental y Norteamérica es el juego de caracteres que la mayoría de los editores de texto admiten. Si tiene un editor de texto que admita UTF-8 o alguna otra codificación de caracteres, no dude en usarlo.

```xml
<xsl:stylesheet
   version="1.0"
   xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
```

Este es el encabezado estándar XSLT 1.0. En términos XML, es una etiqueta de inicio de elemento e identifica el documento como una hoja de estilo. El atributo `xmlns:xsl` es una declaración de espacio de nombres XML, que indica que el prefijo `xsl` se utilizará para los elementos definidos en la especificación W3C XSLT. XSLT hace un uso extensivo de los espacios de nombres XML, y todos los nombres de elementos definidos en el estándar tienen el prefijo de este espacio de nombres para evitar cualquier conflicto con los nombres utilizados en su documento fuente. El atributo de versión indica que la hoja de estilo está diseñada para funcionar con un procesador XSLT 1.0.

Vamonos.

```xml
<xsl:template match="/">
```

Un elemento `<xsl:template>` define una regla de plantilla que se activará cuando se procese una parte particular del documento de origen. El atributo `«match = "/"»` indica que esta regla en particular se activa justo al comienzo del procesamiento del documento fuente. Aquí `«/»` es un patrón que identifica el nodo de documento del documento: un documento XML tiene una estructura jerárquica, y de la misma manera que Unix usa el nombre de archivo especial `«/»` para indicar la raíz de un store de archivos jerárquico, XPath usa `«/»` para representar la raíz de la jerarquía de contenido XML.

```html
<html>
<head>
   <title>Today's greeting</title>
</head>
<body>
   <p><xsl:value-of select="greeting"/></p>
</body>
</html>
```

Una vez que se activa esta regla, el cuerpo de la plantilla dice qué salida generar. La mayor parte del cuerpo de la plantilla aquí es una secuencia de elementos HTML y texto que se copiarán en el archivo de salida. Hay una excepción: un elemento `<xsl:value-of>`, que reconocemos como una instrucción XSLT porque usa el namespace prefix `xsl`. Esta instrucción en particular copia el contenido textual de un nodo en el documento fuente al documento de salida. El atributo `select` del elemento especifica el nodo para el que se debe evaluar el valor. La expresión XPath `«greeting»` significa "buscar el conjunto de todos los elementos `<greeting>` que son hijos del nodo que esta regla de plantilla está procesando actualmente". En este caso, esto significa que el elemento `<greeting>` es el elemento más externo del documento fuente. La instrucción `<xsl:value-of>` luego extrae el texto de este elemento y lo copia en la salida en el lugar relevante, en otras palabras, dentro del elemento `<p>` generado.

Todo lo que queda es terminar lo que comenzamos.

```xml
</xsl:template>

</xsl:stylesheet>
```

¿Por qué querría colocar el saludo de hoy en un archivo XML separado y mostrarlo usando una hoja de estilo? Una razón es que es posible que desee mostrar el saludo de diferentes formas, según el contexto; por ejemplo, podría mostrarse de manera diferente en un dispositivo diferente, o el saludo podría depender de la hora del día. En este caso, podría escribir una hoja de estilo diferente para transformar el mismo documento fuente de una manera diferente. Esto plantea la cuestión de cómo se selecciona una hoja de estilo en tiempo de ejecución. No hay una respuesta única a esta pregunta; depende del producto que esté utilizando.

Con Saxon, usamos la opción `-a` para procesar el documento XML usando la hoja de estilo especificada en su instrucción de procesamiento `<?xml-stylesheet?>`. En cambio, simplemente podríamos haber especificado la hoja de estilo en la línea de comando:

```sh
java -jar c:\saxon\saxon8.jar -s:hello.xml -xsl:hello.xsl -o:hello.html
```

Habiendo examinado una hoja de estilo XSLT 1.0 muy simple, veamos ahora una hoja de estilo que usa características que son nuevas en XSLT 2.0.

### 1.2.4. Una Hoja de Estilo XSLT 2.0

Esta hoja de estilo es muy corta, pero se las arregla para utilizar cuatro o cinco nuevas funciones XSLT 2.0 y XPath 2.0 en el espacio de unas pocas líneas. Lo escribí en respuesta a una consulta de usuario planteada en la lista xsl en http://www.mulberrytech.com/ (un lugar excelente para conocer a otros desarrolladores XSLT con niveles de experiencia muy variados); por lo que es un problema real, no una invención. La solución XSLT 1.0 a este problema es de aproximadamente 60 líneas de código.

#### 💻 Ejemplo: Tabulación Frecuencias de Palabras

El problema se plantea simplemente: dado cualquier documento XML, producir una lista de las palabras que aparecen en su texto, dando el número de veces que aparece cada palabra, junto con su frecuencia.

**Input**

La entrada puede ser cualquier documento XML. Usaré el texto del ***Otelo de Shakespeare*** como ejemplo; se proporciona como `othello.xml` en los archivos de descarga de este libro.

**Output**

La salida requerida es un archivo XML que enumera palabras en orden decreciente de frecuencia. Si ejecuta la transformación con Kernow, la salida aparece como se muestra en la Figura 1-7.

**Stylesheet**

Aquí está la hoja de estilo que produce este resultado. Puede encontrarlo en `wordcount.xsl`.

`wordcount.xsl`

```xml
<?xml version="1.0" encoding="iso-8859-1"?>
<xsl:stylesheet
   version="2.0"
   xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

<xsl:output method="xml" indent="yes"/>

<xsl:template match="/">
  <wordcount>
    <xsl:for-each-group group-by="." select="
          for $w in //text()/tokenize(., '\W+')[.!=''] return lower-case($w)">
      <xsl:sort select="count(current-group())" order="descending"/>
      <word word="{current-grouping-key()}" frequency="{count(current-group())}"/>
    </xsl:for-each-group>
  </wordcount>
</xsl:template>

</xsl:stylesheet>
```

```xml
</xsl:for-each-group>
  </wordcount>
</xsl:template>
</xsl:stylesheet>
```

Veamos cómo funciona esto.

![image](https://user-images.githubusercontent.com/23094588/114051284-3ad85980-988d-11eb-8b4d-acbbe49474f8.png)

El elemento `<xsl:stylesheet>` introduce el espacio de nombres XSLT, como antes, y nos dice que esta hoja de estilo está diseñada para usarse con un procesador XSLT 2.0.

El elemento `<xsl:output>` solicita que se aplique una sangría a la salida XML de la hoja de estilo, lo que hace que sea mucho más fácil de leer para los humanos.

Hay un elemento `<xsl:template>`, como antes, que define el código que se ejecutará cuando se encuentre el nodo de documento del documento fuente. Esto genera un elemento `<wordcount>` en el resultado, y dentro de este pone las frecuencias de palabras.

Para comprender la instrucción `<xsl:for-each-group>`, que es nueva en XSLT 2.0, primero debemos observar su atributo de selección. Esto contiene la expresión XPath 2.0

```xml
for $w in //text()/tokenize(., '\W+')[.!=''] return lower-case($w)
```

Esto primero selecciona `«//text()»`, el conjunto de todos los nodos de texto en el árbol de entrada. Luego tokeniza cada uno de estos nodos de texto, es decir, lo divide en una secuencia de subcadenas. La tokenización se realiza aplicando la expresión regular `«\W+»`. Las expresiones regulares son nuevas en XPath 2.0 y XSLT 2.0, aunque resultarán muy familiares para los usuarios de otros lenguajes como Perl. Proporcionan al idioma una capacidad de manejo de texto muy mejorada. Esta expresión en particular, `«\W+»`, coincide con cualquier secuencia de uno o más caracteres "que no son palabras", una categoría conveniente que incluye espacios, signos de puntuación y otros separadores. Entonces, el resultado de llamar a la función `tokenize()` es una secuencia de cadenas que contiene las palabras que aparecen en el texto. Debido a que hay nodos de texto que no contienen nada de interés, el resultado también incluye algunos tokens de longitud cero, y los filtramos aplicando el predicado `«[.! = '']»`

La expresión XPath `«for»` ahora aplica la función `lower-case()` a cada una de las cadenas de esta secuencia, produciendo el equivalente en minúsculas de la palabra. (Casi todo en esta expresión XPath es nuevo en XPath 2.0: la función  `lower-case()`, la función `tokenize()`, la expresión `«for»` y, de hecho, la capacidad de manipular una secuencia de cadenas).

La hoja de estilo XSLT ahora toma esta secuencia de cadenas y le aplica la instrucción `<xsl:for-each-group>`. Esto procesa el cuerpo de la instrucción `<xsl:for-each-group>` una vez para cada grupo de elementos seleccionados, donde un grupo se identifica como aquellos elementos que tienen un valor común para una clave de agrupación. En este caso, la clave de agrupación se escribe como `«group-by="."»`, Lo que significa que los valores (las palabras) se agrupan según su propio valor. (En otra aplicación, podríamos haber elegido agruparlos por su longitud o por su letra inicial). Entonces, el cuerpo de la instrucción se ejecuta una vez para cada palabra distinta, y la instrucción `<xsl:sort>` nos dice que clasifiquemos los grupos en orden descendente del tamaño de los grupos (es decir, el número de veces que aparece cada palabra). Para cada uno de los grupos, generamos un elemento `<word>` con dos atributos: un atributo es el valor que usamos como clave de agrupación; el otro es el número de elementos del grupo.

#### 💻 Ejemplo: Ejecución Propia

![image](https://user-images.githubusercontent.com/23094588/114053179-01085280-988f-11eb-9571-9023907e0ac1.png)



## 1.3. El lugar de XSLT en la familia XML
### 1.3.1. Objetos de formato XSLT y XSL
### 1.3.2. XSLT y XPath
### 1.3.3. Espacios de nombres XSLT y XML
### 1.3.4. XSLT y CSS
### 1.3.5. Esquemas XSLT y XML
### 1.3.6. XSLT y XQuery
## 1.4. La historia de XSL
### 1.4.1. Prehistoria
### 1.4.2. La primera propuesta XSL
### 1.4.3. sajón
### 1.4.4. Más allá de XSLT 1.0
### 1.4.5. Convergencia con XQuery
### 1.4.6. El desarrollo de XSLT 2.0 y XPath 2.0
## 1.5. XSLT 2.0 como lenguaje
### 1.5.1. Uso de sintaxis XML
### 1.5.2. Sin efectos secundarios
### 1.5.3. Basado en reglas
### 1.5.4. Tipos basados en esquema XML
### 1.5.5. Un sistema de dos idiomas: XSLT y XPath
## 1.6. Resumen
