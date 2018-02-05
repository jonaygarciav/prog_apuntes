# Objetos y Clases

## Objetivos

* Presentar el concepto de objeto, clase, atributo, método e instancia.
* Interpretar el código fuente de una aplicación Java donde aparecen implementados los conceptos anteriores.
* Construir una aplicación Java sencilla, convenientemente especificada, que emplee los conceptos anteriores.
* Introducir el concepto de constructor de una clase en Java.
* Interpretar el código fuente de una aplicación Java donde aparecen declaraciones y llamadas a constructores.
* Construir una aplicación Java sencilla, convenientemente especificada, que emplee clases en los que se declaren explícitamente constructores.

## Introducción

Aunque parezca una obviedad, la base de la Programación Orientada a Objetos es el objeto.
En la vida real todos los objetos tienen una serie de características y un comportamiento. Por
ejemplo, una puerta tiene color, forma, dimensiones, material... (goza de una serie de características) y puede abrirse, cerrarse... (posee un comportamiento). En Programación Orientada a Objetos, un objeto es una combinación de unos datos específicos y de las rutinas que pueden operar con esos datos. De forma que los dos tipos de componentes de un objeto son:

* __Campos o atributos__: componentes de un objeto que almacenan datos. También se les denomina variables miembro. Estos datos pueden ser de tipo primitivo (boolean, int, double, char...) o, a su vez, de otro tipo de objeto (lo que se denomina agregación o composición de objetos). La idea es que un atributo representa una propiedad determinada de un objeto.
* __Rutinas o métodos__: es una componente de un objeto que lleva a cabo una determinada acción
o tarea con los atributos.

## Clases

Una clase representa al conjunto de objetos que comparten una estructura y un comportamiento comunes. Una clase es una combinación específica de atributos y métodos y puede considerarse un tipo de dato de cualquier tipo __no__ primitivo. Así, una clase es una especie de plantilla o prototipo de objetos: define los atributos que componen ese tipo de objetos y los métodos que
pueden emplearse para trabajar con esos objetos. Aunque, por otro lado, una clase también puede
estar compuesta por métodos estáticos que no necesitan de objetos (como las clases construidas en
los capítulos anteriores que contienen un método estático main). La declaración de una clase sigue la siguiente sintaxis:

```java
[modificadores] class IdentificadorClase {
    // Declaraciones de atributos
    ...
    // Declaraciones de métodos
    ...
}
```

> __Nota__: Los identificadores de las clases deberían ser simples, descriptivos y sustantivos y, en el caso de nombres compuestos, con la primera letra de cada uno en mayúsculas.


## Instancias

Una __instancia__ es un elemento tangible (ocupa memoria durante la ejecución del programa) generado a partir de una definición de clase. Todos los objetos empleados en un programa han de
pertenecer a una clase determinada.

Aunque el término a veces se emplea de una forma imprecisa, un objeto es una instancia de
una clase predefinida en Java o declarada por el usuario y referenciada por una variable que
almacena su dirección de memoria. Cuando se dice que Java no tiene punteros simplemente se indica que Java no tiene punteros que el programador pueda ver, ya que todas las referencias a objeto son de hecho punteros en la representación interna.

En general, el acceso a los atributos se realiza a través del operador punto, que separa al
identificador de la referencia del identificador del atributo (idReferencia.idAtributo). Las
llamadas a los métodos para realizar las distintas acciones se llevan a cabo separando los
identificadores de la referencia y del método correspondiente con el operador punto
(idReferencia.idMetodo(parametros)).

### Ejemplo sencillo de clase e instancia

El siguiente código muestra la declaración de la clase __Precio__. La clase __Precio__ consta de un único atributo (euro) y dos métodos: uno que asigna un valor al atributo llamado __setEuros__ sin devolver ningún valor y otro que devuelve el valor del atributo llamado __getEuros__:

```java
/**
 * Ejemplo de declaracion de la clase Precio
 * double getEuros() --> devuelve el valor almacenado en euros
 * void setEuros(double euros) --> almacena valor en euros
 * Jonay Garcia
 */
public class Precio {
    // Atributo o variable miembro
    public double euros;
    
    // Metodos
    public double getEuros() {
        return euros;
    }
    
    public void setEuros(double euros) {
        this.euros = euros;
    }
}
```

