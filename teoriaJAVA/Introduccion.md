Java es un lenguaje de programación que tiene las siguientes características:
- **Independencia de la plataforma**: las aplicaciones Java se compilan en un
código de bytes que se almacena en archivos de clase y se carga en una JVM.
Dado que las aplicaciones se ejecutan en una JVM, se pueden ejecutar en
muchos sistemas operativos y dispositivos diferentes.
- **Orientado a objetos**: Java es un lenguaje orientado a objetos que toma
muchas de las características de C y C ++ y las mejora.
- **Recolección automática de basura**: Java asigna y desasigna memoria
automáticamente para que los programas no tengan que cargar con esa tarea.
- **Biblioteca estándar enriquecida**: Java incluye una gran cantidad de objetos
prefabricados que se pueden usar para realizar tareas como entrada / salida,
redes y manipulación de fechas.)

![Texto alternativo](https://media.licdn.com/dms/image/D4E12AQHBgWTV5phDHw/article-inline_image-shrink_400_744/0/1683789925642?e=1721865600&v=beta&t=iAVdGP15p0sdAPFiRaJ0HbWxxKEA1w_Pzk2scsKySO4)
- JDK (Java Development Kit)
- JRE (Java Runtime Environment)
- JVM (Java Virtual Machine)

## Hola Mundo
```java
public class ClaseMain {
    public static void main(String[] args) {
        System.out.println("Hola Mundo");
    }
}
```
- Java se basa en clases. Sólo hay clases (métodos, atributos) e interacciones entre ellas.
- Debe haber al menos una definicion de clase en el programa
- El programa prinicpal **main** es una función/metodo público de una clase **public class**. Sólo pueden haber 1 **main(String[] args**
  en el programa (podría haber otros si se cambian los argumentos de entrada, sobrecargar)
```java
public static void main(String[] args) {}
public static void main (int x) {}
```














