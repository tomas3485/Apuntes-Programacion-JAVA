# Abstract Factory
Proporciona una interfaz para crear familias de objetos relacionados o dependientes sin especificar sus clases concretas. Es útil cuando se necesita crear conjuntos de objetos
que deben ser utilizados juntos y asegurarse de que se usen objetos compatibles.
### Ejemplo:
Imaginemos que queremos crear familias de animales (Perro y Gato) que hacen sonidos distintos según su tipo (Doméstico o Salvaje).
1. Definir las interfaces de los productos (Perro y Gato)
 ```java
// Interfaz para el producto Perro
interface Dog {
    void speak();
}

// Interfaz para el producto Gato
interface Cat {
    void speak();
}
```
2. Implementar los productos concretos
```java
// Implementación del Perro Doméstico
class DomesticDog implements Dog {
    @Override
    public void speak() {
        System.out.println("Woof! (Soy un perro doméstico)");
    }
}

// Implementación del Perro Salvaje
class WildDog implements Dog {
    @Override
    public void speak() {
        System.out.println("Grrr! (Soy un perro salvaje)");
    }
}

// Implementación del Gato Doméstico
class DomesticCat implements Cat {
    @Override
    public void speak() {
        System.out.println("Meow! (Soy un gato doméstico)");
    }
}

// Implementación del Gato Salvaje
class WildCat implements Cat {
    @Override
    public void speak() {
        System.out.println("Rawr! (Soy un gato salvaje)");
    }
```
3. Definir la fábrica abstracta
```java
// Interfaz para la fábrica abstracta
interface AnimalFactory {
    Dog createDog();
    Cat createCat();
}
```
4. Implementar las fábricas concretas
```java
// Fábrica concreta para Animales Domésticos
class DomesticAnimalFactory implements AnimalFactory {
    @Override
    public Dog createDog() {
        return new DomesticDog();
    }

    @Override
    public Cat createCat() {
        return new DomesticCat();
    }
}

// Fábrica concreta para Animales Salvajes
class WildAnimalFactory implements AnimalFactory {
    @Override
    public Dog createDog() {
        return new WildDog();
    }

    @Override
    public Cat createCat() {
        return new WildCat();
    }
 ```
5. Uso de la fábrica abstracta
```java
public class AbstractFactoryExample {
    public static void main(String[] args) {
        // Crear una fábrica de animales domésticos
        AnimalFactory domesticFactory = new DomesticAnimalFactory();
        Dog domesticDog = domesticFactory.createDog();
        Cat domesticCat = domesticFactory.createCat();
        
        domesticDog.speak();
        domesticCat.speak();
        
        // Crear una fábrica de animales salvajes
        AnimalFactory wildFactory = new WildAnimalFactory();
        Dog wildDog = wildFactory.createDog();
        Cat wildCat = wildFactory.createCat();
        
        wildDog.speak();
        wildCat.speak();
    }
}
```
