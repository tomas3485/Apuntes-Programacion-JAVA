# Paneles - JPanel
**IMPORTANTE** los ejemplos de este apartado estan relacionado con las Ventanas(JFrame) de los apuntes anteriores.

Creación de paneles sobre las ventanas. Es como si la ventana fuera una mesa y los paneles los manteles.
Se puede realizar en el constructor o en otro método.
Hay que importar su libreria **import javax.swing.JPanel;**
- Clase Panel
```java
`import javax.swing.JPanel;
public class Panel extends JPanel{

}
```
- Main

Creamos un objeto de la clase Panel en el main
```java
public class Main{
    public static void main(String[] args) {
        Ventana v1 = new Ventana();
        v1.setVisible(true);

        Panel p1 = new Panel();  //Creacion del panel p1
    }
}
```
### Para poner el panel en una ventana usaremos el metodo en el main junto con la ventana a la que lo añado
```java
public class Main{
    public static void main(String[] args) {
        Ventana v1 = new Ventana();  //creamos la ventana
        v1.setVisible(true);

        Panel p1 = new Panel();  //creamos el panel

        v1.getContentPane().add(p1);  //añadimos el panel a la ventana v1
    }
}
```
Inicialmente al igual que las ventanas, se verá invisible. En el ejemplo anteror de las ventanas dejamos la ventana v1 con un fondo azul. Ahora que hemos añadido el panel p1, el fondo vuelve a ser blanco(que es lo que entendemos por fondo invisible inicialmente)
Si ahora cambiamos el color al panel, podemos hacerlo o bien en el constructor de la clase o bien usando un método directaente en el main. Por eso, si queremos que todos o casi todos nuestros paneles sean de un color en concreto lo mejor será hacer este cambio de color en el constructor y si queremos hacer cambios puntuales mejor en el main al panel(objeto) en concreto.
- Cambio de color en el constructor
```java
public class Panel extends JPanel{
    public Panel(){
        setBackground(Color.GREEN);  //paneles verdes
    }
}
```
- Cambio de color en el main
```java
public class Main{
    public static void main(String[] args) {
        Ventana v1 = new Ventana();
        v1.setVisible(true);

        Panel p1 = new Panel();

        v1.getContentPane().add(p1);
        p1.setBackground(Color.gray);  //panel p1 gris
    }
}
```
Ahora que tenemos nuestro panel sobre la ventana, podemos escribir sobre él y poner botones, imagenes, textos...
También podemos hacer todo esto en la misma ventana sin necesidad de panel pero NO SE RECOMIENDA.



