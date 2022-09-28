---
title: "Instalar Homebrew"
tags: ["Instalar y Configurar"]
date: 2022-09-28T03:54:39-03:00
description: "Guía para instalar Homebrew."
draft: false
type: "post"
showTableOfContents: true
---

# Instalar Homebrew
A continuación dejo los pasos para la instalación de Homebrew, el cual puede ser utilizado en Linux y Mac.

> Homebrew es un sistema de gestión de paquetes que simplifica la instalación, actualización y eliminación de programas en los sistemas operativos Mac OS de Apple y GNU/Linux.

## Terminal
Abrimos nuestra `Terminal` de preferencia y ejecutamos:
{{< highlight bash >}}
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
{{< / highlight >}}

Revisa la versión de Homebrew con:
{{< highlight bash >}}
brew -v
{{< / highlight >}}

En mi caso la salida es la siguiente:
{{< highlight bash >}}
Homebrew 3.6.3
Homebrew/homebrew-core (git revision 2c17277b7fb; last commit 2022-09-28)
{{< / highlight >}}

Ya tenemos instalado Homebrew listo para instalar más cosas :sunglasses:.

:link:Te dejo la [página Web de Homebrew](https://brew.sh/) para documentación más detallada.
