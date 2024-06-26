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









