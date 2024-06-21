# Polimorfismo
- Para que haya polimorfismo tiene que haber herencia.
- En una relación de tipo herencia, un objeto de la superclase puede almacenar un objeto de cualquiera de sus clases subclases.
- Esto signrifica que la clase Padre(superclase) es compatible con los tipos que derivan de ella. Pero no al revés.
![Texto alternativo](https://github.com/DanielBraun11/ApuntesProgramacionJAVA/blob/main/fotosJAVA/FotoPolimorfismo.jpg)
## Ejemplo en código:
Creamos las 4 clases con sus métodos constructores correspondientes y sus getter. También creamos para cada clase el método **mostraDatos()**(sobre escritura de miembros) que para las clases hijas se irá sobreescribiendo de la clase padre **Vehiculo**.
- Clase Padre(Vehiculo)
```java
public class Vehiculo{
    String matricula;
    String marca;
    String modelo;

    //CONSTRUCTOR
    public Vehiculo(String matr, String marc, String mod){
        matricula = matr;
        marca = marc;
        modelo = mod;
    }

    //MÉTODOD 
    public void mostrarDatos(){
        System.out.println("Matricula: " + matricula);
        System.out.println("Marca: " + marca);
        System.out.println("Modelo: " + modelo);
    }
}
```
- Clase Hija(VehiculoTurismo)
```java
public class VehiculoTurismo extends Vehiculo{
    int numeroPuertas;

    public VehiculoTurismo(String matr, String marc, String mode, int numP){
        super(matr,marc,mode);
        numeroPuertas = numP;

    }

    @Override
    public void mostrarDatos() {
        super.mostrarDatos();
        System.out.println("Numero de puertas: " + numeroPuertas);
    }
}
```
- clase Hija(VehiculoDeportivo)
```java
public class VehiculoDeportivo extends Vehiculo{
    int cilindrada;

    public VehiculoDeportivo(String matr, String marc, String mode, int cilin){
        super(matr,marc,mode);
        cilindrada = cilin;

    }

    @Override
    public void mostrarDatos() {
        super.mostrarDatos();
        System.out.println("Cilindradas: " + cilindrada);
    }
}
```
- Clase Hija(VehiculoFurgoneta)
```java
public class VehiculoFurgoneta extends Vehiculo{
    int carga;

    public VehiculoFurgoneta(String matr, String marc, String mode, int carg){
        super(matr,marc,mode);
        carga = carg;

    }

    @Override
    public void mostrarDatos() {
        super.mostrarDatos();
        System.out.println("Carga: " + carga);
    }
}
```
Entonces ahora en la clase Main donde crearemos nuestros objetos:
```java
public class Main{
    
    public static void main(String[] args) {
        Vehiculo vehiculo1 = new VehiculoTurismo("1234PQL","Ford","Puma",4);
        Vehiculo vehiculo2 = new VehiculoDeportivo("4321SSL","Porche","911",6);
        Vehiculo vehiculo3 = new VehiculoFurgoneta("9812KGL", "Volkswagen","Caravelle",1000);

        //MOSTRAR LOS DATOS DE LOS VEHICULOS CREADOS
        vehiculo1.mostrarDatos();
        System.out.println();
        vehiculo2.mostrarDatos();
        System.out.println();
        vehiculo3.mostrarDatos();
    }
}
```
## ¿Que hemos hecho?
He creado 4 objetos de la clase Padre Vehiculo. Estos objetos los podemos instanciar en otra clase hija gracias al molimorfismo y la anterior herencia. Y para cada objeto instanciado en su clase Hija tendremos los atributos que le correspondan.



