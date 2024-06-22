# Botones de Opciones - JRadioButton
**IMPORTANTE** los ejemplos de este apartado estan relacionados con las Ventanas(JFrame) y Paneles(JPanel) de los apuntes anteriores.
Son múltiples botones de encuestas
###Creacion de Radio Botón
```java
JRadioButton radioBoton1 = new JRadioButton(); //Boton vacio
JRadioButton radioBoton1 = new JRadioButton("RadioBoton1",true); //Agrego texto y activo el botón
```
Si ponemos el boton activado (true), cuadno iniciemos el programa el botón ya aparecerá seleccionado mientras que si lo ponemos (false) aparecera no seleccionado.
Independientemente de como aparezca el boton al inicio se podra cambiar de estado seleccionandolo o no.
### Agregar el Radio Boton al panel
```java
p1.add(radioBoton1);
```
### Agregar posicion y tamaño al botón
```java
radioBoton1.setBounds(50,100,100,50); //(x,y,ancho,alto)
```
## Contexto de uso
Dado que estos botones se suelen usar en programas destinados a encuestas o examenes tipo test, no se deberian de poder activar los 3 votones si es que cada pregunta tuviera por ejemplo 3 opciones. 
Por ello, si tuvieramos ya nuestros 3 botones creados y agregados al panel, deberemos crear un grupo de botones **ButtonGroup**:
```java
ButtonGroup grupoRadioBotones = new ButtonGroup();
//agregamos los botones
grupoRadioBotones.add(radioBoton1); //Agregar radioBoton1 al grupo
grupoRadioBotones.add(radioBoton2); //Agregar radioBoton2 al grupo
grupoRadioBotones.add(radioBoton3); //Agregar radioBoton3 al grupo
```
Ahora solo podremos selecionar SOLO una opcion (boton) del grupo. Si activamos 2 se desactiva 1 y asi...
### Desabilitar y avilitar botones
```java
radioBoton1.setEnabled(true); //radioBoton1 está habilitado
radioBoton2.setEnabled(false); //radioBoton1 está deshabilitado
```
### Agregar texto al botón
Si no lo hemos agregado en el constructor a la hora de crearlo podemos usar el método **setText();**
```java
radioBoton3.setText("Texto"); //Con texto
radioBoton3.setText(null); //Sin texto
```


