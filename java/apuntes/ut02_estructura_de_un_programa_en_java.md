# UT02. ESTRUCTURA DE UN PROGRAMA EN JAVA

## Objetivos

* Describir la estructura del código fuente de una aplicación Java
* Presentar los conceptos de comentario y de identificador dentro del código fuente de un programa.

Esta unidad tiene como objecito mostrar dos elementos típicos del código fuente: los comentarios y los identificadores. La estructura de un programa de Java es similar a la de un programa de C/C++. Por su diseño, permite a los programadores de cualquier otro lenguaje leer código en Java sin mucha dificultad. Java emplea siempre la Programación Orientada a Objetos por lo que todo el código se incluye dentro de las clases. Aunque ya se explicarán detenidamente más adelante, las clases son combinaciones de datos (constantes y variables) y rutinas (métodos).

## La Clase Principal y el Método main

Un programa puede construirse empleando varias clases. En el caso más simple se utilizará
una única clase. Esta clase contiene el programa, rutina o método principal: __main()__ y en éste se incluyen las sentencias del programa principal. Estas sentencias se separan entre sí por caracteres de punto y coma.

La estructura de un programa simple en Java es la siguiente:

```java
public class ClasePrincipal {
    public static void main(String[] args) {
        sentencia_1;
        sentencia_2;
        // comentario_1
        ...
        sentencia_N;
    }
}
```

Ejemplo de un programa en Java llamado que muestra un mensaje por la pantalla del ordenador llamado __HolaMundo.java__:

```java
/**
 * La clase HolaMundo construye un programa que
 * muestra un mensaje en pantalla
 */
public class HolaMundo {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

Como se ha indicado anteriormente, en un programa de Java todo se organiza dentro de clases. En el ejemplo anterior, __HolaMundo__ es el nombre de la _clase principal_ y del archivo que contiene el código fuente. Todos los programas o aplicaciones independientes escritas en Java tienen un método main o principal que, a su vez, contiene un conjunto de sentencias.

### ¿Qué Significa cada Término de la Clase Principal?

La primera parte del programa corresponde a la _definición de la clase_:

* __public__: es un _modificador de acceso_ que determina quién puede acceder a las clases o propiedades y métodos de una clase.
* __class__: palabra reservada que se utiliza para definir una clase. Contiene un conjunto de propiedades y métodos que luego sirven de modelo o plantilla para crear objetos o instancias de esa clase.
* __Greeting__: es un identificador de clase, no una palabra reservada, que identifica a la clase pública que se ha creado.

Resumiendo, esta línea define una clase pública identificada como _HolaMundo_.

```java
public class HolaMundo {

}
```

La segunda parte del programa corresponde a la _definición del método main_:

* __public__: cada método en una clase puede ser _público_, _protegido_ o _privado_ dependiendo del nivel de acceso que el programador quiere darle. _public_ significa que el método puede ser accedido desde cualquier otro método que tenga una instancia de esta clase.
* __static__: un método puede ser de instancia o de clase. Un método no estático es un método de instancia (que necesita una instancia de la clase donde se declara para ser invocado) y un método estático es un método de clase (no necesita una instancia de la clase donde se declara para ser invocado).
* __void__: Los métodos pueden devolver algo, por ejemplo, un método que suma dos números, devuelve el resultado de la suma; pero hay métodos que no devuelven nada y que sólo ejecutan acciones. Dichos métodos se declaran con la palabra reservada _void_ (vacío) como tipo de retorno.
* __main()__: Es el nombre del método que la máquina virtual de Java busca para comenzar a ejecutar un programa. Siempre ha de llamarse _main_.
* __String__: Es una clase que define cadenas de caracteres. Gracias a la clase String, Java puede manipular textos.
* __StringString[]__: Cualquier clase que se declara con corchetes “[]”, quiere decir que lo que tienes no es una instancia de esa clase, sino un array de objetos de dicha clase. Por ejemplo, _String[] meses_ contendría los nombres de los meses del año. El método _main()_ de Java necesita un String[] porque el usuario de nuestro programa puede pasar _parámetros extra_ desde la línea de comando a nuestro programa. Esos parámetros, el programador los recibe a través de ese array.

```java
public static void main(String[] args) {

}
```

La tercera parte del código corresponde a las sentencias:

* __System.out.println()__: es una método contenido en la _API de Java SE_ que imprime por pantalla el texto que se le pasa entre paréntesis, en este caso imprimirá el mensaje _Hello World!_:

```java
System.out.println("Hello World!");
```

Documentación Oracle sobre [cómo crear la aplicación "Hello World!" en Java](https://docs.oracle.com/javase/tutorial/getStarted/application/)


## Elementos del Lenguaje Java

### Sentencias

Una __sentencia__ es una orden que se le da al programa para realizar una tarea específica, esta puede ser: mostrar un mensaje en la pantalla, declarar una variable (para reservar espacio en memoria), inicializarla, llamar a una función, etc. Las sentencias acaban con el carácter __;__. Este carácter separa una sentencia de la siguiente. Normalmente, las sentencias se ponen unas debajo de otras (una en cada línea), aunque sentencias cortas pueden colocarse en una misma línea. Algunos ejemplos de sentencias:

```java
int i=1;

