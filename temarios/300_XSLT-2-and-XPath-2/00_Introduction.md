# Introduction

* Para quien es este libro
* Qué cubre este libro
* Cómo está estructurado este libro
   * Parte I: Fundamentos
      * Capítulo 1: XSLT en contexto
      * Capítulo 2: El modelo de procesamiento XSLT
      * Capítulo 3: Estructura de la hoja de estilo
      * Capítulo 4: Hojas de estilo y esquemas
      * Capítulo 5: El sistema de tipos
   * Parte II: Referencia XSLT y XPath
      * Capítulo 6: Elementos XSLT
      * Capítulo 7: Conceptos básicos de XPath
      * Capítulo 8: XPath: Operadores en elementos
      * Capítulo 9: XPath: Expresiones de ruta
      * Capítulo 10: XPath: Expresiones de secuencia
      * Capítulo 11: XPath: Expresiones de tipo
      * Capítulo 12: Patrones XSLT
      * Capítulo 13: La biblioteca de funciones
      * Capítulo 14: Expresiones regulares
      * Capítulo 15: Serialización
   * Parte III: Explotación
      * Capítulo 16: Extensibilidad
      * Capítulo 17: Patrones de diseño de hojas de estilo
      * Capítulo 18: Estudio de caso: XMLSpec
      * Capítulo 19: Estudio de caso: un árbol genealógico
      * Capítulo 20: Estudio de caso: Knight's Tour
   * Parte IV: Apéndices
      * Apéndice A: Resumen de sintaxis de XPath 2.0
      * Apéndice B: Códigos de error
      * Apéndice C: Compatibilidad con versiones anteriores
      * Apéndice D: Procesadores Microsoft XSLT
      * Apéndice E: JAXP: API de Java para procesamiento XML
      * Apéndice F: sajón
      * Apéndice G: Altova
      * Apéndice H: Glosario
      * Índice
* Qué necesita para usar este libro
* Convenciones
* Descarga del código
* Errata
* p2p.wrox.com

Este libro, como indica el título, es principalmente un libro de referencia práctico para desarrolladores profesionales de XSLT. No asume ningún conocimiento previo del lenguaje y muchos desarrolladores lo han utilizado como su primera introducción a XSLT; sin embargo, no está estructurado como un tutorial y hay otros libros sobre XSLT que brindan un enfoque más suave para principiantes.

## Para quien es este libro

El libro asume un conocimiento básico de XML, HTML y la arquitectura de la Web, y está escrito para programadores experimentados. No se asume que conoces ningún lenguaje en particular como Java o Visual Basic, solo que reconoces los conceptos que todos los lenguajes de programación tienen en común.

He intentado que el libro sea adecuado tanto para los usuarios de XSLT 1.0 que se actualizan a XSLT 2.0 como para los recién llegados a XSLT. Esto es más fácil de hacer en un libro de referencia, por supuesto, que en un tutorial. También he intentado que el libro sea igualmente adecuado tanto si trabajas en el mundo Java como en .NET.

Como corresponde a un libro de referencia, un objetivo clave es que la cobertura sea completa y autorizada. Está diseñado para brindarle todos los detalles, no solo una descripción general del 20 por ciento del idioma que la mayoría de la gente usa el 80 por ciento del tiempo. Está diseñado para que siga volviendo al libro cada vez que encuentre tareas de programación nuevas y desafiantes, no como un libro que hojea rápidamente y luego deja en el estante. Si le gustan los detalles, disfrutará de este libro; si no, probablemente no lo hará.

Pero además de dar los detalles, este libro tiene como objetivo explicar los conceptos, con cierta profundidad. Por lo tanto, es un libro para personas que no solo quieren usar el idioma, sino que también quieren entenderlo en un nivel profundo. Muchos lectores me han escrito diciéndome que aprecian particularmente estos conocimientos sobre el lenguaje, y tengo la más sincera esperanza de que después de leerlo, no solo sea un programador XSLT más productivo, sino también un ingeniero de software con más conocimientos.

## Qué cubre este libro

El libro tiene como objetivo contarte todo lo que necesitas saber sobre el lenguaje XSLT 2.0. Le da el mismo peso a las cosas que son nuevas en XSLT 2.0 y las cosas que ya estaban presentes en la versión 1.0. El libro trata sobre el idioma, no sobre productos específicos. Sin embargo, hay apéndices sobre Saxon (mi propia implementación de XSLT 2.0), sobre la implementación de Altova XSLT 2.0 y sobre las API de Java y Microsoft para controlar las transformaciones XSLT, que sin duda se actualizarán para manejar tanto XSLT 2.0 como 1.0. Un tercer procesador XSLT 2.0, Gestalt, se lanzó poco antes de que saliéramos a la imprenta, demasiado tarde para describirlo en detalle. Pero la experiencia de XSLT 1.0 es que ha habido un nivel muy alto de interoperabilidad entre diferentes procesadores XSLT, y si puede usar uno de ellos, puede usarlos todos.

