# XSLT 2.0 and XPath 2.0 Programmer's Reference, 4th Edition

Descripción del libro
Este libro es principalmente un libro de referencia práctico para desarrolladores XSLT profesionales. No asume ningún conocimiento previo del lenguaje y muchos desarrolladores lo han utilizado como su primera introducción a XSLT; sin embargo, no está estructurado como un tutorial y hay otros libros sobre XSLT que brindan un enfoque más suave para principiantes.

El libro asume un conocimiento básico de XML, HTML y la arquitectura de la Web, y está escrito para programadores experimentados. No se asume que conoces ningún lenguaje en particular como Java o Visual Basic, solo que reconoces los conceptos que todos los lenguajes de programación tienen en común.

El libro es adecuado tanto para los usuarios de XSLT 1.0 que se actualizan a XSLT 2.0 como para los recién llegados a XSLT. El libro también es igualmente adecuado si trabaja en el mundo Java o .NET.

Como corresponde a un libro de referencia, un objetivo clave es que la cobertura sea completa y autorizada. Está diseñado para brindarle todos los detalles, no solo una descripción general del 20 por ciento del idioma que la mayoría de la gente usa el 80 por ciento del tiempo. Está diseñado para que siga volviendo al libro cada vez que encuentre tareas de programación nuevas y desafiantes, no como un libro que hojea rápidamente y luego deja en el estante. Si le gustan los detalles, disfrutará de este libro; si no, probablemente no lo hará.

Pero además de dar los detalles, este libro tiene como objetivo explicar los conceptos, con cierta profundidad. Por lo tanto, es un libro para personas que no solo quieren usar el idioma, sino que también quieren entenderlo en un nivel profundo.

El libro tiene como objetivo contarte todo lo que necesitas saber sobre el lenguaje XSLT 2.0. Le da el mismo peso a las cosas que son nuevas en XSLT 2.0 y las cosas que ya estaban presentes en la versión 1.0. El libro trata sobre el idioma, no sobre productos específicos. Sin embargo, hay apéndices sobre Saxon (la propia implementación del autor de XSLT 2.0), sobre la implementación de Altova XSLT 2.0 y sobre las API de Java y Microsoft para controlar las transformaciones XSLT, que sin duda se actualizarán para manejar tanto XSLT 2.0 como 1.0. . Un tercer procesador XSLT 2.0, Gestalt, fue lanzado poco antes de que el libro saliera a la imprenta, demasiado tarde para describirlo en detalle. Pero la experiencia de XSLT 1.0 es que ha habido un nivel muy alto de interoperabilidad entre diferentes procesadores XSLT, y si puede usar uno de ellos, puede usarlos todos.

En la edición anterior, dividimos XSLT 2.0 y XPath 2.0 en volúmenes separados. La idea era que algunos lectores pudieran estar interesados ​​solo en XPath. Sin embargo, muchos compraron el libro XSLT 2.0 sin su compañero XPath y, como resultado, quedaron confundidos; así que esta vez, el material vuelve a estar unido. La información de referencia de XPath se encuentra en capítulos independientes, por lo que aún debería estar accesible cuando utilice XPath en contextos distintos de XSLT.

El libro no cubre los objetos de formato XSL, un tema importante en sí mismo. Tampoco cubre los esquemas XML en detalle. Si desea utilizar estas importantes tecnologías junto con XSLT, existen otros libros que les hacen justicia.

Este libro contiene veinte capítulos y ocho apéndices (el último de los cuales es un glosario) organizados en cuatro partes. La siguiente sección describe lo que puede encontrar en cada parte, capítulo y apéndice.

Parte I: Fundamentos: La primera parte del libro cubre conceptos esenciales. Debería leerlos antes de comenzar a codificar. Si ignora este consejo, como hace la mayoría de la gente, entonces los leerá cuando llegue a ese punto de desesperación en el que le resulte imposible hacer que el lenguaje haga otra cosa que las tareas más triviales. XSLT es diferente de otros lenguajes y, para que funcione para usted, debe comprender cómo se diseñó para su uso.

Capítulo 1: XSLT en contexto: este capítulo explica cómo XSLT encaja en el panorama general: cómo surgió el lenguaje y cómo se ubica junto a otras tecnologías. También tiene algunos ejemplos de codificación simples para mantenerte alerta.

Capítulo 2: El modelo de procesamiento XSLT: se trata de la arquitectura de un procesador XSLT: las entradas, las salidas y el modelo de datos. Comprender el modelo de datos es quizás lo más importante que distingue a un experto en XSLT de un aficionado; puede parecer información que no puede usar de inmediato, pero es el conocimiento lo que evitará que cometa muchos errores estúpidos.

Capítulo 3: Estructura de la hoja de estilo: el desarrollo XSLT se trata de escribir hojas de estilo, y este capítulo ofrece una visión general de cómo se ven las hojas de estilo. Explica los conceptos clave de la programación basada en reglas usando plantillas y explica cómo llevar a cabo la programación en general al estructurar su aplicación usando módulos y canalizaciones.

