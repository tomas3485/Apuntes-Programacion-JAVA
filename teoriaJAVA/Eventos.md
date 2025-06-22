# Oyente de acción - ActionListener
**IMPORTANTE** los ejemplos de este apartado estan relacionados con las Ventanas(JFrame) y Paneles(JPanel) de los apuntes anteriores.

Estos eventos se realizarán cuando pulsemos un botón. Eso es lo que hace el **ActionListener()**, que es una esucha de acción.

```java
ActionListener oyenteAccion = new ActionListener(){

  @Override
  public void actionPerformed(ActionEvent ae){
      saludo.setText("Hola " + cajaTexto.getText();
  }
};

boton.addActionListener(oyenteAccion);
```
En el programa, **saludo** es una etiqueta JLabel que ya se ha creado, añadido y colocado al panel. El método **cajaTexto.getText()** mostrará lo que se ha introducido el la caja de texto de nombre **cajaTexto**.


## Extras
En Java, un oyente de acción (ActionListener) es una interfaz utilizada para manejar eventos de acción, como clics de botones.
Un ActionListener se registra en un componente, y cuando ocurre una acción en ese componente, se llama al método actionPerformed del oyente registrado.

1. **Implementar la interfaz ActionListener**: Una clase debe implementar la interfaz **ActionListener** y sobrescribir su método **actionPerformed**.
2. **Registrar el ActionListener**: El oyente de acción se registra en el componente (como un botón) que generará el evento.
3. **Definir el comportamiento**: En el método **actionPerformed**, defines lo que debe ocurrir cuando se detecta el evento de acción.

### Ejemplo práctico
1. Crear la clase que implementa ActionListener:
```java
import javax.swing.*;
import java.awt.event.*;

public class MiVentana extends JFrame implements ActionListener {
    private JButton boton;

    public MiVentana() {
        // Configuración de la ventana
        this.setSize(300, 200);
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setTitle("Ejemplo de ActionListener");

        // Crear el botón y añadirlo a la ventana
        boton = new JButton("Haz clic aquí");
        this.add(boton);

        // Registrar el ActionListener al botón
        boton.addActionListener(this);

        // Hacer visible la ventana
        this.setVisible(true);
    }

    // Sobrescribir el método actionPerformed para manejar el evento
    @Override
    public void actionPerformed(ActionEvent e) {
        // Acción a realizar cuando se clica el botón
        if (e.getSource() == boton) {
            System.out.println("¡Botón clicado!");
        }
    }

    // Método principal para ejecutar el programa
    public static void main(String[] args) {
        new MiVentana();
    }
}
```
### Explicación del Ejemplo
1. **Clase MiVentana**: Esta clase hereda de **JFrame** y también implementa **ActionListener**.
2. **Botón boton**: Se crea un botón con el texto "Haz clic aquí".
3. **Registro del ActionListener**: **boton.addActionListener(this)** registra la ventana (que implementa ActionListener) como el oyente de acciones del botón.
4. **Método actionPerformed**: Sobrescribimos este método para definir lo que ocurre cuando el botón es clicado. En este caso, simplemente imprime "¡Botón clicado!" en la consola.
5. **main**: El método principal crea una instancia de MiVentana, mostrando la interfaz gráfica.

Cuando ejecutas este programa y clicas el botón, se dispara un evento de acción, invocando el método actionPerformed, y se muestra el mensaje en la consola.
Este es un ejemplo sencillo pero ilustra claramente cómo funcionan los ActionListener en Java.

Esta seria otra manera de hacerlo : 
```java
// Acción para mostrar todos los estudiantes
        botonMostrarTodos.addActionListener(e -> cardLayout.show(panelPrincipal, Panel.MOSTRAR_TODOS.getNombreInterno()));
```



