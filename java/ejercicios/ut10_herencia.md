# UT10. Herencia

## Ejercicios

__Ejercicio 1__

Construir una clase __Factura__ que descienda de la clase _Precio_ y que incluya dos atributos específicos llamados __emisor__ y __cliente__ y, al menos, un método llamado __imprimirFactura__.

__Ejercicio 2__

Construir una clase _final Math2_ que amplíe las declaraciones de métodos estáticos de la clase Math y que incluya funciones que devuelvan, respectivamente, el _máximo_, el _mínimo_, el _sumatorio_, la _media aritmética_ y la _media geométrica_ de un array de números reales dado como parámetro.

## Resolución de los ejercicios

__Ejercicio 1__

Definición de la clase _Precio_ utilizada en los apuntes:

```java
/**
 * Declaracion de la clase Precio
 * Jonay Garcia
 */
public class Precio {
    // Variable de instancia
    public double euros;
    
    // Metodos publicos
    public double getEuros() {
        return euros;
    }
    
    public void setEuros(double x) {
        euros = x;
    }
}
```

Definición de la clase _Factura_:

```java
/**
 * Declaracion de la clase Factura
 * descendiente de la clase precio
 * Jonay Garcia
 */
public class Factura extends Precio {

    private int cliente;
    private final String emisor = "Almacenes ACME S.A";

    public void setCliente(int cliente) {
        this.cliente = cliente;
    }

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
        f.setCliente(12345);
        f.setEuros(1000);
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

__Ejercicio 2__

Definición de la clase _Math2_:

```java
public final class Math2 {

    public static double min (double [] v) {
        double menor = v[0];
        for (int i=0; i<v.length; i++) {
            if (menor>v[i]) { menor=v[i]; }
        }
        return menor;
    }

    public static double max (double [] v) {
        double mayor = v[0];
        for (int i=0; i<v.length; i++) {
            if (mayor<v[i]) 
                mayor=v[i]; 
        }
        return mayor;
    }

    public static double sum (double [] v) {
        double sumatorio =0.0;
        for (int i=0; i<v.length; i++) {
            sumatorio=sumatorio+v[i];
        }
        return sumatorio;
    }

    public static double mediaAritmetica (double [] v) {
        double sumatorio =0.0;
        for (int i=0; i<v.length; i++) {
            sumatorio+=v[i];
        }
        return (sumatorio/v.length);
    }

    public static double mediaGeometrica (double [] v) {
        double producto =1.0;
        for (int i=0; i<v.length; i++) {
            producto*=v[i];
        }
        return Math.sqrt(producto);
    }
}
```

Ejemplo de uso de la clase _Math2_:

```java
/**
 * Programa PruebaMath2
 * A. Garcia-Beltran - diciembre, 2004
 */
public class PruebaMath2 {
    public static void main (String [] args) {
        double [] x = new double[10];
        for (int i=0; i<x.length; i++) {
            x[i] = 5*Math.random();
            System.out.println("x["+i+"] = "+x[i]);
        }
        System.out.println("Minimo : " + Math2.min(x));
        System.o ut.println("Maximo : " + Math2.max(x));
        System.out.println("Sumatorio : " + Math2.sum(x));
        System.out.println("Media arit. : " + Math2.mediaAritmetica(x));
        System.out.println("Media geom. : " + Math2.mediaGeometrica(x));
    }
}
```

Salida por pantalla de la ejecución del código anterior:

```bash
$ java PruebaMath2
x[0] = 3.9295964172220037
x[1] = 3.3033982387050598
x[2] = 0.38413320538334517
x[3] = 1.441533972096129
x[4] = 0.5194720253569335
x[5] = 0.5801662478628711
x[6] = 4.370186448410964
x[7] = 1.2908820504663692
x[8] = 3.8520244358555944
x[9] = 0.1450533020411976
Minimo : 0.1450533020411976
Maximo : 4.370186448410964
Sumatorio : 19.816446343400468
Media arit. : 1.981644634340047
Media geom. : 2.6131642597311173
```