Gráficamente una clase puede representarse como un rectángulo según se muestra en la siguiente figura:

![img_01][img_01]

* __+/-__: indica el ámbito, '-' representa __privated__ y '+' representa 'public'.

El anterior código puede compilarse:

```bash
$ javac Precio.java
```

generando el archivo de bytecodes __Precio.class__. Este archivo no es directamente ejecutable por el intérprete, ya que el código fuente no incluye ningún método principal (main). Para poder probar el código anterior, puede construirse otro archivo con el código fuente que se muestra a continuación:

```java
/**
* Ejemplo de uso de la clase Precio
* Jonay Garcia
*/
public class PruebaPrecio {
    public static void main (String [] args ) {
        Precio p;         // Crea una referencia de la clase Precio
        p = new Precio(); // Crea el objeto de la clase Precio
        p.setEuros(56.8); // Llamada al metodo setEuros quee asigna 56.8 al atributo euros
        System.out.println("Valor = " + p.da()); // Llamada al metodo get Euros
                                                 // que devuelve el valor de euros

        Precio q = new Precio();  // Crea una referencia y el objeto de la clase Precio
        q.euros = 75.6;           // Asigna 75.6 al atributo euros
        System.out.println("Valor = " + q.euros);
    }
}
```

Representación gráfica del espacio de la memoria utilizado por las referencias e instancias de la clase _Precio_ durante la ejecución del método _main()_ de la clase _PruebaPrecio_:

![img_02][img_02]


El código anterior puede compilarse y ejecutarse monstrando la siguiente salida por pantalla:

```bash
$ javac PruebaPrecio.java
$ java PruebaPrecio
Valor = 56.8
Valor = 75.6
```

### Explicación del código anterior

Para poder trabajar con objetos se tendrá que seguir un proceso de dos pasos. Lo primero que debe hacer el programa es crear una referencia o puntero de la clase _Precio_ con el identificador _p_. De forma similar a cómo se declara una variable de un tipo primitivo, la declaración del identificador de la referencia se realiza con la sintaxis:

```java
Precio p;
```

Creación de la referencia _p_:

![img_03][img_03]

La referencia o puntero, p, tiene como misión almacenar la dirección de memoria de (apuntar
a) los componentes de la instancia que todavía no ha sido creada ni referenciada. En este momento se dice que la referencia p, recien creada, almacena una dirección de memoria nula (que no corresponde a objeto alguno) o null. El segundo paso del proceso para trabajar con objetos lleva a la creación de una nueva instancia referenciada por p, que se realiza con la sentencia:

```java
p = new Precio();
```

Creación de la nueva instancia de la clase _Precio_ referenciado por _p_:

![img_04][img_04]

A esta operación se le denomina también instanciación. Aunque las dos operaciones anteriores (creación de la referencia y creación de la instancia referenciada) pueden realizarse  conjuntamente en la misma línea de código:

```java
Precio q = new Precio();
```

Creación de la referencia _q_ y de la nueva instancia de la clase _Precio_ referenciado por q:

![img_05][img_05]

El resultado de la ejecución del código anterior son dos nuevas instancias de la clase _Precio_ referenciados respectivamente por _p_ y _q_. El atributo euros de cada una de las nuevas instancias de la clase Precio es accesible a través del identificador de la referencia y del operador punto (_p.euros_ y _q.euros_). Los métodos da y pone pertenecientes a la clase _Precio_ son accesibles a través del identificador de la referencia y del operador punto:

_p.getEuros()_ y _p.setEuros(56.8)_ y _q.getEuros()_ y _q.setEuros(75.6)_ respectivamenteamente.

En el caso de los métodos, la instancia mediante la cual se realiza la llamada correspondiente actúa como un parámetro o argumento implícito del método.

Si se asigna una referencia a otra mediante una sentencia de asignación, no se copian los valores de los atributos, sino que se tiene como resultado una única instancia apuntada por dos referencias distintas. Por ejemplo:

```java
q = p;
```

Resultado de la asignación de valores entre referencias:

![img_06][img_06]

