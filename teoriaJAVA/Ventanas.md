# Ventanas - JFrame
Para usar ventanas debemos importar su libreria: **import javax.swing.JFrame**
- Clase Ventana
- En el método constructor indicamos el tamaño que tendrá nuestra ventana.
```java
import javax.swing.JFrame;
public class Ventana extends JFrame{
    public Ventana(){
        setSize(500,500); //(ancho,alto)
    }
}
```
- Main
Aqui podemos crear tantas ventanas(objetos de la clase Ventana) como queramos en nuestro programa.
```java
public class Main{
    public static void main(String[] args) {
        Ventana v1 = new Ventana();
    }
}
```
Inicialmente, la ventana aparece invisible/oculta. Por eso debemos usar el método **setVisible(true)**.
```java
public class Main{
    public static void main(String[] args) {
        Ventana v1 = new Ventana();
        v1.seVisible(true);
    }
}
```
A partir de este programa:
### Para que se cierre la ventana añadiremos en el métodod constructor el método **setDefaultCloseOperation(EXIT_ON_CLOSE);**
```java
public Ventana(){
        setSize(500,500); //(ancho,alto)
        setDefaultCloseOperation(EXIT_ON_CLOSE);
    }
```
### Añadir un título a la ventana añadiremos en el método constructor el método **setTitle("El titulo");**
```java
public Ventana(){
        setSize(500,500); //(ancho,alto)
        setTitle("España");
    }
```
### Posición inicial de la ventana
A partir del programa anterior:
Añadimos al constructor el método **setLocation(x,y)** donde x e y son numeros enteros con funcion de coordenadas.
```java
public Ventana(){
        setSize(500,500); //(ancho,alto)
        setLocation(50,50);  //(x,y)
    }
```
### Para indicar el tamaño de la ventana y las coordenadas donde aparece esta a la vez podemos usar el método **setBounds(x,y,ancho,largo)** directamente.
```java
public Ventana(){
        //setSize(500,500); //(ancho,alto)
        //setLocation(50,50);  //(x,y)
        setBounds(50,50,500,500);  //(x,y,ancho,largo)
    }
```
### Para que te salga en el centro de cualquier pantalla(monitor) usamos el método **setLocationRelativeTo(null);**
```java
  public Ventana(){
        setBounds(50,50,500,500);  //(x,y,ancho,largo)
        setLocationRelativeTo(null);  //centrado
    }
```
### Para establecer si una ventana puede cambiar de tamaño o no usamos el método **setResizable(false);**
```java
  public Ventana(){
        setBounds(50,50,500,500);  //(x,y,ancho,largo)
        setLocationRelativeTo(null);  //centrado
        setResizable(false);  //no puede cambiar (true) ->si puede cambiar (-)
    }
```
### Para establecer el tamaño mínimo importaremos la libreria **import java.awt.Dimension;** y usaremos el método **setMinimumSize(new Dimension(x,y);** donde los valores de x e y seran enteros que
  indiquen las coordenadas.
```java
  public Ventana(){
        setBounds(50,50,500,500);  //(x,y,ancho,largo)
        setLocationRelativeTo(null);  //centrado
        setResizable(false);  //no puede cambiar (true) ->si puede cambiar (-)
        setMinimumSize(new Dimension(30,30)); //nueva dimension
    }
```
### Para establecer un color al fondo de la ventana importaremos la libreria **import java.awt.Color;** y usaremos el método **this.getContentPane().setBackground(Color.BLUE);**
en este caso en color azul
```java
  public Ventana(){
        setBounds(50,50,500,500);  //(x,y,ancho,largo)
        setLocationRelativeTo(null);  //centrado
        setResizable(false);  //no puede cambiar (true) ->si puede cambiar (-)
        setMinimumSize(new Dimension(30,30)); //nueva dimension minima
        this.getContentPane().setBackground(Color.BLUE);  //colorear de azul
    }
```

  
