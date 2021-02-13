# 01 Introducción a XML • 14 clases • 1h 11m

* 1.- Bienvenida al curso Aprende XML sin dolor 07:39
* 2.- Qué es y qué no es XML 07:31
* 3.- ¿Qué necesitamos para crear un archivo XML? 03:43
* 4.- Las etiquetas de XML 07:06
* 5.- Reglas para un documento XML bien formado 06:55
* 6.- Elementos de un archivo XML 03:20
* 7.- La declaración XML 05:24
* 8.- Los nodos o elementos de XML 04:30
* 9.- Los atributos en un documento XML 03:38
* 10.- Los comentarios en un documento XML 05:25
* 11.- Character Data Section 05:11
* 12.- Instrucciones de proceso o processing instruction 04:11
* 13.- Los caracteres especiales o Entities 04:03
* 14.- Los espacios en blanco en un archivo XML 02:24

## 1.- Bienvenida al curso Aprende XML sin dolor 07:39

### Introducción a XML

* Qué es y qué no es XML
* ¿Qué necesitamos para crear un archivo XML?
* Las etiquetas XML
* Reglas para un documento bien formado
* La declaración XML

Todo lo necesario para crear un archivo XML.

### Los estilos en cascada para XML

Alrededor de XML hay muchas herramientas, una de ellas son los estilos en cascada para darle estilos a un XML

* Ligar un archivo en cascada con un documento XML
* Crear el archivo en cascada con las etiquetas generales
* Crear los estilos en cascada para los subnodos de XML
* Manejar los atributos y colocar cadenas antes y después de los nodos

### El Modelo DOM para XML

El DOM nos permite manejar el HTML y el XML, lo haremos a través de JS.

* Introducción al modelo DOM en XML
* Padres, hijos y hermanos en XML
* Cargar un archivo XML por medio de XMLHttpRequest
* Propiedades y métadatos para analízar un archivo XML
* Recorrer un documento XML con las intrucciones DOM

### La herramienta XPath

Otra herramienta importante es el XPath.

* Introducción a XPath
* Elementos de una cadena XPath
* Cargar un archivo externo con `XMLHttpRequest`
* Utilizar las instrucciones `xml.evaluate()` y `xml.iterateNext()`
* Evaluar una expresión XPath en Internet

### XSLT: eXtensible Stylesheet Language Transformation

XSLT nos permite transformar un XML en una página, añade cosas que no se pueden hacer con CSS.

* Introducción a XSLT
* Crear un template con XSL
* Extraer los datos de un documento XML con `value-of`
* Hacer un ciclo en XSL con la etiqueta `<xsl:for-each>`
* Realizar un filtro por medio de la etiqueta `<xsl:for-each>`

### DTD: Definición de Tipo de Documento

Un DTD nos permite saber si un documento XML esta ***bien formado*** y además si es ***valido***, podemos tener ciertas reglas para definir un lenguaje. Esta es una tecnología más vieja que los Schemas.  

* Introducción a la Definición de Tipo de Documento (DTD)
* La Definición de Tipo de Documento interna y externa
* Conceptos generales de modelado de datos
* Definir los elementos de un documento DTD
* Crear un DTD interno y validarlo
* Crear y validar un documento XML con un DTD externo

### Introducción al XML Schema

Con XML Schema, es otra forma de hacer validaciones o archivos de validaciones, es más poderoso que DTD, se apega más a a las reglas del XML, es más complejo que DTD pero nos permite hacer muchas más cosas que DTD. 

* Crear un archivo XSD y llamarlo desde un documento XML
* Definición de los elementos simples, definición de los elementos complejos.
* Los indicadores de orden, número y grupo en XSD
* Definir los atributos en los archivos XSD
* Las restricciones o facets en los archivos XSD
* Definir el archivo XSD y su enlace con XML
* Definir los elementos principales del XSD

En resumen vamos a ver como armamos un documento XML, como lo hacemos bien formado, como hacemos que sea valido, como darle estilo. 

## 2.- Qué es y qué no es XML 07:31

### Introdución a XML

* En 1991 Tim Barnes Lee crea las reglas de la primera versión de HTML. Invento 18 etiquetas para desarrollar el HTML.

* En 1993 Marc Andressen y colaboradores crean Mosaic y Nescape el primer navegador.

* En 1995 Bill Clinton permite el acceso libre a Internet... y lo demás es historia.

* En 1998, ante la enorme explosión de páginas de internet y su necesario intercarcambio de información, la W3C genera la especificación del XML. Ya que HTML nunca fue pensado para manejar datos, se tenian más etiquetas que información.

**XML** significa **eXtensible Markup Lenguage** es decir, nace como una ***extensión*** de HTML, pero sirve para el manejo de los datos.

