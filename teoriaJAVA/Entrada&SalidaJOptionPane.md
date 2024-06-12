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
![MensajeEntradaInt](https://github.com/DanielBraun11/ApuntesProgramacionJAVA/blob/main/fotosJAVA/JOPint1.png)   ![MensajeSalidaInt](https://github.com/DanielBraun11/ApuntesProgramacionJAVA/blob/main/fotosJAVA/JOPint2.png) 

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
![MensajeEntrada](https://github.com/DanielBraun11/ApuntesProgramacionJAVA/blob/main/fotosJAVA/JOPfloat1.png)   ![MensajeSalida](https://github.com/DanielBraun11/ApuntesProgramacionJAVA/blob/main/fotosJAVA/JOPfloat2.png) 

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
![MensajeEntrada](https://github.com/DanielBraun11/ApuntesProgramacionJAVA/blob/main/fotosJAVA/JOPdouble1.png)   ![MensajeSalida](https://github.com/DanielBraun11/ApuntesProgramacionJAVA/blob/main/fotosJAVA/JOPdouble2.png) 

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
![MensajeEntrada](https://github.com/DanielBraun11/ApuntesProgramacionJAVA/blob/main/fotosJAVA/JOPchar1.png)  ![MensajeSalida](https://github.com/DanielBraun11/ApuntesProgramacionJAVA/blob/main/fotosJAVA/JOPchar2.png)

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
![MensajeEntrada](https://github.com/DanielBraun11/ApuntesProgramacionJAVA/blob/main/fotosJAVA/JOPstring1.png)   ![MensajeSalida](https://github.com/DanielBraun11/ApuntesProgramacionJAVA/blob/main/fotosJAVA/JOPstring2.png) 

