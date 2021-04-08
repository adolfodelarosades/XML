# XSLT 2.0 and XPath 2.0 Programmer's Reference, 4th Edition

![image](https://user-images.githubusercontent.com/23094588/113984505-794d2480-984b-11eb-942a-7728df5e0cc0.png)

### Descripción del libro

Este libro es principalmente un libro de referencia práctico para desarrolladores XSLT profesionales. No asume ningún conocimiento previo del lenguaje y muchos desarrolladores lo han utilizado como su primera introducción a XSLT; sin embargo, no está estructurado como un tutorial y hay otros libros sobre XSLT que brindan un enfoque más suave para principiantes.

El libro asume un conocimiento básico de XML, HTML y la arquitectura de la Web, y está escrito para programadores experimentados. No se asume que conoces ningún lenguaje en particular como Java o Visual Basic, solo que reconoces los conceptos que todos los lenguajes de programación tienen en común.

El libro es adecuado tanto para los usuarios de XSLT 1.0 que se actualizan a XSLT 2.0 como para los recién llegados a XSLT. El libro también es igualmente adecuado si trabaja en el mundo Java o .NET.

Como corresponde a un libro de referencia, un objetivo clave es que la cobertura sea completa y autorizada. Está diseñado para brindarle todos los detalles, no solo una descripción general del 20 por ciento del idioma que la mayoría de la gente usa el 80 por ciento del tiempo. Está diseñado para que siga volviendo al libro cada vez que encuentre tareas de programación nuevas y desafiantes, no como un libro que hojea rápidamente y luego deja en el estante. Si le gustan los detalles, disfrutará de este libro; si no, probablemente no lo hará.

Pero además de dar los detalles, este libro tiene como objetivo explicar los conceptos, con cierta profundidad. Por lo tanto, es un libro para personas que no solo quieren usar el idioma, sino que también quieren entenderlo en un nivel profundo.

El libro tiene como objetivo contarte todo lo que necesitas saber sobre el lenguaje XSLT 2.0. Le da el mismo peso a las cosas que son nuevas en XSLT 2.0 y las cosas que ya estaban presentes en la versión 1.0. El libro trata sobre el idioma, no sobre productos específicos. Sin embargo, hay apéndices sobre Saxon (la propia implementación del autor de XSLT 2.0), sobre la implementación de Altova XSLT 2.0 y sobre las API de Java y Microsoft para controlar las transformaciones XSLT, que sin duda se actualizarán para manejar tanto XSLT 2.0 como 1.0. . Un tercer procesador XSLT 2.0, Gestalt, fue lanzado poco antes de que el libro saliera a la imprenta, demasiado tarde para describirlo en detalle. Pero la experiencia de XSLT 1.0 es que ha habido un nivel muy alto de interoperabilidad entre diferentes procesadores XSLT, y si puede usar uno de ellos, puede usarlos todos.

En la edición anterior, dividimos XSLT 2.0 y XPath 2.0 en volúmenes separados. La idea era que algunos lectores pudieran estar interesados solo en XPath. Sin embargo, muchos compraron el libro XSLT 2.0 sin su compañero XPath y, como resultado, quedaron confundidos; así que esta vez, el material vuelve a estar unido. La información de referencia de XPath se encuentra en capítulos independientes, por lo que aún debería estar accesible cuando utilice XPath en contextos distintos de XSLT.

El libro no cubre los objetos de formato XSL, un tema importante en sí mismo. Tampoco cubre los esquemas XML en detalle. Si desea utilizar estas importantes tecnologías junto con XSLT, existen otros libros que les hacen justicia.

Este libro contiene veinte capítulos y ocho apéndices (el último de los cuales es un glosario) organizados en cuatro partes. La siguiente sección describe lo que puede encontrar en cada parte, capítulo y apéndice.

## Parte I

**Fundamentos:** La primera parte del libro cubre conceptos esenciales. Debería leerlos antes de comenzar a codificar. Si ignora este consejo, como hace la mayoría de la gente, entonces los leerá cuando llegue a ese punto de desesperación en el que le resulte imposible hacer que el lenguaje haga otra cosa que las tareas más triviales. XSLT es diferente de otros lenguajes y, para que funcione para usted, debe comprender cómo se diseñó para su uso.

**Capítulo 1: XSLT en Contexto:** Este capítulo explica cómo XSLT encaja en el panorama general: cómo surgió el lenguaje y cómo se ubica junto a otras tecnologías. También tiene algunos ejemplos de codificación simples para mantenerte alerta.

**Capítulo 2: El Modelo de Procesamiento XSLT:** Se trata de la arquitectura de un procesador XSLT: las entradas, las salidas y el modelo de datos. Comprender el modelo de datos es quizás lo más importante que distingue a un experto en XSLT de un aficionado; puede parecer información que no puede usar de inmediato, pero es el conocimiento lo que evitará que cometa muchos errores estúpidos.

**Capítulo 3: Estructura de la Hoja de Estilo:** El desarrollo XSLT se trata de escribir hojas de estilo, y este capítulo ofrece una visión general de cómo se ven las hojas de estilo. Explica los conceptos clave de la programación basada en reglas usando plantillas y explica cómo llevar a cabo la programación en general al estructurar su aplicación usando módulos y canalizaciones.

**Capítulo 4: Hojas de Estilo y Esquemas:** Una innovación clave en XSLT 2.0 es que las hojas de estilo pueden aprovechar el conocimiento sobre la estructura de sus documentos de entrada y salida, proporcionado en forma de un esquema XML. Este capítulo proporciona una descripción general rápida del esquema XML para describir su impacto en el desarrollo XSLT. No todo usa esquemas, y puede omitir este capítulo si entra en esa categoría.

**Capítulo 5: El Sistema de Tipos:** XPath 2.0 y XSLT 2.0 ofrecen mecanografía fuerte como alternativa al enfoque de escritura débil de los idiomas 1.0. Esto significa que puede declarar los tipos de sus variables, funciones y parámetros, y utilizar esta información para obtener una advertencia temprana de errores de programación. Este capítulo explica los tipos de datos disponibles y los mecanismos para crear tipos definidos por el usuario.

## Parte II

**Referencia XSLT y XPath:** Esta sección del libro contiene material de referencia, organizado con la esperanza de que pueda encontrar fácilmente lo que necesita cuando lo necesite. No está diseñado para lectura secuencial, aunque es posible que desee hojear las páginas para descubrir qué hay allí.

**Capítulo 6: Elementos XSLT:** Este capítulo monstruoso enumera todos los elementos XSLT que puede usar en una hoja de estilo, en orden alfabético, brindando reglas detalladas para la sintaxis y semántica de cada elemento, consejos sobre el uso y ejemplos. Esta es probablemente la parte del libro que utilizará con más frecuencia a medida que se convierta en un usuario experto de XSLT. Es un enfoque "sin piedra sin remover", basado en la creencia de que, como desarrollador profesional, necesita saber qué sucede cuando las cosas se ponen difíciles, no solo cuando el viento está en su dirección.

**Capítulo 7: Conceptos Básicos de XPath:** Este capítulo explica los conceptos básicos de XPath: las construcciones de bajo nivel como literales, variables y llamadas a funciones. También explica las reglas de contexto, que describen cómo la evaluación de las expresiones XPath depende del contexto de procesamiento XSLT en el que aparecen.

**Capítulo 8: XPath:** Operadores sobre elementos: XPath ofrece el rango habitual de operadores para realizar operaciones aritméticas, comparaciones booleanas y similares. Sin embargo, estos no siempre se comportan exactamente como cabría esperar, por lo que vale la pena leer este capítulo para ver qué está disponible y en qué se diferencia del último idioma que usó.

**Capítulo 9: XPath:*** Expresiones de ruta: Las expresiones de ruta son las que hacen que XPath sea especial; le permiten navegar por la estructura de un documento XML. Este capítulo explica la sintaxis de las expresiones de ruta, los 13 ejes que puede usar para ubicar los nodos que necesita y los operadores asociados como unión, intersección y diferencia.

**Capítulo 10: XPath:** Expresiones de secuencia: A diferencia de XPath 1.0, en la versión 2.0 todos los valores son secuencias (los singleton son solo un caso especial). Algunos de los operadores más importantes de XPath 2.0 son los que manipulan secuencias, en particular la expresión "for", que traduce una secuencia en otra mediante la aplicación de un mapeo.

**Capítulo 11: XPath:** Expresiones de tipos: El sistema de tipos se explicó en el Capítulo 5; este capítulo explica las operaciones que puede utilizar para aprovechar los tipos. Esto incluye la operación de "conversión" que se utiliza para convertir valores de un tipo a otro. Una gran parte de este capítulo está dedicada a las reglas detalladas sobre cómo se realizan estas conversiones.

**Capítulo 12: Patrones XSLT:** Este capítulo vuelve de XPath a un tema específico de XSLT. Los patrones se utilizan para definir reglas de plantilla, la esencia del enfoque de programación basada en reglas de XSLT. La razón para explicarlos ahora es que la sintaxis y la semántica de los patrones depende en gran medida de las reglas correspondientes para las expresiones XPath.

**Capítulo 13: La Library de Funciones:** XPath 2.0 incluye una Library de funciones que se pueden llamar desde cualquier expresión XPath; XSLT 2.0 amplía esto con algunas funciones adicionales que están disponibles solo cuando se usa XPath dentro de XSLT. La Library ha crecido enormemente desde XPath 1.0. Este capítulo proporciona una única referencia alfabética para todas estas funciones.

**Capítulo 14: Expresiones Regulares:** El procesamiento de texto es un área donde XSLT 2.0 y XPath 2.0 son mucho más poderosos que la versión 1.0, y esto se debe principalmente al uso de construcciones que aprovechan las expresiones regulares. Si está familiarizado con las expresiones regulares de lenguajes como Perl, este capítulo le explica en qué se diferencian las expresiones regulares XPath. Si eres nuevo en el tema, lo explica desde los primeros principios.

**Capítulo 15: Serialización:** La serialización en XSLT significa la capacidad de generar un documento XML textual a partir de la estructura de árbol que es manipulada por una hoja de estilo. Esto no es parte del procesamiento XSLT propiamente dicho, por lo que (siguiendo el ejemplo de W3C) lo ha separado en su propio capítulo. Puede controlar la serialización desde la hoja de estilo mediante una declaración, pero muchos productos también le permiten controlarla directamente a través de una API.

### Parte III

**Explotación:** La sección final del libro es un consejo y una guía sobre cómo aprovechar XSLT para escribir aplicaciones reales. Está destinado a convertirlo no solo en un codificador XSLT competente, sino también en un diseñador competente. La mejor forma de aprender es estudiando el trabajo de otros, por lo que el énfasis aquí está en los estudios de casos prácticos.

**Capítulo 16: Extensibilidad:** Este capítulo describe los "ganchos" proporcionados en la especificación XSLT para permitir a los proveedores y usuarios incorporar funciones adicionales. La forma en que esto funciona variará de una implementación a otro, por lo que no podemos cubrir todas las posibilidades, pero un aspecto importante que sí cubre el capítulo es cómo usar dichas extensiones y aún así mantener su código portátil.

**Capítulo 17: Patrones de Diseño de Hojas de Estilo:** Este capítulo explora una serie de patrones de diseño y codificación para la programación XSLT, comenzando con la hoja de estilo de "rellenar los espacios en blanco" más simple y extendiéndose hasta el uso completo de la programación recursiva en el estilo de programación funcional , que es necesario para abordar problemas de cualquier complejidad computacional. Esto brinda la oportunidad de explicar el pensamiento detrás de la programación funcional y el cambio de mentalidad necesario para aprovechar al máximo este estilo de desarrollo.

**Capítulo 18: Estudio de caso: XMLSpec:** XSLT se utiliza a menudo para representar documentos, por lo que, ¿dónde mejor buscar un estudio de caso que las hojas de estilo utilizadas por el W3C para representar las especificaciones XML y XSLT, y otras de la misma familia, para su visualización en ¿La web? Las hojas de estilo resultantes son típicas de las que encontrará en cualquier organización editorial que utilice XML para desarrollar una serie de documentos con una apariencia compatible.

**Capítulo 19: Caso de Estudio: Un Árbol Genealógico:** La visualización de un árbol genealógico es otra aplicación XSLT típica. Este ejemplo con datos semiestructurados, una mezcla de datos bastante complejos y texto narrativo, que se puede presentar de muchas formas diferentes para diferentes audiencias. También muestra cómo abordar otro problema típico de XSLT, la conversión de datos a XML desde un formato heredado basado en texto. Da la casualidad de que esto utiliza casi todas las nuevas características importantes de XSLT 2.0 en una hoja de estilo corta. Pero otro objetivo de este capítulo es mostrar una colección de hojas de estilo que realizan diferentes trabajos como parte de una aplicación completa.

**Capítulo 20:Caso de Estudio: Tour del Caballero:** Encontrar una ruta alrededor de un tablero de ajedrez donde un caballero visita cada casilla sin volver sobre sus pasos puede parecer una aplicación bastante esotérica para XSLT, pero es una buena manera de mostrar cómo son incluso los algoritmos más complejos, dentro de las capacidades del idioma. Es posible que no necesite abordar este problema en particular, pero si desea construir un diagrama SVG que muestre el progreso con respecto al plan de su proyecto, entonces los problemas no serán tan diferentes.

### Parte IV: Apéndices

**Apéndice A: Resumen de Sintaxis de XPath 2.0:** Recopila las reglas gramaticales de XPath y las precedencias de operadores en un solo lugar para facilitar la referencia.

**Apéndice B: Códigos de error:** Una lista de todos los códigos de error definidos en las especificaciones de lenguaje XSLT y XPath, con breves explicaciones para ayudarlo a comprender qué salió mal.

**Apéndice C: Compatibilidad con Versiones Anteriores:** La lista de cosas que debe tener en cuenta al convertir aplicaciones desde XSLT 1.0.

**Apéndice D: Procesadores Microsoft XSLT:** Aunque los dos procesadores Microsoft XSLT aún no son compatibles con XSLT 2.0, pensamos que a muchos lectores les resultaría útil tener aquí un resumen rápido de los principales objetos y métodos utilizados en sus API.

**Apéndice E: JAXP:** La API de Java para procesamiento XML: JAXP es una interfaz en lugar de un producto. Nuevamente, aún no tiene soporte explícito para XSLT 2.0, pero los programadores de Java lo usarán a menudo en proyectos XSLT 2.0, por lo que el libro incluye una descripción general de las clases y métodos disponibles.

**Apéndice F: Saxon:** En el momento de escribir este artículo, Saxon (desarrollado por el autor de este libro) proporciona la implementación más completa de XSLT 2.0 y XPath 2.0, por lo que sus interfaces y extensiones se tratan con cierto detalle.

**Apéndice G: Altova:** Altova, los desarrolladores de XML Spy, tienen un procesador XSLT 2.0 que se puede utilizar como parte del entorno de desarrollo o como un componente independiente. Este apéndice proporciona detalles de sus interfaces.

**Apéndice H: Glosario**

**Nota:** CD-ROM/DVD y otros materiales complementarios no se incluyen como parte del archivo de libro electrónico.

## Table of Contents

### Copyright
### About the Author
### Credits
### Acknowledgments
## [Introduction](https://github.com/adolfodelarosades/XML/blob/main/temarios/300_XSLT-2-and-XPath-2/00_Introduction.md)
* Who This Book Is For
* What This Book Covers
* How This Book Is Structured
   * Part I: Foundations
      * Chapter 1: XSLT in Context
      * Chapter 2: The XSLT Processing Model
      * Chapter 3: Stylesheet Structure
      * Chapter 4: Stylesheets and Schemas
      * Chapter 5: The Type System
   * Part II: XSLT and XPath Reference
      * Chapter 6: XSLT Elements
      * Chapter 7: XPath Fundamentals
      * Chapter 8: XPath: Operators on Items
      * Chapter 9: XPath: Path Expressions
      * Chapter 10: XPath: Sequence Expressions
      * Chapter 11: XPath: Type Expressions
      * Chapter 12: XSLT Patterns
      * Chapter 13: The Function Library
      * Chapter 14: Regular Expressions
      * Chapter 15: Serialization
   * Part III: Exploitation
      * Chapter 16: Extensibility
      * Chapter 17: Stylesheet Design Patterns
      * Chapter 18: Case Study: XMLSpec
      * Chapter 19: Case Study: A Family Tree
      * Chapter 20: Case Study: Knight's Tour
   * Part IV: Appendices
      * Appendix A: XPath 2.0 Syntax Summary
      * Appendix B: Error Codes
      * Appendix C: Backward Compatibility
      * Appendix D: Microsoft XSLT Processors
      * Appendix E: JAXP: The Java API for XML Processing
      * Appendix F: Saxon
      * Appendix G: Altova
      * Appendix H: Glossary
      * Index
* What You Need to Use This Book
* Conventions
* Downloading the Code
* Errata
* p2p.wrox.com

## [List of Examples](https://github.com/adolfodelarosades/XML/blob/main/temarios/300_XSLT-2-and-XPath-2/000.Lista.md)
* Chapter 1
* Chapter 2
* Chapter 3
* Chapter 4
* Chapter 6
* Chapter 12
* Chapter 13
* Chapter 15
* Chapter 16
* Chapter 17
* Chapter 18
* Chapter 19
* Chapter 20
* Appendix F

## I. Foundations

### 1. XSLT in Context
#### 1.1. What Is XSLT?
##### 1.1.1. Why Version 2.0?
##### 1.1.2. A Scenario: Transforming Music
#### 1.2. How Does XSLT Transform XML?
##### 1.2.1. XSLT and SQL: An Analogy
##### 1.2.2. XSLT Processors
##### 1.2.3. A Simple XSLT Stylesheet
##### 1.2.4. An XSLT 2.0 Stylesheet
#### 1.3. The Place of XSLT in the XML Family
##### 1.3.1. XSLT and XSL Formatting Objects
##### 1.3.2. XSLT and XPath
##### 1.3.3. XSLT and XML Namespaces
##### 1.3.4. XSLT and CSS
##### 1.3.5. XSLT and XML Schemas
##### 1.3.6. XSLT and XQuery
#### 1.4. The History of XSL
##### 1.4.1. Prehistory
##### 1.4.2. The First XSL Proposal
##### 1.4.3. Saxon
##### 1.4.4. Beyond XSLT 1.0
##### 1.4.5. Convergence with XQuery
##### 1.4.6. The Development of XSLT 2.0 and XPath 2.0
#### 1.5. XSLT 2.0 as a Language
##### 1.5.1. Use of XML Syntax
##### 1.5.2. No Side Effects
##### 1.5.3. Rule-Based
##### 1.5.4. Types Based on XML Schema
##### 1.5.5. A Two-Language System: XSLT and XPath
#### 1.6. Summary

### 2. The XSLT Processing Model
2.1. XSLT: A System Overview
2.1.1. A Simplified Overview
2.1.2. Trees, Not Documents
2.1.3. Different Output Formats
2.1.4. Multiple Inputs and Outputs
2.2. The XDM Tree Model
2.2.1. XML as a Tree
2.2.1.1. Nodes in the Tree Model
2.2.1.2. The Name of a Node
2.2.1.3. The String Value of a Node
2.2.1.4. The Typed Value of a Node
2.2.1.5. The Type Annotation of a Node
2.2.1.6. The Base URI of a Node
2.2.1.7. The Children of a Node
2.2.1.8. The Parent of a Node
2.2.1.9. The Attributes of a Node
2.2.1.10. The Namespaces of a Node
2.2.2. Completing the UML Class Diagram
2.2.3. Document Order
2.2.4. Names and Namespaces
2.2.4.1. Namespaces: An Overview
2.2.4.2. Namespaces in the Data Model
2.2.4.3. Namespace Sensitive Content
2.2.5. IDs and IDREFs
2.2.6. Characters in the Data Model
2.2.7. What Does the Tree Leave Out?
2.2.8. From Textual XML to a Data Model
2.2.9. Controlling Serialization
2.3. The Transformation Process
2.3.1. Invoking a Transformation
2.3.2. Template Rules
2.3.2.1. Contents of a Template Rule
2.3.2.2. Sequence Constructors
2.3.2.3. Nested Sequence Constructors
2.3.3. Push Processing
2.3.4. Controlling Which Nodes to Process
2.3.5. Modes
2.3.6. Built-In Template Rules
2.3.7. Conflict Resolution Policy
2.4. Error Handling
2.5. Variables and Expressions
2.5.1. Variables
2.5.2. Parameters
2.5.3. Expressions
2.5.4. Context
2.5.5. Temporary Documents
2.6. Summary

### 3. Stylesheet Structure
3.1. Changes in XSLT 2.0
3.2. The Modular Structure of a Stylesheet
3.3. The <xsl:stylesheet> Element
3.4. The <?xml-stylesheet?> Processing Instruction
3.5. Embedded Stylesheets
3.6. Declarations
3.6.1. XSLT-Defined Declarations
3.6.2. Implementor-Defined Declarations
3.6.3. User-Defined Top-Level Elements
3.7. Instructions
3.7.1. XSLT Instructions
3.7.2. Extension Instructions
3.7.3. Literal Result Elements
3.7.3.1. Format
3.7.3.2. Position
3.7.3.3. Attributes
3.7.3.4. Content
3.7.3.5. Effect
3.7.3.6. Usage
3.7.3.7. Attributes of a Literal Result Element
3.7.3.8. Namespaces for a Literal Result Element
3.7.3.9. Namespace Inheritance
3.7.3.10. Namespace Prefixes
3.7.3.11. Namespace Aliasing
3.7.4. Attribute Value Templates
3.8. Simplified Stylesheets
3.9. Writing Portable Stylesheets
3.9.1. Conditional Compilation
3.9.2. Version Compatibility
3.9.2.1. Forward Compatibility in XSLT 1.0
3.9.2.2. Backward Compatibility in XSLT 2.0
3.9.3. Extensibility
3.9.3.1. Extension Functions
3.9.3.2. Extension Instructions
3.10. Whitespace
3.10.1. The Effect of Stripping Whitespace Nodes
3.10.2. Whitespace Nodes in the Stylesheet
3.10.3. Solving Whitespace Problems
3.10.3.1. Too Much Whitespace
3.10.3.2. Too Little Whitespace
3.11. Summary

### 4. Stylesheets and Schemas
4.1. XML Schema: An Overview
4.1.1. Simple Type Definitions
4.1.2. Elements with Attributes and Simple Content
4.1.3. Elements with Mixed Content
4.1.4. Elements with Element-Only Content
4.1.5. Defining a Type Hierarchy
4.1.6. Substitution Groups
4.2. Declaring Types in XSLT
4.3. Validating the Source Document
4.4. Validating the Result Document
4.5. Validating a Temporary Document
4.6. Validating Individual Elements
4.7. Validating Individual Attributes
4.8. The default-validation Attribute
4.9. Importing Schemas
4.10. Using xsi:type
4.11. Nillability
4.12. Summary

### 5. Types
5.1. What Is a Type System?
5.2. Changes in 2.0
5.3. Sequences
5.4. Atomic Values
5.5. Atomic Types
5.5.1. The Major Atomic Types
5.5.1.1. xs:anyURI
5.5.1.2. xs:boolean
5.5.1.3. xs:date
5.5.1.4. xs:dateTime
5.5.1.5. xs:decimal
5.5.1.6. xs:double
5.5.1.7. xs:integer
5.5.1.8. xs:QName
5.5.1.9. xs:string
5.5.1.10. xs:time
5.5.1.11. xs:dayTimeDuration and xs:yearMonthDuration
5.5.2. The Minor Atomic Types
5.5.2.1. The Partial Date Types
5.5.2.2. Binary Types
5.5.2.3. Single-Precision Floating Point
5.5.2.4. The xs:duration Type
5.5.2.5. The xs:NOTATION Type
5.5.3. Derived Numeric Types
5.5.4. Derived String Types
5.5.5. Untyped Atomic Values
5.5.6. xs:NMTOKENS, xs:IDREFS, and xs:ENTITIES
5.6. Schema Types and XPath Types
5.7. The Type Matching Rules
5.8. Static and Dynamic Type Checking
5.9. Summary

## II. XSLT and XPath Reference

### 6. XSLT Elements
6.1. xsl:analyze-string
6.1.1. Changes in 2.0
6.1.2. Format
6.1.2.1. Position
6.1.2.2. Attributes
6.1.2.3. Content
6.1.3. Effect
6.1.3.1. Regular Expression Syntax
6.1.3.2. Captured Groups
6.1.4. Usage and Examples
6.1.4.1. A Single-Match Example
6.1.4.2. A Multiple-Match Example
6.1.5. See Also
6.2. xsl:apply-imports
6.2.1. Changes in 2.0
6.2.2. Format
6.2.2.1. Position
6.2.2.2. Attributes
6.2.2.3. Content
6.2.3. Effect
6.2.4. Usage and Examples
6.2.5. See Also
6.3. xsl:apply-templates
6.3.1. Changes in 2.0
6.3.2. Format
6.3.2.1. Position
6.3.2.2. Attributes
6.3.2.3. Content
6.3.3. Effect
6.3.3.1. The select Attribute
6.3.3.2. Sorting
6.3.3.3. Choosing a Template Rule
6.3.3.4. Parameters
6.3.3.5. Result
6.3.4. Usage and Examples
6.3.4.1. <xsl:apply-templates> versus <xsl:for-each>
6.3.4.2. Modes
6.3.4.3. Simulating Higher Order Functions
6.3.5. See Also
6.4. xsl:attribute
6.4.1. Changes in 2.0
6.4.2. Format
6.4.2.1. Position
6.4.2.2. Attributes
6.4.2.3. Content
6.4.3. Effect
6.4.3.1. The Name of the Attribute
6.4.3.2. Using the New Attribute Node
6.4.3.3. The Value of the Attribute
6.4.3.4. Validating and Annotating the Attribute
6.4.4. Usage
6.4.4.1. Different Ways of Creating Attributes
6.4.4.2. Creating an Attribute Whose Value Is a QName
6.4.5. Examples
6.4.6. See Also
6.5. xsl:attribute-set
6.5.1. Changes in 2.0
6.5.2. Format
6.5.2.1. Position
6.5.2.2. Attributes
6.5.2.3. Content
6.5.3. Effect
6.5.4. Usage
6.5.5. Examples
6.5.6. See Also
6.6. xsl:call-template
6.6.1. Changes in 2.0
6.6.2. Format
6.6.2.1. Position
6.6.2.2. Attributes
6.6.2.3. Content
6.6.3. Effect
6.6.3.1. The Template Name
6.6.3.2. Parameters
6.6.3.3. Context
6.6.4. Usage and Examples
6.6.4.1. Using the Result
6.6.4.2. Changing the Context Item
6.6.4.3. Recursion: Processing a List of Values
6.6.5. See Also
6.7. xsl:character-map
6.7.1. Changes in 2.0
6.7.2. Format
6.7.2.1. Position
6.7.2.2. Attributes
6.7.2.3. Content
6.7.3. Effect
6.7.4. Usage and Examples
6.7.5. See Also
6.8. xsl:choose
6.8.1. Changes in 2.0
6.8.2. Format
6.8.2.1. Position
6.8.2.2. Attributes
6.8.2.3. Content
6.8.3. Effect
6.8.4. Usage
6.8.5. Examples
6.8.6. See Also
6.9. xsl:comment
6.9.1. Changes in 2.0
6.9.2. Format
6.9.2.1. Position
6.9.2.2. Attributes
6.9.2.3. Content
6.9.3. Effect
6.9.4. Usage
6.9.5. Examples
6.9.5.1. Example 1: Showing the Date and Time of Transformation
6.9.5.2. Example 2: Generating Commented-Out JavaScript
6.9.5.3. Example 3: Generating Comments Containing Markup
6.10. xsl:copy
6.10.1. Changes in 2.0
6.10.2. Format
6.10.2.1. Position
6.10.2.2. Attributes
6.10.2.3. Content
6.10.3. Effect
6.10.4. Usage
6.10.5. Examples
6.10.6. See Also
6.11. xsl:copy-of
6.11.1. Changes in 2.0
6.11.2. Format
6.11.2.1. Position
6.11.2.2. Attributes
6.11.2.3. Content
6.11.3. Effect
6.11.4. Usage and Examples
6.11.4.1. Copying Nodes to and from Temporary Trees
6.11.4.2. Deep Copy
6.11.4.3. Copying Namespace Nodes
6.11.4.4. Copying Type Annotations
6.11.5. See Also
6.12. xsl:decimal-format
6.12.1. Changes in 2.0
6.12.2. Format
6.12.2.1. Position
6.12.2.2. Attributes
6.12.2.3. Content
6.12.3. Effect
6.12.4. Usage
6.12.5. Examples
6.12.5.1. Example 1: Comma as a Decimal Separator
6.12.5.2. Example 2: Non-Western Digits
6.12.5.3. Example 3: NaN and Infinity
6.12.6. See Also
6.13. xsl:document
6.13.1. Changes in 2.0
6.13.2. Format
6.13.2.1. Position
6.13.2.2. Attributes
6.13.2.3. Content
6.13.3. Effect
6.13.3.1. The Content of the Document
6.13.3.2. Validating and Annotating the Document
6.13.4. Usage and Examples
6.13.5. See Also
6.14. xsl:element
6.14.1. Changes in 2.0
6.14.2. Format
6.14.2.1. Position
6.14.2.2. Attributes
6.14.2.3. Content
6.14.3. Effect
6.14.3.1. The Name of the Element
6.14.3.2. The Content of the Element
6.14.3.3. Namespace Fixup
6.14.3.4. Namespace Inheritance
6.14.3.5. Validating and Annotating the Element
6.14.4. Usage and Examples
6.14.5. See Also
6.15. xsl:fallback
6.15.1. Changes in 2.0
6.15.2. Format
6.15.2.1. Position
6.15.2.2. Attributes
6.15.2.3. Content
6.15.3. Effect
6.15.4. Usage
6.15.5. Examples
6.15.5.1. Example 1: XSLT Forward Compatibility
6.15.5.2. Example 2: Vendor Portability
6.15.5.3. Example 3: Temporary Trees
6.15.6. See Also
6.16. xsl:for-each
6.16.1. Changes in 2.0
6.16.2. Format
6.16.2.1. Position
6.16.2.2. Attributes
6.16.2.3. Content
6.16.3. Effect
6.16.3.1. The select Attribute
6.16.3.2. Sorting
6.16.4. Usage and Examples
6.16.4.1. Iterating over a Sequence of Nodes
6.16.4.2. Changing the Context Item
6.16.5. See Also
6.17. xsl:for-each-group
6.17.1. Changes in 2.0
6.17.2. Format
6.17.2.1. Position
6.17.2.2. Attributes
6.17.2.3. Content
6.17.3. Effect
6.17.3.1. group-by
6.17.3.2. group-adjacent
6.17.3.3. group-starting-with
6.17.3.4. group-ending-with
6.17.3.5. Sorting the Groups
6.17.4. Usage and Examples
6.17.4.1. Using group-by
6.17.4.2. Using group-adjacent
6.17.4.3. Using group-starting-with
6.17.4.4. Using group-ending-with
6.17.4.5. Arranging Data in Tables
6.17.5. See Also
6.18. xsl:function
6.18.1. Changes in 2.0
6.18.2. Format
6.18.2.1. Position
6.18.2.2. Attributes
6.18.2.3. Content
6.18.3. Effect
6.18.3.1. The override Attribute
6.18.4. Usage and Examples
6.18.4.1. Functions versus Named Templates
6.18.4.2. Recursion
6.18.5. See Also
6.19. xsl:if
6.19.1. Changes in 2.0
6.19.2. Format
6.19.2.1. Position
6.19.2.2. Attributes
6.19.2.3. Content
6.19.3. Effect
6.19.4. Usage
6.19.5. Examples
6.19.6. See Also
6.20. xsl:import
6.20.1. Changes in 2.0
6.20.2. Format
6.20.2.1. Position
6.20.2.2. Attributes
6.20.2.3. Content
6.20.3. Effect
6.20.3.1. Locating the Stylesheet Module
6.20.3.2. Determining the Import Precedence
6.20.3.3. Effect of Import Precedence
6.20.4. Usage
6.20.5. Examples
6.20.6. See Also
6.21. xsl:import-schema
6.21.1. Changes in 2.0
6.21.2. Format
6.21.2.1. Position
6.21.2.2. Attributes
6.21.2.3. Content
6.21.3. Effect
6.21.4. Usage
6.21.5. Examples
6.22. xsl:include
6.22.1. Changes in 2.0
6.22.2. Format
6.22.2.1. Position
6.22.2.2. Attributes
6.22.2.3. Content
6.22.3. Effect
6.22.4. Usage and Examples
6.22.5. See Also
6.23. xsl:key
6.23.1. Changes in 2.0
6.23.2. Format
6.23.2.1. Position
6.23.2.2. Attributes
6.23.2.3. Content
6.23.3. Effect
6.23.4. Usage and Examples
6.23.4.1. Keys versus IDs
6.23.4.2. Using a Simple Key
6.23.4.3. Multivalued Keys
6.23.4.4. Multiple Named Keys
6.23.4.5. Multiple Definitions for the Same Key
6.23.4.6. Composite Keys
6.23.4.7. Using Keys for Grouping
6.23.5. See Also
6.24. xsl:matching-substring
6.24.1. Changes in 2.0
6.24.2. Format
6.24.2.1. Position
6.24.2.2. Attributes
6.24.2.3. Content
6.24.3. Effect
6.24.4. Usage and Examples
6.24.5. See Also
6.25. xsl:message
6.25.1. Changes in 2.0
6.25.2. Format
6.25.2.1. Position
6.25.2.2. Attributes
6.25.2.3. Content
6.25.3. Effect
6.25.4. Usage
6.25.5. Examples
6.25.5.1. Localized Messages
6.25.6. See Also
6.26. xsl:namespace
6.26.1. Changes in 2.0
6.26.2. Format
6.26.2.1. Position
6.26.2.2. Attributes
6.26.2.3. Content
6.26.3. Effect
6.26.4. Usage and Examples
6.26.5. See Also
6.27. xsl:namespace-alias
6.27.1. Changes in 2.0
6.27.2. Format
6.27.2.1. Position
6.27.2.2. Attributes
6.27.2.3. Content
6.27.3. Effect
6.27.4. Usage and Examples
6.27.4.1. Aliasing the XML Namespace
6.27.4.2. Choice of Prefixes in the Result Document
6.27.5. See Also
6.28. xsl:next-match
6.28.1. Changes in 2.0
6.28.2. Format
6.28.2.1. Position
6.28.2.2. Attributes
6.28.2.3. Content
6.28.3. Effect
6.28.4. Usage and Examples
6.28.5. See Also
6.29. xsl:non-matching-substring
6.29.1. Changes in 2.0
6.29.2. Format
6.29.2.1. Position
6.29.2.2. Attributes
6.29.2.3. Content
6.29.3. Effect
6.29.4. Usage and Examples
6.29.5. See Also
6.30. xsl:number
6.30.1. Changes in 2.0
6.30.2. Format
6.30.2.1. Position
6.30.2.2. Attributes
6.30.2.3. Content
6.30.3. Effect
6.30.3.1. Determining a Sequence Number
6.30.3.2. Analyzing the Format String
6.30.3.3. Formatting the Numbers
6.30.3.4. Outputting the Number
6.30.4. Usage and Examples
6.30.4.1. level = "single"
6.30.4.2. level = "any"
6.30.4.3. level = "multiple"
6.30.5. See Also
6.31. xsl:otherwise
6.31.1. Changes in 2.0
6.31.2. Format
6.31.2.1. Position
6.31.2.2. Attributes
6.31.2.3. Content
6.31.3. Effect
6.31.4. Usage and Examples
6.31.5. See Also
6.32. xsl:output
6.32.1. Changes in 2.0
6.32.2. Format
6.32.2.1. Position
6.32.2.2. Attributes
6.32.3. Content
6.32.4. Effect
6.32.5. Examples
6.32.6. See Also
6.33. xsl:output-character
6.33.1. Changes in 2.0
6.33.2. Format
6.33.2.1. Position
6.33.2.2. Attributes
6.33.2.3. Content
6.33.3. Effect
6.33.4. See Also
6.34. xsl:param
6.34.1. Changes in 2.0
6.34.2. Format
6.34.2.1. Format for Stylesheet Parameters
6.34.2.2. Format for Template Parameters
6.34.2.3. Format for Function Parameters
6.34.2.4. Position
6.34.2.5. Attributes
6.34.2.6. Content
6.34.3. Effect
6.34.3.1. The Type of the Parameter
6.34.3.2. The Default Value of the Parameter
6.34.3.3. The Name of the Parameter
6.34.3.4. Tunnel Parameters
6.34.4. Usage
6.34.4.1. Using Stylesheet Parameters
6.34.4.2. Using Template Parameters
6.34.4.3. Using Tunnel Parameters
6.34.5. Examples
6.34.6. See Also
6.35. xsl:perform-sort
6.35.1. Changes in 2.0
6.35.2. Format
6.35.2.1. Position
6.35.2.2. Attributes
6.35.2.3. Content
6.35.3. Effect
6.35.4. Usage and Examples
6.35.5. See Also
6.36. xsl:preserve-space
6.36.1. Changes in 2.0
6.36.2. Format
6.36.2.1. Position
6.36.2.2. Attributes
6.36.2.3. Content
6.36.3. Effect
6.36.4. Usage
6.36.5. Examples
6.36.6. See Also
6.37. xsl:processing-instruction
6.37.1. Changes in 2.0
6.37.2. Format
6.37.2.1. Position
6.37.2.2. Attributes
6.37.2.3. Content
6.37.3. Effect
6.37.4. Usage
6.37.5. Examples
6.38. xsl:result-document
6.38.1. Changes in 2.0
6.38.2. Format
6.38.2.1. Position
6.38.2.2. Attributes
6.38.2.3. Content
6.38.3. Effect
6.38.4. Usage
6.38.5. Examples
6.38.6. See Also
6.39. xsl:sequence
6.39.1. Changes in 2.0
6.39.2. Format
6.39.2.1. Position
6.39.2.2. Attributes
6.39.2.3. Content
6.39.3. Effect
6.39.4. Usage and Examples
6.39.5. See Also
6.40. xsl:sort
6.40.1. Changes in 2.0
6.40.2. Format
6.40.2.1. Position
6.40.2.2. Attributes
6.40.2.3. Content
6.40.3. Effect
6.40.3.1. Collations
6.40.4. Usage
6.40.4.1. Using Collations
6.40.4.2. Dynamic Sort Keys
6.40.5. Examples
6.40.6. See Also
6.41. xsl:strip-space
6.41.1. Changes in 2.0
6.41.2. Format
6.41.2.1. Position
6.41.2.2. Attributes
6.41.2.3. Content
6.41.3. Effect, Usage, and Examples
6.41.4. See Also
6.42. xsl:stylesheet
6.42.1. Changes in 2.0
6.42.2. Format
6.42.2.1. Position
6.42.2.2. Namespace Declarations
6.42.2.3. Attributes
6.42.2.4. Content
6.42.3. The id Attribute
6.42.3.1. Effect
6.42.3.2. Usage
6.42.4. The default-collation Attribute
6.42.4.1. Effect
6.42.4.2. Usage
6.42.5. The default-validation Attribute
6.42.5.1. Effect
6.42.5.2. Usage
6.42.6. The exclude-result-prefixes Attribute
6.42.6.1. Effect
6.42.6.1.1. What exclude-result-prefixes Does
6.42.6.1.2. What exclude-result-prefixes Doesn't Do
6.42.6.2. Usage
6.42.7. The extension-element-prefixes Attribute
6.42.7.1. Effect
6.42.7.2. Usage
6.42.8. The input-type-annotations Attribute
6.42.8.1. Effect
6.42.8.2. Usage
6.42.9. The use-when Attribute
6.42.9.1. Effect
6.42.9.2. Usage
6.42.10. The version Attribute
6.42.10.1. Effect
6.42.10.2. Usage
6.42.11. The xpath-default-namespace Attribute
6.42.11.1. Effect
6.42.11.2. Usage
6.42.12. See Also
6.43. xsl:template
6.43.1. Changes in 2.0
6.43.2. Format
6.43.2.1. Position
6.43.2.2. Attributes
6.43.2.3. Content
6.43.3. Effect
6.43.3.1. The match Attribute
6.43.3.2. The name Attribute
6.43.3.3. The priority Attribute
6.43.3.4. The mode Attribute
6.43.3.5. Evaluating a Template
6.43.4. Usage and Examples
6.43.4.1. Using Template Rules
6.43.4.2. Using Modes
6.43.5. See Also
6.44. xsl:text
6.44.1. Changes in 2.0
6.44.2. Format
6.44.2.1. Position
6.44.2.2. Attributes
6.44.2.3. Content
6.44.3. Effect
6.44.4. Usage
6.44.4.1. Whitespace Control
6.44.4.2. Examples
6.44.5. See Also
6.45. xsl:transform
6.45.1. Format
6.45.2. See Also
6.46. xsl:value-of
6.46.1. Changes in 2.0
6.46.2. Format
6.46.2.1. Position
6.46.2.2. Attributes
6.46.2.3. Content
6.46.3. Effect
6.46.4. Usage
6.46.4.1. Avoiding Surprises
6.46.5. Examples
6.46.6. See Also
6.47. xsl:variable
6.47.1. Changes in 2.0
6.47.2. Format
6.47.2.1. Position
6.47.2.2. Attributes
6.47.2.3. Content
6.47.3. Effect
6.47.3.1. The Name of the Variable
6.47.3.2. The Value of the Variable
6.47.3.3. Standard Conversion Rules
6.47.4. Usage
6.47.5. Examples
6.47.5.1. Convenience Variables
6.47.5.2. Variables to Capture Context-Sensitive Values
6.47.5.3. Variables to Hold Intermediate Results
6.47.5.4. Avoiding Trivial Documents
6.47.6. See Also
6.48. xsl:when
6.48.1. Changes in 2.0
6.48.2. Format
6.48.2.1. Position
6.48.2.2. Attributes
6.48.2.3. Content
6.48.3. Effect
6.48.4. Usage and Examples
6.48.5. See Also
6.49. xsl:with-param
6.49.1. Changes in 2.0
6.49.2. Format
6.49.2.1. Position
6.49.2.2. Attributes
6.49.2.3. Content
6.49.3. Effect
6.49.4. Usage and Examples
6.49.5. See Also
6.50. Summary

### 7. XPath Fundamentals
7.1. Notation
7.2. Where to Start
7.3. Expressions
7.3.1. Examples
7.4. Lexical Constructs
7.4.1. Comments
7.4.1.1. Changes in XPath 2.0
7.4.2. Numeric Literals
7.4.2.1. Examples
7.4.2.2. Changes in XPath 2.0
7.4.3. String Literals
7.4.3.1. Examples
7.4.3.2. Changes in XPath 2.0
7.4.3.3. XSLT Usage
7.4.4. Names
7.4.4.1. Examples
7.4.4.2. XSLT Usage
7.4.5. Operators
7.5. Primary Expressions
7.5.1. Examples
7.6. Variable References
7.6.1. Usage
7.6.2. Examples
7.7. Parenthesized Expressions
7.7.1. Changes in XPath 2.0
7.8. Context Item Expressions
7.8.1. Changes in XPath 2.0
7.8.2. Usage
7.9. Function Calls
7.9.1. Identifying the Function to Be Called
7.9.2. Converting the Arguments and the Result
7.9.3. Changes in XPath 2.0
7.9.4. Side Effects
7.9.5. Examples
7.10. Conditional Expressions
7.10.1. Changes in XPath 2.0
7.10.2. Examples
7.11. The XPath Evaluation Context
7.11.1. The Static Context
7.11.1.1. XPath 1.0 Compatibility Mode
7.11.1.2. In-Scope Namespaces
7.11.1.3. Default Namespaces
7.11.1.4. In-Scope Schema Definitions
7.11.1.5. In-Scope Variables
7.11.1.6. In-Scope Functions
7.11.1.7. Collations
7.11.1.8. Base URI
7.11.1.9. Statically Known Documents and Collections
7.11.2. The Dynamic Context
7.11.2.1. The Focus
7.11.2.2. Variable Values
7.11.2.3. Function Implementations
7.11.2.4. Current dateTime
7.11.2.5. Implicit Timezone
7.11.2.6. Available Documents and Collections
7.12. Summary

### 8. XPath: Operators on Items
8.1. Arithmetic Operators
8.1.1. Syntax
8.1.2. Type Promotion
8.1.3. Changes in XPath 2.0
8.1.4. Effect
8.1.5. Arithmetic Using Numbers
8.1.5.1. Integer Arithmetic
8.1.5.2. Decimal Arithmetic
8.1.5.3. Floating-Point Arithmetic
8.1.6. Examples of Numeric Arithmetic
8.1.7. Arithmetic Using Durations
8.1.7.1. Date/Time Plus Duration
8.1.7.2. Duration Plus Duration
8.1.7.3. Duration Times Number
8.1.7.4. Date/Time Minus Date/Time
8.1.7.5. Duration Divided by Duration
8.2. Value Comparisons
8.2.1. Permitted Operand Types
8.2.2. Type Checking for Value Comparisons
8.2.3. Examples of Value Comparisons
8.3. General Comparisons
8.3.1. Changes in XPath 2.0
8.3.2. Rules for General Comparisons
8.3.3. Existential Comparison
8.3.4. Examples of General Comparisons
8.4. Node Comparisons
8.4.1. The «is» Operator
8.4.2. The operators «<<» and «>>»
8.4.3. Changes in XPath 2.0
8.5. Boolean Expressions
8.5.1. Shortcut Semantics
8.5.2. Examples
8.6. Summary

### 9. XPath: Path Expressions
9.1. Examples of Path Expressions
9.2. Changes in XPath 2.0
9.3. Document Order and Duplicates
9.4. The Binary « /» Operator
9.4.1. Syntax
9.4.2. Effect
9.4.3. Examples of the Binary «/» Operator
9.4.4. Associativity of the «/» Operator
9.5. Axis Steps
9.5.1. Syntax of Axis Steps
9.5.2. Effect
9.5.3. Examples of Axis Steps
9.5.4. Axes
9.5.5. Node Tests
9.5.5.1. Usage
9.5.5.2. Examples of Node Tests
9.5.6. Name Tests
9.5.6.1. Syntax
9.5.6.2. Usage
9.5.6.3. Examples of Name Tests
9.5.7. Kind Tests
9.5.7.1. Usage
9.5.7.2. Examples of Kind Tests
9.5.8. Predicates
9.5.9. Abbreviated Axis Steps
9.5.9.1. Syntax
9.5.9.2. Defaulting the Axis Name in a Step
9.5.9.3. The «@» Abbreviation
9.5.9.3.1. Examples
9.5.9.4. The «..» Abbreviation
9.5.9.4.1. Examples in Context
9.5.9.5. The Root Expression «/»
9.6. Rooted Path Expressions
9.6.1. Syntax
9.6.2. Examples of Rooted Paths
9.7. The « //» Abbreviation
9.7.1. Examples Using «//»
9.7.2. Comparing «//» with «/descendant::»
9.8. Combining Sets of Nodes
9.8.1. Syntax
9.8.2. Examples
9.8.3. Usage
9.8.4. Set Intersection and Difference in XPath 1.0
9.8.5. Sets of Atomic Values
9.9. Summary

### 10. XPath: Sequence Expressions
10.1. The Comma Operator
10.1.1. Examples
10.2. Numeric Ranges: The «to» Operator
10.2.1. Examples
10.3. Filter Expressions
10.3.1. Examples
10.4. The «for» Expression
10.4.1. Mapping a Sequence
10.4.2. Examples
10.4.3. The Context Item in a «for» Expression
10.4.4. Combining Multiple Sequences
10.4.5. Example
10.5. Simple Mapping Expressions
10.6. The «some» and «every» Expressions
10.6.1. Examples
10.6.2. Quantification and the «=» Operator
10.6.3. Errors in «some» and «every» Expressions
10.7. Summary

### 11. XPath: Type Expressions
11.1. Converting Atomic Values
11.1.1. Converting between Primitive Types
11.1.1.1. Converting from anyURI
11.1.1.2. Converting from base64Binary
11.1.1.3. Converting from boolean
11.1.1.4. Converting from date
11.1.1.5. Converting from dateTime
11.1.1.6. Converting from decimal
11.1.1.7. Converting from double
11.1.1.8. Converting from duration
11.1.1.9. Converting from float
11.1.1.10. Converting from gDay
11.1.1.11. Converting from gMonth
11.1.1.12. Converting from gMonthDay
11.1.1.13. Converting from gYear
11.1.1.14. Converting from gYearMonth
11.1.1.15. Converting from hexBinary
11.1.1.16. Converting from NOTATION
11.1.1.17. Converting from QName
11.1.1.18. Converting from string
11.1.1.19. Converting from time
11.1.1.20. Converting from untypedAtomic
11.1.2. Converting between Derived Types
11.1.2.1. Casting from xs:string to a Derived Type
11.1.2.2. Converting Non-string Values to a Derived Type
11.1.2.3. Casting to an xs:integer
11.1.2.4. Casting to xs:yearMonthDuration and xs:dayTimeDuration
11.2. Sequence Type Descriptors
11.2.1. Matching Atomic Values
11.2.2. Matching Nodes
11.2.3. Matching Elements and Attributes
11.2.3.1. Using Global Element and Attribute Declarations
11.2.3.2. Examples
11.3. The «instance of» Operator
11.4. The «treat as» Operator
11.5. Summary

### 12. XSLT Patterns
12.1. Patterns and Expressions
12.2. Changes in XSLT 2.0
12.3. The Formal Definition
12.3.1. Applying the Definition in Practice
12.3.2. An Algorithm for Matching Patterns
12.3.3. Patterns Containing Predicates
12.4. An Informal Definition
12.5. Conflict Resolution
12.6. Matching Parentless Nodes
12.7. The Syntax of Patterns
12.7.1. Pattern
12.7.1.1. Syntax
12.7.1.2. Effect
12.7.1.3. Usage
12.7.1.4. Examples
12.7.2. PathPattern
12.7.2.1. Syntax
12.7.2.2. Effect
12.7.2.3. Usage
12.7.2.4. Examples
12.7.3. RelativePathPattern
12.7.3.1. Syntax
12.7.3.2. Effect
12.7.3.3. Usage
12.7.3.4. Examples
12.7.4. PatternStep
12.7.4.1. Syntax
12.7.4.2. Effect
12.7.4.2.1. The PatternAxis
12.7.4.2.2. The NameTest
12.7.4.2.3. The KindTest
12.7.4.2.4. KindTests for Element Nodes
12.7.4.2.5. KindTests for Attribute Nodes
12.7.4.2.6. KindTests for Document Nodes
12.7.4.2.7. Using KindTests
12.7.4.2.8. Predicates
12.7.4.3. Examples
12.7.5. IdKeyPattern
12.7.5.1. Syntax
12.7.5.2. Usage
12.7.5.3. Examples
12.8. Summary

### 13. The Function Library
13.1. A Word about Naming
13.2. Functions by Category
13.2.1. Boolean Functions
13.2.2. Numeric Functions
13.2.3. String Functions
13.2.4. Date and Time Functions
13.2.5. Duration Functions
13.2.6. Aggregation Functions
13.2.7. Functions on URIs
13.2.8. Functions on QNames
13.2.9. Functions on Sequences
13.2.10. Functions That Return Properties of Nodes
13.2.11. Functions That Find Nodes
13.2.12. Functions That Return Context Information
13.2.13. Diagnostic Functions
13.2.14. Functions That Return Information about the XSLT Environment
13.2.15. Functions That Assert a Static Type
13.3. Notation
13.4. Code Samples
13.5. Function Definitions
13.5.1. abs
13.5.1.1. Signature
13.5.1.2. Effect
13.5.1.3. Examples
13.5.2. adjust-date-to-timezone, adjust-dateTime-to-timezone, adjust-time-to-timezone
13.5.2.1. Signature
13.5.2.2. Effect
13.5.2.3. Examples
13.5.2.4. Usage
13.5.2.5. See Also
13.5.3. avg
13.5.3.1. Signature
13.5.3.2. Effect
13.5.3.3. Examples
13.5.3.4. See Also
13.5.4. base-uri
13.5.4.1. Signature
13.5.4.2. Effect
13.5.4.3. Usage and Examples
13.5.4.4. See Also
13.5.5. boolean
13.5.5.1. Changes in 2.0
13.5.5.2. Signature
13.5.5.3. Effect
13.5.5.4. Examples
13.5.5.5. Usage
13.5.5.6. XSLT Examples
13.5.5.7. See Also
13.5.6. ceiling
13.5.6.1. Changes in 2.0
13.5.6.2. Signature
13.5.6.3. Effect
13.5.6.4. Examples
13.5.6.5. Usage
13.5.6.6. See Also
13.5.7. codepoint-equal
13.5.7.1. Signature
13.5.7.2. Effect
13.5.7.3. Examples
13.5.7.4. See Also
13.5.8. codepoints-to-string
13.5.8.1. Signature
13.5.8.2. Effect
13.5.8.3. Examples
13.5.8.4. Usage
13.5.8.5. See Also
13.5.9. collection
13.5.9.1. Signature
13.5.9.2. Effect
13.5.9.3. See Also
13.5.10. compare
13.5.10.1. Signature
13.5.10.2. Effect
13.5.10.3. Examples
13.5.10.4. Usage
13.5.10.5. See Also
13.5.11. concat
13.5.11.1. Changes in 2.0
13.5.11.2. Signature
13.5.11.3. Effect
13.5.11.4. Examples
13.5.11.5. Usage in XSLT
13.5.11.6. See Also
13.5.12. contains
13.5.12.1. Changes in 2.0
13.5.12.2. Signature
13.5.12.3. Effect
13.5.12.4. Examples
13.5.12.5. Usage
13.5.12.6. See Also
13.5.13. count
13.5.13.1. Changes in 2.0
13.5.13.2. Signature
13.5.13.3. Effect
13.5.13.4. Examples
13.5.13.5. Usage
13.5.13.6. See Also
13.5.14. current
13.5.14.1. Changes in 2.0
13.5.14.2. Signature
13.5.14.3. Effect
13.5.14.4. Usage
13.5.14.5. Example
13.5.15. current-date, current-dateTime, current-time
13.5.15.1. Signature
13.5.15.2. Effect
13.5.15.3. Examples
13.5.15.4. Usage
13.5.15.5. See Also
13.5.16. current-group
13.5.16.1. Signature
13.5.16.2. Effect
13.5.16.3. Usage and Examples
13.5.16.4. See Also
13.5.17. current-grouping-key
13.5.17.1. Signature
13.5.17.2. Effect
13.5.17.3. Usage and Examples
13.5.17.4. See Also
13.5.18. current-time
13.5.19. data
13.5.19.1. Signature
13.5.19.2. Effect
13.5.19.3. Examples
13.5.19.4. Usage
13.5.19.5. See Also
13.5.20. dateTime
13.5.20.1. Signature
13.5.20.2. Effect
13.5.20.3. Examples
13.5.20.4. See Also
13.5.21. day-from-date, day-from-dateTime
13.5.21.1. Signature
13.5.21.2. Effect
13.5.21.3. Examples
13.5.21.4. See Also
13.5.22. days-from-duration
13.5.22.1. Signature
13.5.22.2. Effect
13.5.22.3. Examples
13.5.22.4. See Also
13.5.23. deep-equal
13.5.23.1. Signature
13.5.23.2. Effect
13.5.23.3. Examples
13.5.23.4. Usage
13.5.24. default-collation
13.5.24.1. Signature
13.5.24.2. Usage
13.5.24.3. See Also
13.5.25. distinct-values
13.5.25.1. Signature
13.5.25.2. Effect
13.5.25.3. Examples
13.5.25.4. Usage
13.5.25.5. See Also
13.5.26. doc, doc-available
13.5.26.1. Changes in 2.0
13.5.26.2. Signatures
13.5.26.2.1. The doc() function
13.5.26.2.2. The doc-available() function
13.5.26.3. Effect
13.5.26.4. Usage and Examples
13.5.26.5. See Also
13.5.27. document
13.5.27.1. Changes in 2.0
13.5.27.2. Signature
13.5.27.3. Effect
13.5.27.4. Resolving the URI
13.5.27.5. Parsing the Document
13.5.27.6. URIs Held in Nodes
13.5.27.6.1. Usage: document() Applied to Nodes
13.5.27.7. URIs as Atomic Values
13.5.27.7.1. Usage: document() Applied to Atomic Values
13.5.27.8. Supplying an Explicit Base URI
13.5.27.9. See Also
13.5.28. document-uri
13.5.28.1. Signature
13.5.28.2. Effect
13.5.28.3. Usage
13.5.28.4. See Also
13.5.29. element-available
13.5.29.1. Changes in 2.0
13.5.29.2. Signature
13.5.29.3. Effect
13.5.29.4. Usage and Examples
13.5.29.4.1. Testing for Features Available in Later XSLT Versions
13.5.29.5. Testing for Vendor Extensions
13.5.29.6. See Also
13.5.30. empty
13.5.30.1. Signature
13.5.30.2. Effect
13.5.30.3. Examples
13.5.30.4. Usage
13.5.30.5. See Also
13.5.31. encode-for-uri
13.5.31.1. Signature
13.5.31.2. Effect
13.5.31.3. Examples
13.5.31.4. Usage
13.5.31.5. See Also
13.5.32. ends-with
13.5.32.1. Signature
13.5.32.2. Effect
13.5.32.3. Examples
13.5.32.4. Usage
13.5.32.5. See Also
13.5.33. error
13.5.33.1. Signature
13.5.33.2. Effect
13.5.33.3. Examples
13.5.33.4. Usage
13.5.33.5. See Also
13.5.34. escape-html-uri
13.5.34.1. Signature
13.5.34.2. Effect
13.5.34.3. Examples
13.5.34.4. Usage
13.5.34.5. See Also
13.5.35. exactly-one
13.5.35.1. Signature
13.5.35.2. Effect
13.5.35.3. Examples
13.5.35.4. Usage
13.5.35.5. See Also
13.5.36. exists
13.5.36.1. Signature
13.5.36.2. Effect
13.5.36.3. Examples
13.5.36.4. Usage
13.5.36.5. See Also
13.5.37. false
13.5.37.1. Changes in 2.0
13.5.37.2. Signature
13.5.37.3. Usage
13.5.37.4. XSLT Example
13.5.37.5. See Also
13.5.38. floor
13.5.38.1. Changes in 2.0
13.5.38.2. Signature
13.5.38.3. Effect
13.5.38.4. Examples
13.5.38.5. Usage
13.5.38.6. See Also
13.5.39. format-date, format-dateTime, format-time
13.5.39.1. Signature
13.5.39.2. Effect
13.5.39.2.1. The Picture Argument
13.5.39.2.2. The Language Argument
13.5.39.2.3. The Calendar Argument
13.5.39.2.4. The Country Argument
13.5.39.3. Usage and Examples
13.5.39.4. See Also
13.5.40. format-number
13.5.40.1. Changes in 2.0
13.5.40.2. Signature
13.5.40.3. Effect
13.5.40.3.1. The decimal-format Name
13.5.40.3.2. The Picture String
13.5.40.4. Usage
13.5.40.5. Examples
13.5.40.6. See Also
13.5.41. format-time
13.5.42. function-available
13.5.42.1. Changes in 2.0
13.5.42.2. Signature
13.5.42.3. Effect
13.5.42.4. Usage
13.5.42.4.1. Testing for the Existence of System-Defined Functions
13.5.42.4.2. Testing for Vendor or Third-Party Extensions
13.5.42.5. See Also
13.5.43. generate-id
13.5.43.1. Changes in 2.0
13.5.43.2. Signature
13.5.43.3. Effect
13.5.43.4. Usage and Examples
13.5.43.5. See Also
13.5.44. hours-from-dateTime, hours-from-time
13.5.44.1. Signature
13.5.44.2. Effect
13.5.44.3. Examples
13.5.44.4. See Also
13.5.45. hours-from-duration
13.5.45.1. Signature
13.5.45.2. Effect
13.5.45.3. Examples
13.5.45.4. See Also
13.5.46. id
13.5.46.1. Changes in 2.0
13.5.46.2. Signature
13.5.46.3. Effect
13.5.46.4. IDs and Validation
13.5.46.5. Usage and Examples
13.5.46.6. See Also
13.5.47. idref
13.5.47.1. Signature
13.5.47.2. Effect
13.5.47.3. IDs and Validation
13.5.47.4. Example
13.5.47.5. See Also
13.5.48. implicit-timezone
13.5.48.1. Signature
13.5.48.2. Effect
13.5.48.3. Example
13.5.48.4. See Also
13.5.49. index-of
13.5.49.1. Signature
13.5.49.2. Effect
13.5.49.3. Examples
13.5.50. in-scope-prefixes
13.5.50.1. Changes in 2.0
13.5.50.2. Signature
13.5.50.3. Effect
13.5.50.4. Examples
13.5.50.5. Usage
13.5.50.6. See Also
13.5.51. insert-before
13.5.51.1. Signature
13.5.51.2. Effect
13.5.51.3. Examples
13.5.51.4. Usage
13.5.51.5. See Also
13.5.52. iri-to-uri
13.5.52.1. Signature
13.5.52.2. Effect
13.5.52.3. Examples
13.5.52.4. Usage
13.5.52.5. See Also
13.5.53. key
13.5.53.1. Changes in 2.0
13.5.53.2. Signature
13.5.53.3. Effect
13.5.53.4. Usage and Examples
13.5.53.4.1. Using Keys to Find Nodes by Value
13.5.53.5. Using Keys for Grouping
13.5.53.6. See Also
13.5.54. lang
13.5.54.1. Changes in 2.0
13.5.54.2. Signature
13.5.54.3. Effect
13.5.54.4. Examples
13.5.54.5. Usage
13.5.55. last
13.5.55.1. Changes in 2.0
13.5.55.2. Signature
13.5.55.3. Effect
13.5.55.4. Usage
13.5.55.5. Usage in XSLT
13.5.55.6. See Also
13.5.56. local-name
13.5.56.1. Changes in 2.0
13.5.56.2. Signature
13.5.56.3. Effect
13.5.56.4. Examples
13.5.56.5. Usage
13.5.56.6. XSLT Example
13.5.56.7. See Also
13.5.57. local-name-from-QName
13.5.57.1. Signature
13.5.57.2. Effect
13.5.57.3. Examples
13.5.57.4. See Also
13.5.58. lower-case
13.5.58.1. Signature
13.5.58.2. Effect
13.5.58.3. Examples
13.5.58.4. Usage
13.5.58.5. See Also
13.5.59. matches
13.5.59.1. Signature
13.5.59.2. Effect
13.5.59.3. Examples
13.5.59.4. Usage
13.5.59.5. See Also
13.5.60. max, min
13.5.60.1. Signature
13.5.60.2. Effect
13.5.60.3. Examples
13.5.60.4. Usage
13.5.61. min
13.5.62. minutes-from-dateTime, minutes-from-time
13.5.62.1. Signature
13.5.62.2. Effect
13.5.62.3. Examples
13.5.62.4. See Also
13.5.63. minutes-from-duration
13.5.63.1. Signature
13.5.63.2. Effect
13.5.63.3. Examples
13.5.63.4. See Also
13.5.64. minutes-from-time
13.5.65. month-from-date, month-from-dateTime
13.5.65.1. Signature
13.5.65.2. Effect
13.5.65.3. Examples
13.5.65.4. See Also
13.5.66. months-from-duration
13.5.66.1. Signature
13.5.66.2. Effect
13.5.66.3. Examples
13.5.66.4. See Also
13.5.67. name
13.5.67.1. Changes in 2.0
13.5.67.2. Signature
13.5.67.3. Effect
13.5.67.4. Usage
13.5.67.5. Examples
13.5.67.6. See Also
13.5.68. namespace-uri
13.5.68.1. Changes in 2.0
13.5.68.2. Signature
13.5.68.3. Effect
13.5.68.4. Examples
13.5.68.5. Usage
13.5.68.6. See Also
13.5.69. namespace-uri-for-prefix
13.5.69.1. Changes in 2.0
13.5.69.2. Signature
13.5.69.3. Effect
13.5.69.4. Example
13.5.69.5. Usage
13.5.69.6. See Also
13.5.70. namespace-uri-from-QName
13.5.70.1. Signature
13.5.70.2. Effect
13.5.70.3. Examples
13.5.70.4. See Also
13.5.71. nilled
13.5.71.1. Signature
13.5.71.2. Effect
13.5.71.3. Examples
13.5.71.4. Usage
13.5.72. node-name
13.5.72.1. Signature
13.5.72.2. Effect
13.5.72.3. Examples
13.5.72.4. Usage
13.5.72.5. See Also
13.5.73. normalize-space
13.5.73.1. Changes in 2.0
13.5.73.2. Signature
13.5.73.3. Effect
13.5.73.4. Examples
13.5.73.5. Usage
13.5.73.6. XSLT Example
13.5.73.7. See Also
13.5.74. normalize-unicode
13.5.74.1. Signature
13.5.74.2. Effect
13.5.74.3. Usage
13.5.74.4. See Also
13.5.75. not
13.5.75.1. Changes in 2.0
13.5.75.2. Signature
13.5.75.3. Effect
13.5.75.4. Examples
13.5.75.5. Usage
13.5.75.6. XSLT Examples
13.5.75.7. See Also
13.5.76. number
13.5.76.1. Changes in 2.0
13.5.76.2. Signature
13.5.76.3. Effect
13.5.76.4. Examples
13.5.76.5. Usage
13.5.76.6. See Also
13.5.77. one-or-more
13.5.77.1. Signature
13.5.77.2. Effect
13.5.77.3. Examples
13.5.77.4. Usage
13.5.77.5. See Also
13.5.78. position
13.5.78.1. Changes in 2.0
13.5.78.2. Signature
13.5.78.3. Effect
13.5.78.4. Usage in XSLT
13.5.78.4.1. Displaying the Current Position
13.5.78.4.2. Testing the Current Position
13.5.78.5. See Also
13.5.79. prefix-from-QName
13.5.79.1. Signature
13.5.79.2. Effect
13.5.79.3. Usage
13.5.79.4. Examples
13.5.79.5. See Also
13.5.80. QName
13.5.80.1. Signature
13.5.80.2. Effect
13.5.80.3. Examples
13.5.80.4. Usage
13.5.80.5. See Also
13.5.81. regex-group
13.5.81.1. Signature
13.5.81.2. Effect
13.5.81.3. Usage and Examples
13.5.81.4. See Also
13.5.82. remove
13.5.82.1. Signature
13.5.82.2. Effect
13.5.82.3. Examples
13.5.82.4. Usage
13.5.82.5. See Also
13.5.83. replace
13.5.83.1. Signature
13.5.83.2. Effect
13.5.83.3. Examples
13.5.83.4. Usage
13.5.83.5. See Also
13.5.84. resolve-QName
13.5.84.1. Signature
13.5.84.2. Effect
13.5.84.3. Examples
13.5.84.4. Usage
13.5.84.5. See Also
13.5.85. resolve-uri
13.5.85.1. Signature
13.5.85.2. Effect
13.5.85.3. Examples
13.5.85.4. Usage
13.5.85.5. See Also
13.5.86. reverse
13.5.86.1. Signature
13.5.86.2. Effect
13.5.86.3. Examples
13.5.86.4. See Also
13.5.87. root
13.5.87.1. Signature
13.5.87.2. Effect
13.5.87.3. Examples
13.5.87.4. Usage
13.5.87.5. See Also
13.5.88. round
13.5.88.1. Changes in 2.0
13.5.88.2. Signature
13.5.88.3. Effect
13.5.88.4. Examples
13.5.88.5. Usage
13.5.88.6. See Also
13.5.89. round-half-to-even
13.5.89.1. Signature
13.5.89.2. Effect
13.5.89.3. Examples
13.5.89.4. Usage
13.5.89.5. See Also
13.5.90. seconds-from-dateTime, seconds-from-time
13.5.90.1. Signature
13.5.90.2. Effect
13.5.90.3. Examples
13.5.90.4. See Also
13.5.91. seconds-from-duration
13.5.91.1. Signature
13.5.91.2. Effect
13.5.91.3. Examples
13.5.91.4. See Also
13.5.92. seconds-from-time
13.5.93. starts-with
13.5.93.1. Changes in 2.0
13.5.93.2. Signature
13.5.93.3. Effect
13.5.93.4. Examples
13.5.93.5. Usage
13.5.93.6. See Also
13.5.94. static-base-uri
13.5.94.1. Signature
13.5.94.2. Effect
13.5.94.3. Usage
13.5.94.4. See Also
13.5.95. string
13.5.95.1. Changes in 2.0
13.5.95.2. Signature
13.5.95.3. Effect
13.5.95.4. Examples
13.5.95.5. Usage
13.5.95.6. See Also
13.5.96. string-join
13.5.96.1. Signature
13.5.96.2. Effect
13.5.96.3. Examples
13.5.96.4. Usage
13.5.96.5. See Also
13.5.97. string-length
13.5.97.1. Changes in 2.0
13.5.97.2. Signature
13.5.97.3. Effect
13.5.97.4. Examples
13.5.97.5. Usage
13.5.97.6. See Also
13.5.98. string-to-codepoints
13.5.98.1. Signature
13.5.98.2. Effect
13.5.98.3. Examples
13.5.98.4. See Also
13.5.99. subsequence
13.5.99.1. Signature
13.5.99.2. Effect
13.5.99.3. Examples
13.5.99.4. See Also
13.5.100. substring
13.5.100.1. Changes in 2.0
13.5.100.2. Signature
13.5.100.3. Effect
13.5.100.4. Examples
13.5.100.5. Usage
13.5.100.5.1. Using substring() as a Conditional Expression
13.5.100.6. See Also
13.5.101. substring-after
13.5.101.1. Changes in 2.0
13.5.101.2. Signature
13.5.101.3. Effect
13.5.101.4. Examples
13.5.101.5. Usage
13.5.101.6. XSLT Example
13.5.101.7. See Also
13.5.102. substring-before
13.5.102.1. Changes in 2.0
13.5.102.2. Signature
13.5.102.3. Effect
13.5.102.4. Examples
13.5.102.5. Usage and Examples
13.5.102.6. See Also
13.5.103. sum
13.5.103.1. Changes in 2.0
13.5.103.2. Signature
13.5.103.3. Effect
13.5.103.4. Examples
13.5.103.5. Usage
13.5.103.6. See Also
13.5.104. system-property
13.5.104.1. Changes in 2.0
13.5.104.2. Signature
13.5.104.3. Effect
13.5.104.4. Usage
13.5.104.5. Examples
13.5.104.6. See Also
13.5.105. timezone-from-date, timezone-from-dateTime, timezone-from-time
13.5.105.1. Signature
13.5.105.2. Effect
13.5.105.3. Examples
13.5.105.4. See Also
13.5.106. tokenize
13.5.106.1. Signature
13.5.106.2. Effect
13.5.106.3. Examples
13.5.106.4. Usage
13.5.106.5. See Also
13.5.107. trace
13.5.107.1. Signature
13.5.107.2. Effect
13.5.107.3. Usage and Examples
13.5.107.4. See Also
13.5.108. translate
13.5.108.1. Changes in 2.0
13.5.108.2. Signature
13.5.108.3. Effect
13.5.108.4. Examples
13.5.108.5. Usage and Examples
13.5.108.6. See Also
13.5.109. true
13.5.109.1. Changes in 2.0
13.5.109.2. Signature
13.5.109.3. Effect
13.5.109.4. Usage
13.5.109.5. XSLT Example
13.5.109.6. See Also
13.5.110. type-available
13.5.110.1. Signature
13.5.110.2. Effect
13.5.110.3. Usage
13.5.110.4. See Also
13.5.111. unordered
13.5.111.1. Signature
13.5.111.2. Effect
13.5.111.3. Usage and Examples
13.5.112. unparsed-entity-public-id, unparsed-entity-uri
13.5.112.1. Changes in 2.0
13.5.112.2. Signatures
13.5.112.2.1. The unparsed-entity-public-id() function
13.5.112.2.2. The unparsed-entity-uri() function
13.5.112.3. Effect
13.5.112.4. Usage
13.5.112.5. Examples
13.5.112.6. See Also
13.5.113. unparsed-text, unparsed-text-available
13.5.113.1. Signatures
13.5.113.1.1. The unparsed-text() function
13.5.113.1.2. The unparsed-text-available() function
13.5.113.2. Effect
13.5.113.3. Usage and Examples
13.5.113.3.1. Up-Conversion
13.5.113.4. XML Envelope/Payload Applications
13.5.113.5. HTML Boilerplate Generation
13.5.114. See Also
13.5.115. upper-case
13.5.115.1. Signature
13.5.115.2. Effect
13.5.115.3. Examples
13.5.115.4. Usage
13.5.115.5. See Also
13.5.116. year-from-date, year-from-dateTime
13.5.116.1. Signature
13.5.116.2. Effect
13.5.116.3. Examples
13.5.116.4. See Also
13.5.117. years-from-duration
13.5.117.1. Signature
13.5.117.2. Effect
13.5.117.3. Examples
13.5.117.4. See Also
13.5.118. zero-or-one
13.5.118.1. Signature
13.5.118.2. Effect
13.5.118.3. Examples
13.5.118.4. Usage
13.5.118.5. See Also
13.6. Summary

### 14. Regular Expressions
14.1. Branches and Pieces
14.2. Quantifiers
14.3. Atoms
14.4. Subexpressions
14.5. Back-References
14.6. Character Groups
14.7. Character Ranges
14.8. Character Class Escapes
14.9. Character Blocks
14.10. Character Categories
14.11. Flags
14.11.1. The «i» flag
14.11.2. The «m» flag
14.11.3. The «s» flag
14.11.4. The «x» flag
14.12. Disallowed Constructs
14.13. Summary

### 15. Serialization
15.1. The XML Output Method
15.2. The HTML Output Method
15.3. The XHTML Output Method
15.4. The Text Output Method
15.5. Using the <xsl:output> declaration
15.6. Character Maps
15.6.1. Usage
15.6.2. Choosing Characters to Map
15.6.3. Limitations of Character Maps
15.7. Disable Output Escaping
15.7.1. Reasons to Disable Output Escaping
15.7.2. Why disable-output-escaping Is Deprecated
15.7.3. Using disable-output-escaping to Wrap HTML in CDATA
15.7.4. Character Maps as a Substitute for disable-output-escaping
15.8. Summary

## III. Exploitation

### 16. Extensibility
16.1. What Vendor Extensions Are Allowed?
16.2. Extension Functions
16.2.1. When Are Extension Functions Needed?
16.2.2. When Are Extension Functions Not Needed?
16.2.3. Calling Extension Functions
16.2.4. What Language Is Best?
16.2.5. Client-Side Script
16.2.6. Binding Extension Functions
16.2.6.1. Binding in MSXML
16.2.6.2. Binding by Namespace in Java Processors
16.2.6.3. Binding Using External Objects in the Microsoft .NET Processor
16.2.6.4. Binding to Assemblies in Saxon on .NET
16.2.6.5. Binding to Extension Functions in Gestalt
16.2.7. XPath Trees and the DOM
16.2.8. Calling External Functions within a Loop
16.2.9. Functions with Uncontrolled Side Effects
16.3. Keeping Extensions Portable
16.4. Summary

### 17. Stylesheet Design Patterns
17.1. Fill-in-the-Blanks Stylesheets
17.2. Navigational Stylesheets
17.3. Rule-Based Stylesheets
17.4. Computational Stylesheets
17.4.1. Programming without Assignment Statements
17.4.2. So Why Are They Called Variables?
17.4.3. Avoiding Assignment Statements
17.4.3.1. Conditional Initialization
17.4.3.2. Avoid Doing Two Things at Once
17.4.3.3. Don't Iterate, Recurse
17.4.3.4. Recursion: Summary
17.5. Summary

### 18. Case Study: XMLSpec
18.1. Formatting the XML Specification
18.2. Preface
18.3. Creating the HTML Outline
18.4. Formatting the Document Header
18.5. Creating the Table of Contents
18.6. Creating Section Headers
18.7. Formatting the Text
18.8. Producing Lists
18.9. Making Cross-References
18.10. Setting Out the Production Rules
18.11. Overlay Stylesheets
18.11.1. diffspec.xsl
18.11.2. REC-xml.xsl
18.12. Stylesheets for Other Specifications
18.12.1. xslt.xsl
18.12.2. xsltdiff.xsl
18.12.3. funcproto.xsl
18.12.4. xsl-query.xsl
18.12.5. xmlspec.xsl
18.13. Summary

### 19. Case Study: A Family Tree
19.1. Modeling a Family Tree
19.1.1. The GEDCOM Data Model
19.1.2. Creating a Schema for GEDCOM 6.0
19.1.3. The GEDCOM 6.0 Schema
19.1.3.1. Individuals
19.1.3.2. Events
19.1.3.3. Families
19.1.3.4. Dates
19.1.3.5. Places
19.1.3.6. Personal Names
19.2. Creating a Data File
19.2.1. Converting GEDCOM Files to XML
19.2.2. Converting from GEDCOM 5.5 to 6.0
19.2.2.1. Top-Level Processing
19.2.2.2. Creating Family Records
19.2.2.3. Creating Individual Records
19.2.2.4. Creating Event Records
19.2.2.5. Debugging the Stylesheet
19.3. Displaying the Family Tree Data
19.3.1. The Stylesheet
19.3.2. Putting It Together
19.3.2.1. Publishing Static HTML
19.3.2.2. Generating HTML Pages from a Servlet
19.3.2.3. Installing and Configuring the Servlet
19.3.2.4. Generating HTML Using ASP.NET Pages
19.3.2.5. Generating HTML in the Browser
19.4. Summary

### 20. Case Study: Knight's Tour
20.1. The Problem
20.2. The Algorithm
20.2.1.
20.2.1.1. The Initial Template
20.3. Placing the Knight
20.4. Displaying the Final Board
20.5. Finding the Route
20.5.1. Finding the Possible Moves
20.5.2. Trying the Possible Moves
20.5.3. Selecting the Best Move
20.6. Running the Stylesheet
20.7. Observations
20.8. Summary

## IV. Appendices

### A. XPath 2.0 Syntax Summary
A.1. Whitespace and Comments
A.2. Tokens
A.3. Syntax Productions
A.4. Operator Precedence

### B. Error Codes
B.1. Functions and Operators (FO)
B.2. XPath Errors (XP)
B.3. XSLT Errors (XT)

### C. Backward Compatibility
C.1. Stage 1: Backward-Compatibility Mode
C.1.1. Deprecated Facilities
C.1.2. Error Handling
C.1.3. Comparing Strings
C.1.4. Numeric Formats
C.1.5. Other XPath Changes
C.1.6. Serialization Changes
C.2. Stage 2: Setting version="2.0"
C.2.1. The First Node Rule
C.2.2. Type Checking of Function Arguments
C.2.3. Comparison Operators
C.2.4. Arithmetic
C.2.5. The Empty Sequence
C.2.6. Error Semantics for «and» and «or»
C.2.7. Other XSLT Differences
C.3. Stage 3: Adding a Schema
C.4. Summary

### D. Microsoft XSLT Processors
D.1. MSXML
D.1.1. Objects
D.1.2. IXMLDOMDocument and IXMLDOMDocument2
D.1.3. Additional Methods
D.1.4. Additional Properties
D.1.5. IXMLDOMNode
D.1.6. Methods
D.1.7. Properties
D.1.8. IXMLDOMNodeList
D.1.9. Methods
D.1.10. Properties
D.1.11. IXMLDOMParseError
D.1.12. Properties
D.1.13. IXMLDOMSelection
D.1.14. Methods
D.1.15. Properties
D.1.16. IXSLProcessor
D.1.17. Methods
D.1.18. Properties
D.1.19. IXSLTemplate
D.1.20. Methods
D.1.21. Properties
D.1.22. Putting it Together
D.1.23. Restrictions
D.2. System.Xml
D.2.1. XPathDocument
D.2.2. XmlNode
D.2.3. IXPathNavigable
D.2.4. XPathNavigator
D.2.5. XSLTransform
D.3. Summary

### E. JAXP: The Java API for Transformation
E.1. The JAXP Parser API
E.1.1. JAXP Support for SAX
E.1.1.1. javax.xml.parsers.SAXParserFactory
E.1.1.2. javax.xml.parsers.SAXParser
E.1.2. JAXP Support for DOM
E.1.2.1. javax.xml.parsers.DocumentBuilderFactory
E.1.2.2. javax.xml.parsers.DocumentBuilder
E.2. The JAXP Transformation API
E.2.1.
E.2.1.1. javax.xml.transform.dom.DOMLocator
E.2.1.2. javax.xml.transform.dom.DOMResult
E.2.1.3. javax.xml.transform.dom.DOMSource
E.2.1.4. javax.xml.transform.ErrorListener
E.2.1.5. javax.xml.transform.OutputKeys
E.2.1.6. javax.xml.transform.Result
E.2.1.7. javax.xml.transform.sax.SAXResult
E.2.1.8. javax.xml.transform.sax.SAXSource
E.2.1.9. javax.xml.transform.sax.SAXTransformerFactory
E.2.1.10. javax.xml.transform.Source
E.2.1.11. javax.xml.transform.SourceLocator
E.2.1.12. javax.xml.transform.stream.StreamSource
E.2.1.13. javax.xml.transform.Templates
E.2.1.14. javax.xml.transform.sax.TemplatesHandler
E.2.1.15. javax.xml.transform.Transformer
E.2.1.16. javax.xml.transform.TransformerConfigurationException
E.2.1.17. javax.xml.transform.TransformerException
E.2.1.18. javax.xml.transform.TransformerFactory
E.2.1.19. javax.xml.transform.TransformerFactoryConfigurationError
E.2.1.20. javax.xml.transform.sax.TransformerHandler
E.2.1.21. javax.xml.transform.URIResolver
E.3. Examples of JAXP Transformations
E.3.1. Example 1: Transformation Using Files
E.3.2. Example 2: Supplying Parameters and Output Properties
E.3.3. Example 3: Holding Documents in Memory
E.3.4. Example 4: Using the <?xml-stylesheet?> Processing Instruction
E.3.5. Example 5: A SAX Pipeline
E.4. Summary

### F. Saxon
F.1. Using Saxon from the Command Line
F.2. Using Saxon from a Java Application
F.2.1. Using Saxon via JAXP Interfaces
F.2.1.1. Running XSLT Transformations
F.2.1.2. The Schema Validation API
F.2.1.3. Using XPath Expressions in Saxon
F.2.2. The s9api Interface
F.3. Using Saxon from a .NET Application
F.4. Saxon Tree Models
F.5. Extensibility
F.5.1. Writing Extension Functions in Java
F.5.2. Writing Extension Functions under .NET
F.5.3. Collations
F.6. Extensions
F.6.1. Serialization Extensions
F.6.2. Extension Attributes
F.6.3. Extension Instructions
F.6.4. Extension Functions
F.7. The evaluate() Extension
F.8. Summary

### G. Altova
G.1. Running from within XMLSpy
G.2. Conformance
G.3. Extensions and Extensibility
G.4. The Command Line Interface
G.5. Using the API
G.5.1. The COM API
G.5.1.1. XMLValidator
G.5.1.2. XSLT2
G.5.2. The Java API
G.5.3. The .NET API
G.6. Summary

### H. Glossary
