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

### 🔴 💻 "Hello, world!" XSLT Stylesheet

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

### 🔴 💻 Ejemplo: Tabulación Frecuencias de Palabras

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

![image](https://user-images.githubusercontent.com/23094588/114053179-01085280-988f-11eb-9571-9023907e0ac1.png)

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

## 1.3. El lugar de XSLT en la familia XML

XSLT es una publicación del World Wide Web Consortium (W3C) y encaja en la familia de estándares XML, la mayoría de los cuales también son desarrollados por W3C. En esta sección intentaré explicar la relación, a veces confusa, de XSLT con otros estándares y especificaciones relacionados.

### 1.3.1. Objetos de formato XSLT y XSL

XSLT nació como parte de un lenguaje más grande llamado ***XSL (Extensible Stylesheet Language - Lenguaje de hoja de estilo extensible)***. Como su nombre lo indica, XSL fue (y está) destinado a definir el formato y la presentación de documentos XML para su visualización en pantalla, en papel o en la palabra hablada. A medida que avanzaba el desarrollo de XSL, quedó claro que, por lo general, se trataba de un proceso de dos etapas: primero, una transformación estructural, en la que los elementos se seleccionan, agrupan y reordenan; y luego un proceso de formateo en el que los elementos resultantes se renderizan como tinta sobre papel o píxeles en la pantalla. Se reconoció que estas dos etapas eran bastante independientes, por lo que XSL se dividió en dos partes: XSLT para definir transformaciones; y "el resto" - que todavía se llama oficialmente XSL, aunque la mayoría de la gente prefiere llamarlo ***XSL-FO (XSL Formatting Objects)*** - para la etapa de formateo.

XSL-FO no es más que otro vocabulario XML, en el que los objetos descritos son áreas de la página impresa y sus propiedades. Dado que este es solo otro vocabulario XML, XSLT no necesita capacidades especiales para generarlo como su salida. XSL-FO está fuera del alcance de este libro. Es un tema importante. XSL-FO ofrece maravillosas instalaciones para lograr una salida tipográfica de alta calidad de sus documentos. Sin embargo, para muchas personas, traducir documentos a HTML para presentarlos en un navegador estándar es bastante bueno, y eso se puede lograr usando XSLT solo, o si es necesario, usando XSLT junto con hojas de estilo en cascada (CSS o CSS2), que yo volverá en breve.

Es mejor evitar el término XSL, porque se usa con muchos significados diferentes. Es el nombre correcto para los objetos de formato XSL, pero muchas personas lo usan para referirse a XSLT. También se utiliza en documentos de Microsoft más antiguos para referirse a su lenguaje WD-xsl obsoleto, que se emitió como parte de Internet Explorer 4 antes de que XSLT se estandarizara en 1999.

### 1.3.2. XSLT y XPath

A mitad del desarrollo de XSLT 1.0, se reconoció que había una superposición significativa entre la sintaxis de expresión en XSLT para seleccionar partes de un documento y el lenguaje XPointer que se estaba desarrollando para vincular de un documento a otro. Para evitar tener dos lenguajes de expresión separados pero superpuestos, los dos comités decidieron unir fuerzas y definir un único lenguaje, XPath, que serviría para ambos propósitos. XPath 1.0 se publicó el mismo día que XSLT 1.0, 16 de noviembre de 1999.

XPath actúa como un sublenguaje dentro de una hoja de estilo XSLT. Una expresión XPath puede usarse para cálculos numéricos o manipulaciones de cadenas, o para probar condiciones booleanas, pero su uso más característico (y el que le da su nombre) es identificar partes del documento de entrada a procesar. Por ejemplo, la siguiente instrucción genera el precio promedio de todos los libros en el documento de entrada:

```xsl
<xsl:value-of select="avg(//book/@price)"/>
```

Aquí, el elemento `<xsl:value-of>` es una instrucción definida en el estándar XSLT, que hace que se escriba un valor en el documento de salida. El atributo `select` contiene una expresión XPath, que calcula el valor a escribir: específicamente, el valor promedio de los atributos de precio en todos los elementos `<book>`. (La función `avg()` también es nueva en XPath 2.0).

Después de su publicación, la especificación XPath adquirió cada vez más vida propia, separada de XSLT. Varias implementaciones de DOM (incluida la de Microsoft) le permitieron seleccionar nodos dentro de una estructura de árbol DOM, utilizando un método como `selectNodes(XPath)`, y esta característica ahora está incluida en la versión actual del estándar, DOM3. Los subconjuntos de XPath se utilizan dentro del lenguaje de esquema XML y en XForms para definir las condiciones de validación, y los enlaces de XPath a otros lenguajes como Perl se están multiplicando. Quizás lo más importante de todo es que los diseñadores de XQuery decidieron hacer de su lenguaje un superconjunto puro de XPath. El lenguaje también ha resultado interesante para los académicos, y se han publicado varios artículos analizando su semántica, lo que proporciona la base para implementaciones optimizadas.

### 1.3.3. Namespaces XSLT y XML

XSLT está diseñado sobre la base de que los ***XML namespaces*** son una parte esencial del estándar XML. Entonces, cuando el estándar XSLT se refiere a un documento XML, siempre significa un documento XML que cumple con la especificación de espacios de nombres XML, que se puede encontrar en http://www.w3.org/TR/REC-xml-names.

Los Namespaces juegan un papel importante en XSLT. Su propósito es permitirle mezclar etiquetas de dos vocabularios diferentes en el mismo documento XML. Ya hemos visto cómo una hoja de estilo puede mezclar elementos del vocabulario de destino (por ejemplo, HTML o XSL-FO) con elementos que actúan como instrucciones XSLT. Aquí hay un recordatorio rápido de cómo funcionan los Namespaces:

* Los Namespaces se identifican mediante un identificador uniforme de recursos (URI). Esto puede tomar varias formas. Una forma es la URL familiar, por ejemplo, http://www.wrox.com/namespace. Otra forma, no completamente estandarizada pero que se usa en algunos vocabularios XML, es una URN, por ejemplo, urn:biztalk-org:biztalk:biztalk_1. La forma detallada de la URI no importa, pero es una buena idea elegir una que sea única. Una buena forma de lograrlo es utilizar el nombre de dominio de su propio sitio web. Pero no dejes que esto te confunda y te haga pensar que debe haber algo en el sitio web para que apunte el URI. El URI del espacio de nombres es simplemente una cadena que ha elegido para que sea diferente de los URI del namespace de otras personas; no es necesario que apunte a nada.

* La última versión, XML Namespaces 1.1, le permite utilizar un Identificador de recursos internacional (IRI) en lugar de un URI. La principal diferencia es que permite caracteres de cualquier alfabeto (por ejemplo, chino); ya no se limita a ASCII. En la práctica, la mayoría de los analizadores XML siempre le han permitido utilizar cualquier carácter que desee en un URI de namespaces.

* Dado que los URI del namespace suelen ser bastante largos y utilizan caracteres especiales como `«/»`, no se utilizan en su totalidad como parte de los nombres de los elementos y atributos. En su lugar, a cada namespace utilizado en un documento se le puede asignar un apodo corto, y este apodo se utiliza como prefijo de los nombres de los elementos y atributos. No importa qué prefijo elija, porque el nombre real del elemento o atributo está determinado solo por su URI de espacio de nombres y su nombre local (la parte del nombre después del prefijo). Por ejemplo, todos mis ejemplos usan el prefijo `xsl` para referirse al URI del espacio de nombres http://www.w3.org/1999/XSL/Transform, pero también podría usar el prefijo `xslt`, siempre que lo use de manera consistente.

* Para los nombres de elementos, también puede declarar un URI de espacio de nombres predeterminado, que se asociará con nombres de elementos sin prefijo. Sin embargo, el URI del espacio de nombres predeterminado no se aplica a los nombres de atributo sin prefijo.

Un prefijo de namespace se declara usando un pseudo-atributo especial dentro de cualquier etiqueta de inicio de elemento, con la forma:

```xml
xmlns:prefix = "namespace-URI"
```

Esto declara un prefijo de namespace, que se puede usar para el nombre de ese elemento, para sus atributos y para cualquier elemento o nombre de atributo contenido en ese elemento. El namespace predeterminado, que se usa para elementos que no tienen prefijo (pero no para atributos), se declara de manera similar usando un pseudo-atributo:

```xml
xmlns = "namespace-URI"
```

XML Namespaces 1.1 se convirtió en una recomendación el 4 de febrero de 2004, y la especificación XSLT 2.0 prevé que los procesadores XSLT funcionen con esta versión, aunque no es obligatorio. Aparte del cambio en gran parte cosmético de URI a IRIs mencionado anteriormente, la principal innovación es la capacidad de anular la declaración de un namespace, utilizando la sintaxis de la forma `«xmlns:prefix=""»`. Esto está especialmente diseñado para aplicaciones como la mensajería SOAP, donde un documento de carga útil XML se envuelve en un sobre XML para su transmisión. Sin las declaraciones de namespace, existe una tendencia a que los namespaces utilizados en el sobre SOAP se adhieran al XML de carga útil cuando se quita del sobre(envelope), lo que puede causar problemas; por ejemplo, puede invalidar una firma digital adjunta al documento.

### 1.3.4. XSLT y CSS

¿Por qué hay dos lenguajes de hojas de estilo, XSL (es decir, XSLT plus XSL Formatting Objects) y hojas de estilo en cascada (CSS y CSS2)?

Es justo decir que en un mundo ideal habría un solo lenguaje en este rol, y que la razón por la que hay dos es que nadie fue capaz de inventar algo que lograra la simplicidad y economía de CSS para hacer cosas simples, combinadas con el poder de XSL para hacer cosas más complejas.

CSS se utiliza principalmente para renderizar HTML, pero también se puede utilizar para renderizar XML directamente, definiendo las características de visualización de cada elemento XML. Sin embargo, tiene serias limitaciones. No puede reordenar los elementos en el documento de origen, no puede agregar texto o imágenes, no puede decidir qué elementos deben mostrarse y cuáles omitirse, tampoco puede calcular totales o promedios o números de secuencia. En otras palabras, solo se puede utilizar cuando la estructura del documento de origen ya está muy cerca de la forma de visualización final.

Dicho esto, CSS es simple de escribir y es muy económico en recursos de máquina. No reordena el documento, por lo que no necesita crear una representación de árbol del documento en la memoria, y puede comenzar a mostrar el documento tan pronto como se reciba el primer texto a través de la red. Quizás, lo más importante de todo, CSS es muy simple de escribir para los autores de HTML, sin conocimientos de programación. En comparación, XSLT es mucho más potente, pero también consume mucha más memoria y potencia del procesador, además de presupuesto de formación.

A menudo es apropiado usar ambas herramientas juntas. Use XSLT para crear una representación del documento que esté cerca de su forma final, en el sentido de que contiene el texto correcto en el orden correcto, y luego use CSS para agregar los toques finales, seleccionando tamaños de fuente, colores, etc. Normalmente, haría el procesamiento XSLT en el servidor y el procesamiento CSS en el cliente (en el navegador); por lo tanto, otra ventaja de este enfoque es que reduce la cantidad de datos enviados por la línea, lo que debería mejorar el tiempo de respuesta para sus usuarios y posponer el próximo aumento costoso del ancho de banda.

### 1.3.5. Schemas XSLT y XML

Uno de los mayores cambios en XSLT 2.0, y uno de los más controvertidos, es la integración de XSLT con el lenguaje de esquema XML. XML Schema proporciona un reemplazo para DTD como una forma de especificar las restricciones estructurales que se aplican a una clase de documentos; a diferencia de las DTD, un esquema XML puede regular el contenido del texto, así como el anidamiento de los elementos y atributos. Muchos de los vocabularios de la industria que se utilizan para definir los estándares de intercambio XML se especifican mediante definiciones de esquemas XML. Por ejemplo, varios de los vocabularios XML para describir música, a los que aludí anteriormente en este capítulo, tienen un esquema XML para definir sus reglas, y este esquema puede usarse para verificar la conformidad de documentos individuales con el estándar en cuestión.

Cuando escribe una hoja de estilo, debe hacer suposiciones sobre la estructura de los documentos de entrada que está diseñada para procesar y la estructura de los documentos de resultado para la que está diseñada. Con XSLT 1.0, estos supuestos estaban implícitos; no había una forma formal de establecer los supuestos en la propia hoja de estilo. Como resultado, si intenta aplicar una hoja de estilo al tipo incorrecto de documento de entrada, el resultado generalmente será basura.

La idea de vincular XSLT y XML Schema fue impulsada por dos consideraciones principales:

* En principio, debería haber beneficios de ingeniería de software si un programa (y una hoja de estilo es de hecho un programa) hace afirmaciones explícitas sobre sus entradas y salidas esperadas. Estas afirmaciones pueden conducir a una detección de errores mejor y más rápida, lo que a menudo permite informar errores en el momento de la compilación que, de lo contrario, solo se informarían la primera vez que se aplicó la hoja de estilo a algunos datos de prueba que ejercieron una parte particular del código.

* Cuanta más información esté disponible para un procesador XSLT en tiempo de compilación, más potencial tiene para generar código óptimo, dando una ejecución más rápida y un mejor uso de la memoria.

Entonces, ¿por qué la controversia? Esto se debe principalmente a que el esquema XML en sí mismo es menos que universalmente popular. Es una especificación extremadamente compleja que es muy difícil de leer, y cuando descubres lo que dice, parece estar llena de reglas que parecen artificiales e inconsistentes. Al mismo tiempo, se las arregla para ser especificado en un lenguaje muy formal y, sin embargo, tiene un número preocupantemente alto de errores que se han corregido a través de erratas publicadas. Aunque hay buenos libros que presentan el esquema XML de una manera más legible, lo logran pasando por alto las complicaciones, lo que significa que los mensajes de error que recibe cuando hace algo mal pueden ser extremadamente oscuros. Como resultado, ha habido una cantidad significativa de soporte para un lenguaje de esquema alternativo, Relax NG, que fue co-desarrollado por el diseñador de XSLT y XPath, James Clark, y es ampliamente considerado como un enfoque mucho más elegante. .

Los grupos de trabajo XSL y XQuery respondieron a estas inquietudes asegurándose de que el soporte para el esquema XML fuera opcional, tanto para los implementadores como para los usuarios. Esto ha silenciado en gran medida las objeciones.

Las señales son que XML Schema llegó para quedarse, le guste o no a la gente. Cuenta con el respaldo de los principales proveedores de software, como IBM, Oracle y Microsoft, y ha sido adoptado por la mayoría de las organizaciones e industrias de usuarios más importantes. Y como tantas cosas que el mundo de las tecnologías de la información ha adoptado como estándares, puede que sea imperfecto, pero en realidad funciona. Mientras tanto, para simplificar la situación de manera bastante cruel, Relax NG está asumiendo el papel de Apple Mac: la elección de los entendidos que juzgan un diseño por su calidad intrínseca en lugar de por un análisis de costo-beneficio a sangre fría.

Como ya he mencionado, el W3C no es una organización a la que le guste dejar florecer mil flores. No se trata de una organización general flexible en la que cada grupo de trabajo es libre de hacer lo suyo. Existen procesos sólidos que garantizan que los grupos de trabajo cooperen y se esfuercen por reconciliar sus diferencias. Por lo tanto, existe la determinación de hacer que todas las especificaciones funcionen correctamente juntas, y el mensaje era que si XML Schema tenía sus problemas, la gente debería trabajar en conjunto para solucionarlos. XSLT y XML Schema provienen del mismo establo, por lo que se esperaba que trabajaran juntos. Y ahora que las especificaciones están terminadas y los productos están disponibles, creo que los usuarios están comenzando a descubrir que pueden trabajar juntos de manera beneficiosa.

El Capítulo 4 proporciona una descripción general de cómo se integran las hojas de estilo y los esquemas en XSLT 2.0, y el Capítulo 19 proporciona un ejemplo práctico de una aplicación que utiliza esta capacidad. Cuando desarrollé por primera vez esta aplicación para el libro (lo que hice al mismo tiempo que desarrollaba el soporte subyacente en Saxon), me sorprendió gratamente ver que realmente estaba obteniendo beneficios de la integración. En el nivel más simple, me gustó mucho la retroalimentación inmediata que recibe cuando una hoja de estilo genera una salida que no se ajusta al esquema del documento de resultado, con mensajes de error que apuntan directamente a la línea ofensiva en la hoja de estilo. Esta makes para un ciclo de depuración mucho más rápido que el antiguo enfoque de poner el archivo de salida terminado a través de un validador de esquema como una operación completamente separada.

### 1.3.6. XSLT y XQuery

XQuery es una especificación separada de W3C, diseñada para permitir la consulta de datos en documentos XML. Puede operar en documentos individuales o en colecciones que contienen millones de documentos almacenados en una base de datos XML.

Funcionalmente, XQuery ofrece un subconjunto de las capacidades de XSLT. Puede considerarlo como XSLT sin las reglas de la plantilla y sin algunas de las características adicionales, como la capacidad de agrupar, dar formato a fechas y horas, o importar módulos y anularlos selectivamente. Sin embargo, sería un error pensar que al ser un lenguaje más pequeño, XQuery es un pariente pobre. La relativa simplicidad de XQuery hace que sea más difícil escribir aplicaciones grandes y complejas, pero trae dos ventajas significativas: el lenguaje es más fácil de aprender, especialmente para aquellos que provienen de SQL, y es más fácil de optimizar, especialmente cuando que se ejecuta en gigabytes de datos precargados y preindexados en una base de datos XML.

XQuery tiene XPath 2.0 como subconjunto. Esto lo convierte en un miembro de la misma familia que XSLT. Los dos idiomas tienen mucho en común, lo más importante es su sistema de tipos. No hay instalaciones formales en las especificaciones del W3C que permitan que XSLT y XQuery se mezclen en una sola aplicación, pero debido a que los modelos de procesamiento están tan estrechamente alineados, muchas implementaciones permiten llamar a un idioma desde el otro. De hecho, Saxon implementa ambos lenguajes como sintaxis de superficie diferentes para el mismo motor de procesamiento subyacente.

Hay algunas aplicaciones para las que XSLT es definitivamente más adecuado, en particular la publicación de documentos. Hay otros en los que XQuery es la única opción sensata, en particular, la búsqueda de datos en grandes bases de datos XML. Existe una tercera clase de aplicaciones, especialmente la conversión de mensajes, en las que cualquiera de los dos idiomas hará el trabajo y donde la elección depende en gran medida de las preferencias personales. Mi consejo sería usar XQuery si es una aplicación muy pequeña y XSLT si es más grande, en gran parte porque, en mi experiencia, es más fácil escribir código XSLT que se adapte al cambio y se pueda reutilizar en diferentes aplicaciones.

## 1.4. La historia de XSL

Como la mayoría de los estándares de la familia XML, XSLT fue desarrollado por el World Wide Web Consortium (W3C), una coalición de empresas orquestada por Tim Berners-Lee, el inventor de la Web. Hay una página interesante sobre la historia de XSL y propuestas de estilo en general, en http://www.w3.org/Style/History/.

Escribir historia es un asunto complicado. Sharon Adler, presidenta del Grupo de Trabajo XSL, me dice que sus recuerdos de eventos son muy diferentes de la forma en que los describo. Esto solo demuestra que el registro documental es una instantánea muy cruda de lo que la gente realmente estaba pensando y hablando. Desafortunadamente, sin embargo, es todo lo que tenemos.

### 1.4.1. Prehistoria

HTML fue concebido originalmente por Berners-Lee (www.w3.org/MarkUp/draft-ietf-iiir-html-01.txt) como un conjunto de etiquetas para marcar la estructura lógica de un documento; títulos, párrafos, enlaces, citas, secciones de código y similares. Pronto, la gente quería tener más control sobre el aspecto del documento; querían lograr el mismo control sobre la apariencia de la publicación entregada que tenían con la impresión y el papel. Entonces, HTML adquirió cada vez más etiquetas y atributos para controlar la presentación; fuentes, márgenes, tablas, colores y todo lo demás que siguió. A medida que evolucionó, los documentos que se publicaban se volvieron cada vez más dependientes del navegador, y se vio que los objetivos originales de simplicidad y universalidad comenzaban a desvanecerse.

El remedio fue ampliamente visto como una separación entre el contenido y la presentación. Este no era un concepto nuevo; se había desarrollado bien durante la década de 1980s en el desarrollo del ***Standard Generalized Markup Language (SGML)***.

Así como XML se derivó como un subconjunto muy simplificado de SGML, XSLT tiene sus orígenes en un estándar basado en SGML llamado ***DSSSL (Document Style Semantics and Specification Language)***. DSSSL (pronunciado *Dissel*) se desarrolló principalmente para satisfacer la necesidad de un lenguaje estándar independiente del dispositivo para definir la reproducción de salida de documentos SGML, particularmente para presentaciones tipográficas de alta calidad. SGML existió durante mucho tiempo antes de que apareciera DSSSL a principios de la década de 1990, pero hasta entonces el lado de la producción se había manejado utilizando herramientas patentadas y, a menudo, extremadamente caras, orientadas a impulsar fotocomponedoras igualmente caras, de modo que la tecnología realmente fue adoptada solo por los grandes editoriales.

Michael Sperberg-McQueen y Robert F. Goldstein presentaron un artículo influyente en la conferencia WWW '94 en Chicago bajo el título *A Manifesto for Adding SGML Intelligence to the World-Wide Web*. Puede encontrarlo en http://tigger.uic.edu/~cmsmcq/htmlmax.html.

Los autores presentaron un conjunto de requisitos para un lenguaje de hoja de estilo, que es una declaración tan buena como cualquiera de los objetivos que los diseñadores de XSL estaban tratando de cumplir. Al igual que con otras propuestas de esa época, el concepto de un lenguaje de transformación separado aún no había aparecido, y una gran parte del artículo está dedicado a las capacidades de interpretación del lenguaje. Sin embargo, existen muchas ideas formativas, incluido el concepto de procesamiento alternativo para hacer frente a situaciones en las que las características particulares no están disponibles en el entorno actual.

Vale la pena citar aquí algunos extractos del artículo:

Idealmente, el lenguaje de la hoja de estilo debería ser declarativo, no procedimental, y debería permitir que las hojas de estilo exploten al máximo la estructura de los documentos SGML. Los estilos deben poder variar con la ubicación estructural del elemento: los párrafos dentro de las notas pueden tener un formato diferente al de los párrafos del texto principal. Los estilos deben poder variar con los valores de atributo del elemento en cuestión: una cita de tipo "display" puede necesitar un formato diferente de una cita de tipo "inline". . .

Al mismo tiempo, el lenguaje tiene que ser razonablemente fácil de interpretar de manera procedimental: implementar el lenguaje de la hoja de estilo no debe convertirse en el mayor desafío en la implementación de un cliente web.

La semántica debe ser aditiva: los usuarios deben poder crear nuevas hojas de estilo agregando nuevas especificaciones a alguna hoja de estilo existente (posiblemente estándar). Esto no debería requerir copiar toda la hoja de estilo base; en su lugar, el usuario debe poder almacenar localmente solo los cambios del usuario en la hoja de estilo estándar, y deben agregarse en el momento de la exploración. Esto es particularmente importante para admitir modificaciones locales de DTD estándar.

Sintácticamente, el lenguaje de la hoja de estilo debe ser muy simple, preferiblemente trivial de analizar. Una posibilidad obvia: formular el lenguaje de la hoja de estilo como un DTD SGML, de modo que cada hoja de estilo sea un documento SGML. Dado que el navegador ya sabe cómo analizar SGML, no se necesitará ningún esfuerzo adicional.

Recomendamos encarecidamente que se utilice un subconjunto de DSSSL para formular hojas de estilo para su uso en la World Wide Web; Con la finalización del trabajo de estándares en DSSSL, no hay razón para que ninguna comunidad invente su propio lenguaje de hoja de estilo desde cero. El estándar DSSSL completo puede ser demasiado exigente para implementarlo en su totalidad, pero incluso si eso resulta cierto, solo proporciona un argumento para definir un subconjunto de DSSSL que debe ser compatible, no un argumento para desarrollar el nuestro. A diferencia de las especificaciones de elaboración casera, un subconjunto de un estándar viene con una ruta de crecimiento predefinida automáticamente. Esperamos trabajar en la formulación de un subconjunto utilizable e implementable de DSSSL para su uso en hojas de estilo WWW e invitamos a todas las partes interesadas a unirse al esfuerzo.

A finales de 1995, se llevó a cabo en París un taller patrocinado por el W3C sobre lenguajes de hojas de estilo. En vista del papel posterior de James Clark como editor de la Recomendación XSLT, es interesante leer las notas de su contribución sobre los objetivos de DSSSL,que se puede encontrar en http://www.w3.org/Style/951106_Workshop/report1.html#clark.

Aquí hay algunos párrafos seleccionados de estas notas:

DSSSL contiene un lenguaje de transformación y un lenguaje de formato. Originalmente, la transformación era necesaria para hacer posibles ciertos tipos de estilos (como tablas de contenido). El lenguaje de consulta ahora se encarga de eso, pero el lenguaje de transformación sobrevive porque es útil por derecho propio.

El lenguaje es estrictamente declarativo, lo que se logra mediante la adopción de un subconjunto funcional de Scheme. Los editores de hojas de estilo interactivos deben ser posibles.

Una hoja de estilo DSSSL describe con mucha precisión una función de SGML a un árbol de objetos de flujo. Permite combinar hojas de estilo parciales ("en cascada" como en CSS): alguna regla puede anular otra regla, basada en prioridades implícitas y explícitas, pero no hay combinación entre estilos en conflicto.

James Clark cerró su charla con el comentario:

¡Crear un buen lenguaje de estilo extensible es difícil!

Uno sospecha que el esfuerzo de editar la Recomendación XSLT 1.0 no le hizo cambiar de opinión.

### 1.4.2. La primera propuesta XSL

Después de estas primeras discusiones, el W3C estableció una actividad formal para crear una propuesta de lenguaje de hoja de estilo. El mandato de este grupo especificó que debería basarse en DSSSL.

Como resultado de esta actividad surgió la primera propuesta formal para XSL, con fecha del 27 de agosto de 1997. Titulada ***A Proposal for XSL***, enumera 11 autores: James Clark (que trabaja para él mismo), cinco de Microsoft, tres de Imso Corporation, uno de ArborText, y uno (Henry Thompson) de la Universidad de Edimburgo. El documento se puede encontrar en http://www.w3.org/TR/NOTE-XSL.html.

Vale la pena leer la sección que describe el propósito del lenguaje.

XSL es un lenguaje de hoja de estilo diseñado para la comunidad web. Proporciona funcionalidad más allá de CSS (por ejemplo, reordenación de elementos). Esperamos que CSS se utilice para mostrar documentos XML estructurados de forma sencilla y XSL cuando se requieran capacidades de formato más potentes o para formatear información altamente estructurada, como datos estructurados XML o documentos XML que contienen datos estructurados.

Los autores web crean contenido en tres niveles diferentes de sofisticación, según se indica a continuación:

* markup: se basa únicamente en una sintaxis declarativa

* script: además, utiliza "fragmentos" de código para comportamientos más complejos

* program: utiliza un lenguaje de programación completo

XSL está destinado a ser accesible para el usuario de nivel de "marcado" al proporcionar una solución declarativa para la mayoría de los requisitos de descripción y representación de datos. Las tareas menos comunes se adaptan a través de un elegante escape a un entorno de secuencias de comandos familiar. Este enfoque es familiar para la comunidad de publicación web, ya que se basa en el entorno HTML/JavaScript.

Las poderosas capacidades proporcionadas por XSL permiten:

* formato de los elementos de origen en función de la ascendencia / descendencia, la posición y la unicidad
* la creación de construcciones de formato que incluyen texto y gráficos generados
* la definición de macros de formato reutilizables
* hojas de estilo independientes de la dirección de escritura
* conjunto extensible de objetos de formato

Luego, los autores explicaron cuidadosamente por qué habían considerado necesario divergir de DSSSL y describieron por qué se creía necesario un lenguaje separado de CSS (Cascading Style Sheets).

Luego establecieron algunos principios de diseño:

* XSL debería poder utilizarse directamente a través de Internet.

* XSL debe expresarse en sintaxis XML.

* XSL debe proporcionar un lenguaje declarativo para realizar todas las tareas de formato comunes.

* XSL debería proporcionar un "escape" a un lenguaje de secuencias de comandos para dar cabida a tareas de formato más sofisticadas y permitir la extensibilidad y la completitud.

* XSL será un subconjunto de DSSSL con la enmienda propuesta. (*Como XSL ya no era un subconjunto de DSSSL, astutamente propusieron enmendar DSSSL para que se convirtiera en un superconjunto de XSL*).

* Debería ser posible un mapeo mecánico de una hoja de estilo CSS en una hoja de estilo XSL.

* XSL debe estar informado por la experiencia del usuario con el lenguaje de la hoja de estilo FOSI.

* El número de funciones opcionales en XSL debe mantenerse al mínimo.

* Las hojas de estilo XSL deben ser legibles y razonablemente claras.

* El diseño XSL debe prepararse rápidamente.

* Las hojas de estilo XSL serán fáciles de crear.

* La concisión en el marcado XSL es de mínima importancia.

Como declaración de requisitos, esto no se encuentra entre los mejores. No se lee como el tipo de lista que obtiene cuando habla con los usuarios y averigua lo que necesitan. Es mucho más el tipo de lista que los diseñadores escriben cuando saben lo que quieren producir, incluidas algunas concesiones políticas a las personas que podrían presentar objeciones. Pero si quiere entender por qué XSLT se convirtió en el lenguaje que lo hizo, esta lista es sin duda una prueba del pensamiento.

El lenguaje descrito en esta primera propuesta contiene muchos de los conceptos clave de XSLT cuando finalmente surgió, pero la sintaxis es prácticamente irreconocible. Ya estaba claro que el lenguaje debería basarse en plantillas que manejaran nodos en el documento de origen que coincidieran con un patrón definido, y que el lenguaje debería estar libre de efectos secundarios, para permitir "la representación y el manejo progresivos de documentos grandes". Exploraré la importancia de este requisito con más detalle en la página 34 y discutiré sus implicaciones en la forma en que se diseñan las hojas de estilo en el Capítulo 17. La idea básica es que si una hoja de estilo se expresa como una colección de operaciones completamente independientes, cada una de las que no tiene ningún efecto externo más que generar parte de la salida a partir de su entrada (por ejemplo, no puede actualizar las variables globales), entonces es posible generar cualquier parte de la salida de forma independiente si esa parte particular de la entrada cambia. Si el lenguaje XSLT realmente logra este objetivo sigue siendo una pregunta abierta.

El primer Borrador de Trabajo de XSL (que no debe confundirse con la Propuesta) se publicó el 18 de agosto de 1998, y el lenguaje comenzó a tomar forma, convergiendo gradualmente hacia la forma final que tomó en la Recomendación del 16 de noviembre de 1999 a través de una serie de Borradores de trabajo, cada uno de los cuales hizo cambios radicales, pero mantuvo intactos los principios de diseño originales.

> **NOTA**
>
> Una recomendación es el documento más definitivo producido por el W3C. Técnicamente, no es un estándar, porque los estándares solo pueden ser publicados por organizaciones de estándares aprobadas por el gobierno. Pero a menudo me referiré a él de manera vaga como "el estándar" en este libro.

### 1.4.3. Sajón

En este punto, podría ser una buena idea aclarar cómo me involucré en la historia. En 1998 trabajaba para el fabricante británico de ordenadores ICL, que forma parte de Fujitsu. Fujitsu, en Japón, había desarrollado un sistema de base de datos de objetos, que luego se comercializó como Jasmine, y yo estaba usando esta tecnología para crear aplicaciones de administración de contenido para grandes editoriales. Desarrollamos algunas aplicaciones grandes exitosas, pero descubrimos que era demasiado complejo para las personas que querían algo en seis semanas en lugar de seis meses. Así que me pidieron que mirara qué podíamos hacer con XML, que estaba apareciendo en el horizonte.

Llegué a la conclusión de que XML parecía algo bueno, pero que no había ningún software. Así que desarrollé las primeras versiones de Saxon para proporcionar una demostración de prueba de concepto. En esa etapa, Saxon era solo una biblioteca Java, no un procesador XSLT, pero a medida que se desarrollaban los estándares XSL, descubrí que mis propias ideas convergían cada vez más con lo que estaba haciendo el grupo de trabajo del W3C, y comencé a implementar el lenguaje tal como estaba. siendo especificado. ICL había decidido que sus recursos de marketing se distribuían en demasiados productos, por lo que la dirección tomó la imaginativa decisión de hacer que la tecnología estuviera disponible como código abierto. Diecisiete días después de que se publicara la especificación XSLT 1.0 en noviembre de 1999, anuncié la primera implementación conforme. Y el día que se publicó, comencé a trabajar en la primera edición de este libro.

Cuando se publicó el libro, el grupo de trabajo XSL me invitó a unirme y participar en el desarrollo de XSLT 1.1. Inicialmente, al estar basado en el Reino Unido y con poco tiempo disponible para el trabajo, mi participación fue bastante esporádica. Pero a principios de 2001 cambié de trabajo y me uní a Software AG, que quería que asumiera un papel completo en el trabajo del W3C. Al año siguiente, James Clark se retiró del Grupo de Trabajo y yo me puse en su lugar como editor.

La razón por la que estoy explicando esta secuencia de eventos es que espero que les ayude a comprender el punto de vista desde el que está escrito este libro. Cuando escribí la primera edición, era un extraño y me sentí completamente libre de criticar la especificación cuando lo creyera necesario. He tratado de mantener un enfoque objetivo en la presente edición, pero como editor de la especificación de lenguaje es mucho más difícil ser imparcial. He tratado de mantener el equilibrio: no sería justo usar el libro como plataforma para impulsar mis puntos de vista sobre los de mis colegas del grupo de trabajo, pero al mismo tiempo, no he hecho ningún esfuerzo por ser a la defensiva sobre las decisiones que habría tomado de manera diferente si me las hubieran dejado.

Software AG continuó apoyando mi participación en el trabajo del W3C (en el grupo XQuery y en el grupo XSL), junto con el desarrollo de Saxon y la redacción de este libro, hasta febrero de 2004, momento en el que dejé para establecer mi propia empresa, Saxonica.

### 1.4.4. Más allá de XSLT 1.0

Después de que se publicó XSLT 1.0, el Grupo de Trabajo XSL responsable del lenguaje decidió dividir los requisitos para las mejoras en dos categorías: XSLT 1.1 estandarizaría una pequeña cantidad de características urgentes que los proveedores ya habían considerado necesarias para agregar a sus productos como extensiones, mientras que XSLT 2.0 manejaría los requisitos más estratégicos que necesitaban más investigación.

Un borrador de trabajo de XSLT 1.1 se publicó el 12 de diciembre de 2000. Describía tres mejoras principales a la especificación XSLT 1.0: la capacidad de producir múltiples documentos de salida, la capacidad de usar árboles temporales para crear una transformación de múltiples pasadas y enlaces estándar a funciones de extensión escritas en Java o ECMAScript.

Por varias razones, XSLT 1.1 nunca pasó de la etapa de borrador de trabajo. Esto se debió en parte a la controversia en torno a los enlaces del lenguaje Java, pero más en particular porque se estaba volviendo más claro que XSLT 2.0 sería una revisión bastante radical del lenguaje, y el Grupo de Trabajo no quería hacer nada en 1.1 que entrara en juego. la forma de lograr las metas 2.0. Hubo sentimientos, por ejemplo, de que la facilidad para los árboles temporales podría perjudicar la capacidad de soportar secuencias en 2.0, un temor que resultó ser en gran parte infundado.

### 1.4.5. Convergencia con XQuery

Para cuando comenzaba el trabajo en XSLT 2.0, el Grupo de Trabajo XQuery separado en W3C había creado un borrador de su propio lenguaje.

Si bien el Grupo de Trabajo XSL había identificado la necesidad de un lenguaje de transformación para respaldar una parte autónoma del proceso de formateo, XQuery se originó en la necesidad de buscar grandes cantidades de documentos XML almacenados en una base de datos.

El trabajo en un lenguaje de consulta XML había comenzado ya en 1998. Se llevó a cabo un taller en diciembre de 1998, y puede encontrar los 66 documentos de posición presentados en este taller en http://www.w3.org/TandS/QL/QL98/ pp.html. Es interesante ver cómo los participantes vieron la relación con XSL, como se conocía entonces. El documento de posición de Microsoft afirma la creencia de que un lenguaje de consulta podría desarrollarse como una extensión de XSLT, pero en esto está casi solo. Muchos de los participantes tenían experiencia en bases de datos, con ideas firmemente arraigadas en la tradición de SQL y lenguajes de bases de datos de objetos como OQL, y para estas personas, XSL no se parecía ni remotamente a un lenguaje de consulta. Pero a la luz de los eventos posteriores, es interesante leer el documento de posición del Grupo de Trabajo XSL, que dice en su resumen:

1. El lenguaje de consulta debe utilizar patrones XSL como base para la recuperación de información.

2. El lenguaje de consulta debe utilizar plantillas XSL como base para materializar los resultados de la consulta.

3. El lenguaje de consulta debe ser al menos tan expresivo como lo es XSL actualmente.

4. El desarrollo de los lenguajes de patrones y transformación debe permanecer en el Grupo de Trabajo XSL.

5. Un grupo de coordinación debe garantizar que un solo lenguaje de consulta satisfaga todos los requisitos del grupo de trabajo o que todos los lenguajes de consulta del W3C compartan un modelo de consulta subyacente.

(Recuerde que XPath aún no se había identificado como un lenguaje separado y que las expresiones que luego se convirtieron en XPath se conocían como patrones).

Esta oferta de coordinación, y el fuerte deseo de asegurar la coherencia entre las diferentes especificaciones del W3C, puede verse como directamente conducente a la posterior colaboración entre los dos grupos de trabajo para definir XPath 2.0.

El grupo XQuery comenzó a reunirse en septiembre de 1999. El primer documento de requisitos publicado se publicó en enero siguiente (http://www.w3.org/TR/2000/WD-xmlquery-req-20000131). Incluía un compromiso de compatibilidad con XML Schema y una promesa redactada con bastante cautela de "tener en cuenta la expresibilidad y las facilidades de búsqueda de XPath al formular su álgebra y sintaxis de consulta". En julio de 2000 se vio un documento de requisitos revisado que incluía una selección de consultas que el idioma debe poder expresar. El primer borrador visible externamente del lenguaje XQuery se publicó en febrero de 2001 (ver http://www.w3.org/TR/2001/WD-xquery-20010215/), y fue en esta etapa cuando la colaboración entre los dos los grupos de trabajo comenzaron en serio.

La estrecha cooperación entre los equipos que desarrollan los dos lenguajes contrasta extrañamente con la posición un tanto contradictoria adoptada por partes de la comunidad de usuarios. Los usuarios de XSLT se apresuraron a señalar que XSLT 1.0 satisfacía todos los requisitos del primer documento de requisitos de XQuery y podía resolver todos los casos de uso publicados en la segunda versión en agosto de 2000. Al mismo tiempo, los usuarios del lado de la valla de XQuery A menudo han sido desdeñosos con XSLT, quejándose de su sintaxis detallada y, a veces, de su semántica arcana. Incluso hoy en día, cuando las similitudes de los dos lenguajes en un nivel profundo son claramente evidentes, hay poca superposición entre sus comunidades de usuarios: encuentro que la mayoría de los usuarios del motor XQuery en Saxon no tienen experiencia XSLT. La diferencia entre XSLT y XQuery es, en muchos sentidos, una diferencia de estilo más que de sustancia, pero los usuarios a menudo se sienten muy interesados en el estilo.

### 1.4.6. El desarrollo de XSLT 2.0 y XPath 2.0

Los requisitos para XSLT 2.0 y XPath 2.0 se publicaron el 14 de febrero de 2001. En el caso de los requisitos de XPath 2.0, el documento fue escrito conjuntamente por los dos grupos de trabajo. Puede encontrar los documentos en las siguientes URL:

```sh
http://www.w3.org/TR/2001/WD-xslt20req-20010214

http://www.w3.org/TR/2001/WD-xpath20req-20010214
```

En términos generales, los requisitos se dividen en tres categorías:

* Funciones que obviamente faltan en los estándares actuales y que facilitarían mucho la vida de los usuarios, por ejemplo, facilidades para agrupar nodos relacionados, funciones numéricas y de manejo de cadenas adicionales, y la capacidad de leer archivos de texto y documentos XML.

* Cambios deseados por el Grupo de trabajo de consultas XML. La dificultad en esta etapa era que el grupo Query no solo quería adiciones al lenguaje XPath; querían cambios fundamentales en su semántica. Muchos miembros del grupo XQuery sintieron que no podían vivir con algunas de las arbitrariedades de la forma en que XPath manejaba los tipos de datos en general, y los conjuntos de nodos en particular, por ejemplo, el hecho de que `«a = 1»` comprueba si hay alguna `«a»` que es igual a uno, mientras que `«a − 1 = 0»` comprueba si la primera `«a»` es igual a uno.

* Funciones diseñadas para explotar e integrarse con XML Schema. La especificación del esquema XML del W3C había llegado a una etapa avanzada (se convirtió en una recomendación candidata el 20 de octubre de 2000) y comenzaban a aparecer implementaciones en los productos. La idea era que si el esquema especificaba que un elemento en particular contiene un número o una fecha (por ejemplo), entonces debería ser posible utilizar este conocimiento al comparar u ordenar fechas dentro de una hoja de estilo.

El desarrollo de XSLT 2.0, que culminó con la Recomendación del 23 de enero de 2007, resultó ser un proceso prolongado. Hubo retrasos tempranos para llegar a un acuerdo con el grupo XQuery sobre los detalles de XPath 2.0. En primer lugar, esto llevó mucho tiempo, debido a la cantidad de personas involucradas; en segundo lugar, debido a los lugares muy diferentes de donde provenían las personas (la comunidad de bases de datos y la comunidad de documentos históricamente han estado completamente aisladas entre sí, y fue necesario hablar mucho antes de que las personas comenzaran a comprender las posiciones de los demás); y finalmente, debido a la enorme dificultad técnica de encontrar un diseño viable que ofreciera el equilibrio adecuado entre compatibilidad con versiones anteriores y una semántica rigurosa y coherente. Más tarde, cuando la especificación parecía estar casi terminada, todavía tomó un par de años aprobar las revisiones públicas exigidas por el proceso W3C, que generó miles de comentarios detallados.

Pero eso es todo historia ahora. Veamos a continuación las características esenciales de XSLT 2.0 como lenguaje.

## 1.5. XSLT 2.0 como lenguaje

¿Cuáles son las características más significativas de XSLT como idioma, que lo distinguen de otros idiomas? En esta sección elegiré cinco de las características más llamativas: el hecho de que está escrito en sintaxis XML, el hecho de que es un lenguaje libre de efectos secundarios, el hecho de que el procesamiento se describe como un conjunto de reglas de coincidencia de patrones, el hecho de que tiene un sistema de tipos basado en XML Schema, y el hecho de que es un sistema de dos idiomas en el que un idioma (XPath) está incrustado en otro (XSLT).

### 1.5.1. Uso de sintaxis XML

Como hemos visto, el uso de la sintaxis SGML para hojas de estilo se propuso ya en 1994, y parece que esta idea se convirtió gradualmente en la sabiduría aceptada. Es difícil rastrear exactamente cuáles fueron los argumentos primordiales y cuándo se encuentra escribiendo algo como:

```xml
<xsl:variable name="y">
   <xsl:call-template name="f">
      <xsl:with-param name="x"/>
   </xsl:call-template>
</xsl:variable>
```

para expresar lo que en otros idiomas se escribiría como `«y = f(x);»`, es posible que se pregunte cómo se tomó esa decisión.

Los argumentos más obvios para expresar hojas de estilo XSLT en XML son quizás los siguientes:

* Ya existe un analizador XML en el navegador; por lo que mantiene la huella pequeña si se puede reutilizar.

* Todos estaban hartos de las inconsistencias sintácticas entre HTML / XML y CSS y no querían que volviera a suceder lo mismo.

* La sintaxis similar a Lisp de DSSSL fue ampliamente vista como una barrera para su adopción; por lo que sería mejor tener una sintaxis que ya sea familiar en la comunidad de destino.

* Muchos lenguajes de plantilla populares existentes (incluidas las páginas ASP y JSP simples) se expresan como un esquema del documento de salida con instrucciones integradas; entonces este es un concepto familiar.

* El aparato léxico es reutilizable, por ejemplo, soporte Unicode, referencias de caracteres y entidades, manejo de espacios en blanco, espacios de nombres.

* Las herramientas de desarrollo visual eliminan el inconveniente de escribir muchos corchetes angulares.

* A menudo es útil tener una hoja de estilo como entrada o salida de una transformación; por lo que es una ventaja si una hoja de estilo puede leer y escribir otras hojas de estilo.

En mi experiencia, el argumento más generalizado es el último: es sorprendente la frecuencia con la que las aplicaciones complejas construyen o modifican hojas de estilo sobre la marcha. Pero nos guste o no, la sintaxis basada en XML es ahora una característica intrínseca del lenguaje que tiene ventajas e inconvenientes. Hace que el lenguaje sea detallado, pero al final, el número de pulsaciones de teclas tiene muy poca relación con la facilidad o dificultad de resolver problemas de transformación particulares.

En XSLT 2.0, la amplitud del lenguaje se ha reducido considerablemente al aumentar la expresividad de la parte no XML de la sintaxis, a saber, las expresiones XPath. Muchos cálculos que requerían cinco líneas de código XSLT en 1.0 ahora se pueden expresar en una sola expresión XPath. Dos construcciones en particular llevaron a esta simplificación: la expresión condicional (`if..then..else`) en XPath 2.0; y la capacidad de definir una función en XSLT (usando `<xsl:function>`) que se puede llamar directamente desde una expresión XPath. Para tomar el ejemplo discutido anteriormente, si reemplaza la plantilla «f» por una función escrita por el usuario «f», puede reemplazar las cinco líneas en el ejemplo con:


### 1.5.2. Sin efectos secundarios
### 1.5.3. Basado en reglas
### 1.5.4. Tipos basados en esquema XML
### 1.5.5. Un sistema de dos idiomas: XSLT y XPath
## 1.6. Resumen
