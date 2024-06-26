# Enum
En Java, un enum (abreviatura de "enumeration") es un tipo de dato especial que representa un conjunto fijo de constantes conocidas.
Este tipo de dato es útil cuando necesitas definir un grupo de valores constantes y bien definidos, como los días de la semana,
los estados de un semáforo, los tipos de tarjetas de crédito, etc.
##Características principales de los enums en Java:
1. Definición y Sintaxis:
Un **enum** se define usando la palabra clave **enum**. Los valores del **enum** se enumeran dentro de llaves **{}** y están separados por comas.
```java
public enum Dia {
    LUNES, MARTES, MIERCOLES, JUEVES, VIERNES, SABADO, DOMINGO
}
```
2. Uso en Programas:
```java
Dia diaActual = Dia.LUNES;
```
3. Métodos internos
Los enums en Java tienen algunos métodos internos útiles, como **values()**, que devuelve un array de todos los valores del **enum**, y **valueOf(String name)**,
que convierte una cadena en el valor correspondiente del **enum**.
```java
Dia[] dias = Dia.values();
for (Dia dia : dias) {
    System.out.println(dia);
}

Dia dia = Dia.valueOf("LUNES");
```
4. Métodos y Campos Personalizados:
Los enums pueden tener métodos, constructores y campos personalizados. Esto permite agregar funcionalidades adicionales y datos a cada valor del **enum**.
```java
public enum Planeta {
    MERCURIO (3.303e+23, 2.4397e6),
    VENUS    (4.869e+24, 6.0518e6),
    TIERRA   (5.976e+24, 6.37814e6),
    MARTE    (6.421e+23, 3.3972e6);

    private final double masa;   // en kilogramos
    private final double radio;  // en metros

    Planeta(double masa, double radio) {
        this.masa = masa;
        this.radio = radio;
    }

    public double getMasa() {
        return masa;
    }

    public double getRadio() {
        return radio;
    }
}
```
5. Constructores en Enums:
Los constructores de un **enum** son siempre privados. No puedes instanciar un **enum** fuera de su definición. Los valores del **enum** son instancias predefinidas.
```java
public class Main {
    public enum Dia {
        LUNES, MARTES, MIERCOLES, JUEVES, VIERNES, SABADO, DOMINGO
    }

    public enum Planeta {
        MERCURIO(3.303e+23, 2.4397e6),
        VENUS(4.869e+24, 6.0518e6),
        TIERRA(5.976e+24, 6.37814e6),
        MARTE(6.421e+23, 3.3972e6);

        private final double masa;   // en kilogramos
        private final double radio;  // en metros

        Planeta(double masa, double radio) {
            this.masa = masa;
            this.radio = radio;
        }

        public double getMasa() {
            return masa;
        }

        public double getRadio() {
            return radio;
        }
    }

    public static void main(String[] args) {
        Dia diaActual = Dia.LUNES;
        System.out.println("Día actual: " + diaActual);

        for (Dia dia : Dia.values()) {
            System.out.println(dia);
        }

        Planeta planeta = Planeta.TIERRA;
        System.out.println("Planeta: " + planeta + ", Masa: " + planeta.getMasa() + ", Radio: " + planeta.getRadio());
    }
}
```
### Explicación del programa
En este ejemplo, **Dia** es un **enum** simple que enumera los días de la semana, y **Planeta** es un **enum** más complejo que incluye datos adicionales (masa y radio) y métodos 
para acceder a esos datos. Los **enums** en Java son muy versátiles y útiles para representar conjuntos fijos de constantes de manera más segura y estructurada.
