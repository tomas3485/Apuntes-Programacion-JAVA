# Etiquetas - JLabel
**IMPORTANTE** los ejemplos de este apartado estan relacionados con las Ventanas(JFrame) y Paneles(JPanel) de los apuntes anteriores.

Creación de etiquetas, pueden ser de tipo texto o imagen.
Hay que importar su librería **import javax.swing.JLabel;** 
- Clase Etiqueta
```java
import javax.swing.*;

public class Etiqueta extends JLabel {
    public Etiqueta(){

    }
}
```
- Main

Creamos un objeto e1 de la clase Etiqueta en el main
```java
import java.awt.*;

public class Main{
    public static void main(String[] args) {
        Ventana v1 = new Ventana();
        v1.setVisible(true);

        Panel p1 = new Panel();

        v1.getContentPane().add(p1);
        p1.setBackground(Color.gray);

        Etiqueta e1 = new Etiqueta(); //Creacion de etiqueta e1
    }
}
```
### Crear etiquetas sin clase Etiqueta
Podemos crear etiquetas sin necesidad de crear una clase de esta ya que ya esta creada como JLavel. Entonces directamente en el main y habiendo importado la libreria
pondremos **JLabel e1 = new JLabel();**
```java
import java.awt.*;

public class Main{
    public static void main(String[] args) {
        Ventana v1 = new Ventana();
        v1.setVisible(true);

        Panel p1 = new Panel();

        v1.getContentPane().add(p1);
        p1.setBackground(Color.gray);

        JLabel e1 = new JLabel(); //Creacion de etiqueta e1
    }
}
```
### Agregamos la etiqueta al panel con el método **.add()**
```java
import java.awt.*;

public class Main{
    public static void main(String[] args) {
        Ventana v1 = new Ventana();
        v1.setVisible(true);

        Panel p1 = new Panel();

        v1.getContentPane().add(p1);
        p1.setBackground(Color.gray);

        JLabel e1 = new JLabel(); //Creacion de etiqueta
        
        p1.add(e1);  //Agrego etiqueta e1 a panel p1
    }
}
```
## ETIQUETAS TEXTO
### Agregar texto a la etiqueta
```java
e1.setText("Texto");
```
La etiqueta se mostrará por defecto en el centro del panel.
### Establecer dimension y posicion de la etiqueta
```java
e1.setBounds(50,50,200,200); //(x,y,ancho,largo)
```
**ERROR** Sin embargo, con esto no nos hace caso. Para que funcione debemos agregar previamente al objeto panel el método **setLayout(null);**
```java
p1.setLayout(null);  //permitir modificar - desactiva diseño
e1.setBounds(40,40,30,50); //(x,y,ancho,largo)
```
### Cambiar el color de letra y el fondo
- Color letra
```java
e1.setForeground(Color.BLUE);  //letra de color azul
```
- Fondo etiqueta
Inicialmente la etiqueta es transparente.
```java
e1.setBackground(Color.white); //fondo etiqueta color blanco
```
**ERROR** Sin embargo, con esto no nos hace caso. Para que funcione debemos agregar previamente al objeto etiqueta el método **setOpaque(true);**
```java
e1.setOpaque(true);
e1.setBackground(Color.white); //fondo etiqueta color blanco
```
Ahora si se mostrara el tamaño de la etiqueta con un fondo blanco y el texto en letras de color azul.
### Cambiar ubicación del texto dentro de la etiqueta
Para indicar si queremos que el texto aparezca en el centro, izquierda o derecha de nuestra etiqueta:
- Cuando creamos e instanciamos el objeto etiqueta:
```java
JLabel e2 = new JLabel("Adios",SwingConstants.CENTER); //centro
JLabel e2 = new JLabel("Adios",SwingConstants.LEFT); //izquierda
JLabel e2 = new JLabel("Adios",SwingConstants.RIGHT); //derecha
```
- Usando el método **setHorizontalAlignment(SwingConstants.CENTER)** para en este caso en el centro
```java
e1.setHorizontalAlignment(SwingConstants.CENTER); //centro
e1.setHorizontalAlignment(SwingConstants.LEFT); //izquierda
e1.setHorizontalAlignment(SwingConstants.RIGHT); //derecha
```
## ETIQUETA IMAGEN
Para esto debemos tener la imagen descargada en la misma carpeta donde guardemos el proyecto de Java en nuestro ordenador. Para ello debemos importar la libreria **import javax.swing.Image.Icon;**
### Crear etiqueta con imagen 
```java
JLabel e3 = new JLabel(new ImageIcon("nombre.jpg");
```
También se podria hacer de estas pormas:
```java
ImageIcon imagen1 = new ImageIcon("nombre.jpg");
JLabel e3 = new JLabel(imagen1);
```
O así:
```java
JLabel e3 = new JLabel();
e3.setIcon(new ImageIcon("nombre.jpg"));
```
### Agregar al panel
```java
p1.add(e3);
```
### Posicionar la etiqueta con la imagen
Se recomienda mirar el ancho y largo de la imagen y ponerlo igual para no perder información de esta(se recorte)
```java
e3.setBounds(40,40,30,50); //(x,y,ancho,largo)
```
### Cambiar el tamaño de la imagen
Una vez tengamos la imagen y la etiqueta por separado y tengamos instanciada la etiqueta con su posición y tamaño.
```java
e3.setIcon(new ImageIcon(imagen1.getImage().getScaledInstance(5,10,13))); //(ancho,largo,escalado)
```
Escalado recomendado: **Image.SCALE_SMOOTH**

