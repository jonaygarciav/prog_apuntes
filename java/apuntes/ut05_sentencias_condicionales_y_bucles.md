# Sentencias Condicionales y Bucles

Objetivos:

* Describir el funcionamiento de las sentencias selectivas o condicionales (if-else y switch).
* Interpretar el resultado de una secuencia de sentencias condicionales combinadas.
* Codificar una tarea sencilla convenientemente especificada, utilizando la secuencia y combinación de sentencias condicionales.
* Describir el funcionamiento de las sentencias iterativas o bucles (for, while y dowhile)
* Interpretar el resultado de una secuencia simple o combinada de sentencias de control
* Codificar una tarea sencilla convenientemente especificada, utilizando la secuencia y combinación de sentencias iterativas y condicionales.

## Sentencias de control del flujo de un programa

Sin sentencias de control del flujo, el intérprete ejecuta las sentencias conforme aparecen en el programa de principio a fin. Las sentencias de control de flujo se emplean en los programas para ejecutar sentencias condicionalmente, repetir un conjunto de sentencias o, en general, cambiar el flujo secuencial de ejecución.

### Sentencia if-else

La instrucción if ... else permite controlar qué procesos tienen lugar, típicamente en función del valor de una o varias variables, de un valor de cálculo o booleano, o de las decisiones del usuario.

Sintaxis de la instrucción _if_:

```java
if (expresionLogica) {
    sentencia_1;
}
```

Sintaxis de la instrucción _if_ con la cláusula _else_:

```java
if (expresionLogica) {
    sentencia_1;
}
else {
    sentencia_2;
}
```

En el ejemplo anterior, primero se evalúa _expresionLogica_. Si el resultado es _true_, se ejecuta __sentencia_1__, si el resultado es _false_, se ejecuta __sentencia_2__. La _expresionLogica_ debe ir entre paréntesis. Las llaves sólo son obligatorias si las sentencias son compuestas (las llaves sirven para agrupar varias sentencias simples).

La cláusula _else_ no es obligatoria y sirve para indicar instrucciones a realizar en caso de no cumplirse la condición. 

![img_01][img_01]

Sintaxis:

```java
if (expresionLogica_1) {
    sentencia_1;
}
else if (expresionLogica_2) {
    sentencia_2;
}
else if (expresionLogica_3) {
    sentencia_3;
}
else {
    sentencia_4;
}
```

Ejemplo de uso de la sentencia if-else:

```java
/**
* Ejemplo de uso de la sentencia if-else
* Jonay Garcia
*/
public class NumeroMayor {
    public static void main (String [] args) {

        int a = 5;
        int b = 10;

        System.out.println("a vale " + 5);
        System.out.println("b vale " + 10);

        if (a > b) {
            System.out.println(”a es mayor que b");
        }
        else {
            System.out.println(”a no es mayor que b");
        }
    
    }
}
```

La salida del programa anterior es:

```bash
a vale 5
b vale 10
a no es mayor que b
```

#### Sentencia if-else con múltiples condiciones

Cuando se quieren evaluar distintas condiciones una detrás de otra, se usa la expresión __else if { }__. De este modo, la evaluación que se produce es: si se cumple la primera condición, se ejecutan ciertas instrucciones; si no se cumple, comprobamos la segunda, tercera, cuarta… n condición. Si no se cumple ninguna de las condiciones, se ejecuta el else final en caso de existir.

Ejemplo de uso de la sentencia if-else con múltiples sentencias:

```java
/**
* Ejemplo de uso de la sentencia if-else con multiples condiciones
* Jonay Garcia
*/
public class Caracter {
    public static void main (String [] args) {
        char c = 'a';

        if (c == 'a') {
            System.out.println("Es la vocal a");
        }
        else if (c == 'e') {
            System.out.println("Es la vocal e");
        }
        else if (c == 'i') {
            System.out.println("Es la vocal i");
        }
        else if (c == 'o') {
            System.out.println("Es la vocal o");
        }
        else if (c == 'u') {
            System.out.println("Es la vocal u");
        }
        else {
            System.out.println("No es una vocal");
        }
        
    }
}
```

Ejemplos de ejecución del programa anterior:

```bash
Es la vocal a
```

## Sentencia Switch

Es una sentencia condicional multiramificada o de selección multiple: dependiendo del valor de una variable o expresion entera permite ejecutar una o varias sentencias de entre muchas. La expresión puede ser de un tipo ordinal (de tipo entero byte, short ó int o de tipo carácter char) pero no puede ser de un tipo real o de un tipo cadena.

Sintaxis:

```java
switch (expresion) {
    case valor_1: sentencias_1; break;
    case valor_2: sentencias_2; break;
    ...
    case valor_n: sentencias_n; break;
    [default: sentencias_x;]
}
```

Cada sentencia _case_ contiene un único valor distinto del de las demás sentencias case. A continuación del valor se introduce la sentencia o sentencias que se ejecutan en el caso de que el valor indicado coincida con el de la variable o expresión selector. Las sentencias que siguen a cada uno de los valores no se engloban entre llaves, pero suelen ir seguidas de un break.

