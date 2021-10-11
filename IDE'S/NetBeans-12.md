<div align="justify">

# Instalación del IDE Netbeans 12


<div align="center">
  <img src="" width="250px">
</div>


## Pasos

### Prerrequisitos

  Para instalar NetBeans primero necesitamos haber instalado Java. Si aún no lo has instalado puedes hacerlo en el siguiente enlace: [Instalación Java](https://github.com/nuhazet6/jdk/blob/4543e358060c3cdcf33c71454588e322a8b98518/Instalaci%C3%B3nJdk.md).

  Para verificarlo recuerda ejecutar el siguiente enlace:

  ```console
  java -version
  ```

## Instalación

  Los paquetes Snap son paquetes de software universales prediseñados que se envían con las bibliotecas y dependencias requeridas por el paquete de software. Son independientes de la distribución y se pueden instalar en cualquier distribución principal de Linux. Los snaps son populares ya que no requieren ninguna dependencia durante la instalación, lo que hace que el proceso de instalación sea fluido y sin errores.

  Para instalar la edición Netbeans, ejecute el siguiente comando:

```console
sudo snap install netbeans --classic
```

  La instalación finalizará cuando veas el sigueinte mensaje:

  ```console
  netbeans 12.5 from Apache NetBeans✓ installed
  ```

# Ejecutando Netbeans 12

  Ahora que Netbeans está instalado en su sistema Ubuntu, puede iniciarlo escribiendo netbeans en su terminal o haciendo clic en el icono de Netbeans ( Activities -> Netbeans ).

  Una vez que se cargue el IDE de Netbeans, se le presentará la página de inicio.

# Eliminar Netbeans

__No realices este paso, es para que conozcas como se elimina__.

 Una vez que no necesite Netbeans en su sistema. Use el siguiente comando para eliminar netbeans del sistema Ubuntu usando el comando snap.

```console
sudo snap remove netbeans
```