XML no sustituye a HTML, sino que lo complementa.

* XML se caracteríza por ser sencillo, pero poderoso.
* Tecnologías al rededor de él lo hacen fundamental en el desarrollo Web, como son:
   * AJAX
   * RSS
   * WebService
   * y un largo etcétera

XML se caracteríza por ser muy sencillo, cualquier dispositivo puede tener un XML, teléfonos, TV, moviles, etc.

* XML no es un sustituto de HTML, aunque el estándar XHTML trata de reunir a ambos.
* Al rededor de este lenguaje XML, tendremos otras especificaciones como DTD, XSLT o XPath.
* Incluso se puede utilizar estilos en cascada (CSS) en documentos XML.

XHTML domina las páginas Web hasta antes de aparecer HTML5.

* Todas las especificaciones del lenguaje se encuentran en la página de W3C.
http://www.w3.org/XML/

## 3.- ¿Qué necesitamos para crear un archivo XML? 03:43

* Un Editor
* Un Navegador

## 4.- Las Etiquetas de XML 07:06

Vamos a crear nuestro primer archivo XML donde vamos a guardar información sobre Libros en nuestras etiquetas XML.

XML cuenta con una etiqueta inicial que es opcional.
Tenemos una etiqueta inicial llamada etiqueta raíz que generalmente se nombra en plural, en este caso es `<libros></libros>` todas las demas etiquetas estaran contenido dentro de esta etiqueta raíz.

`libros.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<libros>
<libro pagina="600">
    <nombre>El Quijote de la Mancha</nombre>
    <autor>Miguel de Cervantes Savedra</autor>
    <editorial>Una muy vieja</editorial>
</libro>
<libro pagina="500">
    <nombre>Cien años de soledad</nombre>
    <autor>Gabriel García Márquez</autor>
    <editorial>Obeja Negra</editorial>
</libro>
</libros>
```

Las etiquetas que usamos no estan definidas en ningún sitio nosotros les damos los nombres que consideremos pertinentes.

Dentro de una etiqueta podemos colocar atributos cuyos valores deben estar entre comillas, en este ejemplo tenemos el atributo `pagina` con su respectivo valor para cada libro.

Si abrimos este documento XML en el navegador tenemos:

![4-1](images/4-1.PNG)
![4-2](images/4-2.PNG)
![4-3](images/4-3.PNG)

En el mismo navegador me va informar si el documento esta o no bien formado.

Como podemos ver tenemos etiquetas de apertura y de cierre, valores entre estas dos etiquetas, tenemos atributos dentro de las etiquetas de apertura y tenemos los valores de los atributos. Son los elementos principales de un documento XML.

## 5.- Reglas para un Documento XML Bien Formado 06:55

* Documentos bien formados
* Contenidos de un archivo XML, un documento XML contiene los datos.
* Validación de un archivo XML, todos los navegadores validan los archivos XML.
* XML Namespaces

### Documentos Bien Formados

* La declaración de XML es opcional.

   ![05-15](images/05-15.png)
   ![05-16](images/05-16.png)
   ![05-17](images/05-17.png)
   
* Todos los archivos XML tienen sólo un nodo raíz.
   Si se mete más de un nodo raíz nos mostrara el siguiente error:
   
   ![05-00](images/05-00.png)
   ![05-01](images/05-01.png)

* El anidamiento de las etiquetas debe de ser siempre el correcto.

   ![05-13](images/05-13.png)
   ![05-14](images/05-14.png)
   
* Los valores de los atributos siempre deben ir entre comillas.

   ![05-11](images/05-11.png)
   ![05-12](images/05-12.png)
   
* No puede haber atributos sin valor.
  
   ![05-07](images/05-07.png)
   ![05-08](images/05-08.png)
   
   Pero si pongo el '=""' si lo acepta.
   
   ![05-09](images/05-09.png)
   ![05-10](images/05-10.png)

* Las etiquetas sin contenido, deben ser cerradas con una diagonal.

   ![05-02](images/05-02.png)
   ![05-03](images/05-03.png)
   
   ![05-04](images/05-04.png)
   ![05-05](images/05-05.png)
   ![05-06](images/05-06.png)
   
**A un documento XML que sigue todas las reglas se le conoce como "Bien Formado" (Well-Formed)**.


## 6.- Elementos de un archivo XML 03:20
## 7.- La declaración XML 05:24
## 8.- Los nodos o elementos de XML 04:30
## 9.- Los atributos en un documento XML 03:38
## 10.- Los comentarios en un documento XML 05:25
## 11.- Character Data Section 05:11
## 12.- Instrucciones de proceso o processing instruction 04:11
## 13.- Los caracteres especiales o Entities 04:03
## 14.- Los espacios en blanco en un archivo XML 02:24

