---
title: "Generar Favicons y Manifest"
tags: ["Web"]
date: 2022-09-28T05:14:39-03:00
description: "Como generar favicons y manifest para tu web."
draft: false
type: "post"
showTableOfContents: true
---

# Favicons y Manifest
En internet puedes encontrar muchas herramientas para generar estos archivos, aqui te dejo uno que he probado y como usarlo.

## Favicon Web
Esta herramienta online va a generar por ti los iconos (favicons) y manifest, debes tener una imagen ya lista y subirla aquí en el [convertidor de Favicon](https://favicon.io/favicon-converter/) y luego descargarlo.

![Favicon Drag & Drop](/images/ddfavicon.png "Favicon Drag & Drop")

El contenido del archivo descargado debería ser así:

![Contenido zip Favicon](/images/zipfavicon.png "Contenido zip Favicon")

Si seguimos las instrucciones de la web, ahora deberíamos insertar los archivos en nuestro `HTML` en la etiqueta `HEAD`, algo así:
{{< highlight html >}}
<head>
  <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
  <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
  <link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
  <link rel="manifest" href="/site.webmanifest">
</head>
{{< / highlight >}}

Si vienes de instalar HUGO con Gokarna y quieres agregarlo a `customHeadHTML` debes agregarlo de la siguiente manera:
{{< highlight bash >}}
customHeadHTML = '''
<link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
<link rel="manifest" href="/site.webmanifest">
'''
{{< / highlight >}}
Y no olvides dejar las imagenes/iconos en la carpeta `/static`.

### Manifest
En el zip descargado tenemos un archivo llamado `site.webmanifest` el cual entrega información sobre nuestra web, la estructura es algo asi (los datos varian ya que este ejemplo es de Mozilla):
{{< highlight json >}}
{
  "name": "Google I/O 2015",
  "short_name": "I/O 2015",
  "icons": [{
    "src": "images/touch/homescreen48.png",
    "sizes": "48x48",
    "type": "image/png"
  }, {
    "src": "images/touch/homescreen72.png",
    "sizes": "72x72",
    "type": "image/png"
  }],
  "related_applications": [{
    "platform": "web"
  }, {
    "platform": "play",
    "url": "https://play.google.com/store/apps/details?id=com.google.samples.apps.iosched"
  }]
}
{{< / highlight >}}
El archivo que nosotros descargamos está reducido, aunque lo único que nos interesa cambiar es `name` y `short_name`
{{< highlight json >}}
{"name":"MiBew","short_name":"Bloc de notas", ...}
{{< / highlight >}}

:link:Te dejo la [página Web de Favicon](https://favicon.io) para que la mires.
:link:[Documentación de Mozilla sobre App Manifest](https://developer.mozilla.org/es/docs/Web/Manifest).
