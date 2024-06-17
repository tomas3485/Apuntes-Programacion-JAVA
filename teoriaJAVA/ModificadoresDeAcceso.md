# Modificadores de Acceso
Sirven para determinar que clases pueden tener acceso a los atributos de otras clases.
```java
//Atributos
public int edad;
private int peso;
```
## Sin Modificador de acceso
Si no definimos un atributo con un modificador de acceso, este aparecerá por defecto. El atributo no definido SOLO se podrá usar en las clases que esten en su mismo paquete.
```java
//Atributos
int amigos;
```
## Privado
Si definimos un atributo con el modificador de acceso privado, ese atributo SOLO se podrá usar en los métodos de su misma clase.
```java
//Atributos
private int peso;
```
## Público
Si definimos un atributo como público, ese atributo se podrá usar en cualquier clase de nuestro programa.
```java
//Atributos
public int edad;
```
Recordar que si la clase se encuentra en otro paquete distinto, deberás importar el paquete.
```java
import nombre_package.nombre_clase;  //nombre_clase = nombre de la clase donde se encuentra el atributo
```
