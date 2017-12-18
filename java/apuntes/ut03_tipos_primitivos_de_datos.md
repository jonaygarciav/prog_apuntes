# TIPOS PRIMITIVOS DE DATOS

## Objetivos

* Describir los tipos de datos primitivos (numéricos, booleano y de tipo carácter)
en el lenguaje de programación Java y su formato de representación.
* Escribir la declaración de constantes y variables de cualquiera de los tipos de datos primitivos
* Presentar el concepto de conversión y los distintos tipos de conversiones de datos de tipo primitivo en Java

Todo lenguaje de programación consta de elementos específicos que permiten realizar las operaciones básicas de la programación: tipos de datos, operadores e instrucciones o sentencias. En este apartado se introducen los distintos tipos de dato que pueden emplearse en la programación con Java. En concreto, se presentan los tipos primitivos en Java, así como las constantes y las variables.

En los capítulos sucesivos se mostrarán el resto de elementos básicos de programación, incluyendo otras estructuras de datos más complejas.

## Categorías de Tipos de Datos

Los tipos de datos utilizados en Java se pueden clasificar según diferentes categorías:

* De acuerdo con el tipo de información que representan. Esta correspondencia determina los valores que un dato puede tomar y las operaciones que se pueden realizar con él. Según este punto de vista, pueden clasificarse en:

    * __Datos de tipo primitivo__: Representan un único dato simple que puede ser de tipo _char_, _byte_, _short_, _int_, _long_, _float_, _double_ o _boolean_. Por ejemplo: ‘a’, 12345, 750.68, False,… Cada tipo de dato presenta un conjunto de valores o constantes literales.
    * __Variables referencia (Arrays, Clases, Interfaces, ...)__: Se implementan mediante un nombre o referencia (puntero) que contiene la dirección en memoria de un valor o conjunto de valores (por ejemplo, un objeto creado con new).

* Según cambie su valor o no durante la ejecución del programa. En este caso, se tienen:

    * __Variables__: sirven para almacenar datos durante la ejecución del programa; el valor asociado puede cambiar varias veces durante la ejecución del programa.
    * __Constantes o variables finales__: también sirven para almacenar datos pero una vez asignado el valor, éste no puede modificarse posteriormente.

* Según su papel en el programa. Pueden ser:

    * __Variables miembro de una clase__: Se definen dentro de una clase, fuera de los métodos. Pueden ser de tipos primitivos o referencias y también variables o constantes.
    * __Variables locales__: Se definen dentro de un método o, en general, dentro de cualquier bloque de sentencias entre llaves {}. La variable desaparece una vez finalizada la ejecución del método o del bloque de sentencias. También pueden ser de tipos primitivos o referencias.

A continuación se describen cada uno de estos tipos de dato.


## Tipos de Dato Primitivos en Java

A todo dato (constante, variable o expresión) le corresponde un tipo específico en Java. Como se ha indicado anteriormente un tipo de dato determina los valores que puedenasignarse a un dato, el formato de representación correspondiente y las operaciones que pueden realizarse con dicho dato.

En Java casi todo es un objeto. Existen algunas excepciones como, por ejemplo, los tipos primitivos, tales como int, char, etc., que no se consideran objetos y se tratan de forma especial. Java tiene un conjunto de tipos primitivos para representar datos enteros (cuatro tipos diferentes), para datos numéricos reales en coma flotante (dos tipos diferentes), para caracteres y para datos lógicos o booleanos. Cada uno de ellos tiene idéntico tamaño y comportamiento en todas las versiones de Java y para cualquier tipo de ordenador. Esto implica que no hay directivas de compilación condicionales y asegura la portabilidad de los programas a diferencia de lo que ocurre, por ejemplo, con el lenguaje de programación C.

> __Nota__: En otros lenguajes de programación el formato y tamaño de los tipos de dato primitivos puede depender de la plataforma o sistema operativo en la que se ejecute el programa. Sin embargo Java especifica el tamaño y formato de todos los tipos de dato primitivos para que el programador no tenga que preocuparse sobre las dependencias del sistema.

