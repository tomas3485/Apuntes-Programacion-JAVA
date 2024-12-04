# Concurrencia
La concurrencia en Java se refiere a la capacidad de un programa para realizar varias tareas al mismo tiempo o manejar múltiples procesos que se ejecutan simultáneamente.
Esto no necesariamente significa que todas las tareas se ejecuten a la vez (como en el paralelismo), sino que el programa está diseñado para alternar entre tareas de manera
eficiente, compartiendo los recursos del sistema.
La concurrencia se puede lograr en Java utilizando herramientas y características que permiten dividir el trabajo en múltiples **flujos** (hilos), manejar tareas en segundo plano y coordinar procesos.
Esto incluye:
1. Hilos: La unidad más básica de ejecución concurrente en Java.
2. Ejecutores (Executors): Abstracciones de alto nivel para gestionar grupos de hilos.
3. Colas concurrentes: Para gestionar datos entre hilos de forma segura.
4. Sincronización: Mecanismos para evitar problemas como condiciones de carrera o acceso simultáneo no controlado a recursos compartidos.

En esencia, la concurrencia trata de la gestión de múltiples tareas que progresan de manera eficiente y coordinada.

# Hilos
Un hilo es la unidad más básica de ejecución concurrente en Java. Un programa en Java siempre tiene al menos un hilo principal (el que ejecuta el método main).
Los hilos permiten que un programa ejecute varias partes de su código simultáneamente.

Por ejemplo:
- Un hilo puede encargarse de descargar datos de internet.
- Otro puede procesar esos datos al mismo tiempo.

En Java, los hilos se pueden crear de dos maneras principales:
1. Extendiendo la clase Thread:
```java
class MiHilo extends Thread {
    public void run() {
        System.out.println("Este es un hilo en ejecución");
    }
}

MiHilo hilo = new MiHilo();
hilo.start(); // Comienza la ejecución del hilo
```

2. Implementando la interfaz Runnable:
```java
class MiTarea implements Runnable {
    public void run() {
        System.out.println("Tarea concurrente en ejecución");
    }
}

Thread hilo = new Thread(new MiTarea());
hilo.start(); // Comienza la ejecución del hilo
```

### Diferencias principales
| Aspecto  | Concurrencia | Hilos | 
| ------ | ------------ | --------------- |
| Definición  | Habilidad de ejecutar múltiples tareas de manera coordinada. | Unidad básica de ejecución concurrente en Java. | 
| Nivel   | Es un concepto de alto nivel. | Es una implementación de bajo nivel. |              
| Enfoque | Diseño de sistemas que pueden manejar múltiples procesos. | Ejecución paralela de tareas individuales. |              
| Ejemplo | `ExecutorService` para gestionar tareas concurrentes. |  Clase `Thread` para crear y manejar hilos directamente. |  

### Herramientas de Concurrencia en Java

Java proporciona muchas herramientas en el paquete `java.util.concurrent` para trabajar con concurrencia de forma más eficiente y menos propensa a errores:

- Executor Framework: Maneja automáticamente los hilos y las tareas.
- Locks explícitos: (`ReentrantLock`, por ejemplo) para control más preciso.
- Clases sincronizadas: Como `ConcurrentHashMap` o `CopyOnWriteArrayList`.

En resumen:

- Concurrencia es un concepto más amplio relacionado con cómo diseñar sistemas que pueden manejar múltiples tareas simultáneamente.
- Hilos son uno de los medios más básicos para implementar concurrencia en Java.