En la edición anterior, dividimos XSLT 2.0 y XPath 2.0 en volúmenes separados. La idea era que algunos lectores pudieran estar interesados ​​solo en XPath. Sin embargo, muchos compraron el libro XSLT 2.0 sin su compañero XPath y, como resultado, quedaron confundidos; así que esta vez, hemos reunido el material. La información de referencia de XPath se encuentra en capítulos independientes, por lo que aún debería estar accesible cuando utilice XPath en contextos distintos de XSLT.

El libro no cubre los objetos de formato XSL, un tema importante en sí mismo. Tampoco cubre los esquemas XML en detalle. Si desea utilizar estas importantes tecnologías junto con XSLT, existen otros libros que les hacen justicia.

## Cómo está estructurado este libro

Este libro contiene veinte capítulos y ocho apéndices (el último de los cuales es un glosario) organizados en cuatro partes. La siguiente sección describe lo que puede encontrar en cada parte, capítulo y apéndice.

### Parte I: Fundamentos

#### CAPÍTULO 1: XSLT EN CONTEXTO

Este capítulo explica cómo XSLT encaja en el panorama general: cómo surgió el lenguaje y cómo se ubica junto a otras tecnologías. También tiene algunos ejemplos de codificación simples para mantenerte alerta.

#### CAPÍTULO 2: EL MODELO DE PROCESAMIENTO XSLT

Se trata de la arquitectura de un procesador XSLT: las entradas, las salidas y el modelo de datos. Comprender el modelo de datos es quizás lo más importante que distingue a un experto en XSLT de un aficionado; puede parecer información que no puede usar de inmediato, pero es el conocimiento lo que le impedirá cometer muchos errores estúpidos.

#### CAPÍTULO 3: ESTRUCTURA DE LA HOJA DE ESTILOS

El desarrollo de XSLT se trata de escribir hojas de estilo, y este capítulo ofrece una visión general de cómo se ven las hojas de estilo. Explica los conceptos clave de la programación basada en reglas usando plantillas y explica cómo llevar a cabo la programación en general al estructurar su aplicación usando módulos y canalizaciones.

#### CAPÍTULO 4: PLANTILLAS Y ESQUEMAS

Una innovación clave en XSLT 2.0 es que las hojas de estilo pueden aprovechar el conocimiento sobre la estructura de sus documentos de entrada y salida, proporcionado en forma de un esquema XML. Este capítulo proporciona una descripción general rápida del esquema XML para describir su impacto en el desarrollo XSLT. No todo el mundo usa esquemas, y puede saltarse este capítulo si entra en esa categoría.

#### CAPÍTULO 5: EL TIPO DE SISTEMA

XPath 2.0 y XSLT 2.0 ofrecen mecanografía fuerte como alternativa al enfoque de escritura débil de los idiomas 1.0. Esto significa que puede declarar los tipos de sus variables, funciones y parámetros, y utilizar esta información para obtener una advertencia temprana de errores de programación. Este capítulo explica los tipos de datos disponibles y los mecanismos para crear tipos definidos por el usuario.

### Parte II: Referencia XSLT y XPath

Esta sección del libro contiene material de referencia, organizado con la esperanza de que pueda encontrar fácilmente lo que necesita cuando lo necesita. No está diseñado para lectura secuencial, aunque si eres como yo, es posible que desees hojear las páginas para descubrir qué hay allí.

#### CAPÍTULO 6: ELEMENTOS XSLT
Este capítulo monstruoso enumera todos los elementos XSLT que puede usar en una hoja de estilo, en orden alfabético, brindando reglas detalladas para la sintaxis y semántica de cada elemento, consejos sobre el uso y ejemplos. Esta es probablemente la parte del libro que utilizará con más frecuencia a medida que se convierta en un usuario experto de XSLT. Es un enfoque "sin piedra sin remover", basado en la creencia de que, como desarrollador profesional, necesita saber qué sucede cuando las cosas se ponen difíciles, no solo cuando el viento está en su dirección.

#### CAPÍTULO 7: FUNDAMENTOS DE XPATH

