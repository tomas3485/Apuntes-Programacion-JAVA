# Botones - JButton
### Creación de un botón
```java
JButton boton1 = new JButton();
```
### Agregar el botón al panel
```java
p1.add(boton1);
```
### Indicar posicion y tamaño del boton en el panel
```java
boton1.setBounds(300,300,50,75); //(x,y,ancho,alto)
```
### Agregar texto al botón
- Desde el constructor del objeto boton:
```java
JButton boton2 = new JButton("Boton");  //Creo boton2 con texto "Boton" dentro
```
- Con un método **.setText()**
```java
boton1.setText("Texto"); //Agrego un texto al boton1
```
### Activar y desactivar el botón
```java
boton2.setEnable(true); //boton2 funciona (activado)
boton1.setEnable(false); //boton2 no funciona (desactivado)
```
### Presionar el botón sin el rato (Ctrl + letra)
```java
boton1.setMnemonic('a'); //Presionando Ctrl + a = click del raton en el botón
```
### Cambiar el color de la letra del texto de dentro del botón
```java
boton1.setForeground(Color.BLUE); //color de letra azul
```
### Agregar una imagen al botón
```java
boton2.setIcon(new ImageIcon(imagen2.getImagen().getScaledInstance(boton2.getWidth(),boton2.getHeight(),Image.SCALE_SMOOTH)); //(ancho,largo,escalado adacptados a los del boton)
```
### Cambiar el color de fondo del botón
```java
boton2.setBackground(Color.gray); //Boton con fondo de color gris
```