Por otro lado, a partir de estos tipos primitivos de dato pueden construirse otros tipos de datos compuestos como _arrays_, _clases_ e _interfaces_.

En la siguiente tabla se muestran los tipos de datos primitivos de Java con el intervalo de representación de valores que puede tomar y el tamaño en memoria correspondiente.

| Tipo     | Representación/Valor               | Tamaño (en bits) | Valor mínimo               | Valor máximo              | Ejemplos      |
|----------|------------------------------------|------------------|----------------------------|---------------------------|---------------|
| boolean  | true o false                       | 1                | N.A.                       | N.A.                      | false, true   |
| char     | Carácter Unicode                   | 16               | \u0000                     | \uFFFF                    | a, A, n. N, Ñ |
| byte     | Entero con signo                   | 8                | -128                       | 128                       | -20, 127      |
| short    | Entero con signo                   | 16               | -332768                    | 32767                     | -250, 2017    |
| int      | Entro con signo                    | 32               | -2147483648                | 2147483647                | 12534556      |
| long     | Entero con signo                   | 64               | -9223372036854775808       | 9223372036854775807       | 36854775808   |
| float    | Coma flotante de presición simple  | 32               | ±3.40282347E+38            | ±1.40239846E-45           | 0.0F          |
| double   | Coma flotante de presición doble   | 64               | ±1.79769313486231570E+308  | ±4.94065645841246544E-324 | 0.0. 0.0D     |

