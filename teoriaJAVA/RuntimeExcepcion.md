# RuntimeExcepcion
Son un tipo de excepción en Java que el compilador no obliga a capturar explícitamente.
## ArithmeticException
La **ArithmeticException** se lanza cuando ocurre una operación aritmética inválida. El escenario más común es la división por cero:
```java
public class ArithmeticExceptionExample {
    public static void main(String[] args) {
        try {
            int result = 10 / 0; // Esto lanzará ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("Se ha lanzado ArithmeticException: " + e.getMessage());
        }
    }
}
```
En este ejemplo, intentamos dividir **10** entre **0**, lo cual no está permitido y resulta en una **ArithmeticException**.

## NullPointerException
La **NullPointerException** es una excepción común en Java que ocurre cuando intentas acceder o invocar un método sobre una referencia de objeto que es **null**. 
Por ejemplo:
```java
public class NullPointerExceptionExample {
    public static void main(String[] args) {
        String str = null;
        try {
            int length = str.length(); // Esto lanzará NullPointerException
        } catch (NullPointerException e) {
            System.out.println("Se ha lanzado NullPointerException: " + e.getMessage());
        }
    }
}
```
En este caso, la variable **str** es **null**, por lo tanto, llamar al método **length()** sobre ella lanzará una **NullPointerException**.

## ClassCastException
La **ClassCastException** ocurre cuando intentas convertir (cast) un objeto a un tipo incompatible en tiempo de ejecución.
Por ejemplo:
```java
public class ClassCastExceptionExample {
    public static void main(String[] args) {
        Object obj = new Integer(10);
        try {
            String str = (String) obj; // Esto lanzará ClassCastException
        } catch (ClassCastException e) {
            System.out.println("Se ha lanzado ClassCastException: " + e.getMessage());
        }
    }
}
```
En este caso, estamos intentando convertir un objeto **Integer** a **String** utilizando un cast (**(String) obj**).
Esto lanzará una **ClassCastException** porque un **Integer** no se puede convertir directamente a un **String**.

## IndexOutOfBoundsException
La **IndexOutOfBoundsException** es una excepción base para las excepciones que indican que un índice dado está fuera del rango válido.
Hay dos subclases comunes de **IndexOutOfBoundsException**:
- **ArrayIndexOutOfBoundsException**: Se lanza cuando intentas acceder a un índice fuera del rango válido para un array.
```java
public class ArrayIndexOutOfBoundsExceptionExample {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3};
        try {
            int num = arr[5]; // Esto lanzará ArrayIndexOutOfBoundsException
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Se ha lanzado ArrayIndexOutOfBoundsException: " + e.getMessage());
        }
    }
}
```
En este ejemplo, intentamos acceder al índice 5 en un array que solo tiene tres elementos.
- **StringIndexOutOfBoundsException**: Se lanza cuando intentas acceder a un índice fuera del rango válido para una cadena (String).
```java
public class StringIndexOutOfBoundsExceptionExample {
    public static void main(String[] args) {
        String str = "Hola";
        try {
            char ch = str.charAt(10); // Esto lanzará StringIndexOutOfBoundsException
        } catch (StringIndexOutOfBoundsException e) {
            System.out.println("Se ha lanzado StringIndexOutOfBoundsException: " + e.getMessage());
        }
    }
}
```
En este ejemplo, intentamos obtener el carácter en la posición **10** de la cadena **"Hola"**, que solo tiene 4 caracteres. Esto resultará en una **StringIndexOutOfBoundsException**.

### Manejo de Excepciones en Java
En todos los casos anteriores, hemos utilizado un bloque try-catch para manejar las excepciones. Esto es una buena práctica para capturar y manejar los errores que pueden ocurrir durante la ejecución del programa. Al capturar las excepciones, podemos proporcionar mensajes de error significativos o tomar acciones correctivas para evitar que el programa falle inesperadamente.

Es importante recordar que las excepciones RuntimeException (incluyendo las mencionadas anteriormente) no requieren ser declaradas en la firma del método o manejadas explícitamente por el código. Sin embargo, capturar estas excepciones mejora la robustez y la fiabilidad del programa, haciendo que sea más fácil de mantener y depurar.
