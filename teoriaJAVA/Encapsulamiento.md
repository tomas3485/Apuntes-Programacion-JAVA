# Encapsulamiento
Consiste en ocultar los detalles internos de los objetos y exponer solo lo necesario a través de interfaces controladas.
Este principio mejora la modularidad, facilita el mantenimiento y la protección de los datos dentro de un objeto.
## Getters
Son métodos públicos que permiten acceder al valor de una propiedad privada o protegida desde fuera de la clase.
Su principal función es proporcionar un acceso controlado a los datos.
```java
public class Persona {
    String nombre;

    // Getter
    public String getNombre() {
        return nombre;
    }
}
```
## Setters
Son métodos públicos que permiten modificar el valor de una propiedad privada o protegida desde fuera de la clase.
Su función es controlar y validar cualquier cambio en los datos.
```java
public class Persona {
    String nombre;

    // Setter
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
}
```
### Ventajas del uso de getters y setters:
- Control de acceso: Permiten restringir el acceso directo a los atributos, asegurando que cualquier interacción con ellos pase por un punto de control.
- Validación: Se pueden incluir validaciones dentro de los setters para asegurar que los datos ingresados cumplen con los criterios establecidos.
- Mantenimiento y flexibilidad: Facilitan la modificación de la implementación interna sin afectar a las clases que usan el objeto. Por ejemplo,
  si se necesita cambiar la manera en que se almacena un dato, solo se modifica el getter y/o setter.
- Encapsulamiento: Refuerzan el principio de encapsulamiento al ocultar los detalles de implementación y exponer solo lo necesario.
