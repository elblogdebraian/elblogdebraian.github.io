---
layout: post
title: Actualizar nodejs en Parrot Sec OS
subtitle: Hoy aprenderemos como actualizar Nodejs y npm en Parrot Security Os y otras distros no soportadas
bigimg: /img/path.jpg
category: [tutorial]
tags: [tutorial]
comments: true
css:
  - '/css/extend-home.css'
---

Trabajando un poco con Jekyll noté que hay algunas cosas que son difíciles de instalar o hacer, 
si bien no son difíciles porque Linux sea complicado o porque Jekyll sea un dolor de cabeza.
Más bien son complicadas, porque en ciertos casos nuestra distribución de Linux no es la más sencilla.

Hoy voy a hablar acerca de como instalar, o en el caso, actualizar nodejs y npm, 
ya que en mi distribución «Parrot Security OS» viene instalado nodejs 6x, 
y npm no está soportado en esa versión.

Bueno primero comentar, no es tan simple con un «apt-get install nodejs». 
No sé porque los repositorios de Parrot no cuentan con nodejs actualizado. 
Así que vamos a comentar paso a paso como actualizar esta herramienta importante en el desarrollo web.

# Comprobar version de nodejs y npm:
- Abrimos la terminal y chequeamos:

```console
$ nodejs --version
```

```console
$ npm --version
```

*Como puede darse el la situación de que no uses Parrot pero uses otra distribución de Linux 
que no esté soportada por **nodejs**, es necesario que veamos que versión tenemos. 
En el caso de que se use Kali Linux o Deepin, seguiremos los mismos pasos.*


# Comprobar que nos devuelve nodejs:

```powershell
$ curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
## Confirming "intruder" is supported...

+ curl -sLf -o /dev/null 'https://deb.nodesource.com/node_9.x/dists/intruder/Release'

## Your distribution, identified as "intruder", is not currently supported, 
## please contact NodeSource at [https://github.com/nodesource/distributions/issues]
## if you think this is incorrect or would like your distribution to be considered for support
```
Nos devolverá algo parecido o similar a eso. Si vamos al link que nos indica 
[NodeSource](https://github.com/nodesource/distributions/issues). 
Vamos a ver que hay muchísimas personas con el mismo problema y ninguna solución.

<center><img src="/img/posts/nodejs1.png" height="500" width="900"></center>

**Para solucionarlo, basta con unos sencillos pasos que cualquiera puede lograr:**

# Chequeamos nuestra distro:

```powershell
$ sudo cat /etc/*-release
DISTRIB_ID=Parrot
DISTRIB_RELEASE=3.10
DISTRIB_CODENAME=intruder
DISTRIB_DESCRIPTION="Parrot 3.10 - Intruder"
PRETTY_NAME="Parrot GNU/Linux 3.10 Intruder"
NAME="Parrot GNU/Linux"
ID=parrot
VERSION="3.10 (Intruder)"
VERSION_ID="3.10"
ID_LIKE=debian
ANSI_COLOR="1;31"
HOME_URL="https://www.parrotsec.org/"
SUPPORT_URL="https://community.parrotsec.org/"
BUG_REPORT_URL="https://dev.parrotsec.org/"
```
Veremos que en Distrib_codename, nos marca justamente el mismo error de la distribución no soportada. 
Para modificar esto vamos a la terminal

```console
$ sudo nano /etc/*-release
```
*Se les abrira un archivo en nano, y deben editar justamente «DISTRIB_CODENAME=intruder».
Modifican el nombre de la distribución a **stretch**, **jessie**, **xenial**; 
cualquier nombre de esos da igual y devuelve el mismo resultado.

# Quedaría algo así:

```powershell
DISTRIB_ID=Parrot
DISTRIB_RELEASE=3.10
DISTRIB_CODENAME=xenial
DISTRIB_DESCRIPTION="Parrot 3.10 - Intruder"
```

Una vez editado, simplemente dan `ctrl+o` luego `ctrl+x` y `ctrl+x` de nuevo.

# Volvemos a ejecutar el mismo comando de hoy:

```powershell
$ curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
```

# Instalamos:

```console

$ sudo apt install nodejs
```

*En ocasiones no hará simplemente nada, ya que nuestra distribución cuenta con repositorios propios. **Para solucionarlo:***

# Solución al fail del *sudo apt-get install nodejs*:

- Vamos al gestor de paquetes synaptic.
- Configuración.
- Repositorios.

y deseleccionamos el repositorio oficial de Parrot.

# Actualizamos en la terminal con:

```console
$ sudo apt-get update
```
# Volvemos a iniciar el comando para instalar nodejs:

```console
$ sudo apt-get install nodejs
```

Y listo, tendremos la actualización de nodejs y npm.

# Aún no terminamos: Volvemos a Synaptic:

**Volvemos a activar los repositorios de Parrot (o la distribución que estés: kali, arch, deepin, manjaro, etc.)**

# Chequeamos la versión de nodejs y npm:

```console
$ nodejs --version
```

```console
$ npm --version
```

# Y ya queda instalado nodejs

***¿Qué te pareció este tutorial? Comenta si te ha servido!***