import java.awt.*;

System.out.println("Mi primer programa");

rect.mover(10, 20);
```

> __Nota__: En el lenguaje Java, los caracteres __espacio en blanco__ se pueden emplear libremente. Como podremos ver en los siguientes ejemplos, es muy importante para la legibilidad de un programa la colocación de unas líneas debajo de otras empleando tabuladores. El editor del IDE nos ayudará a realizar esta tarea de manera automática sin apenas percibirlo.

### Bloques de código

Un __bloque__ de código no es más que una agrupación de sentenciasque están agrupados entre llaves __{ }__. En el ejemplo anterior __Saludo.java__, el conjunto de sentencias se reduce a tres sentencias, que llaman a los métodos predefinidos en Java __print__ y __println__ que permiten visualizar texto por el dispositivo de salida de datos (por defecto la pantalla).

Por el momento y hasta que se explique con detalle el concepto de clase, los ejemplos de
programa que se utilizarán constarán de una sóla clase en la que se declara el método main. Este método es el punto de arranque de la ejecución de todo programa en Java.

### Expresiones

Una __expresión__ es todo aquello que se puede poner a la derecha del operador de asignación __=__. Por ejemplo:

```java
x = 123;

y = (x+100)/4;

area = circulo.calcularArea(2.5);

Rectangulo r = new Rectangulo(10, 10, 200, 300);
```

* La primera expresión asigna un valor a la variable x.
* La segunda, realiza una operación aritmética y el resultado se asigna a la variable _y_.
* La tercera, es una llamada a una función miembro _calcularArea_ desde un objeto circulo de una clase determinada y el resultado se asigna a la variable _area_.
* La cuarta, reserva espacio en memoria para un objeto de la clase Rectangulo mediante la llamada a una función especial que tienen todas las clases denominada _constructor_.

### Comentarios

Un __comentario__ es un texto adicional que se añade al código para explicar su funcionalidad, bien a otras personas que lean el programa, o al propio autor como recordatorio. Los comentarios son una parte importante de la documentación de un programa. Los comentarios son ignorados por el compilador, por lo que no incrementan el tamaño del archivo ejecutable; se pueden por tanto, añadir libremente al código para que pueda entenderse mejor.

El primer tipo de comentarios son los __comentarios de una sola línea__. En ellos se utiliza la secuencia de caracteres __//__. El compilador ignora
todo lo que se incluya entre la secuencia de caracteres // y el final de la línea. Por ejemplo:

```java
// Este es un comentario estilo C++, llega al final de la linea
sentencia_1;
```

> __Nota__: La pareja de caracteres __//__ hay que escribirla sin dejar ningún espacio en blanco entre ellos.

El segundo tipo de comentarios son los __comentarios de múltiples líneas__. En ellos se utilizan las secuencias de caracteres __/*__ para abrir el comentario y __*/__ para cerrar el comentario. Por
ejemplo:

```java
/* En este otro comentario estilo C, el final
 lo indica la marca */
 sentencia_1;
