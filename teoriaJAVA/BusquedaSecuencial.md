# Busqueda Secuencial
La búsqueda secuencial, también conocida como búsqueda lineal, es un método simple de encontrar un elemento en una lista.
Este algoritmo consiste en recorrer la lista elemento por elemento desde el principio hasta el final, comparando cada uno con el valor buscado
hasta encontrar una coincidencia o llegar al final de la lista.
```java
public class Ejemplo {
    public static void main(String[] args) {
        int numeroBuscado = 11;
        int i = 0;
        boolean band = false;

        int [] cadenaNumeros = {2,34,6,12,89,11,45};
        while(i < cadenaNumeros.length && band == false){
            if(cadenaNumeros[i] == numeroBuscado){
                band = true;
            }
            i++;
        }

        //Mensaje de si se encuentra y en que posicion o no
        if(band == false){
            System.out.println("No se ha encontrado");
        }else{
            System.out.println("Se ha encontrado en la posicion: " + (i - 1));
        }
    }
}
```
Leyenda del algoritmo:
- El bucle 'while' se encarga de buscar el dato 'numeroBuscado', variable que almacena lo que buscamos.
- Dentro, el condicional 'if' que checkea si el dato que se encuentra en la posicion 'i' del array es igual al dato que buscamos.
- En el algoritmo usamos un buleano 'band' inicializad oen fasle indicando que el dato aun no ha sido reconocido. Este solo cambiará si se cumple la condición del 'if'.
- Antes de salir del bucle 'while', aumentamos el valor de 'i' en 1 para seguir recorriendo la siguiente posición del array.

## Método más sencillo
Recorremos el almacen con un for( ; ; ) ya que este nos permite inicializar la variable entera i para acceder a las posiciones. Si quisieramos un mensaje de no encontrado
podriamos incorporar un booleando que cambiase su valor si lo encuentra y usarlo en un 'if' con un mensaje de no encontrado.
```java
public class Ejemplo {
    public static void main(String[] args) {
        int numeroBuscado = 11;
        boolean encontrado = false;

        int[] cadenaNumeros = {32,56,2,78,102,4,11,51};

        for(int i = 0 ; i  <cadenaNumeros.length ;i++){
            if(cadenaNumeros[i] == numeroBuscado){
                System.out.println("El numero "+ numeroBuscado +" se ha encontrado en la posicion: " + i);
                encontrado = true;
            }
        }

        if(encontrado == false){
            System.out.println("Dato no encontrado");
        }
    }
}
```
