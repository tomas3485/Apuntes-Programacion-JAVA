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
Al colocar `final` estamos indicando que el valor de esa variable no va a cambiar a lo largo del programa.
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

## Variable string -> Variable int
El método *Integer.parseInt(String cadena)* en Java es utilizado para convertir una cadena de texto (string) que contiene una representación numérica en un número entero de tipo *int*. Es parte de la clase *Integer* y es útil cuando tienes una entrada de texto que representa un número y necesitas convertirlo para poder realizar operaciones aritméticas u otras manipulaciones numéricas.

Ejemplo:
```java
String numeroEnTexto = "42";
int numero = Integer.parseInt(numeroEnTexto);
System.out.println("El número es: " + numero); // Salida: El número es: 42
```

Si no sabemos si la cadena de texto es valida como contenido de una variable de tipo int, podemos usar lo siguiente:
```java
try {
// Convertir la entrada a número y agregarla a la lista
int numero = Integer.parseInt(entrada);
numeros.add(numero);

} catch (NumberFormatException e) {
System.out.println("Por favor, introduce un número válido o 'x' para salir.");
}
```
