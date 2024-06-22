# Cajas de Texto - JTextField
**IMPORTANTE** los ejemplos de este apartado estan relacionados con las Ventanas(JFrame) y Paneles(JPanel) de los apuntes anteriores.
### Creación de una caja de texto
```java
JTextField cajaTexto1 = new JTextField(); //caja vacía
JTextField cajaTexto1 = new JTextField("Escribe..."); //caja con texto
```
### Constructores de las cajas de texto
```java
JTextField cajaTexto1 = new JTextField("Hola",50); //(texto,numeroDeColumnas)
```
Sin embargo, ese numero de columnas (50) será ignorado/cambiado si después usas el método setBounds() donde indicas el ancho(numero de columnas).
Además, si no ponemos este método setBounds() para indicar la posición de nuestra caja de texto esta no se verá en el panel. Entonces, ¿que hacemos?
Para que nos haga caso deberemos activar el diseño del panel si esque lo teniamos desactivado mediante **p1.setLayout(null);**
Simplemente borramos o comentamos esa sentencia.
### Agregar caja de texto al panel
```java
p1.add(cajaTexto);
```
### Indicar posicion y dimensiones de la caja en el panel
```java
cajaTexto1.setBounds(300,300,50,75); //(x,y,ancho,alto)
```
### Agregar texto a la caja de texto
Este texto se verá por detras como si fuera una marca de agua que te puede indicar lo que escribir en la caja.
```java
cajaTexto1.setText("Hola..."); //("texto")
```


