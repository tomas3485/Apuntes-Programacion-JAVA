# Ordenamientos
## Método burbuja
El método burbuja, también conocido como "Bubble Sort", es un algoritmo de ordenamiento sencillo que ordena una lista de elementos
comparando cada par de elementos adyacentes y cambiándolos de posición si están en el orden incorrecto. Este proceso se repite hasta
que la lista está completamente ordenada.
```java
public class Ejemplo {
    public static void main(String[] args) {
        int[] cadenaNumeros = {6,8,1,3,2,9,14};
        int aux;

        //Método burbuja
        for(int i = 0 ; i<(cadenaNumeros.length - 1) ; i++){
            for(int j = 0 ; j<(cadenaNumeros.length - 1) ; j++){
                if(cadenaNumeros[j] > cadenaNumeros[j + 1]){
                    aux = cadenaNumeros[j];
                    cadenaNumeros[j] = cadenaNumeros[j + 1];
                    cadenaNumeros[j + 1] = aux;
                }
            }
        }

        //Mostrar cadena de numeros
        for(int i = 0 ; i<cadenaNumeros.length ; i++){
            System.out.print(cadenaNumeros[i] + ", ");
        }
    }
}
```