Capítulo 4: Hojas de estilo y esquemas: una innovación clave en XSLT 2.0 es que las hojas de estilo pueden aprovechar el conocimiento sobre la estructura de sus documentos de entrada y salida, proporcionado en forma de un esquema XML. Este capítulo proporciona una descripción general rápida del esquema XML para describir su impacto en el desarrollo XSLT. No todosne usa esquemas, y puede omitir este capítulo si entra en esa categoría.

Capítulo 5: El sistema de tipos: XPath 2.0 y XSLT 2.0 ofrecen mecanografía fuerte como alternativa al enfoque de escritura débil de los idiomas 1.0. Esto significa que puede declarar los tipos de sus variables, funciones y parámetros, y utilizar esta información para obtener una advertencia temprana de errores de programación. Este capítulo explica los tipos de datos disponibles y los mecanismos para crear tipos definidos por el usuario.

Parte II: Referencia XSLT y XPath: Esta sección del libro contiene material de referencia, organizado con la esperanza de que pueda encontrar fácilmente lo que necesita cuando lo necesite. No está diseñado para lectura secuencial, aunque es posible que desee hojear las páginas para descubrir qué hay allí.

Capítulo 6: Elementos XSLT: este capítulo monstruoso enumera todos los elementos XSLT que puede usar en una hoja de estilo, en orden alfabético, brindando reglas detalladas para la sintaxis y semántica de cada elemento, consejos sobre el uso y ejemplos. Esta es probablemente la parte del libro que utilizará con más frecuencia a medida que se convierta en un usuario experto de XSLT. Es un enfoque "sin piedra sin remover", basado en la creencia de que, como desarrollador profesional, necesita saber qué sucede cuando las cosas se ponen difíciles, no solo cuando el viento está en su dirección.

Capítulo 7: Conceptos básicos de XPath: este capítulo explica los conceptos básicos de XPath: las construcciones de bajo nivel como literales, variables y llamadas a funciones. También explica las reglas de contexto, que describen cómo la evaluación de las expresiones XPath depende del contexto de procesamiento XSLT en el que aparecen.

Capítulo 8: XPath: Operadores sobre elementos: XPath ofrece el rango habitual de operadores para realizar operaciones aritméticas, comparaciones booleanas y similares. Sin embargo, estos no siempre se comportan exactamente como cabría esperar, por lo que vale la pena leer este capítulo para ver qué está disponible y en qué se diferencia del último idioma que usó.

Capítulo 9: XPath: Expresiones de ruta: Las expresiones de ruta son las que hacen que XPath sea especial; le permiten navegar por la estructura de un documento XML. Este capítulo explica la sintaxis de las expresiones de ruta, los 13 ejes que puede usar para ubicar los nodos que necesita y los operadores asociados como unión, intersección y diferencia.

Capítulo 10: XPath: Expresiones de secuencia: A diferencia de XPath 1.0, en la versión 2.0 todos los valores son secuencias (los singleton son solo un caso especial). Algunos de los operadores más importantes de XPath 2.0 son los que manipulan secuencias, en particular la expresión "for", que traduce una secuencia en otra mediante la aplicación de un mapeo.

Capítulo 11: XPath: Expresiones de tipos: El sistema de tipos se explicó en el Capítulo 5; este capítulo explica las operaciones que puede utilizar para aprovechar los tipos. Esto incluye la operación de "conversión" que se utiliza para convertir valores de un tipo a otro. Una gran parte de este capítulo está dedicada a las reglas detalladas sobre cómo se realizan estas conversiones.

Capítulo 12: Patrones XSLT: este capítulo vuelve de XPath a un tema específico de XSLT. Los patrones se utilizan para definir reglas de plantilla, la esencia del enfoque de programación basada en reglas de XSLT. La razón para explicarlos ahora es que la sintaxis y la semántica de los patrones depende en gran medida de las reglas correspondientes para las expresiones XPath.

Capítulo 13: La biblioteca de funciones: XPath 2.0 incluye una biblioteca de funciones que se pueden llamar desde cualquier expresión XPath; XSLT 2.0 amplía esto con algunas funciones adicionales que están disponibles solo cuando se usa XPath dentro de XSLT. La biblioteca ha crecido enormemente desde XPath 1.0. Este capítulo proporciona una única referencia alfabética para todas estas funciones.

Capítulo 14: Expresiones regulares: El procesamiento de texto es un área donde XSLT 2.0 y XPath 2.0 son mucho más poderosos que la versión 1.0, y esto se debe principalmente al uso de construcciones que aprovechan las expresiones regulares. Si está familiarizado con las expresiones regulares de lenguajes como Perl, este capítulo le explica en qué se diferencian las expresiones regulares XPath. Si eres nuevo en el tema, lo explica desde los primeros principios.

Capítulo 15: Serialización: La serialización en XSLT significa la capacidad de generar un documento XML textual a partir de la estructura de árbol que es manipulada por una hoja de estilo. Esto no es parte del procesamiento XSLT propiamente dicho, por lo que (siguiendo el ejemplo de W3C) lo ha separado en su propio capítulo. Puede controlar la serialización desde la hoja de estilo mediante una declaración, pero muchos productos también le permiten controlarla directamente a través de una API.

