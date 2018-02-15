# UT10. Herencia

## Ejercicios

__Ejercicio 1__

Construir una clase __Factura__ que descienda de la clase _Precio_ y que incluya dos atributos específicos llamados __emisor__ y __cliente__ y, al menos, un método llamado __imprimirFactura__.

__Ejercicio 2__

Construir una clase _final Math2_ que amplíe las declaraciones de métodos estáticos de la clase Math y que incluya funciones que devuelvan, respectivamente, el _máximo_, el _mínimo_, el _sumatorio_, la _media aritmética_ y la _media geométrica_ de un array de números reales dado como parámetro.

__Ejercicio 3__

Escribir un programa que genere un array que pueda almacenar objetos de las clases Integer, Float, Double y Byte. Pista: Number[]x = new Number[];

## Resolución de los ejercicios

__Ejercicio 1__

Definición de la clase _Factura_:

```java
/**
 * Declaracion de la clase Factura
 * descendiente de la clase precio
 * Jonay Garcia
 */
public class Factura extends Precio {

    public int cliente;
    private final String emisor = "Almacenes ACME S.A";

    public void imprimirFactura () {
        System.out.println("");
        System.out.println("Emisor: " + emisor);
        System.out.println("----------------------");
        System.out.println("Cliente: " + cliente);
        System.out.println("Total: " + euros + " euros");
    }
}
```

Ejemplo de uso de la clase _Factura_:

```java
/**
 * Programa PruebaFactura
 * Jonay Garcia
 */
public class PruebaFactura {
    public static void main (String [] args) {
        Factura f = new Factura();
        f.cliente = 12345;
        f.pone(1000);
        f.imprimirFactura();
    }
}
```

Salida por pantalla de la ejecución del código anterior:

```bash
$ java pruebaFactura
Emisor: Almacenes ACME S.A
----------------------
Cliente: 12345
Total: 1000.0 euros
```