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


## 1.2. ¿Cómo XSLT transforma XML?
### 1.2.1. XSLT y SQL: una analogía
### 1.2.2. Procesadores XSLT
### 1.2.3. Una hoja de estilo XSLT simple
### 1.2.4. Una hoja de estilo XSLT 2.0
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
