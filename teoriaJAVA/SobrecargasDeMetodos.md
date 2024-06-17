# Sobrecargas
Es una característica que permite definir múltiples métodos con el mismo nombre en una clase, pero con diferentes parámetros (número, tipo o ambos).
Esto permite que el mismo método pueda manejar diferentes tipos de datos o cantidades de argumentos, mejorando la legibilidad y flexibilidad del código.
```java
    public Persona(String n, int e){
        nombre = n;
        edad = e;
    }
    public Persona(String d){
        dni = d;
    }
}
```
Denominamos sobrecarga de Constructores cuando hay más de un constructor.
No se pueden tener 2 métodos iguales.
Estos puedes tener el mismo nombre y se diferencian con el número de parámetros que reciben.
Estos parámetros también pueden tener el mismo nombre pero entonces deben almacenarse en variables distintas.
```java
    public void presentarse(){
        System.out.println("Soy " + nombre + ", tengo " + edad + " anios");
    }

    public void presentarse(int peso){
        System.out.println("Peso" + peso +"Kg");
    }
```
Java no diferencia a los métodos por su tipo de retorno.
EJEMPLO CON ERROR
```java
    public int presentarse(int peso){
        return peso;
    }

    public void presentarse(int peso){
        System.out.println("Peso" + peso +"Kg");
    }
```


