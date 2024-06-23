# Hilos
Los hilos (threads) en Java permiten la ejecución concurrente de varias tareas dentro de un programa. La programación con hilos es útil para mejorar el
rendimiento de aplicaciones que realizan múltiples tareas independientes o que pueden aprovechar el paralelismo, como en el caso de aplicaciones de servidor,
procesamiento de datos, y aplicaciones gráficas.
## Conceptos Básicos de Hilos en Java
- **Thread**: Un hilo es una unidad ligera de ejecución dentro de un proceso.
- **Runnable**: Una interfaz funcional que debe ser implementada para definir la tarea que ejecutará un hilo.
- **Estado de un hilo**: Los hilos pueden estar en diferentes estados como nuevo, ejecutable, bloqueado, esperando, y terminado.
## Creación de hilos en Java
Hay dos formas principales de crear un hilo en Java:
1. Extendiendo la clase **Thread**.
2. Implementando la interfaz **Runnable**.
### Ejemplo 1: Extender la Clase **Thread**
Aquí se muestra cómo crear un hilo extendiendo la clase **Thread**:
```java
class HiloExtendido extends Thread {
    private String nombre;

    public HiloExtendido(String nombre) {
        this.nombre = nombre;
    }

    @Override
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println(nombre + " ejecutando " + i);
            try {
                Thread.sleep(1000); // Pausa de 1 segundo
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
        System.out.println(nombre + " terminado.");
    }
}

public class HilosEjemplo {
    public static void main(String[] args) {
        HiloExtendido hilo1 = new HiloExtendido("Hilo 1");
        HiloExtendido hilo2 = new HiloExtendido("Hilo 2");

        hilo1.start(); // Iniciar hilo1
        hilo2.start(); // Iniciar hilo2
    }
}
```
En este ejemplo, la clase **HiloExtendido** extiende **Thread** y sobrescribe el método **run()**, que contiene el código que se ejecutará en el hilo. Los hilos
se inician llamando al método **start()**.
### Ejemplo 2: Implementar la Interfaz **Runnable**
Aquí se muestra cómo crear un hilo implementando la interfaz **Runnable**:
```java
class HiloRunnable implements Runnable {
    private String nombre;

    public HiloRunnable(String nombre) {
        this.nombre = nombre;
    }

    @Override
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println(nombre + " ejecutando " + i);
            try {
                Thread.sleep(1000); // Pausa de 1 segundo
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
        System.out.println(nombre + " terminado.");
    }
}

public class HilosEjemplo {
    public static void main(String[] args) {
        Thread hilo1 = new Thread(new HiloRunnable("Hilo 1"));
        Thread hilo2 = new Thread(new HiloRunnable("Hilo 2"));

        hilo1.start(); // Iniciar hilo1
        hilo2.start(); // Iniciar hilo2
    }
}
```
En este ejemplo, la clase **HiloRunnable** implementa la interfaz **Runnable** y sobrescribe el método **run()**. Los hilos se crean pasando una instancia de **HiloRunnable**
al constructor de **Thread**, y se inician llamando al método **start()**.
##Sincronización de Hilos
Cuando varios hilos acceden a recursos compartidos, es crucial sincronizarlos para evitar condiciones de carrera y mantener la consistencia de los datos.
Esto se puede hacer utilizando el bloque **synchronized** o métodos sincronizados.

Ejemplo de uso de **synchronized**:
```java
class Contador {
    private int cuenta = 0;

    public synchronized void incrementar() {
        cuenta++;
    }

    public int getCuenta() {
        return cuenta;
    }
}

class HiloContador extends Thread {
    private Contador contador;

    public HiloContador(Contador contador) {
        this.contador = contador;
    }

    @Override
    public void run() {
        for (int i = 0; i < 1000; i++) {
            contador.incrementar();
        }
    }
}

public class SincronizacionEjemplo {
    public static void main(String[] args) throws InterruptedException {
        Contador contador = new Contador();
        Thread hilo1 = new HiloContador(contador);
        Thread hilo2 = new HiloContador(contador);

        hilo1.start();
        hilo2.start();

        hilo1.join(); // Espera a que hilo1 termine
        hilo2.join(); // Espera a que hilo2 termine

        System.out.println("Cuenta final: " + contador.getCuenta());
    }
}
```
En este ejemplo, el método incrementar() está sincronizado para asegurar que solo un hilo pueda ejecutarlo a la vez, garantizando así la consistencia del valor del contador.