Este capítulo explica los conceptos básicos de XPath: las construcciones de bajo nivel como literales, variables y llamadas a funciones. También explica las reglas de contexto, que describen cómo la evaluación de las expresiones XPath depende del contexto de procesamiento XSLT en el que aparecen.

#### CAPÍTULO 8: XPATH: OPERADORES EN ARTÍCULOS

XPath ofrece la gama habitual de operadores para realizar operaciones aritméticas, comparaciones booleanas y similares. Sin embargo, estos no siempre se comportan exactamente como cabría esperar, por lo que vale la pena leer este capítulo para ver qué está disponible y en qué se diferencia del último idioma que usó.

#### CAPÍTULO 9: XPATH: EXPRESIONES DE LA RUTA

Las expresiones de ruta son las que hacen que XPath sea especial; le permiten navegar por la estructura de un documento XML. Este capítulo explica la sintaxis de las expresiones de ruta, los 13 ejes que puede usar para ubicar los nodos que necesita y los operadores asociados como unión, intersección y diferencia.

#### CAPÍTULO 10: XPATH: EXPRESIONES DE SECUENCIA

A diferencia de XPath 1.0, en la versión 2.0 todos los valores son secuencias (los singleton son solo un caso especial). Algunos de los operadores más importantes de XPath 2.0 son los que manipulan secuencias, en particular la expresión «for», que traduce una secuencia en otra aplicando un mapeo.

#### CAPÍTULO 11: XPATH: EXPRESIONES DE TIPO

El sistema de tipos se explicó en el Capítulo 5; este capítulo explica las operaciones que puede utilizar para aprovechar los tipos. Esto incluye la operación de «conversión» que se utiliza para convertir valores de un tipo a otro. Una gran parte de este capítulo está dedicada a las reglas detalladas sobre cómo se realizan estas conversiones.

#### CAPÍTULO 12: PATRONES XSLT

Este capítulo vuelve de XPath a un tema específico de XSLT. Los patrones se utilizan para definir reglas de plantilla, la esencia del enfoque de programación basada en reglas de XSLT. La razón para explicarlos ahora es que la sintaxis y la semántica de los patrones depende en gran medida de las reglas correspondientes para las expresiones XPath.

#### CAPÍTULO 13: LA BIBLIOTECA DE FUNCIONES

XPath 2.0 incluye una biblioteca de funciones que se pueden llamar desde cualquier expresión XPath; XSLT 2.0 amplía esto con algunas funciones adicionales que están disponibles solo cuando se usa XPath dentro de XSLT. La biblioteca ha crecido enormemente desde XPath 1.0. Este capítulo proporciona una única referencia alfabética para todas estas funciones.

#### CAPÍTULO 14: EXPRESIONES REGULARES

El procesamiento de texto es un área donde XSLT 2.0 y XPath 2.0 son mucho más poderosos que la versión 1.0, y esto se debe principalmente al uso de construcciones que explotan expresiones regulares. Si está familiarizado con las expresiones regulares de lenguajes como Perl, este capítulo le explica en qué se diferencian las expresiones regulares XPath. Si eres nuevo en el tema, lo explica desde los primeros principios.

#### CAPÍTULO 15: SERIALIZACIÓN

La serialización en XSLT significa la capacidad de generar un documento XML textual a partir de la estructura de árbol que es manipulada por una hoja de estilo. Esto no es parte del procesamiento XSLT propiamente dicho, por lo que (siguiendo el ejemplo de W3C) lo hemos separado en su propio capítulo. Puede controlar la serialización desde la hoja de estilo mediante una declaración <xsl: output>, pero muchos productos también le permiten controlarla directamente a través de una API.

### Parte III: Explotación

La sección final del libro es un consejo y una guía sobre cómo aprovechar XSLT para escribir aplicaciones reales. Está destinado a convertirlo no solo en un codificador XSLT competente, sino también en un diseñador competente. La mejor forma de aprender es estudiando el trabajo de otros, por lo que el énfasis aquí está en los estudios de casos prácticos.

#### CAPÍTULO 16: EXTENSIBILIDAD

Este capítulo describe los "ganchos" proporcionados en la especificación XSLT para permitir a los proveedores y usuarios incorporar funciones adicionales. La forma en que esto funciona variará de una implementación a otra, por lo que no podemos cubrir todas las posibilidades, pero un aspecto importante que cubre el capítulo es cómo usar tales extensiones y aún así mantener su código portátil.

#### CAPÍTULO 17: PATRONES DE DISEÑO DE HOJAS DE ESTILOS

