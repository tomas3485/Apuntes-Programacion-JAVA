# IOException
Las excepciones **IOException** y sus subclases son excepciones verificadas en Java que deben ser manejadas explícitamente en el código.
Estas excepciones suelen estar relacionadas con problemas de entrada y salida (I/O) al interactuar con archivos, streams, redes, etc.

La **IOException** es la clase base para excepciones que pueden ocurrir durante operaciones de entrada y salida. Esta clase representa errores genéricos de E/S
que pueden surgir debido a diversas razones, como problemas de conexión, errores de permisos, o fallos en dispositivos de almacenamiento.
```java
import java.io.IOException;
import java.io.FileReader;

public class IOExceptionExample {
    public static void main(String[] args) {
        try {
            FileReader fileReader = new FileReader("archivo.txt");
            // Operaciones de lectura de archivo
        } catch (IOException e) {
            System.out.println("Se ha lanzado IOException: " + e.getMessage());
        }
    }
}
```
En este ejemplo, intentamos abrir un archivo **"archivo.txt"** para lectura. Si ocurre algún error de E/S durante esta operación, se lanzará una **IOException**.

## EOFException
La **EOFException** (End Of File Exception) se lanza cuando se intenta leer más datos de un flujo de entrada (como un **FileInputStream** o un **ObjectInputStream**) de los que realmente están disponibles.
Esto generalmente ocurre cuando se alcanza prematuramente el final de un archivo.
```java
import java.io.*;

public class EOFExceptionExample {
    public static void main(String[] args) {
        try {
            FileInputStream fileInputStream = new FileInputStream("archivo.bin");
            ObjectInputStream objectInputStream = new ObjectInputStream(fileInputStream);

            Object obj = objectInputStream.readObject();
            // Operaciones con el objeto leído

            objectInputStream.close();
        } catch (EOFException e) {
            System.out.println("Se ha lanzado EOFException: " + e.getMessage());
        } catch (IOException | ClassNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```
En este ejemplo, estamos intentando leer un objeto desde un archivo binario (**"archivo.bin"**). Si alcanzamos el final del archivo mientras estamos leyendo datos, se lanzará una **EOFException**.

## FileNotFoundException
La **FileNotFoundException** se lanza cuando intentas acceder a un archivo que no existe en el sistema de archivos.
```java
import java.io.*;

public class FileNotFoundExceptionExample {
    public static void main(String[] args) {
        try {
            FileReader fileReader = new FileReader("archivo_que_no_existe.txt");
        } catch (FileNotFoundException e) {
            System.out.println("Se ha lanzado FileNotFoundException: " + e.getMessage());
        }
    }
}
```
En este ejemplo, tratamos de abrir el archivo **"archivo_que_no_existe.txt"** para lectura. Como el archivo no existe, se lanzará una **FileNotFoundException**.

## InterruptedIOException
La **InterruptedIOException** se lanza cuando una operación de E/S es interrumpida, generalmente debido a que otro hilo ha interrumpido el hilo actual que está realizando la operación de E/S.
```java
import java.io.*;

public class InterruptedIOExceptionExample {
    public static void main(String[] args) {
        try {
            FileReader fileReader = new FileReader("archivo.txt");
            // Operaciones de lectura de archivo
        } catch (InterruptedIOException e) {
            System.out.println("Se ha lanzado InterruptedIOException: " + e.getMessage());
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```
En este ejemplo, estamos leyendo un archivo **"archivo.txt"**. Si otro hilo interrumpe el hilo actual durante la operación de lectura, se lanzará una **InterruptedIOException**.

### Manejo de Excepciones en Java
Para todas las excepciones mencionadas (IOException y sus subclases), es necesario manejarlas utilizando bloques try-catch o declarándolas en la firma del método (throws).
Esto ayuda a asegurar que cualquier problema de E/S sea manejado correctamente, proporcionando mensajes de error significativos o realizando acciones de recuperación adecuadas.

Es importante considerar la gestión de excepciones de E/S como parte integral de cualquier aplicación Java que interactúe con archivos, streams o conexiones de red,
ya que estos pueden ser puntos críticos de fallo en el programa si no se manejan adecuadamente.
