# [Xeditor](https://documentation.xeditor.com/)

**Xeditor** es una herramienta de creación de XML basada en web, intuitiva y ligera. También es un potente framework para desarrolladores que puede personalizar e integrar en cualquier otro sistema (CMS, Google Drive, etc.).

## Tecnología

**Xeditor** está construido con ***JavaScript (con ExtJS 6), HTML y CSS***. Actualmente se lanza con ***Node.js*** para servir los archivos, aunque puede usar el lenguaje del lado del servidor que elija.

### Esquemas

Hemos creado paquetes prediseñados para ***DITA 1.2 y DITA 1.3***. **Xeditor** también se puede configurar para cualquier ***esquema o DTD***.

## Empezando

Le recomendamos que comience por instalar el paquete de demostración de **Xeditor**. Este paquete viene con un schema simple preinstalado para que pueda familiarizarse con la arquitectura y jugar en un entorno de prueba.

## Requerimientos Xeditor

1. Instale [Node.js](https://nodejs.org/en/) (versión 10.17.0 o versión secundaria superior). Esto instalará todo lo que necesita para usar los comandos `node` y `npm`.
2. Pruebe la instalación y la versión utilizando `node -v` y `npm -v`

## Instalar y Ejecutar la Demostración

1. Necesitará credenciales de usuario para descargar nuestros paquetes. Puede ver nuestra demostración en línea, que no requiere credenciales.
   Inicie sesión en nuestro repositorio npm.
   ```sh
   npm login --registry https://npm.xeditor.com:4873
   ```

2. Cambie al directorio donde desea instalar Xeditor:
   ```sh
   cd myNewXeditor
   ```

3. Obtenga el paquete Xeditor.
   ```sh
   npm pack @xeditor/xeditor-demo --registry https://npm.xeditor.com:4873
   ```
   
4. Descomprime la carpeta descargada.

5. Cambie a la nueva carpeta del paquete.
   ```sh
   cd package
   ```
   
6. Instale las dependencias de los paquetes usando npm.
   ```sh
   npm install --registry https://npm.xeditor.com:4873
   ```
   
7. Inicie la aplicación de demostración.
   ```sh
   npm run start:develop
   ```
   
El paquete de demostración ya está en funcionamiento. ¡Disfrutar!

![1-1](https://github.com/adolfodelarosades/XML/blob/main/temarios/100_Xeditor/images/1-1.PNG)


## Personaliza y Construye

Ahora que estamos en funcionamiento, hagamos algunos cambios. En este ejemplo, cambiaremos el modo de Xeditor para que sea "annotate", lo que significa que el usuario solo podrá hacer comentarios. Esto es útil si tiene un equipo de revisión y no desea que editen el contenido directamente. Codificaremos esto directamente en el archivo, pero también podría enviarse como un parámetro desde su CMS. De esta manera, cada rol de usuario en el CMS podría activar un modo diferente de Xeditor.

> **NOTA**: ***Nunca debe editar la carpeta*** **dist**, que es la carpeta que se envía al navegador. Los archivos de esta carpeta se compilan automáticamente con [Xepack](https://documentation.xeditor.com/topics/tools/xepack/xepack/) cuando ejecuta `start:development` Los fuentes de esta carpeta provienen de las carpetas *static*, *src* y *node_modules*. Para obtener más información sobre la construcción, consulte [Xepack](https://documentation.xeditor.com/topics/tools/xepack/xepack/).

1. Abra el archivo `src/js/config/attributes.js`
2. En la línea: `schema: 'demo'` agregue una coma.
   ```sh
   schema: 'demo',
   ```

3. Inmediatamente después de la coma, inserte una nueva línea y agregue el siguiente código:
   ```sh
   editorMode: 'annotate'
   ```

4. Inicie la aplicación.
   ```sh
   npm run start:develop
   ```

Ahora debería ver Xeditor con la barra de herramientas desactivada y solo la capacidad de agregar comentarios.

![1-2](https://github.com/adolfodelarosades/XML/blob/main/temarios/100_Xeditor/images/1-2.PNG)

## Integración

Xeditor simplifica la integración al proporcionar API que conectan el backend con el frontent. Por ejemplo, en nuestro paquete demo encontrará la siguiente línea de código en `src/js/config/urls.js`

```sh
documentURL: '//127.0.0.1:3000/editor/load',
```

Para cargar su propio documento, simplemente escriba su propio servicio (en cualquier lenguaje de programación que necesite) y devuélvalo a `documentURL`. Nuestros paquetes de demostración utilizan node.js para administrar el servicio de carga, que puede encontrar en `node_modules/@xeditor/server-js`. Puede usar este paquete como punto de partida (se puede descargar por separado en `npm pack @xeditor/server-js`) o escribir el suyo propio. Si usa nuestros archivos `server-js`, debe copiarlos en una nueva ubicación antes de editar las siguientes líneas para incorporar sus propios servicios:

```js
// add load url
app.post('/editor/load', function (req, res) {
   // get parameters
   const schema = req.body.schema || 'demo@0.0';
   const file = req.body.file || 'default';

   console.log(`LOAD '${schema}/${file}'`);

   // write header
   res.setHeader('Content-Type', 'text/xml');

   getXml(schema, file, (err, data) => {
      if (err) {
         // invalid string
         res.status(500).end('No file found. Invalid schema or file');
         return;
      }
      res.end(data);
   });
}); 
```

Para obtener más información, consulte [Configuración del Servidor](https://documentation.xeditor.com/topics/core/server_setup/) y [Blackbox](https://documentation.xeditor.com/topics/core/blackbox_description/).

## Próximos pasos

Ahora que tiene la aplicación Xeditor en funcionamiento, tiene algunas opciones.

**Aprenda Xeditor con el paquete de demostración**. Puede continuar modificando archivos en el paquete para personalizar Xeditor.

**Descarga el paquete prediseñado**. Puede descargar uno de nuestros otros paquetes, como [DITA](https://documentation.xeditor.com/dita/).

**Descargue** [el paquete limpio de Xeditor](https://documentation.xeditor.com/topics/core/configuration/). Puede descargar nuestra versión limpia y ver nuestra [Guía de Configuración](https://documentation.xeditor.com/topics/core/configuration/) para que pueda comenzar a construir su propia versión de Xeditor desde cero.