En este caso ¿qué ocurre con la instancia referenciada previamente por q? Dicha instancia se queda sin referencia (inaccesible). Esto puede ser un problema en algunos lenguajes de programación, como es el caso de Pascal o de C, que utilizan variables dinámicas y que necesitan liberar explícitamente el espacio en memoria reservado para las variables que van a dejar de ser referenciadas. La gestión dinámica de la memoria suele ser una tarea engorrosa para el programador y muy dada a la proliferación de errores de ejecución. Para evitar tales inconvenientes, Java permite crear tantas instancias como se desee (con la única limitación de la memoria que sea capaz de gestionar el sistema), sin que el programador tenga que preocuparse de destruirlas o liberarlas cuando ya no se necesiten. El entorno de ejecución de Java elimina automáticamente las instancias cuando detecta que no se van a usar más (cuando dejan de estar referenciadas). A este proceso se le denomina recogida o recolección de basura (garbage collection).

## Modificadores de visibilidad

El modificador __public__ indica que la componente del método es accesible fuera del código
de la clase a la que pertenece el componente a través del operador punto. El modificador __private__ indica que el componente solamente es accesible a través de los métodos de la propia clase. El modificador __protected__ se verá posteriormente. En el siguiente código se declara el atributo euros con el modificador private:

```java
/**
 * Ejemplo de declaracion de la clase Precio
 * double getEuros() --> devuelve el valor almacenado en euros
 * void setEuros(double euros) --> almacena valor en euros
 * Jonay Garcia
*/
public class Precio {
    // Atributo o variable miembro
    private double euros;

    // Metodos
    public double getEuros() {
        return euros;
    }

    public void setEuros(double euros) {
        this.euros = euros;
    }
}
```

Gráficamente una clase puede representarse como un rectángulo según se muestra en la siguiente figura:

![img_07][img_07]

Si se construye otro código que intente utilizar directamente el atributo euros:

```java
/**
 * Ejemplo de uso de la clase PrecioPrivado
 * double getEuros() --> devuelve el valor almacenado en euros
 * void setEuros(double euros) --> almacena valor en euros
 * euros --> Atributo de acceso privado
 * Jonay Garcia
 */
public class PruebaPrecioPrivado {
    public static void main (String [] args ) {
        precioPrivado p = new precioPrivado(); // Crea instancia
        p.pone(56.8); // Asigna 56.8 a euros
   
        System.out.println("Valor = " + p.da());
        p.euros = 75.6;                             // Asigna 75.6 a euros - ERROR
        System.out.println("Valor = " + p.euros);   // Tambien ERROR
    }
}
```

se producirá un error de compilación:

```java
$ javac PruebaPrecioPrivado.java
pruebaPrecioPrivado.java:15: euros has private access in precioPrivado
p.euros=75.6;
^
pruebaPrecioPrivado.java:16: euros has private access in precioPrivado
System.out.println("Valor = " + p.euros);
                                 ^
```

ya que el atributo __euros__ sólo es accesible a través de los métodos de la clase __getEuros()__ y __setEuros()__.

La utilización del modificador __private__ sirve para implementar una de las características de
la programación orientada a objetos: el _ocultamiento de la información_ o __encapsulación__.

La declaración como público de un atributo de una clase no respeta este principio de ocultación de información. Declarándolos como privados, no se tiene acceso directo a los atributos del objeto fuera del código de la clase correspondiente y sólo puede accederse a ellos de forma indirecta a través de los métodos proporcionados por la propia clase. Una de las ventajas prácticas de obligar al empleo de un método para modificar el valor de un atributo es asegurar la consistencia de la operación. 

> __Nota__: Por ejemplo, un método que asigne valor al tributo __euros__ de un objeto de la clase __Precio__ puede garantizar que no se le asignará un valor negativo.

## this

El __this__ sirve para hacer referencia a un metodo o propiedad del objeto actual.

El __this__, en el caso anterior, se utiliza dentro del método __setEuros()__ para diferenciar la variable __euros__  pasada por parámetro del atributo __euros__ de la clase __Precio__, de esta manera tenemos 2 variables que se llaman igual pero con dos alcances diferentes, la pasada por parámetro solo tiene vida útil dentro del método mientras que __this.euros__ hasta que el objeto se destruya.

### ¿Donde se puede usar el this?

Puede referirse a cualquier miembro del objeto actual desde dentro de un método de instancia o un constructor. Si se intenta utilizar dentro de un _método estático_ dará el siguiente error:

```java
"Cannot use This in a static context"
```

> __Nota__: No se puede usar en un método que es estático ya que un método estático se puede acceder sin la instancia del objeto,  por lo que no podemos hacer referencia a propiedades o metodos que todavía no existen.

