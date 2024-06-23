# Factory Method
El patrón Factory Method define una interfaz para crear un objeto, pero deja que las subclases decidan qué clase instanciar.
### ejemplo:
```java
// Interfaz Producto
interface Product {
    void use();
}

// Implementación concreta del Producto A
class ProductA implements Product {
    public void use() {
        System.out.println("Usando el Producto A");
    }
}

// Implementación concreta del Producto B
class ProductB implements Product {
    public void use() {
        System.out.println("Usando el Producto B");
    }
}

// Clase fábrica que crea productos
class ProductFactory {
    public Product createProduct(String type) {
        if (type.equals("A")) {
            return new ProductA();
        } else if (type.equals("B")) {
            return new ProductB();
        }
        return null;
    }
}

public class FactoryMethodDemo {
    public static void main(String[] args) {
        ProductFactory factory = new ProductFactory();

        // Crear productos usando la fábrica
        Product productA = factory.createProduct("A");
        Product productB = factory.createProduct("B");

        // Usar los productos
        productA.use();
        productB.use();
    }
}
```
