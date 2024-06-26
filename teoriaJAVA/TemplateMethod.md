# Template Method
Define el esqueleto de un algoritmo en una clase base, permitiendo que las subclases concreten o redefinan ciertos pasos del algoritmo sin cambiar su estructura global.
## Ejemplo en Java
Ejemplo donde tenemos un proceso de preparación de una bebida. La clase base **Bebida** define el método plantilla **preparar**, mientras que las subclases **Cafe** y **Te** implementan
los pasos específicos de la preparación.
1. Crear la clase abstracta **Bebida**
```java
public abstract class Bebida {
    // Método plantilla
    public final void preparar() {
        hervirAgua();
        agregarPrincipal();
        verterEnTaza();
        agregarCondimentos();
    }

    // Métodos que serán implementados por las subclases
    abstract void agregarPrincipal();
    abstract void agregarCondimentos();

    // Método común
    private void hervirAgua() {
        System.out.println("Hirviendo agua.");
    }

    // Método común
    private void verterEnTaza() {
        System.out.println("Vertiendo en taza.");
    }
}
```
2. Implementar las subclases **Cafe** y **Te**
```java
public class Cafe extends Bebida {
    @Override
    void agregarPrincipal() {
        System.out.println("Agregando café.");
    }

    @Override
    void agregarCondimentos() {
        System.out.println("Agregando azúcar y leche.");
    }
}

public class Te extends Bebida {
    @Override
    void agregarPrincipal() {
        System.out.println("Agregando té.");
    }

    @Override
    void agregarCondimentos() {
        System.out.println("Agregando limón.");
    }
}
```
3. Probar el patrón Template Method
```java
public class MetodoPlantillaDemo {
    public static void main(String[] args) {
        Bebida cafe = new Cafe();
        Bebida te = new Te();

        System.out.println("Preparando café:");
        cafe.preparar();

        System.out.println("\nPreparando té:");
        te.preparar();
    }
}
```
Salida.
```java
Preparando café:
Hirviendo agua.
Agregando café.
Vertiendo en taza.
Agregando azúcar y leche.

Preparando té:
Hirviendo agua.
Agregando té.
Vertiendo en taza.
Agregando limón.
```
### Explicación del programa
En este ejemplo, la clase **Bebida** define el método plantilla **preparar**, que es el esqueleto del algoritmo para preparar una bebida. Los pasos específicos del algoritmo,
como **agregarPrincipal** y **agregarCondimentos**, son implementados por las subclases **Cafe** y **Te**. Esto permite reutilizar el código común y solo cambiar las partes específicas en las subclases.
