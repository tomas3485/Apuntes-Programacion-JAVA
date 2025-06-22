# Listas desplegables - JComboBox
**IMPORTANTE** los ejemplos de este apartado estan relacionados con las Ventanas(JFrame) y Paneles(JPanel) de los apuntes anteriores.
### Creación de una lista desplegable
```java
JComboBox listaDesplegable = new JComboBox();
```
Estas listas desplegables las podemos inicializar con contenedores como por ejemplo un contenedor de Strings.
```java
String[] paises = {"Espania", "Alemania", "Italia", "Portugal"}; //contenedor de paises
JComboBox listaDesplegable = new JComboBox(paises);  //lista inicializada con el contenedor
```
Debemos indicar el tamaño de la lista y donde va a situarse en el panel. (no hace falta)
```java
listaDesplegable.setBounds(20,20,300,200); //(x,y,ancho,alto)
```
### Agregar la lista desplegable al panel
```java
panel.add(listaDesplegable);
```
Ahora en el panel se verá la lista desplegable con los paises que encontramos en el contenedor de paises con el que hemos inicializado la **listaDesplegable**.
### Añadir elementos a la listaDesplegable
```java
listaDesplegable.addItem("Argentina"); //añadir un objeto
```
Dado que estamos trabajando con una lista que contiene Strings, debemos añadir una cadena de texto para que no de error.
Esa cadena se colocará al final de la lista en la última posición.

Inicialmente en la lista siempre va salir marcado la primera opcion de esta. Para cambiar el objeto que encontramos seleccionado:
```java
listaDesplegable.setSelectedItem("Italia"); //seleccionar el 1er objeto visto
```
Ahora inicialmente me saldrá **Italia** seleccionada en mi lista desplegada.