```

> __Nota__: Los comentarios pueden incluir cualquier carácter válido en Unicode y no pueden anidarse.

Estos dos formatos de comentario se emplean para los denominados _comentarios de implementación_. Los _comentarios de implementación_ se utilizan en el programa fuente para resaltar código o para aclarar un desarrollo en particular.

Además, en Java existe un tercer tipo de comentario llamados __comentarios de documentación__ (_doc comments_) que facilita la generación de documentación en formato HTML al emplear algunas herramientas de documentación (por ejemplo, __javadoc__ incluida en el __Kit de Desarrollo de Java__). Los comentarios para la documentación se emplean para describir la especificación del código, desde una perspectiva independiente cómo se ha implementado y ser leido por desarrolladores que no tengan necesariamente el código fuente a la vista. Ejemplos de este tipo de comentarios:

```java
/** Comentario estilo javadoc, se incluye
automaticamente en documentacion HTML */
```

```java
/**
 * Muchos programadores
 * suelen incluir un asterisco
 * al principio de cada linea del
 * comentario para facilitar su lectura
 */
```

> __Nota__: Los _comentarios_ deberían contener sólo información relevante para la lectura y comprensión del programa. Todos los programas deben empezar por un comentario que describa el propósito general del programa.

Articulo de Oracle (en inglés) sobre [cómo escribir Doc Comments para la herramienta Javadoc](http://www.oracle.com/technetwork/articles/java/index-137868.html).

#### Convención para los comentarios al inicio de los programas

Todos los archivos fuente deberían comenzar con un comentario liste el nombre de la clase, información de la versión, fecha y el aviso de copyright:

```java
/**
* The HelloWorld program implements an application that
* simply displays "Hello World!" to the standard output.
*
* @author  Jonay García
* @version 1.0
* @since   22-01-2017
*/
public class HelloWorld {