Parte III: Explotación: la sección final del libro es un consejo y una guía sobre cómo aprovechar XSLT para escribir aplicaciones reales. Está destinado a convertirlo no solo en un codificador XSLT competente, sino también en un diseñador competente. La mejor forma de aprender es estudiando el trabajo de otros, por lo que el énfasis aquí está en los estudios de casos prácticos.

Capítulo 16: Extensibilidad: este capítulo describe los "ganchos" proporcionados en la especificación XSLT para permitir a los proveedores y usuarios incorporar funciones adicionales. La forma en que esto funciona variará de una implementación a unaotro, por lo que no podemos cubrir todas las posibilidades, pero un aspecto importante que sí cubre el capítulo es cómo usar dichas extensiones y aún así mantener su código portátil.

Capítulo 17: Patrones de diseño de hojas de estilo: este capítulo explora una serie de patrones de diseño y codificación para la programación XSLT, comenzando con la hoja de estilo de "rellenar los espacios en blanco" más simple y extendiéndose hasta el uso completo de la programación recursiva en el estilo de programación funcional , que es necesario para abordar problemas de cualquier complejidad computacional. Esto brinda la oportunidad de explicar el pensamiento detrás de la programación funcional y el cambio de mentalidad necesario para aprovechar al máximo este estilo de desarrollo.

Capítulo 18: Estudio de caso: XMLSpec: XSLT se utiliza a menudo para representar documentos, por lo que, ¿dónde mejor buscar un estudio de caso que las hojas de estilo utilizadas por el W3C para representar las especificaciones XML y XSLT, y otras de la misma familia, para su visualización en ¿La web? Las hojas de estilo resultantes son típicas de las que encontrará en cualquier organización editorial que utilice XML para desarrollar una serie de documentos con una apariencia compatible.

Capítulo 19: Estudio de caso: Un árbol genealógico: La visualización de un árbol genealógico es otra aplicación XSLT típica. Este ejemplo con datos semiestructurados, una mezcla de datos bastante complejos y texto narrativo, que se puede presentar de muchas formas diferentes para diferentes audiencias. También muestra cómo abordar otro problema típico de XSLT, la conversión de datos a XML desde un formato heredado basado en texto. Da la casualidad de que esto utiliza casi todas las nuevas características importantes de XSLT 2.0 en una hoja de estilo corta. Pero otro objetivo de este capítulo es mostrar una colección de hojas de estilo que realizan diferentes trabajos como parte de una aplicación completa.

Capítulo 20: Estudio de caso: Tour del caballero: Encontrar una ruta alrededor de un tablero de ajedrez donde un caballero visita cada casilla sin volver sobre sus pasos puede parecer una aplicación bastante esotérica para XSLT, pero es una buena manera de mostrar cómo son incluso los algoritmos más complejos. dentro de las capacidades del idioma. Es posible que no necesite abordar este problema en particular, pero si desea construir un diagrama SVG que muestre el progreso con respecto al plan de su proyecto, entonces los problemas no serán tan diferentes.

Parte IV: Apéndices: Apéndice A: Resumen de sintaxis de XPath 2.0: Recopila las reglas gramaticales de XPath y las precedencias de operadores en un solo lugar para facilitar la referencia.

Apéndice B: Códigos de error: una lista de todos los códigos de error definidos en las especificaciones de lenguaje XSLT y XPath, con breves explicaciones para ayudarlo a comprender qué salió mal.

Apéndice C: Compatibilidad con versiones anteriores: la lista de cosas que debe tener en cuenta al convertir aplicaciones desde XSLT 1.0.

Apéndice D: Procesadores Microsoft XSLT: aunque los dos procesadores Microsoft XSLT aún no son compatibles con XSLT 2.0, pensamos que a muchos lectores les resultaría útil tener aquí un resumen rápido de los principales objetos y métodos utilizados en sus API.

Apéndice E: JAXP: la API de Java para procesamiento XML: JAXP es una interfaz en lugar de un producto. Nuevamente, aún no tiene soporte explícito para XSLT 2.0, pero los programadores de Java lo usarán a menudo en proyectos XSLT 2.0, por lo que el libro incluye una descripción general de las clases y métodos disponibles.

Apéndice F: Saxon: En el momento de escribir este artículo, Saxon (desarrollado por el autor de este libro) proporciona la implementación más completa de XSLT 2.0 y XPath 2.0, por lo que sus interfaces y extensiones se tratan con cierto detalle.

Apéndice G: Altova: Altova, los desarrolladores de XML Spy, tienen un procesador XSLT 2.0 que se puede utilizar como parte del entorno de desarrollo o como un componente independiente. Este apéndice proporciona detalles de sus interfaces.

Apéndice H: Glosario

Nota: CD-ROM / DVD y otros materiales complementarios no se incluyen como parte del archivo de libro electrónico.
