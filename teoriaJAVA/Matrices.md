# Matrices
Para hacer matrices en programación usamos arrays bidimensionales.
## Matriz con tamaño definido (3x3)
```java
public class Ejemplo {
    public static void main(String[] args) {
        int [][] matrizEnteros = {{1,2,3},{4,5,6},{7,8,9}};

        //Mostrar el contenido de la matriz
        for(int i = 0 ; i < matrizEnteros.length ; i++){            //    1 2 3
            for(int j = 0 ; j < matrizEnteros[i].length ; j++){     //->  4 5 6
                System.out.print(matrizEnteros[i][j]);              //    7 8 9
            }
            System.out.println(" ");
        }
    }
}
```
## Matriz sin conocer la dimensión
```java
import java.util.Scanner;

public class Ejemplo {
    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);
        int nFilas = 4;
        int nColumnas = 3;

        int[][] matrizEnteros = new int[nFilas][nColumnas];

        //Inicilaizar el contenido de la matriz
        for(int i = 0 ; i < matrizEnteros.length ; i++){
            for(int j = 0 ; j < matrizEnteros[i].length ; j++){
                System.out.println("Numero en la posicion fila [" + i + "] columna [" + j + "]: ");
                matrizEnteros[i][j] = entrada.nextInt();
            }
        }

        //Mostrar contenido de la matriz
        for(int i = 0 ; i < matrizEnteros.length ; i++){
            for(int j = 0 ; j < matrizEnteros[i].length ; j++){
                System.out.print(matrizEnteros[i][j]);
            }
            System.out.println(" ");
        }
    }
}
```
