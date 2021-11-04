# Tarea 1: Instalación de Git en linux
Se mostrará cómo instalar y configurar Git en Ubuntu 21.04. Se realizará la instalación de dos maneras distintas: a través del administrador de paquetes integrado y a través de la fuente.

## Índice
1.[Instalación de Git con paquetes predeterminados](#id1)
1.[Instalación desde la fuente](#id2)
1.[Configuración de Git](#id3)

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
 <img src="Imágenes/2.png" alt="Imagen 1">
 
3.	Una vez actualizadas, empezamos a instalar Git:

```
sudo apt install git
```

 <img src="Imágenes/3.png" alt="Imagen 1">
 
4.	Finalmente comprobamos que se haya instalado correctamente:

```
git –version
```

<img src="Imágenes/4.png" alt="Imagen 1">

## Instalación de Git desde la fuente<a name="id2"></a>

Si busca un método más flexible para instalar Git, puede optar por compilar el software desde la fuente, lo cual explicaremos en esta sección. Esto toma más tiempo y no se mantendrá en su administrador de paquetes, pero le permitirá descargar la versión más reciente y le brindará mayor control sobre las opciones que incluya si quiere personalizarlo.

Verifique la versión de Git que está instalada actualmente en el servidor:

```
git --version
```

Si Git está instalado, obtendrá un resultado similar al siguiente:

__Output__

```
git version 2.25.1
```

Antes de comenzar, debe instalar el software necesario para Git. Todo se encuentra disponible en los repositorios predeterminados, de modo que podemos actualizar nuestro índice local de paquetes y luego instalar los paquetes pertinentes.

```
sudo apt update
sudo apt install libz-dev libssl-dev libcurl4-gnutls-dev libexpat1-dev gettext cmake gcc
``` 

Tras haber instalado las dependencias necesarias, cree un directorio temporal y vaya a él. Aquí es donde descargaremos nuestro tarball de Git.

```
mkdir tmp
cd /tmp
``` 

Desde el sitio web del proyecto Git, podemos navegar a la lista de tarball disponible en https://mirrors.edge.kernel.org/pub/software/scm/git/ y descargar la versión que quiera utilizar. En el momento de escribir este artículo, la versión más reciente es 2.29.3, así que descargaremos esa versión para nuestra demostración. Utilizaremos curl y enviaremos el archivo que descarguemos a git.tar.gz.

```
curl -o git.tar.gz https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.29.3.tar.gz
``` 

Descomprima el archivo tarball:

```
tar -zxf git.tar.gz
``` 

A continuación, vaya al nuevo directorio de Git:

```
cd git-*
``` 

Ahora, podrá crear el paquete e instalarlo escribiendo estos dos comandos:

```
make prefix=/usr/local all
sudo make prefix=/usr/local install
``` 

Ahora, sustituya el proceso de shell para que se utilice la versión de Git que acabamos de instalar:

```
 exec bash
```

Una vez completado esto, puede estar seguro de que su instalación se realizó correctamente comprobando la versión.

```
git --version
```

__Output__
git version 2.29.3

Con Git instalado correctamente, ahora puede finalizar su configuración.

## Configuración de Git

Una vez que esté satisfecho con la versión de Git, debería configurar Git de modo que los mensajes de confirmación que genere contengan la información correcta y lo respalden a medida que compile su proyecto de software.

Esta configuración es posible si aplicamos el comando git config. Específicamente, debemos proporcionar nuestro nombre y nuestra dirección de correo electrónico debido a que Git inserta esta información en cada confirmación que hacemos. Podemos añadir esta información escribiendo lo siguiente:

```
git config --global user.name "Your Name"
git config --global user.email "youremail@domain.com"
```

Podemos ver todos los elementos de configuración creados escribiendo lo siguiente:

```
git config --list
```

__Output__

```
user.name=Your Name
user.email=youremail@domain.com
...
```

La información que ingresa se almacena en el archivo de configuración de Git. Tendrá la opción de editarlo manualmente con el editor de texto que prefiera (en este tutorial utilizaremos nano) como se muestra a continuación:

```
nano ~/.gitconfig
```

``` 
~/.gitconfig contents
[user]
  name = Your Name
  email = youremail@domain.com (Un correo personal que indique que es el creador de la tarea)
```

Para salir del editor de texto pulse CTRL y X, luego Y y, a continuación, ENTER.

Existen muchas otras opciones que puede configurar, pero estas son las dos esenciales que se necesitan. Si omite este paso, probablemente verá mensajes de advertencia cuando realice una confirmación con Git. Esto implica un mayor trabajo para usted, pues tendrá que revisar las confirmaciones que haya realizado con la información corregida.