Si la expresión no coincide con ningún valor se ejecuta la sentencia que sigue a default, aunque esta parte (default) no es obligatoria.

> __Nota__: Si no existe algún break, continua la ejecución de la siguiente opción hasta el siguiente break o hasta el final de la sentencia switch.

Ejemplo de uso de la sentencia switch:

```java
/**
* Ejemplo de uso de la sentencia switch
* Jonay Garcia
*/
public class Caracter {
    public static void main (String [] args) {
        char c = 'a';

        switch (c) {
            case 'a': System.out.println("Es la vocal a"); break;
            case 'e': System.out.println("Es la vocal e"); break;
            case 'i': System.out.println("Es la vocal i"); break;
            case 'o': System.out.println("Es la vocal o"); break;
            case 'u': System.out.println("Es la vocal u"); break;
            default: System.out.println("No es una vocal"); break;
        }
        
    }
}
```

Ejemplos de ejecución del programa anterior:

```bash
Es la vocal a
```

## Sentencias repetitivas o bucles

Los bucles, iteraciones o sentencias repetitivas modifican el flujo secuencial de un programa permitiendo la ejecución reiterada de una sentencia o sentencias. En Java hay tres tipos diferentes de bucles: for, while y do-while.

### Sentencia for

Un for permite la ejecución de un bloque de código delimitado entre llaves un número determinado de veces. La sintaxis de un bucle for es la siguiente:

```java
for (inicio; termino; iteracion)
    sentencia;
```

o si se desean repetir un conjunto sentencias:

```java
for (inicio; termino; iteracion) {
    sentencia_1;
    sentencia_2;
    sentencia_n;
}
```

Es un bucle o sentencia repetitiva que:

1. Ejecuta la sentencia de inicio.
2. Verifica la expresión booleana de término.
    a. si es cierta, ejecuta la sentencia entre llaves y la sentencia de iteración para volver a verificar la expresión booleana de término.
    b. si es falsa, sale del bucle.
    

Figura 6.1. Flujograma de la sentencia for