## Método toString()

El método __toString()__ nos permite mostrar la información completa de un objeto, es decir, el valor de sus atributos.

Este método también se hereda de __java.lang.Object__, por lo que deberemos sobrescribir este método. 

A continuación se muestra un ejemplo de uso del método toString():

```java
Public class Empleado() {

    // Atributos
    private String nombre;
    private String apellido;
    private int edad;
    
    // Métodos
    public Empleado(String nombre, String apellido, int edad) {
        this.nombre = nombre;
        this.apellido = apellido;
        this.edad = edad;
    }

    public String toString (){
        String mensaje = "El empleado se llama " + nombre + " " + apellido + " con " +
                         edad + " años " + "y un salario de " + salario;
        return mensaje;
    }
```

El mensaje lo configuramos nosotros como queramos.

Ejemplo práctico:

```java
public class EmpleadoApp {
 
    public static void main(String[] args) {
 
        //Creamos dos objetos distintos
        Empleado empleado1=new Empleado("Fernando", "Ureña", 23, 600);
        Empleado empleado2=new Empleado("Antonio", "Lopez", 28, 900);
        Empleado empleado3=new Empleado("Alvaro", "Perez", 19, 800);
 
        //Mostramos la informacion del objeto
        System.out.println(empleado1.toString());
        System.out.println(empleado2.toString());
        System.out.println(empleado3.toString());
    }
 
}
```

La salida del programa anterior es la siguiente:

```bash
El empleado se llama Fernando Ureña con 23 años y un salario de 600.0
El empleado se llama Antonio López con 28 años y un salario de 900.0
El empleado se llama Álvaro Pérez con 19 años y un salario de 800.0
``` 

## Constructores

Aunque en un principio pueda parecer lo contrario, un constructor no es en realidad un método estrictamente hablando. Un constructor es un elemento de una clase cuyo identificador coincide con el de la clase correspondiente y que tiene por objetivo obligar a y controlar cómo se inicializa una instancia de una determinada clase, ya que el lenguaje Java no permite que las variables miembro de una nueva instancia queden sin inicializar. Además, a diferencia de los métodos, los constructores sólo se emplean cuando se quiere crear una nueva instancia.

Por defecto toda clase tiene un constructor sin parámetros cuyo identificador coincide con el de la clase y que, al ejecutarse, inicializa el valor de cada atributo de la nueva instancia: los atributos de tipo primitivo se inicializan a 0 o false, mientras que los atributos de tipo objeto (referencia) se inicializan a null.

En el ejemplo de la clase _PruebaPrecio_, que utiliza una instancia de la clase _Precio_, la llamada al constructor se produce en la sentencia __p = new Precio();__. Mientras que la ejecución de new genera una nueva instancia y devuelve su dirección de memoria, la ejecución del constructor Precio() inicializa los valores de los atributos.

```java
public class PruebaPrecio {
    public static void main (String [] args ) {
        Precio p; // Crea una referencia de la clase Precio
        p = new Precio(); // Crea el objeto de la clase Precio y realiza
                          // una llamada al metodo constructor
                          
        // Resto del codigo ...
    }
}
```

### Declaración de un constructor

La declaración de un constructor diferente del constructor por defecto, obliga a que se le asigne el mismo identificador que la clase y que no se indique de forma explícita un tipo de valor de retorno. La existencia o no de parámetros es opcional. Por otro lado, la sobrecarga permite que puedan declararse varios constructores (con el mismo identificador que el de la clase), siempre y cuando tengan un tipo y/o número de parámetros distinto. Por ejemplo, para la clase Fecha se declaran dos constructores, el primero sin parámetros (por lo tanto se redefine el constructor por defecto) y el segundo con tres parámetros:

```java
/**
 * Declaracion de la clase Fecha
 * @author Jonay Garcia
 */
public class Fecha {
    // Atributos o variables miembro
    private int dia;
    private int mes;
    private int anho;
    
    /**
     * Constructor 1
     * Asigna los valores 1, 1 y 2000 a los atributos
     * dia, mes y anho respectivamente
     */
    public Fecha() {
        dia = 1;
        mes = 1;
        anho = 2000;
    }

    /**
     * Constructor 2
     * @param ndia el dia del mes a almacenar
     * @param nmes el mes del anho a almacenar
     * @param nanho el anho a almacenar
     */
    public Fecha(int ndia, int nmes, int nanho) {
        dia = ndia;
        mes = nmes;
        anho = nanho;
    }
    
    public String toString() {
        return dia + "/" + mes + "/" + anho;
    }
}
```

