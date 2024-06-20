# Herencia
La herencia nos permite crear una nueva clase basada en una clase existente. La nueva clase, llamada subclase o clase hija, hereda propiedades
y métodos de la clase existente, llamada superclase o clase padre.
## ¿Cómo funciona la herencia en Java?
### Superclase (Clase Padre)
Es la clase de la que se heredan propiedades y comportamientos.
```java
public class Animal {
    public void hacerSonido() {
        System.out.println("El animal hace un sonido");
    }
}
```
### Subclase (Clase Hija)
Es la clase que hereda de la superclase. Puede usar los métodos y propiedades de la superclase, y también puede tener sus propios métodos y propiedades.
```java
public class Perro extends Animal {
    public void hacerSonido() {
        System.out.println("El perro ladra");
    }
}
```
## Beneficios de la herencia
- Reutilización de código: Permite reutilizar el código de la superclase en las subclases, lo que reduce la duplicación y facilita el mantenimiento.
- Extensibilidad: Las subclases pueden añadir nuevas funcionalidades o modificar las existentes, haciendo que el código sea más flexible y adaptable.
- Organización jerárquica: Facilita la organización del código en una estructura lógica y jerárquica, reflejando relaciones naturales entre los objetos.
## Ejemplo práctico
- Superclase (Animal):
```java
public class Animal {
    public void hacerSonido() {
        System.out.println("El animal hace un sonido");
    }
}
```
- Subclase (Perro):
```java
public class Perro extends Animal {
    @Override
    public void hacerSonido() {
        System.out.println("El perro ladra");
    }
}
```
- Uso en un programa:
```java
public class Main {
    public static void main(String[] args) {
        Animal miAnimal = new Animal();
        miAnimal.hacerSonido(); // Salida: El animal hace un sonido

        Perro miPerro = new Perro();
        miPerro.hacerSonido(); // Salida: El perro ladra
    }
}
```
En este ejemplo, la clase Perro hereda de Animal, lo que significa que Perro tiene todos los métodos y propiedades de Animal, pero también puede tener sus propios métodos y propiedades.
Además, Perro puede sobrescribir los métodos de Animal para proporcionar su propia implementación
## Sobre escritura de miembros
Se denomina escritura de métodos cuando en clases hijas usamos un método heredado de la clase padre pero lo modificamos en su interior.
Lo observamos en el ejemplo anterior en la subclase Perro en el método hacerSonido y lo indica el @Override que aparecera automaticamente cuando la clase hereda de otra y tiene una *sobre escritura* de la que hereda.