Este capítulo explora una serie de patrones de diseño y codificación para la programación XSLT, comenzando con la hoja de estilo de "llenar los espacios en blanco" más simple y extendiéndose al uso completo de la programación recursiva en el estilo de programación funcional, que es necesaria para abordar problemas. de cualquier complejidad computacional. Esto brinda la oportunidad de explicar el pensamiento detrás de la programación funcional y el cambio de mentalidad necesario para aprovechar al máximo este estilo de desarrollo.

#### CAPÍTULO 18: ESTUDIO DE CASO: XMLSPEC

XSLT se usa a menudo para representar documentos, por lo que, ¿qué mejor lugar para buscar un estudio de caso que las hojas de estilo utilizadas por el W3C para representar las especificaciones XML y XSLT, y otras de la misma familia, para su visualización en la Web? Las hojas de estilo resultantes son típicas de las que encontrará en cualquier organización editorial que utilice XML para desarrollar una serie de documentos con una apariencia compatible.

#### CAPÍTULO 19: ESTUDIO DE CASO: UN ÁRBOL FAMILIAR

Mostrar un árbol genealógico es otra aplicación XSLT típica. Esta vez comenzamos con datos semiestructurados, una mezcla de datos bastante complejos y texto narrativo, que se pueden presentar de muchas formas diferentes para diferentes audiencias. También mostramos cómo abordar otro problema típico de XSLT, la conversión de datos a XML desde un formato heredado basado en texto. Da la casualidad de que esto utiliza casi todas las nuevas características importantes de XSLT 2.0 en una hoja de estilo corta. Pero otro objetivo de este capítulo es mostrar una colección de hojas de estilo que realizan diferentes trabajos como parte de una aplicación completa.

#### CAPÍTULO 20: ESTUDIO DE CASO: GIRA DEL CABALLERO

Encontrar una ruta alrededor de un tablero de ajedrez donde un caballero visita cada casilla sin volver sobre sus pasos puede parecer una aplicación bastante esotérica para XSLT, pero es una buena manera de mostrar cómo incluso los algoritmos más complejos están dentro de las capacidades del lenguaje. Es posible que no necesite abordar este problema en particular, pero si desea construir un diagrama SVG que muestre el progreso con respecto al plan de su proyecto, entonces los problemas no serán tan diferentes.

### Parte IV: Apéndices

#### APÉNDICE A: RESUMEN DE SINTAXIS DE XPATH 2.0

Recopila las reglas gramaticales de XPath y las precedencias de los operadores en un solo lugar para facilitar la referencia.

#### APÉNDICE B: CÓDIGOS DE ERROR

Una lista de todos los códigos de error definidos en las especificaciones de lenguaje XSLT y XPath, con breves explicaciones para ayudarlo a comprender qué salió mal.

#### APÉNDICE C: COMPATIBILIDAD HACIA ATRÁS

La lista de cosas que debe tener en cuenta al convertir aplicaciones desde XSLT 1.0.

#### APÉNDICE D: PROCESADORES MICROSOFT XSLT

Aunque los dos procesadores Microsoft XSLT aún no son compatibles con XSLT 2.0, pensamos que a muchos lectores les resultaría útil tener aquí un resumen rápido de los principales objetos y métodos utilizados en sus API.

#### APÉNDICE E: JAXP: LA API DE JAVA PARA EL PROCESAMIENTO DE XML

JAXP es una interfaz más que un producto. Nuevamente, aún no tiene soporte explícito para XSLT 2.0, pero los programadores de Java lo usarán a menudo en proyectos XSLT 2.0, por lo que decidimos incluir una descripción general de las clases y métodos disponibles.

#### APÉNDICE F: SAXON

En el momento de escribir este artículo, Saxon (desarrollado por el autor de este libro) proporciona la implementación más completa de XSLT 2.0 y XPath 2.0, por lo que decidimos cubrir sus interfaces y extensiones con cierto detalle.

#### APÉNDICE G: ALTOVA

Altova, los desarrolladores de XML Spy, tienen un procesador XSLT 2.0 que se puede utilizar como parte del entorno de desarrollo o como un componente independiente. Este apéndice proporciona detalles de sus interfaces.

## Qué necesita para usar este libro

Para usar XSLT 2.0, necesitará un procesador XSLT 2.0: en el momento de escribir este artículo, eso significa Saxon, AltovaXML o Gestalt, aunque Gestalt apareció en escena demasiado tarde para que podamos darle mucha cobertura. Puede ejecutar estos productos de diferentes formas, que se describen como parte de "¡Hola mundo!" ejemplo en el Capítulo 1 (páginas 11-18).

