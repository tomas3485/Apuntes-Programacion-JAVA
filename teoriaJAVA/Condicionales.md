# Condicionales
Los condicionales en programación se utilizan para tomar decisiones en el código. Nos permiten ejecutar diferentes
bloques de código según ciertas condiciones o criterios, lo que hace que el programa sea más dinámico y capaz de
responder a diferentes situaciones.
## if
Es el condicional mas simple.
```java
public class Ejemplo {
    public static void main(String[] args) {
       if(0 < 11){
           System.out.println("Se cumple la condicion"); //Como 0 es menor que 11 entro al if {}
       }
    }
}
```
## if else
```java
public class Ejemplo {
    public static void main(String[] args) {
       if(0 > 11){
           System.out.println("Se cumple la condicion"); //Como 0 no es mayor que 11, no entro al if {}
       }else{
           System.out.println("No se cumple la condicion"); //Entro automaticamente al else
       }
    }
}
```
## if else if
```java
public class Ejemplo {
    public static void main(String[] args) {
       if(5 > 11){
           System.out.println("Se cumple la condicion 5 > 11"); //Como 5 no es mayor que 11, no entro al if {}
       }else if(5 > 3){
           System.out.println("Se cumple la condicion 5 > 3"); //Como ahora 5 si es mayor que 3 entro al if del else if {}
       }else{
           System.out.println("Si no se cumple ninguna condicion hago el else");
       }
    }
}
```
## switch
En los switch, tenemos una condicion numerica que ha de ser un valor de tipo simple (int, char...) Dependiendo de la opcion ira directamente a hacer las instrucciones que 
se realicen en el case. Es IMPORTANTE que despues d elas instrucciones y operaciones de los case pongamos el **break;** porque sino el programa se seguira ejecutando dentro del switch hasta que encuentre este break; o ejecute las instrucciones del default (ultimo case).
```java
public class Ejemplo {
    public static void main(String[] args) {
       int opcion = 2;

       switch(opcion){
           case 1:
               System.out.println("Cosas del case 1");
               break;
           case 2:
               System.out.println("Cosas del case 2");
               break;
           case 3:
               System.out.println("Cosas del case 3");
               break;
           default:
               System.out.println("Si no se para en un case acaba aqui");
       }
    }
}
```
## while
```java
public class Ejemplo {
    public static void main(String[] args) {
       int contador = 5;

       while(contador > 0){   //Condicion: que el valor de contador sea mayor que 0
           System.out.print(contador + ", ");
           contador--;  //Decremento el valor del contador en 1
       }
    }
}
```
## do while
Se utiliza cuando vamos a entrar al bucle por lo menos una vez
```java
public class Ejemplo {
    public static void main(String[] args) {
       int contador = 5;

       do{
           System.out.print(contador + 2 + ", "); //Enseño el valor del contador + 2
           contador++; //Ahora si incremento el valor en 1
       }while(contador < 10);  //Con la condicion de que el contador sea menor que 10
    }
}
```
## for( ; ; )
```java
public class Ejemplo {
    public static void main(String[] args) {
       int contador = 5;
       
   //  (inicilizacion ; condicion ; incremento/decremento)
       for(int i = 0 ; i<contador ; i++){
           System.out.println("Hola");  //Acciones
       }
    }
}
```
## for( : )
Este for se utiliza mas para recorrer tipos de datos contenedor como arrays o vectores. Su estructura es la siguiente:
for(creo varriable del mismo tipo que los datos que almacena : nombre de la variable que almacena datos)
Su funcionamiento es simple, el for va recorriendo el almacen y va copiando el datos que se encuentra en la posición del almacen en 
la variabe de dentro del for a la que podemos acceder y operar con ella dentro del for {}
```java
public class Ejemplo {
    public static void main(String[] args) {
       String[] almacenDePalabras = {"futbol", "baloncesto", "tenis"};  //Array de strings

    // (Tipo de dato que se almacena : donde se almacena)
       for(String palabra : almacenDePalabras){
           System.out.print(palabra + ", ");
       }
    }
}
```
