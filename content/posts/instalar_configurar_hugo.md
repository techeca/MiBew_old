---
title: "Instalar y Configurar HUGO"
tags: ["Instalar y Configurar"]
date: 2022-09-27T19:43:30-03:00
description: "Guía para instalar y configurar HUGO, framework para generar web estáticas."
draft: false
type: "post"
showTableOfContents: true
---

# Instalar HUGO
Se puede instalar HUGO de distintas formas, en este proyecto vas a necesitar:

[Chocolatey](https://gokarna-hugo.netlify.app/) (Windows) o [Homebrew](https://brew.sh/index_es) (Linux/Mac)\
[GIT](https://git-scm.com/) (Para descargar Tema)
> Hugo es un framework para la creación de sitios web de propósito general.

Si no tienes Chocolatey/Homebrew o GIT, puedes encontrar una guía con documentación aquí:

:point_right: [Como instalar Chocolatey](/posts/instalar_chocolatey)\
:point_right: [Como instalar Homebrew](/posts/instalar_homebrew)\
:point_right: [Como instalar GIT](/posts/instalar_git)

Instala HUGO corriento el siguiente comando:
{{< highlight bash >}}
choco install hugo -confirm
{{< / highlight >}}
En la ruta donde vas a crear tu proyecto ejecuta lo siguiente:
{{< highlight bash >}}
hugo new site mibew
{{< / highlight >}}
> mibew es el nombre del proyecto

Ya tenemos creado nuestro proyecto, pero aún no tiene nada :joy:, next.  

## Configurar HUGO
Antes de agregar contenido vamos agregar un tema, en este caso [Gokarna](https://main--gokarna-hugo.netlify.app), se ve bonito
y limpio.
![Gokarna Theme Preview](https://d33wubrfki0l68.cloudfront.net/552b6b2d212c894a334d201b1b840a068affe798/ac42b/themes/gokarna/screenshot_hu220694613ad2158d77e02a6451275a96_76721_750x500_fill_catmullrom_top_3.png "Gokarna Theme Preview")
### Agregar Tema
Preparamos nuestro proyecto para git con `git init` (Si es que aún no lo haces) e instalamos el tema desde
su repositorio.
{{< highlight bash >}}
git init
git submodule add https://github.com/526avijitgupta/gokarna.git themes/gokarna
{{< / highlight >}}
En la raíz de tu proyecto se encuentra el archivo `config.toml`, debemos agregar las siguientes líneas.
{{< highlight toml >}}
theme = "gokarna"
enableEmoji = true
enableRobotsTXT = true
{{< / highlight >}}
> Según Wikipedia, TOML es un formato de archivo de configuración que es fácil de leer debido a la semántica obvia que pretende ser "mínima".

#### Configurar Tema
Si bien no todos estos parámetros son necesarios, se recomiendan para un buen funcionamiento.

En `/config.toml` debemos agregar `[params]` para agregar información básica y `[menu]`
para agregar las categorías de nuestro blog.
{{< highlight toml >}}
[params]
    avatarURL = "images/horrible.png"
    description = "Mejor lo voy anotar, después se me olvida"
    customHeadHTML = '''
    <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
    '''
    metaKeywords = ["blog", "gokarna", "hugo", "hola", "mundo", "ggwp"]
    footer = "MiBew"
    showPostsOnHomePage = "recent"
{{< / highlight >}}
`avatarUrl`: Hace referencia al contenido de la carpeta `/static/images`.\
`Description`: Descripción en HomePage.\
`customHeadHTML`: Injecta HTML en el tag HEAD.\
`metaKeywords`: Keywords para SEO.\
`footer`: Texto customizable de footer.\
`showPostsOnHomePage`: Muestra post en la página inicial. (Opcional)

- :point_right: Para `customHeadHTML` [Generar Favicons, Browserconfig & Manifest](https://favicon.io/)

{{< highlight toml >}}
[menu]
  [[menu.main]]
    identifier = "posts"
    url = "/posts/"
    pre = "<span data-feather='book'></span>"
    post = ""
    name = "Posts"
    weight = 1
{{< / highlight >}}
`identifier`: Identificador único para un item del menu.\
`url`: url (En la carpeta `/content` se encuentran todas la rutas)\
`pre`: Inserta un icono antes del menu/categoría.\
`post`: Inserta un icono despues del menu/categoría.\
`name`: Nombre a mostrar.\
`weight`: Determina el orden.
### Agregar Post
{{< highlight bash >}}
hugo new posts/instalar_configurar_hugo.md
{{< / highlight >}}
> "instalar_configurar_hugo.md" es el nombre de tu nuevo Post :smiley:

#### Configurar Post
El Post que hemos creado se encuentra en `/content/posts/` en mi caso el archivo se llama `instalar_configurar_hugo.md`.\
Agregamos propiedades como `description`, `tags`, `type` y editamos `title` a gusto, `draft` debe estar en `false` para
que podamos ver el Post en nuestra web.   
{{< highlight go >}}
---
title: "Instalar y Configurar HUGO"
tags: ["Instalar y Configurar"]
date: 2022-09-27T19:43:30-03:00
description: "Guía para instalar y configurar HUGO, framework para generar web estáticas."
draft: false
type: "post"
---
{{< / highlight >}}

### Agregar Table Content
Este paso si lo dejé como opcional, si quieres puedes continuar a la sección de Pruebas Locales y probar tu web :wink:.

Volvemos a modificar nuestro arhivo `config.toml` que se encuentra en la raíz del proyecto y agregamos `[markup]`.
{{< highlight toml >}}
[markup]
  [markup.tableOfContents]
    startLevel = 1
    endLevel = 5
    ordered = false
{{< / highlight >}}

#### Configurar Table Content
En los post que se desea agregar la Tabla de Contenidos se debe agregar/activar `showTableOfContents`, agregamos la propiedad quedando de la siguiente manera:
{{< highlight go >}}
title: "Instalar y Configurar HUGO"
tags: ["Instalar y Configurar"]
date: 2022-09-27T19:43:30-03:00
description: "Guía para instalar y configurar HUGO, framework para generar web estáticas."
draft: false
type: "post"
showTableOfContents: true
{{< / highlight >}}

## Pruebas locales
Ya podemos probar y ver nuestra hermosa web :heart_eyes: (de manera local).\
Ejecuta el siguiente comando:
{{< highlight bash >}}
hugo serve
{{< / highlight >}}
> 'serve' inicia un servidor local para desarrollo.

:tada:Listo!:tada:

Ingresa en [http://localhost:1313](http://localhost:1313) para ver tu Web.

## Deploy
Not yet

## Documentación relacionada

Mucha de la configuración que se realizó no está bien detallada en esta guía por lo que te recomiendo que leas lo siguiente para que te quites algunas dudas.

:link:[Repositorio de este proyecto en Github](https://github.com/techeca/MiBew)

:link:Si tienes problemas para agregar otros accesos ademas de post (como /tags o /projects), dejo la [documentacion de Gokarna](https://main--gokarna-hugo.netlify.app/posts/theme-documentation-basics//) con más detalles de el porqué de algunas cosas.

:link:Tambien dejo el link a la [documentación oficial de HUGO](https://gohugo.io/getting-started/quick-start/) la cual tiene más información para la customización de tu proyecto.
