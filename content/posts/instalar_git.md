---
title: "Instalar GIT"
tags: ["Instalar y Configurar"]
date: 2022-09-28T04:39:58-03:00
description: "Guía para instalar GIT en Windows, Linux y Mac."
draft: false
type: "post"
showTableOfContents: true
---

# Instalar GIT
A continuación dejo los pasos para la instalación de GIT, el cual puede ser utilizado en Windows, Linux y Mac.

> Homebrew es un sistema de gestión de paquetes que simplifica la instalación, actualización y eliminación de programas en los sistemas operativos Mac OS de Apple y GNU/Linux.

## Windows
Debemos entrar en [la página oficial de GIT](https://git-scm.com/download/win) y descargar la versión que nos corresponda, ya sea de 32-bit o 64-bit.

Podemos probar que todo está correcto con el siguiente comando:
{{< highlight bash >}}
git --version
{{< / highlight >}}

En mi caso la salida es la siguiente:
{{< highlight bash >}}
git version 2.33.1.windows.1
{{< / highlight >}}

## Linux
En Linux va a depender la distro que estás utilizando, aquí está la [web de GIT con todos los comandos disponibles según la distro](https://git-scm.com/download/linux).\

Igual dejo la versión de Ubunto como ejemplo.
Recuerda actualizar la lista de paquetes con `apt-get update` y `sudo` si es necesario.
{{< highlight bash >}}
sudo apt-get install git
{{< / highlight >}}

Revisa la versión con:
{{< highlight bash >}}
git --version
{{< / highlight >}}

En mi caso la salida es la siguiente:
{{< highlight bash >}}
git version 2.25.1
{{< / highlight >}}

## Mac
En los sistemas Mac puedes utilizar Homebrew, puedes ver [como instalar Homebrew aquí](/posts/instalar_homebrew/).

Instalamos GIT utilizando Homebrew con el siguiente comando:
{{< highlight bash >}}
brew install git
{{< / highlight >}}

Revisa la versión con:
{{< highlight bash >}}
git --version
{{< / highlight >}}

En mi caso la salida es la siguiente:
{{< highlight bash >}}
git version 2.25.1
{{< / highlight >}}

Eso es todo, ya tenemos instalado GIT.

:link:Te dejo la [página Web de GIT](https://git-scm.com) para documentación más detallada.