La sobrecarga permite que puedan declararse varios constructores (con el mismo identificador que el de la clase), siempre y cuando tengan un tipo y/o número de parámetros distinto.

Para probar el código anterior, se construye el siguiente programa:

```java
/**
* Ejemplo de uso de la clase Fecha
* Jonay Garcia
*/
public class PruebaFecha {
    
    public static void main (String [] args) {
        Fecha origen = new Fecha();
        Fecha actual = new Fecha(16,2,2009);
        System.out.println("Primera fecha: " + origen.toString());
        System.out.println("Segunda fecha: " + actual.toString());
    }
}
```

Resultado de la ejecución de los respectivos constructores para las nuevas instancias referenciadas por origen y actual:

![img_08][img_08]

El código anterior puede compilarse y ejecutarse, mostrando la siguiente salida por pantalla:

```java
$ javac PruebaFecha.java
Primera fecha: 1/1/2000
Segunda fecha: 16/2/2009
```

> __Nota__: una vez construido un constructor ya no se puede emplear el constructor por defecto sin parámetros. Si se desea trabajar con él, es necesario declararlo explícitamente.

### Más sobre la declaración y uso de varios constructores

Un constructor sólo puede ser llamado por otros constructores o por métodos de clase (static). En el siguiente código se muestra un ejemplo de cómo se declaran dos constructores CuentaBancaria: el primero no tiene parámetros y hace una llamada al segundo constructor, que tiene un parámetro numérico real.

```java
/**
 * Declaracion de la clase CuentaBancaria
 * Ejemplo de declaracion de variables
 * metodos estaticos y uso de this
 * @author Jonay Garcia
 */

public class CuentaBancaria {

    // Atributos o variables miembro
    private double saldo;
    public static int totalCuentas=0;
    
    // Métodos
    public CuentaBancaria( ) {
        this(0.0); // Llamada al constructor que tiene un parametro
    }

    public CuentaBancaria( double ingreso ) {
        saldo = ingreso;
        incCuentas();
    }

    public double saldo() {
        return saldo;
    }

    public static void incCuentas () {
        totalCuentas++;
    }

    public void transferencia( CuentaBancaria origen ) {
        saldo += origen.saldo;
        origen.saldo=0;
    }
}
```

La sentencia __this(0.0);__ en el primer constructor realiza la llamada el segundo constructor. Ejemplo de programa que emplea la clase _CuentaBancaria_:

```java
/**
 * Ejemplo de uso de la clase CuentaBancaria
 * Jonay Garcia
 */
public class PruebaCuentaBancaria {

    public static void main (String [] args) {
        System.out.println("Total cuentas: " + CuentaBancaria.totalCuentas);
        CuentaBancaria c1;
        c1 = new CuentaBancaria();
        System.out.println("Nueva cuenta con: " + c1.saldo() + " euros");
        System.out.println("Total cuentas: " + CuentaBancaria.totalCuentas);
        CuentaBancaria c2;
        c2 = new CuentaBancaria(20.0);
        System.out.println("Nueva cuenta con: " + c2.saldo() + " euros");
       System.out.println("Total cuentas: " + CuentaBancaria.totalCuentas);
    }
}
```

La ejecución del código anterior origina la siguiente salida por pantalla:

```bash
$ java PruebaCuentaBancaria
Total cuentas: 0
Nueva cuenta con: 0.0 euros
Total cuentas: 1
Nueva cuenta con: 20.0 euros
Total cuentas: 2
```

[img_01]: ../img/ut09/01.png "Clase Precio"
[img_02]: ../img/ut09/02.png "Referencia a objetos"
[img_03]: ../img/ut09/03.png "Referencia a objetos"
[img_04]: ../img/ut09/04.png "Referencia a objetos"
[img_05]: ../img/ut09/05.png "Referencia a objetos"
[img_06]: ../img/ut09/06.png "Referencia a objetos"
[img_07]: ../img/ut09/07.png "Clase Precio"
[img_08]: ../img/ut09/08.png "Referencia a objetos"

