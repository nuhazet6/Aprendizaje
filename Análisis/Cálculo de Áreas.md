# Análisis

<p align="justify">
  
Planteamiento de un análisis para el desarrollo de una aplicación que realice el cálculo de áreas de determinadas figuras geométricas siguiendo la siguiente imagen:

</p>
<p align="center">

<img src="Imágenes/Figuras.png" title="Figuras">
  
</p>

## Documento de Requisitos

  
Exponemos los requisitos mínimos para realizar la aplicación:
 
  
-	Qué figuras vamos a incorporar (dadas por la imagen).
-	Menú principal que dirija a un menú donde se muestren y se pueda seleccionar la figura de la que se necesite el área. (¿Por qué dos menús? Porque así desde el principal se pueden añadir otras opciones en un futuro como el perímetro de las figuras, etc)
-	Triángulo, cuadrado, romboide y rectángulo -> conocer altura/lado y base/lado
-	Pentágono -> conocer perímetro (al menos un lado) y apotema (radio)
-	Círculo -> conocer radio
-	Trapecio -> conocer las bases y la altura
-	Unidades de medida (sistema internacional o no, dentro del sistema internacional si es en metros, centímetros, etc)



## MÉTODOS

Métodos generales y opcionales para el funcionamiento de la aplicación:

- Pedir figura
- Pedir parámetros de la fórmula en cuestión (si es cuadrado lado*lado por lo tanto el lado, etc) junto con las unidades (decímetro, centímetros, pulgada, pies, etc)
- Mostrar nombre de la figura junto con el resultado, una opción para mostrar la fórmula (esto es opcional, también se puede poner dicha opción en el menú principal como un ajuste, es decir en el menú principal añadir un apartado de opciones donde activarlo y desactivarlo, en vez de mostrarla obligatoriamente en la pantalla del resultado) y una opción para volver al menú principal/secundario.
