# Observer
Define una dependencia uno a muchos entre objetos, de manera que cuando un objeto cambia su estado, todos sus dependientes son notificados y actualizados automáticamente.
Este patrón es muy útil para implementar mecanismos de eventos o notificaciones.
## Ejemplo en Java
Implementar un ejemplo donde un objeto **Revista** notifica a sus **Suscriptores** cuando hay una nueva edición disponible.
1. Crear la interfaz **Observador**
```java
public interface Observador {
    void actualizar(String edicion);
}
```
2. Crear la clase **Sujeto**
```java
import java.util.ArrayList;
import java.util.List;

public class Sujeto {
    private List<Observador> observadores = new ArrayList<>();
    private String edicion;

    public void agregarObservador(Observador observador) {
        observadores.add(observador);
    }

    public void eliminarObservador(Observador observador) {
        observadores.remove(observador);
    }

    public void notificarObservadores() {
        for (Observador observador : observadores) {
            observador.actualizar(edicion);
        }
    }

    public void nuevaEdicion(String edicion) {
        this.edicion = edicion;
        notificarObservadores();
    }
}
```
3. Implementar los observadores concretos
```java
public class Suscriptor implements Observador {
    private String nombre;

    public Suscriptor(String nombre) {
        this.nombre = nombre;
    }

    @Override
    public void actualizar(String edicion) {
        System.out.println("Hola " + nombre + ", la nueva edición de la revista es: " + edicion);
    }
}
```
4. Probar el patrón Observer
```java
public class ObservadorPatronDemo {
    public static void main(String[] args) {
        Sujeto revista = new Sujeto();

        Suscriptor suscriptor1 = new Suscriptor("Juan");
        Suscriptor suscriptor2 = new Suscriptor("Maria");
        Suscriptor suscriptor3 = new Suscriptor("Pedro");

        revista.agregarObservador(suscriptor1);
        revista.agregarObservador(suscriptor2);
        revista.agregarObservador(suscriptor3);

        revista.nuevaEdicion("Edición 1");

        revista.eliminarObservador(suscriptor2);

        revista.nuevaEdicion("Edición 2");
    }
}
```
Salida.
```java
Hola Juan, la nueva edición de la revista es: Edición 1
Hola Maria, la nueva edición de la revista es: Edición 1
Hola Pedro, la nueva edición de la revista es: Edición 1

Hola Juan, la nueva edición de la revista es: Edición 2
Hola Pedro, la nueva edición de la revista es: Edición 2
```
### Explicación del programa
En este ejemplo, **Sujeto** (la revista) mantiene una lista de **Observadores** (los suscriptores) y los notifica cuando hay una nueva edición disponible.
Cada **Suscriptor** implementa la interfaz **Observador** y se actualiza cuando el **Sujeto** publica una nueva edición. Esto permite que los suscriptores 
reciban notificaciones automáticamente sin que la revista necesite conocer detalles específicos de cada suscriptor.
