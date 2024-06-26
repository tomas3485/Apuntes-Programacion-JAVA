# State
Permite a un objeto alterar su comportamiento cuando su estado interno cambia. El objeto parecerá cambiar su clase.
## Ejemplo en Java
Vamos a implementar un ejemplo sencillo donde un objeto Ventilador puede estar en diferentes estados: Apagado, Bajo, y Alto. Dependiendo del estado actual,
el comportamiento del ventilador cambiará cuando se presione el botón de encendido.
1. Crear la interfaz **Estado**
```java
public interface Estado {
    void manejarSolicitud();
}
```
2. Implementar los estados concretos - 3 clases
```java
public class EstadoApagado implements Estado {
    private final Ventilador ventilador;

    public EstadoApagado(Ventilador ventilador) {
        this.ventilador = ventilador;
    }

    @Override
    public void manejarSolicitud() {
        System.out.println("Encendiendo el ventilador a velocidad baja.");
        ventilador.setEstado(ventilador.getEstadoBajo());
    }

    @Override
    public String toString() {
        return "Ventilador está apagado.";
    }
}

public class EstadoBajo implements Estado {
    private final Ventilador ventilador;

    public EstadoBajo(Ventilador ventilador) {
        this.ventilador = ventilador;
    }

    @Override
    public void manejarSolicitud() {
        System.out.println("Encendiendo el ventilador a velocidad alta.");
        ventilador.setEstado(ventilador.getEstadoAlto());
    }

    @Override
    public String toString() {
        return "Ventilador está en velocidad baja.";
    }
}

public class EstadoAlto implements Estado {
    private final Ventilador ventilador;

    public EstadoAlto(Ventilador ventilador) {
        this.ventilador = ventilador;
    }

    @Override
    public void manejarSolicitud() {
        System.out.println("Apagando el ventilador.");
        ventilador.setEstado(ventilador.getEstadoApagado());
    }

    @Override
    public String toString() {
        return "Ventilador está en velocidad alta.";
    }
}
```
3. Implementar la clase **Ventilador** que actúa como contexto
```java
public class Ventilador {
    private final Estado estadoApagado;
    private final Estado estadoBajo;
    private final Estado estadoAlto;

    private Estado estadoActual;

    public Ventilador() {
        estadoApagado = new EstadoApagado(this);
        estadoBajo = new EstadoBajo(this);
        estadoAlto = new EstadoAlto(this);

        estadoActual = estadoApagado; // El estado inicial es "apagado"
    }

    public void setEstado(Estado estado) {
        this.estadoActual = estado;
    }

    public void presionarBoton() {
        estadoActual.manejarSolicitud();
    }

    public Estado getEstadoApagado() {
        return estadoApagado;
    }

    public Estado getEstadoBajo() {
        return estadoBajo;
    }

    public Estado getEstadoAlto() {
        return estadoAlto;
    }

    @Override
    public String toString() {
        return estadoActual.toString();
    }
}
```
4. Probar el patrón State
```java
public class EstadoPatronDemo {
    public static void main(String[] args) {
        Ventilador ventilador = new Ventilador();

        System.out.println(ventilador);

        ventilador.presionarBoton();
        System.out.println(ventilador);

        ventilador.presionarBoton();
        System.out.println(ventilador);

        ventilador.presionarBoton();
        System.out.println(ventilador);
    }
}
```
Salida.
```java
Ventilador está apagado.
Encendiendo el ventilador a velocidad baja.
Ventilador está en velocidad baja.
Encendiendo el ventilador a velocidad alta.
Ventilador está en velocidad alta.
Apagando el ventilador.
Ventilador está apagado.
```
### Explicación del programa
El objeto **Ventilador** cambia su comportamiento dependiendo de su estado actual. Cuando se presiona el botón, el estado cambia y el comportamiento del **Ventilado** cambia en consecuencia.
Esto se logra sin necesidad de usar múltiples condicionales o cambios en la clase **Ventilador**, haciendo el código más limpio y manejable.
