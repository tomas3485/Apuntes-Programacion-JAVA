# Serialización
La serialización de objetos en Java es el proceso de convertir un objeto en una secuencia de bytes, de manera que pueda ser almacenado en un archivo,
transmitido a través de una red, o guardado en una base de datos. La deserialización es el proceso inverso, es decir, convertir la secuencia de bytes de vuelta en un objeto.

Para que un objeto sea serializable en Java, la clase del objeto debe implementar la interfaz **java.io.Serializable**. Esta interfaz es un marcador, lo que significa que no
contiene métodos que deban ser implementados; simplemente sirve para indicar al compilador que la clase puede ser serializada.
## Ejemplo de serialización en Java
Supongamos que tenemos una clase **Persona** que queremos serializar:
```java
import java.io.Serializable;

public class Persona implements Serializable {
    private static final long serialVersionUID = 1L;
    
    private String nombre;
    private int edad;

    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    @Override
    public String toString() {
        return "Persona [nombre=" + nombre + ", edad=" + edad + "]";
    }
}
```
La clase **Persona** implementa **Serializable** y tiene un campo **serialVersionUID**. Este campo es utilizado para verificar la compatibilidad entre el objeto serializado y la clase.
### Serialización de un Objeto
Para serializar un objeto, se utiliza **ObjectOutputStream**. Aquí hay un ejemplo:
```java
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.ObjectOutputStream;

public class SerializacionEjemplo {
    public static void main(String[] args) {
        Persona persona = new Persona("Juan", 30);

        try (FileOutputStream fileOut = new FileOutputStream("persona.ser");
             ObjectOutputStream out = new ObjectOutputStream(fileOut)) {
            out.writeObject(persona);
            System.out.println("Objeto serializado y guardado en persona.ser");
        } catch (IOException i) {
            i.printStackTrace();
        }
    }
}
```
En este ejemplo, el objeto **persona** se serializa y se guarda en un archivo llamado **persona.ser**.
### Deserialización de un Objeto
Para deserializar un objeto, se utiliza **ObjectInputStream**. Aquí hay un ejemplo:
```java
import java.io.FileInputStream;
import java.io.IOException;
import java.io.ObjectInputStream;

public class DeserializacionEjemplo {
    public static void main(String[] args) {
        Persona persona = null;

        try (FileInputStream fileIn = new FileInputStream("persona.ser");
             ObjectInputStream in = new ObjectInputStream(fileIn)) {
            persona = (Persona) in.readObject();
            System.out.println("Objeto deserializado: " + persona);
        } catch (IOException | ClassNotFoundException i) {
            i.printStackTrace();
        }
    }
}
```
En este ejemplo, el objeto **persona** se deserializa desde el archivo **persona.ser** y se imprime en la consola.
## Consideraciones importantes
- **Compatibilidad de versión**: Si la clase de un objeto cambia (por ejemplo, se añade un nuevo campo), es posible que los objetos serializados anteriormente
  no se puedan deserializar correctamente. Usar **serialVersionUID** ayuda a controlar la compatibilidad entre versiones.
- **Transitoriedad**: Si un campo no debe ser serializado, se puede marcar como **transient**. Por ejemplo:
```java
private transient int edad;
```
  Este campo no será parte de la serialización y deserialización.
- **Seguridad**: La serialización puede ser un vector de ataque si se deserializan objetos de fuentes no confiables. Es importante validar o filtrar los objetos deserializados.


