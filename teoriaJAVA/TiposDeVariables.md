# Variables primitivas y no primitivas
## Variables primitivas
```java
public class ClaseMain {
    public static void main(String[] args) {
        int entero = 11;
        float decimal = 11.5f;
        char caracter = 'a';
        boolean decision = true;
        
    }
}
```
## Varaibles no primitivas
```java
public class ClaseMain {
    public static void main(String[] args) {
        Integer numero1 = 10;
        Integer numero2 = null;
        String cadena = "Programacion Avanzada";
        
        //Constantes
        final int numero = 23;
        numero = 11;  //->Error porque es constante
        
    }
}
```
## Constantes: final
Al colocar "final" estamos indicando que el valor de esa variable no va a cambiar a lo largo del programa.
Siempre va a valer lo mismo.
No te permite crear un encapsulamiento set dado que no cambia.
```java
public class Persona{
    private final String nombre;
    private int edad;

    //Metodos
```
## Miembros estáticos de una clase: static
La clase donde se encuentra el atributo estático es el único dueño de este.

