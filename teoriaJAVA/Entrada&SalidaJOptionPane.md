# Entrada y salida de datos con JOptionPane
Es una forma de solicitar los datos que consiste en una pequeña interfaz que remplaza a la terminal por la que añadiriamos los datos a nuestro programa.
Para usar JOptionPane debemos importar su libreria **javax.swing.JOptionPane**

### int
```java
import javax.swing.JOptionPane;

public class Ejemplo {
    public static void main(String[] args) {
        int entero;

        //Entrada
        entero = Integer.parseInt(JOptionPane.showInputDialog("Introduce un numero entero: ")); //Solicitud y captura

        //Salida
        JOptionPane.showMessageDialog(null, "Entero: " + entero);
    }
}
```

### float
```java
import javax.swing.JOptionPane;

public class Ejemplo {
    public static void main(String[] args) {
        float decimal;

        //Entrada
        decimal = Float.parseFloat(JOptionPane.showInputDialog("Introduce un numero float: ")); //Solicitud y captura

        //Salida
        JOptionPane.showMessageDialog(null, "Decimal: " + decimal);
    }
}
```

### double
```java
import javax.swing.JOptionPane;

public class Ejemplo {
    public static void main(String[] args) {
        double decimalPlus;

        //Entrada
        decimalPlus = Double.parseDouble(JOptionPane.showInputDialog("Introduce un numero double: ")); //Solicitud y captura

        //Salida
        JOptionPane.showMessageDialog(null, "Decimal: " + decimalPlus);
    }
}
```

### char
```java
import javax.swing.JOptionPane;

public class Ejemplo {
    public static void main(String[] args) {
        char caracter;

        //Entrada
        caracter = JOptionPane.showInputDialog("Introduce un caracter: ").charAt(0); //Solicitud y captura

        //Salida
        JOptionPane.showMessageDialog(null, "Caracter: " + caracter);
    }
}
```

### string
```java
import javax.swing.JOptionPane;

public class Ejemplo {
    public static void main(String[] args) {
        String texto;

        //Entrada
        texto = JOptionPane.showInputDialog("Introduce un texto: "); //Solicitud y captura

        //Salida
        JOptionPane.showMessageDialog(null, "Texto: " + texto);
    }
}
```
