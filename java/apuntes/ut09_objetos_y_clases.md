# Objetos y Clases

## Objetivos

* Presentar el concepto de objeto, clase, atributo, método e instancia.
* Interpretar el código fuente de una aplicación Java donde aparecen implementados los conceptos anteriores.
* Construir una aplicación Java sencilla, convenientemente especificada, que emplee los conceptos anteriores.

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
        q.setEuros(75.6);        // Asigna 75.6 al atributo euros
        System.out.println("Valor = " + q.getEuros());
    }
}
```

El código anterior puede compilarse y ejecutarse monstrando la siguiente salida por pantalla:

```bash
$ javac PruebaPrecio.java
$ java PruebaPrecio
Valor = 56.8
Valor = 75.6
```

### Explicación del código anterior

Para poder trabajar con objetos se tendrá que seguir un proceso de dos pasos. Lo primero
que debe hacer el programa es crear una referencia o puntero de la clase Precio con el
identificador p. De forma similar a cómo se declara una variable de un tipo primitivo, la declaración del identificador de la referencia se realiza con la sintaxis


```java
Precio p;
```
La referencia o puntero, p, tiene como misión almacenar la dirección de memoria de (apuntar
a) los componentes de la instancia que todavía no ha sido creada ni referenciada. En este momento se dice que la referencia p, recien creada, almacena una dirección de memoria nula (que no corresponde a objeto alguno) o null. El segundo paso del proceso para trabajar con objetos lleva a la creación de una nueva instancia referenciada por p, que se realiza con la sentencia:

```java
p = new Precio();
```

A esta operación se le denomina también instanciación. Aunque las dos operaciones anteriores (creación de la referencia y creación de la instancia referenciada) pueden realizarse  conjuntamente en la misma línea de código:

```java
Precio q = new Precio();
```

El resultado de la ejecución del código anterior son dos nuevas instancias de la clase Precio referenciados respectivamente por p y q. El atributo euros de cada una de las nuevas instancias de la clase Precio es accesible a través del identificador de la referencia y del operador punto (p.euros y q.euros). Los métodos da y pone pertenecientes a la clase Precio son accesibles a través del identificador de la referencia y del operador punto:

p.getEuros() y p.setEuros(56.8) y q.getEuros() y q.setEuros(75.6) respectivamenteamente.

En el caso de los métodos, la instancia mediante la cual se realiza la llamada correspondiente actúa como un parámetro o argumento implícito del método.

Si se asigna una referencia a otra mediante una sentencia de asignación, no se copian los
valores de los atributos, sino que se tiene como resultado una única instancia apuntada por dos
referencias distintas. Por ejemplo:

```java
q = p;
```

En este caso ¿qué ocurre con la instancia referenciada previamente por q? Dicha instancia se
queda sin referencia (inaccesible). Esto puede ser un problema en algunos lenguajes de
programación, como es el caso de Pascal o de C, que utilizan variables dinámicas y que necesitan liberar explícitamente el espacio en memoria reservado para las variables que van a dejar de ser referenciadas. La gestión dinámica de la memoria suele ser una tarea engorrosa para el programador y muy dada a la proliferación de errores de ejecución. Para evitar tales inconvenientes, Java permite crear tantas instancias como se desee (con la única limitación de la memoria que sea capaz de gestionar el sistema), sin que el programador tenga que preocuparse de destruirlas o liberarlas cuando ya no se necesiten. El entorno de ejecución de Java elimina automáticamente las instancias cuando detecta que no se van a usar más (cuando dejan de estar referenciadas). A este proceso se le denomina recogida o recolección de basura (garbage collection).

## Modificadores de visibilidad

El modificador public indica que la componente del método es accesible fuera del código
de la clase a la que pertenece la componente a través del operador punto. El modificador private indica que la componente solamente es accesible a través de los métodos de la propia clase. El modificador protected se verá posteriormente. En el siguiente código se declara el atributo euros con el modificador private.


[img_01]: ../img/ut09/01.png "Clase Precio"



