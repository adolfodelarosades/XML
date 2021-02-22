# Configuración

Modifique, personalice y amplíe Xeditor.

## Comience con un paquete limpio

Puede construir Xeditor desde cero descargando el paquete limpio usando. Siga las instrucciones para [instalar Xeditor](https://github.com/adolfodelarosades/XML/blob/main/temarios/100_Xeditor.md) pero obtenga `@xeditor/xeditor` en lugar de `@xeditor/xeditor-demo`. Esta versión no contendrá ningún complemento.

## Estructura de Carpetas y Archivos

Los únicos archivos que se actualizarán con `npm update` se encuentran en `/node_modules`.

Carpeta/Archivo | Personalizable(s/n) | Descripción
----------------|---------------------|------------
`/dist`         | n | Contiene el paquete Xeditor integrado para su implementación. Generado con xepack.
`/node_modules` | n | Paquetes distribuidos de Xeditor, herramientas, dependencias y esquemas preconfigurados.
`package-lock.json` | n | Dependencias de Npm. Generado con `npm install`.
`package.json` | y | 	Archivo de información Npm (contiene información como dependencias, versiones usadas, nombre del proyecto).
`/src` | y | Contiene la subcarpeta `/js/config`. Esto incluye todos los archivos JavaScript necesarios para construir Xeditor (por ejemplo, dialogs, plugins, roles, toolbars, schema config, etc.).
`/WEB-INF` | y | Contiene archivos de entrada `/xsl`, `/xsd,` y `/xml`.
`/static` | y | Contiene archivos estáticos para CSS, frases y HTML.
`xeblackbox.config.js` | y | Configuración para blackbox.
`xepack.config.js` | y | Configuración de la herramienta de compilación xepack para generar `/dist`. Opcional y descargado por separado del paquete principal de Xeditor. Incluido automáticamente en paquetes preconfigurados (demo, DITA, etc.).

## Configuración del Schema

Este capítulo describe cómo transferir su propio esquema a Xeditor y configurar Xeditor en consecuencia.

### Conversión de DTD en XSDs

Las herramientas de configuración de Xeditor solo leen desde XSDs. Los DTDs se deben convertir a XSDs para configurar correctamente Xeditor.

1. Descargue el paquete trang-20081028.zip. Se puede descargar aquí: http://www.thaiopensource.com/relaxng/trang.html.
2. Use la línea de comando para navegar hasta el unzipped Trang package: `cd *folder*`

3. **Nota**: Antes de ejecutar el código de la línea de comandos, deberá ajustar la ruta de su archivo dependiendo de dónde descomprimió Trang y dónde se encuentran sus DTDs.

Ingrese lo siguiente en la línea de comando:

```sh
java -jar trang.jar C:\Path\to\sourceDirectory\file.dtd C:\Path\to\destinationDirectory\file.xsd
```

### Preconfigurar la Configuración de Xeditor

Para evitar cambios innecesarios en la configuración de Xeditor generada, también puede agregar información adicional a los elementos. Esta información se utilizará en el proceso de generación y se incluirá en el resultado generado.

#### Generar Archivo de Información XML


Este proceso utiliza pregenerate_info.xsl para generar automáticamente el archivo info.xml necesario para asignar roles. Este proceso es opcional, pero se recomienda para evitar crear manualmente cada elemento en info.xml.

Descargue la herramienta de generación de Xeditor xetypesgen:> npm pack @ xeditor / tool-xetypesgen --registry https://npm.xeditor.com:4873.
Descomprima el paquete descargado.
Ejecute el XSL con Saxon.


java -jar SAXONJAR = pathToSaxon \ saxon9he.jar step1_empty.xml help \ pregenerate_info.xsl> salida \ elements.xml

El archivo info.xml se creará en / output /.

Definición de rol
A cada elemento de un esquema se le debe asignar un rol, que define las propiedades y rige el comportamiento de ese elemento en Xeditor. Al generar una nueva configuración de esquema, los roles se definen en el archivo info.xml. Xeditor viene con roles predefinidos, pero los roles del cliente se pueden crear en src / js / config / roles.js. Todas las propiedades disponibles disponibles se enumeran en roles.js.
