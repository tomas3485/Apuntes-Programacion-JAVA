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

