# Chain of Responsibility
Permite que un objeto pase una solicitud a una cadena de potenciales manejadores hasta que la solicitud sea atendida.
Cada manejador en la cadena decide si procesa la solicitud o la pasa al siguiente manejador en la cadena.
## Ejemplo en Java
Ejemplo donde tenemos una cadena de manejadores que procesan diferentes niveles de solicitudes de soporte técnico (básico, intermedio y avanzado)
1. Crear la interfaz **Handler**
```java
public abstract class SupportHandler {
    protected SupportHandler nextHandler;

    public void setNextHandler(SupportHandler nextHandler) {
        this.nextHandler = nextHandler;
    }

    public abstract void handleRequest(String issue);
}
```
2. Implementar los manejadores concretos
```java
public class BasicSupportHandler extends SupportHandler {
    @Override
    public void handleRequest(String issue) {
        if (issue.equals("basic")) {
            System.out.println("Basic Support: Handling basic issue.");
        } else if (nextHandler != null) {
            nextHandler.handleRequest(issue);
        }
    }
}

public class IntermediateSupportHandler extends SupportHandler {
    @Override
    public void handleRequest(String issue) {
        if (issue.equals("intermediate")) {
            System.out.println("Intermediate Support: Handling intermediate issue.");
        } else if (nextHandler != null) {
            nextHandler.handleRequest(issue);
        }
    }
}

public class AdvancedSupportHandler extends SupportHandler {
    @Override
    public void handleRequest(String issue) {
        if (issue.equals("advanced")) {
            System.out.println("Advanced Support: Handling advanced issue.");
        } else if (nextHandler != null) {
            nextHandler.handleRequest(issue);
        }
    }
}
```
3. Configurar la cadena de responsabilidad y manejar las solicitudes
```java
public class ChainOfResponsibilityDemo {
    public static void main(String[] args) {
        // Crear los manejadores
        SupportHandler basicHandler = new BasicSupportHandler();
        SupportHandler intermediateHandler = new IntermediateSupportHandler();
        SupportHandler advancedHandler = new AdvancedSupportHandler();

        // Configurar la cadena de responsabilidad
        basicHandler.setNextHandler(intermediateHandler);
        intermediateHandler.setNextHandler(advancedHandler);

        // Probar la cadena con diferentes solicitudes
        basicHandler.handleRequest("basic");
        basicHandler.handleRequest("intermediate");
        basicHandler.handleRequest("advanced");
        basicHandler.handleRequest("unknown");
    }
}
```
Salida. 
```java
Basic Support: Handling basic issue.
Intermediate Support: Handling intermediate issue.
Advanced Support: Handling advanced issue.
```
### Explicación del programa
En este ejemplo, la solicitud se pasa a lo largo de la cadena de manejadores hasta que uno de ellos la maneja. Si un manejador no puede manejar la solicitud,
la pasa al siguiente en la cadena. Si la solicitud es "unknown" y ningún manejador puede manejarla, simplemente no se imprime nada (lo cual podría mejorarse 
añadiendo un manejador final que maneje los casos no reconocidos).

Este patrón permite que el sistema sea flexible y extensible, ya que puedes agregar nuevos manejadores a la cadena sin modificar el código existente.
