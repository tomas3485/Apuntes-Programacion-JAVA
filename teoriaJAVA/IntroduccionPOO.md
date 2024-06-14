# Introducción
## Objetos
Un objeto es todo aquello que tenga atributos(características) y métodos(acciones). Dicho de forma más formal, un objeto combina
datos y comportamiento, encapsulándolos dentro de una estructura definida por una clase, permitiendo así una representación y
manipulación más modular y organizada en el desarrollo de software.
## Clases
Una clase actúa como un molde que especifica la estructura y las acciones posibles de los objetos, permitiendo la creación de múltiples
instancias (objetos) que comparten la misma configuración básica definida por la clase.
### Creación de clase
```java
public class Coche {
    
}
```
### Creación de objeto de la clase anterior
```java
public class Main {
    public static void main(String[] args) {
        Coche coche1 = new Coche();
        Coche coche2 = new Coche();
    }
}
```
### Creación de métodos
Los metodos se hacen en el interior de la clase. Su estructura es simple:

(modificador de acceso) (valor de retorno) (nombreMetodo)("posibles parametros que recibe este metodo"){}
```java
public class Coche {

    //Metodo 1
    public void metodo1(){
        
    }
}
```
## Ejemplo de clase
```java
public class Coche {
    //Atributos
    String color;
    String marca;
    int km;
    
    //Metodos
    public static void main(String[] args) {
        Coche coche1 = new Coche();
        
        coche1.color = "Negro";
        coche1.marca = "Toyota";
        coche1.km = 57000;
    }
    
}
```
### Métodos: Parámetros y argumentos
**Parámetro**: es una declaración de variable u objeto
**Argumento**: es un valor que se envía
Los parámetros los ponemos en la declaración del método
```java
public void metodo(int num, String cadena){
        
    }
```
Los argumentos los ponemos en la invocación del método.
```java
coche1.metodo(1,"Ford");
```
### Métodos: Retorno de valores
```java
public class Operacion {
    public int suma(int a, int b){
        int suma = a + b;
        return suma;
    }

    public static void main(String[] args) {
        Operacion op1 = new Operacion();

        int suma = op1.suma(10,5);
        System.out.println("La suma es: " + suma);
    }
}
```
