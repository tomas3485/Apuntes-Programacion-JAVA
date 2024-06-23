# Singleton
El patrón Singleton asegura que una clase tenga solo una instancia y proporciona un punto de acceso global a ella.
## Ejemplo
````java
public class Singleton {
    // Instancia única de la clase
    private static Singleton instance;

    // Constructor privado para evitar instanciación externa
    private Singleton() {
        // Inicialización del Singleton
    }

    // Método público para obtener la instancia única
    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }

    public void showMessage() {
        System.out.println("¡Hola desde Singleton!");
    }

    public static void main(String[] args) {
        // Obtener la única instancia del Singleton
        Singleton singleton = Singleton.getInstance();
        singleton.showMessage();
    }
}
```
