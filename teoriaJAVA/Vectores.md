# Vectores - ArrayList
Los vectores en Java, representados por la clase **Vector** en el paquete **java.util**, son una colección que puede crecer o decrecer en tamaño dinámicamente.
Son similares a las listas(arrays) en cuanto a funcionalidad, pero tienen algunas diferencias clave.
## características de los Vectors en Java
1. **Sincronización**: Los vectores en Java son sincronizados, lo que significa que son seguros para su uso en entornos de múltiples hilos. Esto también implica
   que pueden ser más lentos que otras colecciones no sincronizadas como **ArrayList**.
2. **Capacidad**: Internamente, un vector tiene una capacidad que se ajusta automáticamente cuando se agregan más elementos de los que puede contener. Cada vez que se necesita aumentar la capacidad,
   el tamaño del vector se incrementa automáticamente, generalmente duplicando su tamaño actual.
3. **Métodos**: Los vectores tienen varios métodos útiles como **add()**, **remove()**, **size()**, **get()**, entre otros, que facilitan la manipulación de los elementos almacenados.
### Ejemplo de Uso de un Vector en Java
```java
import java.util.Vector;

public class Main {
    public static void main(String[] args) {
        // Crear un vector
        Vector<Integer> vector = new Vector<>();

        // Añadir elementos al vector
        vector.add(10);
        vector.add(20);
        vector.add(30);

        // Acceder a elementos del vector
        System.out.println("Elemento en el índice 1: " + vector.get(1)); // Salida: 20
        System.out.println("Elemento en el índice 1: " + vector[1]); // Salida: 20

        // Remover un elemento
        vector.remove(1);

        // Tamaño del vector
        System.out.println("Tamaño del vector: " + vector.size()); // Salida: 2

        // Recorrer el vector
        for (int i = 0; i < vector.size(); i++) {
            System.out.println("Elemento en el índice " + i + ": " + vector.get(i));
        }
    }
}

```