> __Nota__: Los tipos de datos _float_ y _double_ vienen definidos por la norma [IEEE 754](https://es.wikipedia.org/wiki/IEEE_coma_flotante), que es el estándard del IEEE para aritmética en coma flotante.

Los tipos de datos numéricos en Java no pueden representar cualquier número entero o real.

Por ejemplo, el tipo de dato entero _int_ tiene un intervalo de representación entre -2147483648 y 2147483647. Si se desea representar el valor correspondiente a la población mundial del planeta (más de 6 mil millones de habitantes) no puede hacerse con dato de tipo _int_.

Los datos de tipo double no tienen tanta limitación. Pueden alcanzar un valor del orden de 10<sup>308</sup>, pero tienen otro problema: la precisión. En concreto, el tipo double tiene una precisión de 15 dígitos significativos cómo se detallará más adelante.

### Literales o constantes literales de tipos de dato primitivos

Un __literal__, valor literal ó constante literal es una constante cuyo nombre o identificador es la representación escrita de su valor y tiene ya ese significado en el código fuente de un programa Java. Seguidamente se muestran algunos ejemplos de valores o constantes literales pertenecientes a los tipos primitivos que pueden utilizarse directamente en un programa fuente de Java.

Las _constantes literales booleanas_ son _false_ y _true_.

Las _constantes literales de tipo carácter_ aparecen entre comillas simples. Como ya se ha comentado anteriormente, los caracteres, cadenas e identificadores en Java se componen de caracteres pertenecientes al conjunto de caracteres Unicode (http://www.unicode.org). Un
dato de tipo caracter representa un único carácter. El formato de Unicode utiliza 16 bits (2 bytes) para poder codificar un total de 65536 caracteres diferentes que incluyen caracteres y símbolos procedentes de distintas lenguas del mundo. En este conjunto de caracteres encontramos letras mayúsculas (‘A’, ‘B’, ‘C’,...), letras minúsculas (‘a’, ‘b’, ‘c’,...), signos de puntuación (‘,’ ‘;’ ‘:’ ...), dígitos (‘0’, ‘1’, ‘2’,...), símbolos especiales (‘#’, ‘&’, ‘%’,...) y caracteres de control (tabulador, retorno de carro,...).

Hay algunos caracteres que pueden causar algún problema en el código fuente de un programa Java debido a que se utilizan para tareas específicas dentro del lenguaje. Por ejemplo, como se verá más adelante, el carácter correspondiente a las comillas dobles (") se emplea para delimitar una cadena de caracteres. Para solucionar este inconveniente es necesario escaparlo con el carácter '\':

```java
System.out.println("En un \"lugar\" de la Mancha");
```

El comando anterior generaría la siguiente salida:

```bash
En un "lugar" de la Mancha
```

Una __secuencia de escape__ es una serie de caracteres que comienza por el carácter '\' seguido de una letra, un conjunto de dígitos o la letra _u_ seguida de un conjunto de dígitos y que representa a un carácter. En este último caso, la secuencia de caracteres o secuencia de escape _\uxxx_ puede emplearse en cualquier lugar en un
programa de Java para representar un carácter Unicode, siendo xxxx una secuencia de cuatro dígitos hexadecimales.

A continuación se muestra una tabla de caracteres representados por una secuencia de escape:

| Secuencia de Escape | Valor                                                                         |
|---------------------|-------------------------------------------------------------------------------|
| \b                  | Retroceso o backspace (equivalente a \u0008)                                  |
| \t                  | Tabulador (equivalente a \u0009)                                              |
| \n                  | Nueva línea (equivalente a \u000A)                                            |
| \f                  | Salto de página (equivalente a \u000C)                                        |
| \r                  | Retorno de carro (equivalente a \u000D)                                       |
| \"                  | Doble comilla (equivalente a \u0022)                                          |
| \'                  | Comilla simple (equivalente a \u0027)                                         |
| \\\                 | Barra diagonal (equivalente a \u005C)                                         |
| \xxx                | Carácter correspondiente al valor octal xxx (donde x es un número del 0 al 7) |
| \uxxxx              | Carácter correspondiente al valor xxxx codificado según Unicode               |

Por ejemplo, la letra 'E' corresponde con el código Unicode 0045:

```java
System.out.println("\u0045n un \"lugar\" de la Mancha");
```

El comando anterior generaría la siguiente salida:

```bash
En un "lugar" de la Mancha
```

En la página [https://unicode-table.com/es](https://unicode-table.com/es) se pueden consultar los códigos unicode relacionados con los caracteres más comunes.

Aunque en realidad una cadena no es un tipo primitivo de Java pueden construirse constantes literales de cadenas de caracteres. Las constantes literales de cadenas de texto se indican entre comillas dobles. Por ejemplo:

```bash
"Hola, mundo" // Con comillas dobles: indica una cadena
```

Al construir una cadena de caracteres se puede incluir cualquier carácter Unicode excepto un
carácter de nueva línea. Si se desea incluir un salto de línea en una cadena de caracteres debe
utilizarse la __secuencia de escape__ _'\n'_.

Por ejemplo:

```java
System.out.println("Línea 1\nLínea 2");
```

El comando anterior generaría la siguiente salida:

```bash
Línea 1
Línea 2
```

Las __constantes enteras__ son secuencias de dígitos _octales_, _decimales_ o _hexadecimales_ en las que no se emplea el punto o coma decimal. Si comienza por un 0 indica un formato octal. Si comienza por un 0x ó 0X indica un formato hexadecimal. El resto se considera en formato decimal. Las constantes de tipo long se indican con una _'l'_ o una _'L'_ al final. Normalmente se emplea la _'L'_ para no confundir con el _'1'_ (uno). __Si no se indica ninguna de estas terminaciones Java supone que la constante es de tipo int__.

A continuación se muestran algunos ejemplos de _constantes enteras_:

* __34__: de tipo _int_, solo digitos.
* __-78__: de tipo _int_, digitos con signo negativo sin punto decimal.
* __034__: en octal (equivale al 28 decimal)
* __0x1C__: en hexadecimal (equivale al 28 decimal)
* __875L__: de tipo _long_

Las __constantes reales__ o en coma flotante se expresan con coma decimal y opcionalmente seguidos de un exponente. El valor puede finalizarse con una _'f'_ o una _'F'_ para indicar el formato float. __Si no se indica ninguna terminación Java supone que es un double__. Por ejemplo:

* __15.2__: valor con punto decimal, de tipo double.
* __15.2D__: el mismo valor de tipo double.
* __1.52e1__: el mismo valor de tipo double.
* __0.152E2__: el mismo valor de tipo double.
* __.8e10__: de tipo double
* __15.8f__: de tipo float
* __15.8F__: tambien de tipo float

Como se verá más adelante cada tipo de dato primitivo tiene una clase correspondiente (_Boolean_, _Character_, _Byte_, _Short_, _Integer_, _Long_, _Float_ y _Double_), llamadas __wrappers__, que definen también constantes y métodos útiles.

### Declaraciones de variables

Una __variable__ es un espacio de la memoria correspondiente a un dato cuyo valor puede modificarse durante la ejecución de un programa y que está asociado a un identificador. __Toda variable ha de declararse antes de ser usada en el código de un programa en Java__. En la declaración de una variable debe indicarse explícitamente el identificador de la variable y el tipo de dato asociado. El tipo de dato determina el espacio reservado en memoria, los diferentes valores que puede tomar la variable y las operaciones que pueden realizarse con ella. La declaración de una variable en el código fuente de un programa de Java puede hacerse de la siguiente forma:

    tipo_de_dato identificador_de_la_variable;

o bien, la declaración de múltiples variables (con los correspondientes identificadores separados por comas) del mismo tipo:

    tipo_de_dato ident_1, ident_2, . . . , ident_n;

Por ejemplo:

```java
int n;
double x, y;
``` 

En el primer ejemplo se declara 'n' como una variable de tipo int. En el segundo ejemplo se declaran dos variables 'x' e 'y' de tipo _double_. En Java una variable queda definida únicamente dentro del bloque de sentencias (entre llaves { } ) en el que ha sido declarada. De esta forma queda determinado su ámbito o alcance (scope) en el que puede emplearse.

El identificador elegido para designar una variable debe respetar las normas de construcción de identificadores de Java. Además, por convención:

* Los identificadores de las variables comienzan con una letra minúscula. Por ejemplo: n, x2, mes, clave, suma, ó nombre.
* Si el identificador es una palabra compuesta, las palabras restantes comienzan por una letra mayúscula. Por ejemplo: esDivisible.
* El carácter del subrayado puede emplearse en cualquier lugar del identificador de una variable pero suele emplearse para separar nombres en identificadores de constantes.

La declaración e inicialización de una variable de tipo primitivo puede realizarse de forma simultánea en la misma línea empleando el operador asignación '='. Por ejemplo:

    int n = 15;

Independientemente de haber inicializado o no, el valor asignado a la variable puede modificarse las veces que se quiera durante la ejecución del programa. También puede realizarse la declaración e inicialización de varias variables del mismo tipo primitivo en la misma línea separándolas por comas. Por ejemplo:

    double x = 12.5, y = 25.0;

En el caso de que no se inicialice explícitamente la variable, ésta toma el valor 0 si es numérica, false si es booleana y ‘\0’ si es de tipo carácter. Como se verá más adelante, la declaración de un objeto o instancia equivalente se realiza empleando la palabra __new__. Por ejemplo:

    Integer n = new Integer(15);


Esta declaración y el tipo de dato (clase) Integer se verá más adelante con detenimiento.

### Declaración de variables final o constantes

Las variables finales en Java son similares a las constantes empleadas en otros lenguajes de programación. Una vez inicializada una variable final su valor no puede ser modificado. La declaración de variables finales o constantes se realiza empleando la palabra reservada final antes del identificador del tipo de dato. Por ejemplo:

    final int MAXIMO = 15;

La asignación de valor se puede posponer en el código, aunque en ningún caso su valor puede modificarse una vez ha sido inicializada ya que se generaría un error. Ejemplo de inicialización posterior a la declaración de la constante:

```java
final int MAXIMO;
...
MAXIMO = 15;
```

Al igual que ocurre con las variables, el identificador elegido para designar una constante debe respetar las normas de construcción de identificadores de Java. Por convención:

* Los identificadores de las constantes se componen de letras mayúsculas. Por ejemplo: MAXIMO.
* El carácter de subrayado ( _ ) es aceptable en cualquier lugar dentro de un identificador, pero se suele emplear sólo para separar palabras dentro de los identificadores de las constantes. Por ejemplo: MAXIMO_VALOR.

### Conversiones entre tipos de dato

El proceso consiste en almacenar el valor de una variable de un determinado tipo primitivo en otra variable de distinto tipo. Suele ser una operación más o menos habitual en un programa y la mayoría de los lenguajes de programación facilitan algún mecanismo para llevarla a cabo. En cualquier caso, no todas las conversiones entre los distintos tipos de dato son posibles. Por ejemplo, en Java no es posible convertir valores booleanos a ningún otro tipo de dato y viceversa. Además, en caso de que la conversión sea posible es importante evitar la pérdida de información en el proceso.

En general, existen dos categorías de conversiones:

* De ensanchamiento o promoción. Por ejemplo: pasar de un valor entero a un real.
* De estrechamiento o contracción. Por ejemplo: pasar de un valor real a un entero.

Las conversiones de promoción transforman un dato de un tipo a otro con el mismo o mayor espacio en memoria para almacenar información. En estos casos puede haber una cierta pérdida de precisión al convertir un valor entero a real al desechar algunos dígitos significativos.

Las conversiones de promoción en Java se resumen en la Tabla 3.3:

| Tipo de origen | Tipo de destino                 |
|----------------|---------------------------------|
| byte           | short, int, long, float, double |
| short          | int, long, float, double        |
| char           | int, long, float, double        |
| int            | long, float, double             |
| long           | double                          |
| float          | float, double                   |
| double         | -                               |

Las conversiones de contracción son más comprometidas ya que transforman un dato de un tipo a otro con menor espacio en memoria para almacenar información. En estos casos se corre el riesgo de perder o alterar sensiblemente la información. Las conversiones de contracción en Java se resumen en la siguiente tabla

| Tipo de origen | Tipo de destino                     |
|----------------|-------------------------------------|
| byte           | char                                |
| short          | byte, char                          |
| char           | byte, short                         |
| int            | byte, short, char                   |
| long           | byte, short, char, int              |
| float          | byte, short, char, int, long        |
| double         | byte, short, char, int, long, float |

Tanto las conversiones de promoción como las de contracción se realizan por __asignación__, __promoción aritmética__ o __casting__.

#### Por asignación

Cuando una variable de un determinado tipo se asigna a una variable de otro tipo. Sólo admite conversiones de promoción. Por ejemplo: si 'n' es una variable de tipo int que vale 25 y 'x' es una variable de tipo double, entonces se produce una conversión por asignación al ejecutarse la sentencia:

    x = n;

La variable 'x' toma el valor 82.0 (valor en formato real). El valor de 'n' no se modifica.

#### Por promoción aritmética

Como resultado de una operación aritmética. Como en el caso anterior, sólo admite conversiones de promoción. Por ejemplo, si 'producto' y 'factor1' son variables de tipo double y 'factor2' es de tipo int entonces al ejecutarse la sentencia 

    producto = factor1 * factor2;

el valor de 'factor2' se convierte internamente en un valor en formato real para realizar la operación aritmética que genera un resultado de tipo double. El valor almacenado en formato entero en la variable factor2 no se modifica.

#### Con casting o "moldes"

Con operadores que producen la conversión entre tipos. Admite las conversiones de promoción y de contracción indicadas anteriormente. Por ejemplo: si se desea convertir un valor de tipo double a un valor de tipo int se utilizará el siguiente código:

    int n;
    double x = 82.4;

    n = (int) x;

la variable 'n' toma el valor 82 (valor en formato entero). El valor de 'x' no se modifica. El código fuente del siguiente programa ilustra algunas de las conversiones que pueden realizarse entre datos de tipo numérico.

```java
/**
 * Ejemplos de conversiones entre distintos tipos de datos numericos
 * Jonay García - Diciembre 2017
 */
public class Conversiones {
    public static void main (String [] args) {
        int a = 2;
        double b = 3.0;
        float c = (float) (200 * a / b + 5);

        System.out.println("Valor en formato float: " + c);
        System.out.println("Valor en formato double: " + (double) c);
        System.out.println("Valor en formato byte: " + (byte) c);
        System.out.println("Valor en formato short: " + (short) c);
        System.out.println("Valor en formato int: " + (int) c);
        System.out.println("Valor en formato long: " + (long) c);
    }
}
```

Ejemplo de compilación y ejecución del programa anterior y salida por pantalla correspondiente:

```bash
$ javac Conversiones.java
$ java Conversiones
Valor en formato float: 13338.333
Valor en formato double: 13338.3330078125
Valor en formato byte: 26
Valor en formato short: 13338
Valor en formato int: 13338
Valor en formato long: 13338
```

## La Clase Scanner

La clase __Scanner__ de Java provee métodos para leer valores de entrada de varios tipos y forma parte del paquete __java.util__. Los valores de entrada pueden venir de varias fuentes, ya sea desde teclado o desde fichero.

Para utilizar esa clase tenemos que crear primero un objeto de ella para poder invocar sus métodos. La siguiente declaración crea un objeto de la clase Scanner que lee valores de entrada del teclado.

    Scanner teclado = new Scanner(System.in);

El propósito de pasar a __System.in__ como argumento es conectar o establecer una relación entre el objeto tipo Scanner, con nombre teclado en la declaración anterior, y el objeto __System.in__, que representa el sistema estándar de entrada de información en Java. Si no se indica lo contrario, el teclado es, por omisión, el sistema estándar de entrada de información en Java.

Luego que se tenga un objeto de la clase Scanner asociado al sistema estándar de entrada _System.in_, llamamos, por ejemplo, su método __nextInt()__ para entrar un valor del tipo __int__. Para entrar otros valores de otros tipos de datos primitivos, se usan los métodos correspondientes como __nextByte()__ o __nextDouble()__.

| Método       |  Ejemplo                         |
|--------------|----------------------------------|
| nextByte()   | byte b = teclado.nextByte();     |
| nextDouble() | double d = teclado.nextDouble(); |
| nextFloat()  | float f = teclado.nextFloat();   |
| nextInt()    | int i = teclado.nextInt();       |
| nextLong()   | long l = teclado.nextLong();     |
| nextShort()  | short s = teclado.nextShort();   |
| next()       | String p = teclado.next();       |
| nextLine()   | String o = teclado.nextLine();   |


El método __next()__ sirve para leer una palabra sola, por ejemplo "Javier".

El método __nextLine()__ sirve para leer varias palabras, por ejemplo "Javier Rodríguez Medina".

Ejemplo de uso de la clase Scanner:

```java
import java.util.Scanner;

public class EntradaDatos {

	public static void main(String[] args) {
	
		//Se crea el lector
		Scanner sc = new Scanner(System.in);

		//Se pide un dato al usuario
		System.out.print("Por favor introduzca sun nombre: ");

		//Se lee el nombre con nextLine() que retorna un String con el dato
		String nombre = sc.nextLine();

		//Se pide otro dato al usuario
		System.out.print("Bienvenido " + nombre + ". Por favor, introduzca su edad: ");

		//Se guarda la edad directamente con nextInt()
		int edad = sc.nextInt();

		System.out.println("Gracias " + nombre + ", tienes " + edad + " años.");
		
		// Cerramos el lector
		sc.close();

	}

}
```
