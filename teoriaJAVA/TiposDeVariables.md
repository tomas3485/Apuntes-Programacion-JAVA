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
```java
public class Persona{
    private String nombre = "Daniel";

    public static void main(String[] args) {
        Persona persona1 = new Persona();
        System.out.println(persona1.frase);  //->Daniel

        Persona persona2 = new Persona();
        persona2.frase = "Frase 2";
        System.out.println(persona2.frase);  //->Diego
    }
}
```
Cuando creo un objeto, este copia toda la informacion que tengan los atributos de su misma clase(Si es que hay alguno inicializado con datos "reales"). Si luego cambio esta información como pasa en el ejemplo anterior con el objeto persona2 de la clase Persona se guarda la nueva información("Diego").
Si comento en el ejemplo anterior la inicialización nueva del atributo nombre del objeto persona2:
```java
public class Persona{
    private String nombre = "Daniel";

    public static void main(String[] args) {
        Persona persona1 = new Persona();
        System.out.println(persona1.frase);  //->Daniel

        Persona persona2 = new Persona();
        //persona2.frase = "Diego";
        System.out.println(persona2.frase);  //->Diego (NO) Ahora ->Daniel
    }
}
```
Sin embargo, si hacemos este miembro(atributo) estatico:
```java
private static String nombre = "Daniel";
```
El miembro pasa a ser propiedad de la clase. Por esto, no hace falta crear un objeto para acceder a esta información sino que podemos acceder de la siguiente forma:
```java
System.out.println(Persona.nombre); //->Daniel   sout(nombre_clase.nombre_atrib_static)
```
Los métodos también pueden ser estáticos:
```java
public class Persona{
    public static int suma(int a, int b){
        int suma = a + b;

        return suma;
    }

    public static void main(String[] args) {
        System.out.println("La suma entre 2 y 4 da: " + suma(2,4)); //->La suma entre 2 y 4 da: 6
    }
}
```

