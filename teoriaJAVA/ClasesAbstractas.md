# Clases Abstractas
Es una clase que no se puede instanciar directamente. Se utiliza como una plantilla para que otras clases la hereden y completen su implementación.
- Se utilizan sólo como superclases.
- No se pueden instanciar objetos.
- Sirve para proporcionar una super clase apropiada a partir de la cual heredan otras clases.
## Características de las Clases Abstractas:
- Declaración: Se declara con la palabra clave abstract.
```java
public abstract class Animal {
    public abstract void hacerSonido();
}
```
- Métodos Abstractos: Puede contener métodos abstractos, que son métodos sin implementación. Las subclases deben implementar estos métodos.
```java
public abstract void hacerSonido(); // Método abstracto
```
- Métodos Concretos: Puede también contener métodos con implementación (métodos concretos) que pueden ser utilizados por las subclases.
```java
public void dormir() {
    System.out.println("El animal está durmiendo");
}
```
- Herencia: Las subclases que heredan de una clase abstracta deben proporcionar implementaciones para todos los métodos abstractos de la clase padre.
```java
public class Perro extends Animal {
    @Override
    public void hacerSonido() {
        System.out.println("El perro ladra");
    }
}
```
## Ejemplo práctico
- Clase Abstracta (Animal):
```java
public abstract class Animal {
    public abstract void hacerSonido(); // Método abstracto

    public void dormir() { // Método concreto
        System.out.println("El animal está durmiendo");
    }
}
```
- Clase Concreta (Perro):
```java
public class Perro extends Animal {
    @Override
    public void hacerSonido() {
        System.out.println("El perro ladra");
    }
}
```
- Uso en un programa(Main):
```java
public class Main {
    public static void main(String[] args) {
        Perro miPerro = new Perro();
        miPerro.hacerSonido(); // Salida: El perro ladra
        miPerro.dormir();      // Salida: El animal está durmiendo
    }
}
```
En este ejemplo, la clase **Animal** es **abstracta** y contiene un método **abstracto hacerSonido()** y un método **concreto dormir()**.
La clase **Perro** extiende **Animal** e implementa el método **abstracto hacerSonido()**. No es posible crear una instancia(objeto) de **Animal** directamente,
pero sí de **Perro**, que hereda de **Animal** y proporciona la implementación necesaria.


