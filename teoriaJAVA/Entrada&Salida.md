# Entrada y salida de datos
## Entrada
Para capturar los valores que almacenen nuestras variables en nuestro programa y estas las tienes que introducir a traves de la consla se utiliza **Scanner**.
Hay que importar su libreria aunque esta se importe automaticamente cuando lo usamos en nuestro programa.
```java
import java.util.Scanner;

public class ClaseMain {
    public static void main(String[] args) {
        Scanner entrada = new Scanner (System.in);
        
    }
}
```
Una vez creado es escaner, cuando queramos inicializar las variables dentro del main lo usaremos de la siguiente forma:
### int
```java
Scanner entrada = new Scanner (System.in);
int numero;
numero = entrada.nextInt();
```
### string
```java
Scanner entrada = new Scanner (System.in);
String cadena;
cadena = entrada.next();   //Solo guarda hasta un espacio
cadena = entrada.nextLine();  //Guarda la línea entera
```
### char
```java
Scanner entrada = new Scanner (System.in);
char caracter;
caracter = entrada.next().charAt(x);  //Donde x será la posicion (x = 0)
```