En caso de duda, la forma más sencilla de empezar es probablemente descargar Kernow http://kernowforsaxon.sourceforge.net/), que tiene Java SE 6 como requisito previo. Kernow viene completo con el motor Saxon XSLT. Lo único que necesitará es un editor de texto.

## Convenciones

Para ayudarlo a aprovechar al máximo el texto y realizar un seguimiento de lo que sucede, hemos utilizado una serie de convenciones a lo largo del libro.

Hay dos tipos de ejemplos de código en este libro: fragmentos de código y ejemplos resueltos.

Los fragmentos de código están incompletos y no están destinados a ejecutarse por sí mismos. Puede compilarlos en sus propias hojas de estilo si los encuentra útiles, pero tendrá que volver a escribir el código.

Los ejemplos resueltos se proporcionan en forma de hojas de estilo completas, acompañadas de documentos XML fuente de muestra a los que se pueden aplicar, y una ilustración del resultado que se espera que produzcan. Puede descargar estos ejemplos y probarlos usted mismo. Por lo general, aparecen en un cuadro como este:

> Un ejemplo de muestra
>
> **Source**
> 
> Esta sección proporciona los datos de origen XML, la entrada a la transformación. Si el nombre del archivo es example.xml, encontrará ese archivo en el archivo que puede descargar del sitio web de Wrox en http://www.wrox.com/, generalmente en un subdirectorio que contiene todos los ejemplos de un capítulo.
> `<source data = "xml" />`
>
> **Hoja de estilo**
>
> Esta sección describe la hoja de estilo XSLT utilizada para lograr la transformación. Nuevamente, generalmente habrá un nombre de archivo como `style.xsl`, por lo que puede encontrar la hoja de estilo en el archivo de descarga de Wrox.
>
> `<xsl:stylesheet...`
>
> **Output**
> 
> Esta sección muestra el resultado cuando aplica esta hoja de estilo a estos datos de origen, ya sea como una lista XML o HTML, o como una captura de pantalla.
> `<html ... </html>`

Ocasionalmente, por razones de espacio, no hemos impreso todo el documento de origen o la hoja de estilo en el libro, sino que lo referimos al sitio web para buscarlo.

> **NOTA:** Los recuadros como este contienen información importante que no debe olvidarse y que es directamente relevante para el texto circundante.

Las notas, consejos, sugerencias, trucos y apartados de la discusión actual se compensan y se colocan en cursiva de esta manera.

En cuanto a estilos en el texto:

* Destacamos términos nuevos y palabras importantes cuando los presentamos.
* Mostramos trazos de teclado como este: Ctrl + A.
* Mostramos nombres de archivo, URL y código dentro del texto de la siguiente manera: `persistence.properties`.
* Mostramos el código dentro del texto de la siguiente manera: Los nombres de los elementos se escriben como `<html>` o `<xsl:stylesheet>`. Los nombres de las funciones se escriben como `concat()` o `current-date()`. Otros nombres (por ejemplo, de atributos o tipos) se escriben simplemente como `version` o `xs:string`. Los fragmentos de código que no sean nombres simples se compensan del texto circundante con chevrones; por ejemplo, `«subcadena ($ a, 1, 1) = 'X'»`. Los galones también se utilizan alrededor de caracteres individuales o valores de cadena, o cuando se hace referencia a palabras clave como `«for»` y `«at»` que deben destacarse del texto. Como regla general, si una cadena está entre comillas, entonces las comillas son parte del ejemplo de código, mientras que si está entre comillas, las comillas están ahí solo para separar el código del texto circundante.

* Presentamos el código de dos formas diferentes:

```sh
For blocks of code we usually use gray highlighting.

But for individual lines of code we sometimes omit the highlighting.
```

## Descarga del código

Todo el código fuente mencionado en este libro está disponible para su descarga en http://www.wrox.com. Una vez en el sitio, simplemente ubique el título del libro (ya sea usando el cuadro de búsqueda o usando una de las listas de títulos) y haga clic en el enlace Descargar Código en la página de detalles del libro para obtener todo el código fuente del libro.

Debido a que muchos libros tienen títulos similares, puede que le resulte más fácil buscar por ISBN; El ISBN de este libro es 978-0-470-19274-0.

Una vez que descargue el código, simplemente descomprímalo con su herramienta de compresión favorita. Alternativamente, puede ir a la página principal de descarga de códigos de Wrox en http://www.wrox.com/dynamic/books/download.aspx para ver el código disponible para este libro y todos los demás libros de Wrox.

## Errata
## p2p.wrox.com