   public static void main(String[] args) {
      // Immprime el texto Hello, World! en la salida estándar.
      System.out.println("Hello World!");
   }

}
```

A continuación se muestran algunas etiquetas (tags) que reconoce la _herramienta Javadoc_:

| Etiqueta  | Descripción                                 | Sintáxis           |
|----------|----------------------------------------------|--------------------|
| @author  | Añade el autor de una clase                  | _@author nombre_   |
| @version | Añade el número de la versión de la clase    | _@version version_ |
| @since   | Añade información de la creación de la clase | _@since fecha      |


### Identificadores

Los __identificadores__ son nombres que se les asignan a _variables_, _métodos_, _clases_, ..., en el código fuente de un programa. Los identificadores sólo existen en el código del programa fuente y no en el programa objeto (resultado de la compilación del programa fuente). Todo nuevo identificador que se emplee en un programa Java debe definirse previamente a su utilización. Las normas para la construcción de un identificador empleando el lenguaje de programación Java son las siguientes:

* Un identificador comienza por una letra, un carácter de subrayado ( _ ) o un carácter de dólar ($). Aunque no se recomienda emplear el carácter $, ya que el compilador suele utilizarlos de forma interna para crear identificadores propios.
* Los siguientes caracteres pueden ser también dígitos. Pero no pueden emplearse espacios en
blanco u otros caracteres como el signo de interrogación (?) o el signo del tanto por ciento
(%).
* No hay límite máximo de caracteres.
* En los identificadores del código fuente de un programa en Java se distinguen las mayúsculas de las minúsculas. Por ejemplo, las palabras _casa_, _CASA_ y _Casa_ son tres identificadores diferentes.
* Pueden incluir caracteres Unicode, con lo que se pueden emplear secuencias de escape
/uxxxx para representar estos caracteres.
* No puede emplearse el identificador de una variable o cualquier otro elemento del código
fuente del programa para otro ya existente en el mismo bloque. Excepción: variable miembro
y local con el mismo identificador.
* Existe una serie de palabras reservadas que no pueden emplearse como identificadores por
el programador en el código fuente para otros usos. Por ejemplo, la palabra double se
utiliza para definir un tipo de dato real y la palabra for se emplea para construir un tipo
determinado de bucle.

En la siguiente tabla se muestran las _palabras reservadas_ en Java.

| A-D      | D-I     | I-P         | P-T          | T-Z       |
|----------|---------|-------------|--------------|-----------|
| abstract | do      | implements  | protected    | throw     |
| boolean  | double  | import      | public       | throws    |
| break    | else    | instanceof  | rest         | transient |
| byte     | extends | int         | return       | true      |    
| case     | false   | interface   | short        | try       |
| catch    | final   | long        | static       | void      |
| char     | finally | native      | strictfp     | volatile  |
| class    | float   | new         | super        | while     |
| const*   | for     | null        | switch       | &nbsp;    |
| continue | goto*   | package     | synchronized | &nbsp;    |
| default  | if      | private     | this         | &nbsp;    |

Algunos de estos _identificadores reservados_ no tienen todavía uso en la implementación actual del lenguaje Java. En concreto, los identificadores marcados con un asterisco * no se utilizan actualmente.

Las palabras reservadas se pueden clasificar en las siguientes categorías:

* __Tipos de datos__: boolean, float, double, int, char.
* __Sentencias condicionales__: if, else, switch.
* __Sentencias iterativas__: for, do, while, continue.
* __Tratamiento de las excepciones__: try, catch, finally, throw.
* __Estructura de datos__: class, interface, implements, extends.
* __Modificadores y control de acceso__: public, private, protected, transient.
* __Otras__: super, null, this.

A continuación se muestran los nombre de métodos reservados en Java cuyo significado y utilización se explicará más adelante cuando se menciones la _clase predefinida Object_:

| A-E    | F-G      | H-N      | N-T       | W-Z    |
|--------|----------|----------|-----------|--------|
| clone  | finalize | hashCode | notifyAll | wait   |
| equals | getClass | notify   | toString  | &nbsp; |

#### Recomencaciones a la hora de escribir identificadores

Aunque la forma de escribir los identificadores en Java no está normalizada, a continuación
se dan algunas recomendaciones para la elección de estos identificadores:

* Todos los identificadores han de comenzar con una letra, el carácter subrayado ( _ ) o el carácter dollar ( $ ).
* Puede incluir, pero no comenzar por un número
* No puede incluir el carácter espacio en blanco
* Distingue entre letras mayúsculas y minúsculas
* No se pueden utilizar las plabras reservadas como identificadores

Además de estas restricciones, hay ciertas convenciones que hacen que el programa sea más legible, pero que no afectan a la ejecución del programa. La primera y fundamental es la de encontrar un nombre que sea significativo, de modo que el programa sea lo más legible posible. El tiempo que se pretende ahorrar eligiendo nombres cortos y poco significativos se pierde con creces cuando se revisa el programa después de cierto tiempo.


| Tipo de identificador	| Convención | 	Ejemplo |
|---------------------| ----------| ---------|
| Nombre de una clase | Comienza por letra mayúscula | String, Rectangulo, CinematicaApplet |
| Nombre de función	  | Comienza con letra minúscula | calcularArea, getValue, setColor     |
| Nombre de variable  |	comienza por letra minúscula | area, color, carSize                 |
| Nombre de constante | En letras mayúsculas         | PI, MAX_ANCHO                        |

__CamelCase__ es un estilo de escritura que se aplica a frases o palabras compuestas. El nombre se debe a que las mayúsculas a lo largo de una palabra en CamelCase se asemejan a las jorobas de un camello. El nombre _CamelCase_ se podría traducir como Mayúsculas/Minúsculas Camello.

Existen dos tipos de _CamelCase_:

* __UpperCamelCase__, cuando la primera letra de cada una de las palabras es mayúscula. Ejemplo: EjemploDeUpperCamelCase.
* __lowerCamelCase__, igual que la anterior con la excepción de que la primera letra es minúscula. Ejemplo: ejemploDeLowerCamelCase.

#### Convenciones para la Legibilidad del Programa Fuente

Aunque la definición exacta de la indentación (espacios vs tabuladores) no se especifica en el lenguaje Java, se recomienda emplear una secuencia de __cuatro espacios como unidad de indentación__.

Por otro lado se recomienda __evitar las lineas de más de 80 caracteres en el código fuente__ ya que no se manejan correctamente por muchos terminales y herramientas de edición.

