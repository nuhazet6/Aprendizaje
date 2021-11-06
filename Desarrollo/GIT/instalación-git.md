# Instalación de Git en linux
Se mostrará cómo instalar y configurar Git en Ubuntu 21.04. Se realizará la instalación de dos maneras distintas: a través del administrador de paquetes integrado y a través de la fuente.

## Índice
1.[Instalación de Git con paquetes predeterminados](#id1)

2.[Instalación desde la fuente](#id2)

3.[Configuración de Git](#id3)

## Instalación de Git con paquetes predeterminados<a name="id1"></a>
1.	Primero verificamos si hay alguna versión de Git instalada escribiendo lo siguiente: 

```
git –version
```

 <img src="Imágenes/1.png" alt="Imagen 1">
 
2.	Antes de instalar Git actualizamos las herramientas de actualización de paquetes:

```
sudo apt update
```
 <img src="Imágenes/2.png" alt="Imagen 2">
 
3.	Una vez actualizadas, empezamos a instalar Git:

```
sudo apt install git
```

 <img src="Imágenes/3.png" alt="Imagen 3">
 
4.	Finalmente comprobamos que se haya instalado correctamente:

```
git –version
```

<img src="Imágenes/4.png" alt="Imagen 4">

## Instalación de Git desde la fuente<a name="id2"></a>

1.	Primero comprobamos la versión:


```
git --version
```

__Output__

```
git version 2.30.2
```
<img src="Imágenes/5.png" alt="Imagen 5">

2.	Antes de empezar debemos actualizar nuestro índice local de paquetes:

```
sudo apt update
```

<img src="Imágenes/6.png" alt="Imagen 6">

3.	A continuación, instalamos los paquetes pertinentes:
```
sudo apt install libz-dev libssl-dev libcurl4-gnutls-dev libexpat1-dev gettext cmake gcc
``` 

<img src="Imágenes/7.png" alt="Imagen 7">
<img src="Imágenes/8.png" alt="Imagen 8">

4.	Tras esto descargamos la versión específica de Git:
Desde el sitio web del proyecto Git, podemos navegar a la lista de tarball disponible en https://mirrors.edge.kernel.org/pub/software/scm/git/ y descargar la versión que quiera utilizar.
```
curl -o git.tar.gz https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.29.3.tar.gz
``` 
<img src="Imágenes/9.png" alt="Imagen 9">
5.	El error se debe a que tenemos que instalar el curl para usar el comando “curl” así que lo instalamos:
```
sudo snap install curl
```
<img src="Imágenes/10.png" alt="Imagen 10">
6.	Una vez instalado, volvemos a hacer el comando curl, descomprimimos el archivo con tar y entramos con cd al nuevo directorio:
```
curl -o git.tar.gz https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.29.3.tar.gz 
```
```
tar -zxf git.tar.gz
``` 
```
cd git-*
``` 
<img src="Imágenes/11.png" alt="Imagen 11">

8.	Ahora creamos el paquete y lo instalamos:

```
make prefix=/usr/local all
```
```
sudo make prefix=/usr/local install
``` 
<img src="Imágenes/12.png" alt="Imagen 12">
<img src="Imágenes/13.png" alt="Imagen 13">
9.	Elegimos el git que acabamos de instalar con "exec bash" y comprobamos que efectivamente tenemos la versión que queremos con version:
```
 exec bash
```
```
git --version
```
__Output__
git version 2.29.3

<img src="Imágenes/14.png" alt="Imagen 14">
Con Git instalado correctamente, ahora puede finalizar su configuración.

## Configuración de Git <a name="id3"></a>
1.	Vamos a poner nuestro nombre de usuario y correo:
```
git config --global user.name "Tu nombre"
git config --global user.email "tuemail@dominio.com"
```
<img src="Imágenes/15.png" alt="Imagen 15">
2.	Comprobamos los elementos de la configuración:

```
git config --list
```
__Output__

```
user.name=Tu nombre
user.email=tuemail@dominio.com
```
<img src="Imágenes/16.png" alt="Imagen 16">
La información que ingresa se almacena en el archivo de configuración de Git. Tendrá la opción de editarlo manualmente con el editor de texto que prefiera (en este tutorial utilizaremos nano) como se muestra a continuación:

```
nano ~/.gitconfig
```
<img src="Imágenes/17.png" alt="Imagen 17">
``` 
~/.gitconfig contents
[user]
  name = Tu nombre
  email = tuemail@dominio.com
```
<img src="Imágenes/18.png" alt="Imagen 18">

Para salir del editor de texto pulse CTRL y X, luego Y y, a continuación, ENTER.

Listo ya tenemos el git instalado y configurado listo para usar.
