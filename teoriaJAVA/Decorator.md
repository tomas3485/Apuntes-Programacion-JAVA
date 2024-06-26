# Decorator
Permite añadir funcionalidades a un objeto de manera dinámica. Este patrón se usa para envolver objetos de tal forma que se puedan agregar
responsabilidades adicionales sin modificar el código original de la clase.
## Ejemplo
Vamos a implementar un ejemplo sencillo donde tenemos una interfaz **Shape** que representa una forma geométrica. Implementaremos una clase **Circle** que representa un círculo.
Luego, crearemos decoradores que añaden funcionalidades adicionales, como el color.
1. Crear la interfaz **Shape**
```java
public interface Shape {
    void draw();
}
```
2. Implementar la clase **Circle** que implementa **Shape**
```java
public class Circle implements Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a Circle");
    }
}
```
3. Crear la clase abstracta **ShapeDecorator** que también implementa **Shape** y contiene una referencia a un **Shape**
```java
public abstract class ShapeDecorator implements Shape {
    protected Shape decoratedShape;

    public ShapeDecorator(Shape decoratedShape) {
        this.decoratedShape = decoratedShape;
    }

    @Override
    public void draw() {
        decoratedShape.draw();
    }
}
```
4. Implementar un decorador concreto que añade funcionalidad (Color)
```java
public class RedShapeDecorator extends ShapeDecorator {

    public RedShapeDecorator(Shape decoratedShape) {
        super(decoratedShape);
    }

    @Override
    public void draw() {
        decoratedShape.draw();
        setRedBorder(decoratedShape);
    }

    private void setRedBorder(Shape decoratedShape) {
        System.out.println("Border Color: Red");
    }
}
```
5. Usar el decorador
Ahora, veamos cómo usar el decorador para agregar funcionalidad adicional a los objetos **Circle**:
```java
public class DecoratorPatternDemo {
    public static void main(String[] args) {
        Shape circle = new Circle();

        Shape redCircle = new RedShapeDecorator(new Circle());

        System.out.println("Circle with normal border");
        circle.draw();

        System.out.println("\nCircle with red border");
        redCircle.draw();
    }
}
```
### Explicación de programa
En este ejemplo, hemos utilizado el patrón Decorator para agregar una funcionalidad adicional (color del borde) a un objeto Circle sin modificar la clase Circle original.
La clase RedShapeDecorator es responsable de agregar esta funcionalidad adicional. Puedes seguir creando más decoradores concretos para agregar otras funcionalidades según
sea necesario, manteniendo el diseño flexible y extensible.
