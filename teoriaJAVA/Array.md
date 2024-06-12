# Array
Un array es un tipo de dato contenedor que permite almacenar múltiples valores en una sola estructura. Estos valores están organizados
en una secuencia y pueden ser de cualquier tipo de datos, como números enteros, float o cadenas de texto. A los elementos de un array se acceden
mediante un índice, que indica su posición en la secuencia, empezando siempre desde el 0.

![Texto alternativo](https://i0.wp.com/somoshackersdelaprogramacion.es/wp-content/uploads/2022/05/arrays01.jpg?resize=500%2C189&ssl=1)

Si inicializas un array con datos, no es necesario poner el tamaño de este ya que se entiende que el tamaño es el numero de elementos que añades
en la inicialización.
```java
public class Ejemplo {
    public static void main(String[] args) {
       //Tipo_de_Variable[] nombre = new Tipo_de_Variable[tamaño]
        int[] numeros = new int[3];
        boolean[] estado = new boolean[5];
        String[] nombres = {"Daniel", "Marcos", "Diego"};

        //Accediendo a las posiciones
        System.out.println(nombres[1]);  //->Marcos
    }
}
```
