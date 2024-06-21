# Paneles - JPanel
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
