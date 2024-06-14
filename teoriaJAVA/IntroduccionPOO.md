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