Las llaves sólo son necesarias si se quieren repetir varias sentencias, aunque se recomienda su
uso porque facilita la lectura del código fuente y ayuda a evitar errores al modificarlo.
Habitualmente, en la expresión lógica de término se verifica que la variable de control alcance un
determinado valor. Por ejemplo:
for (i = valor_inicial; i <= valor_final; i++) {
sentencia;
}
Es completamente legal en Java declarar una variable dentro de la cabecera de un bucle for.
De esta forma la variable (local) sólo tiene ámbito dentro del bucle. Ejemplo sencillo:
System.out.println("Tabla de multiplicar del 5");
for (int i =0 ; i <= 10; i++) {
System.out.println(5 + " * " + i + " = " + 5*i );
}
Salida por pantalla al ejecutar el código anterior:
5 * 0 = 0
5 * 1 = 5
5 * 2 = 10
5 * 3 = 15
5 * 4 = 20
5 * 5 = 25
5 * 6 = 30
5 * 7 = 35
5 * 8 = 40
5 * 9 = 45
5 * 10 = 50
A continuación se muestra un ejemplo completo de un programa que visualiza la tabla de
multiplicar del valor numérico entero introducido como parámetro de la línea de ejecución:
/**
* TablaProducto: Ejemplo de sentencia for
* Visualiza la tabla de multiplicar del valor introducido
* como parametro en la linea de comandos
* A. Garcia-Beltran, 16 de marzo de 2004
*/
public class TablaProducto {
public static void main (String [] args) {
int valor;
valor = Integer.parseInt(args[0]);
System.out.println("Tabla de multiplicar del numero " + valor);
for (int i=1; i<=10; i++) {
System.out.println(valor + " * " + i + " = " + valor*i );
}
}
 Programación orientada a objetos con Java 73
}
Salida por pantalla al ejecutar: $>java TablaProducto 4
Tabla de multiplicar del numero 4
4 * 1 = 4
4 * 2 = 8
4 * 3 = 12
4 * 4 = 16
4 * 5 = 20
4 * 6 = 24
4 * 7 = 28
4 * 8 = 32
4 * 9 = 36
4 * 10 = 40
Puede incluirse un bucle for dentro de otro (bucles for anidados), por ejemplo:
System.out.println("Tablas de multiplicar del 1, 2 y 3");
for (int i=1; i<=3; i++) {
System.out.println("Tabla de multiplicar del " + i);
for (int j=0; j<=10; j++) {
System.out.println(j + " * " + i + " = " + j*i );
}
}
O como en el siguiente programa completo:
/**
* Doblefor: Ejemplo de sentencias for anidadas
* Visualiza por pantalla una cadena que almacena
* valores numericos enteros
* A. Garcia-Beltran, 16 de marzo de 2004
*/
public class Doblefor {
public static void main (String [] args ) {
String s="";
for (int i=0 ; i<10; i++) {
s=s+i+" ";
for (int j=0 ; j<10; j++) {
s=s+" "+i+j;
}
s=s+"\n";
}
System.out.println(s);
}
}
Salida por pantalla al ejecutar: $>java DobleFor
0 00 01 02 03 04 05 06 07 08 09
1 10 11 12 13 14 15 16 17 18 19
2 20 21 22 23 24 25 26 27 28 29
3 30 31 32 33 34 35 36 37 38 39
4 40 41 42 43 44 45 46 47 48 49
5 50 51 52 53 54 55 56 57 58 59
6 60 61 62 63 64 65 66 67 68 69
7 70 71 72 73 74 75 76 77 78 79
8 80 81 82 83 84 85 86 87 88 89
9 90 91 92 93 94 95 96 97 98 99
74  A. García-Beltrán y J.M. Arranz
Por otro lado, tanto la sentencia de inicio como la de iteración pueden componerse de varias
sentencias separadas por comas. Por ejemplo:
for (int i = 0, j = 10 ; i <= 10; i++, j--) {
// . . .
}
la anterior sentencia es equivalente a:
int j = 10;
for (int i = 0; i <= 10; i++) {
// . . .
j--;
}
6.2. Sentencia while
Es un bucle o sentencia repetitiva con una condicion al principio. Se ejecuta una sentencia
mientras sea cierta una condición. La sentencia puede que no se ejecute ni una sola vez.
Sintaxis:
[inicializacion;]
while (expresionLogica) {
sentencias;
[iteracion;]
}
Figura 6.2. Flujograma de la sentencia while
Ejemplo de programa:
/**
* Ejemplo de sentencia while
* Calcula cuantos años deben pasar para duplicar una cantidad
* invertida a un determinado interes anual constante
* A. Garcia-Beltran - marzo, 2004
*/
public class Duplica {
public static void main (String [] args) {
double cantidadInicial=1;
 Programación orientada a objetos con Java 75
double cantidad=cantidadInicial;
double interes=4;
int anhos=0;
while (cantidad < 2*cantidadInicial) {
anhos++;
cantidad += cantidad*interes/100;
}
System.out.println("La cantidad inicial es = " + cantidadInicial);
System.out.println("El interes es = " + interes);
System.out.println("La cantidad final es = " + cantidad);
System.out.println("El numero de años es = " + anhos);
}
}
Ejemplo de ejecución y salida correspondiente por pantalla:
$>java Duplica
La cantidad inicial es = 1.0
El interes es = 4.0
La cantidad final es = 2.025816515378531
El numero de años es = 18.0
Por convención: El carácter de llave de apertura { se coloca al final de la misma línea de la sentencia
while. El carácter de llave de cierre } empieza una nueva línea y se alinea con la palabra while.
Otro ejemplo de programa que emplea la sentencia while
/**
* Ejemplo de sentencia while
* Visualiza los argumentos de la linea de comandos
* A. Garcia-Beltran - marzo, 2004
*/
public class Eco {
public static void main (String [] args ) {
int i=0; // Inicializa la variable de control
while (i < args.length) { // Mientras quede algun argumento
System.out.print(args[i] + " "); // Visualiza el argumento i-esimo
i++; // Incrementa la variable de control
}
System.out.println(); // Salto de linea
}
}
Ejemplo de ejecución y salida correspondiente por pantalla:
$>java Eco Esto es una prueba
Esto es una prueba
Se recuerda que el vector args contiene todos los parámetros o argumentos indicados en la línea
de comandos. El primer elemento de este vector es args[0]. El tamaño del vector puede determinarse
añadiendo .length a su identificador. Como el índice del primer elemento del vector es 0, si el tamaño
del vector es n, entonces el último elemento del vector tiene índice n-1. En el ejemplo anterior de
ejecución del programa eco, args[0] toma como valor la cadena "Esto", args[1] vale "es",
args[2] vale "una" y args[3] vale "prueba".
76  A. García-Beltrán y J.M. Arranz
6.3. Sentencia do-while
Es un bucle o sentencia repetitiva con una condicion al final. Se ejecuta una sentencia mientras sea
cierta una condición. En este caso, la sentencia se ejecuta al menos una vez.
Figura 6.3. Flujograma de la sentencia do/while
Sintaxis:
do {
sentencias;
[iteracion;]
} while (expresionLogica);
Ejemplo de programa:
/**
* Ejemplo de sentencia do-while
* Calcula cuantos años deben pasar para duplicar una cantidad
* invertida a un determinado interes anual constante
* A. Garcia-Beltran - marzo, 2004
*/
public class Duplica2 {
public static void main (String [] args) {
double cantidadInicial=1;
double cantidad=cantidadInicial;
double interes=5;
int anhos=0;
do
{
anhos++;
cantidad += cantidad*interes/100;
} while (cantidad < 2*cantidadInicial);
System.out.println("La cantidad inicial es = " + cantidadInicial);
System.out.println("El interes es = " + interes);
System.out.println("La cantidad final es = " + cantidad);
System.out.println("El numero de años es = " + anhos);
}
}
Ejemplo de ejecución y salida correspondiente por pantalla:
 Programación orientada a objetos con Java 77
$>java Duplica2
La cantidad inicial es = 1.0
El interes es = 5.0
La cantidad final es = 2.0789281794113683
El numero de años es = 15.0

[img_01]: ../img/ut05/01.png "Sentencia if-else"
