---
title: "Instalar Chocolatey"
tags: ["Instalar y Configurar"]
date: 2022-09-28T00:59:58-03:00
description: "Guía para instalar Chocolatey."
draft: false
type: "post"
showTableOfContents: true
---

# Instalar Chocolatey
A continuación dejo los pasos para la instalación que yo considero más simple o posiblemente la única que he probado :clown_face:.

> Chocolatey es un gestor de paquetes de línea de comandos para Microsoft Windows. Utiliza la infraestructura de empaquetado de NuGet y PowerShell para simplificar el proceso de descarga e instalación de software.

Podemos utilizar `CMD` o `PowerShell`

## CMD
Abrimos `CMD` con permisos de administrador y ejecutamos:
{{< highlight bash >}}
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
{{< / highlight >}}

## PowerShell
Tambien lo podemos hacer con `PowerShell`, ejecutamos el siguiente comando:
{{< highlight shell >}}
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
{{< / highlight >}}

Revisa la versión de Chocolatey con:
{{< highlight bash >}}
choco --v
{{< / highlight >}}

En mi caso la salida es la siguiente:
{{< highlight bash >}}
Chocolatey v0.11.2
{{< / highlight >}}

Ya tenemos instalado Chocolatery listo para instalar más cosas :sunglasses:.

:link:Te dejo la [página Web de Chocolatey](https://chocolatey.org/install) para documentación más detallada.
