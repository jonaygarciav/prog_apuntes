# TIPOS PRIMITIVOS DE DATOS

## Objetivos

* Describir los operadores (aritméticos, incrementales, de relación, lógicos y de asignación) y los tipos de dato primitivos sobre los que actúan.
* Evaluar expresiones que empleen datos primitivos, operadores y paréntesis.
* Construir expresiones que empleen combinaciones de datos primitivos, operadores y paréntesis.

Un __operador__ lleva a cabo operaciones sobre uno (operador unario), dos (operador binario) o
tres (operador ternario) datos u operandos de tipo primitivo devolviendo un valor determinado
también de un tipo primitivo. El tipo de valor devuelto tras la evaluación depende del operador y del tipo de los operandos. Por ejemplo, los operadores aritméticos trabajan con operandos numéricos, llevan a cabo operaciones aritméticas básicas y devuelven el valor numérico  correspondiente. Los operadores se pueden clasificar en distintos grupos según se muestra en los siguientes apartados.

## Operador asignación

El operador asignación, =, es un operador binario que asigna el valor del término de la
derecha al operando de la izquierda. El operando de la izquierda suele ser el identificador de una variable. El término de la derecha es, en general, una expresión de un tipo de dato compatible; en particular puede ser una constante u otra variable. Como caso particular, y a diferencia de los demás operadores, este operador no se evalúa devolviendo un determinado valor.

| Operador | Descripción         | Ejemplo de expresión | Resultado del ejemplo |
|----------|---------------------|----------------------|-----------------------|
| =        | Operador asignación | n = 4                | n vale 4              |

No debe confundirse el operador asignación (=) con el operador relacional de igualdad (==)
que se verá más adelante. Además Java dispone de otros operadores que combinan la asignación con otras operaciones (operadores aritméticos combinados).

En el siguiente código se muestran algunos ejemplos de uso del operador asignación con
datos de distintos tipos:

```java
/**
 * Ejemplos de uso del operador asignación
*/
public class OperadorAsignacion {
    public static void main(String[] args) {
        // Declaración de variables
        int i,j;
        float x;
        double y;
        char c;
        boolean b;
        String s;
        
        // Asignación de valores
        i = 15;
        j = i;
        x = 335.57F;
        y = 12.345;
        c = 'A';
        b = false;
        s = "Hola";
        
        // Imprimir valor por pantalla
        System.out.println("i = " + i);
        System.out.println("j = " + j);
        System.out.println("x = " + x);
        System.out.println("y = " + y);
        System.out.println("c = " + c);
        System.out.println("b = " + b);
        System.out.println("s = " + s);
    }
}
```

Salida por pantalla del ejemplo anterior:

```bash
$ javac OperadorAsignacion.java
$ java OperadorAsignacion
i = 15
j = 15
x = 335.57
y = 12.345
c = A
b = false
s = Hola
```

## Operadores aritméticos

El lenguaje de programación Java tiene varios operadores aritméticos para los datos numéricos enteros y reales. En la siguiente tabla se resumen los siguientes operadores aritméticos:

| Operador | Descripción                        | Ejemplo de expresión | Resultado del ejemplo |
|----------|------------------------------------|----------------------|-----------------------|
| -        | operador unario de cambio de signo | -4                   | -4                    |
| +        | Suma                               | 2.5 + 7.1            | 9.6                   |
| -        | Resta                              | 235.6 - 103.5        | 132.1                 |
| \*       | Producto                           | 1.2 * 1.1            | 1.32                  |
| /        | División (tanto entera como real)  | 0.050 / 0.2          | 0.25                  |
|          |                                    | 7 / 2                | 3                     |
| %        | Resto de la división entera        | 20 % 7               | 6                     |


El resultado exacto depende de los tipos de operando involucrados. Es conveniente tener en cuenta las siguientes peculiaridades:

* El resultado es de tipo long si, al menos, uno de los operandos es de tipo long y ninguno es real (float o double).
* El resultado es de tipo int si ninguno de los operandos es de tipo long y tampoco es real (float o double).
* El resultado es de tipo double si, al menos, uno de los operandos es de tipo double.
* El resultado es de tipo float si, al menos, uno de los operandos es de tipo float y ninguno es double.
* El formato empleado para la representación de datos enteros es el complemento a dos. En la aritmética entera no se producen nunca desbordamientos (overflow) aunque el resultado sobrepase el intervalo de representación (int o long).
* La división entera se trunca hacia 0. La división o el resto de dividir por cero es una operación válida que genera una excepción ArithmeticException que puede dar lugar a un error de ejecución y la consiguiente interrupción de la ejecución del programa.
* La aritmética real (en coma flotante) puede desbordar al infinito (demasiado grande, overflow) o hacia cero (demasiado pequeño, underflow).
* El resultado de una expresión inválida, por ejemplo, dividir infinito por infinito, no genera una excepción ni un error de ejecución: es un valor __NaN__ (_Not a Number_).

```java
/**
 * Ejemplos de uso de los operadores aritméticos básicos
*/
public class OperadiresAritmeticos {
    public static void main(String[] args) {
        int i,j;
        i = 7;
        j = 3;

        System.out.println("OPERANDOS ENTEROS: i = " + i + " ; j = " + j);
        System.out.println("Operador suma: i + j = " + (i+j));
        System.out.println("Operador resta: i - j = " + (i-j));
        System.out.println("Operador producto: i * j = " + (i*j));
        System.out.println("Operador division: i / j = " + (i/j));
        System.out.println("Operador resto: i % j = " + (i%j));

        double a,b;        
        a = 12.5;
        b = 4.3;

        System.out.println("OPERANDOS REALES: a = " + a + " ; b = " + b);
        System.out.println("Operador suma: a + b = " + (a+b));
        System.out.println("Operador resta: a - b = " + (a-b));
        System.out.println("Operador producto: a * b = " + (a*b));
        System.out.println("Operador division: a / b = " + (a/b));
        System.out.println("Operador resto: a % b = " + (a%b));
    }
}
```

Salida por pantalla del programa anterior:

```bash
OPERANDOS ENTEROS: i = 7 ; j = 3
Operador suma    : i + j = 10
Operador resta   : i - j = 4
Operador producto: i * j = 21
Operador division: i / j = 2
Operador resto   : i % j = 1
OPERANDOS REALES : a = 12.5 ; b = 4.3
Operador suma    : a + b = 16.8
Operador resta   : a - b = 8.2
Operador producto: a * b = 53.75
Operador division: a / b = 2.906976744186047
Operador resto   : a % b = 3.9000000000000004
```

## Operadores aritméticos incrementales

Los operadores aritméticos incrementales son operadores unarios (un único operando). El operando puede ser numérico o de tipo char y el resultado es del mismo tipo que el operando. Estos operadores pueden emplearse de dos formas dependiendo de su posición con respecto al operando.

| Operador | Tipo        | Descripcion                                                           | Ejemplo de expresión | Resultado del ejemplo |
|----------|-------------|-----------------------------------------------------------------------|----------------------|-----------------------|
| ++       | Incremento  |                                                                       | 4++                  |                       |
|          |             | i++ primero se utiliza la variable y luego se incrementa su valor     | a = 5; b = a++;      | a vale 6 y b vale 5   |
|          |             | ++i primero se incrementa el valor de la variable y luego se utiliza  | a = 5; b = ++a;      | a vale 6 y b vale 6   |
| --       | Decremento  |                                                                       | 4++                  |                       |
|          |             | i-- primero se utiliza la variable y luego se incrementa su valor     | a = 5; b = a--;      | a vale 4 y b vale 5   |
|          |             | --i primero se incrementa el valor de la variable y luego se utiliza  | a = 5; b = --a;      | a vale 4 y b vale 4   |


Estos operadores suelen sustituir a veces al _operador asignación_ y también suelen aparecer en _bucles for_.

```java
/**
 * Ejemplo de uso de los operadores incrementales
*/
class OperadoresIncrementales {
    public static void main(String[] args) {
        int i,j; // Variables enteras. Podrian ser reales o char
        i = 7;

        System.out.println("Operando entero: i = " + i + ";");
        System.out.println("Operador ++: j = i++; ");
        
        j = i++;
        
        System.out.println("// i vale " + i + "; j vale " + j);
        
        i = 7;
        
        System.out.println("i = " + i + ";");
        System.out.println("j = ++i; ");
        
        j = ++i;
        
        System.out.println("// i vale " + i + "; j vale " + j);
        
        i = 7;
        
        System.out.println("\nOperando entero: i = " + i + ";");
        System.out.println("Operador --: j = i--; ");
        
        j = i--;
        
        System.out.println("// i vale " + i + "; j vale " + j);
        
        i = 7;
        
        System.out.println("i = " + i + ";");
        System.out.println("j = --i; ");
        
        j = --i;
        
        System.out.println("// i vale " + i + "; j vale " + j);
    }
}
```

Salida por pantalla del ejemplo anterior:

```bash
 Operando entero: i = 7;
 Operador ++    : j = i++;
 // i vale 8; j vale 7
 i = 7;
 j = ++i;
 // i vale 8; j vale 8

 Operando entero: i = 7;
 Operador --    : j = i--;
 // i vale 6; j vale 7
 i = 7;
 j = --i;
 // i vale 6; j vale 6
```

## Operadores aritméticos combinados

Combinan un operador aritmético con el operador asignación. Como en el caso de los operadores aritméticos pueden tener operandos numéricos enteros o reales y el tipo específico de resultado numérico dependerá del tipo de éstos. En la Tabla 4.4 se resumen los diferentes operadores de esta categoría.

| Operador | Descripción        | Ejemplo de expresión | Resultado del ejemplo |
|----------|--------------------|----------------------|-----------------------|
| +=       | Suma combinada     | a += b               | a = a+b               |
| -=       | Resta combinada    | a -= b               | a = a-b               |
| \*=      | Producto combinado | a \*= b              | a = a\*b              |
| /=       | División combinada | a /= b               | a = a/b               |
| %=       | Resto combinado    | a %= b               | a = a%b               | 

Ejemplo de programa que emplea operadores combinados:

```java
/**
 * Ejemplo de uso de los operadores aritmeticos combinados
 */
public class OperadoresCombinados {
    public static void main(String[] args) {
        int i,j; // Variables enteras. Podrian ser reales
        i = 7;
        j = 3;
        
        System.out.println("Operandos enteros: i = "+ i +" ; j = "+ j);
        i += j;
        System.out.println("Suma combinada: i += j " + " // i vale " + i);
        i = 7;
        i -= j;
        System.out.println("Resta combinada: i -= j " + " // i vale " + i);
        i = 7;
        i *= j;
        System.out.println("Producto combinado: i *= j " + " // i vale " + i);
        i = 7;
        i /= j;
        System.out.println("Division combinada: i /= j " + " // i vale " + i);
        i = 7;
        i %= j;
        System.out.println("Resto combinada: i %= j " + " // i vale " + i);
    }
}
```

Salida por pantalla del ejemplo anterior:

```bash
Operandos enteros : i = 7 ; j = 3
Suma combinada    : i += j // i vale 10
Resta combinada   : i -= j // i vale 4
Producto combinado: i *= j // i vale 21
Division combinada: i /= j // i vale 2
Resto combinada   : i %= j // i vale 1
```

## Operadores de relación

Realizan comparaciones entre datos compatibles de tipos primitivos (numéricos, carácter y booleanos) teniendo siempre un resultado booleano. Los operandos booleanos sólo pueden emplear los operadores de igualdad y desigualdad. En la Tabla 4.5 se resumen los diferentes operadores de esta categoría

| Operador | Descripción       | Ejemplo de expresión | Resultado del ejemplo |
|----------|-------------------|----------------------|-----------------------|
| ==       | igual que         | 7 == 38              | false                 |
| !=       | distinto que      | 'a' != 'k'           | true                  |
| <        | menor que         | 'G' < 'B'            | false                 |
| >        | mayor que         | 'b' > 'a'            | true                  | 
| <=       | menor o igual que | 7.5 <= 7.38          | false                 |
| >=       | mayor o igual que | 38 >= 7              | true                  |

Todos los valores numéricos que se comparan con _NaN_ dan como resultado _false_ excepto el operador _!=_ que devuelve _true_. Esto ocurre incluso si ambos valores son _NaN_.

Ejemplo de programa que emplea operadores relacionales:

```bash
/**
 * Ejemplo de uso de los operadores relacionales
*/
public class OperadoresRelacionales {
    public static void main(String[] args) {
        int i,j;
        i = 7;
        j = 3;
       
        System.out.println("OPERANDOS ENTEROS: i = "+ i +" ; j = "+ j);
        System.out.println("Operador igualdad: i == j es " + (i==j));
        System.out.println("Operador desigualdad: i != j es " + (i!=j));
        System.out.println("Operador mayor que: i > j es " + (i>j));
        System.out.println("Operador menor que: i < j es " + (i<j));
        System.out.println("Operador mayor o igual que: i >= j es " + (i>=j));
        System.out.println("Operador menor o igual que: i <= j es " + (i<=j));
    }
}
```

Salida por pantalla del programa anterior:

```bash
OPERANDOS ENTEROS         : i = 7 ; j = 3
Operador igualdad         : i == j es false
Operador desigualdad      : i != j es true
Operador mayor que        : i > j es true
Operador menor que        : i < j es false
Operador mayor o igual que: i >= j es true
Operador menor o igual que: i <= j es false
```
 
## Operadores lógicos o booleanos

Realizan operaciones sobre datos booleanos y tienen como resultado un valor booleano. 

| Operador | Descripción                           | Ejemplo de expresión | Resultado del ejemplo |
|----------|---------------------------------------|----------------------|-----------------------|
| !        | Negación - NOT (unario)               | !false               | true                  |
|          |                                       | !(5==5)              | false                 |
| \|       | Suma lógica – OR (binario)            | true \| false        | true                  |
|          |                                       | (5==5) \| (5<4)      | true                  |
| ^        | Suma lógica exclusiva – XOR (binario) | true ^ false         | true                  |
|          |                                       | (5==5) \| (5<4)      | true                  |
| &        | Producto lógico – AND (binario)       | true & false         | false                 |
|          |                                       | (5==5) & (5<4)       | false                 |
| \|\|     | Suma lógica con cortocircuito         | true \|\| false      | true                  |
|          |                                       | (5==5) \|\| (5<4)    | true                  |
| &&       | Producto lógico con cortocircuito     | false && true        | false                 |
|          |                                       | (5==5) && (5<4)      | false                 |
 
* __Suma lógica con corticircuito__: si el primer operando es _true_ entonces el segundo se salta y el resultado es _true_.
* __Producto lógico con cortocircuito__: si el primer operando es _false_ entonces el segundo se salta y el resultado es _false_.

Para mejorar el rendimiento de ejecución del código es recomendable emplear en las expresiones booleanas el operador '_&&_' en lugar del operador '_&_'. En este caso es conveniente situar la condición más propensa a ser falsa en el término de la izquierda. Esta técnica puede reducir el tiempo de ejecución del programa. De forma equivalente es preferible emplear el operador '\|\|' al operador '\|'. En este caso es conveniente colocar la condición más propensa a ser verdadera en el término de la izquierda.

```java
/**
 * Ejemplo de uso de los operadores lógicos
*/
public class OperadoresBooleanos {
    public static void main(String [] args) {
        System.out.println("Demostracion de operadores logicos");
        System.out.println("Negacion: ! false es : " + (! false));
        System.out.println(" ! true es : " + (! true));
        System.out.println("Suma: false | false es : " + (false | false));
        System.out.println(" false | true es : " + (false | true));
        System.out.println(" true | false es : " + (true | false));
        System.out.println(" true | true es : " + (true | true));
        System.out.println("Producto: false & false es : " + (false & false));
        System.out.println(" false & true es : " + (false & true));
        System.out.println(" true & false es : " + (true & false));
        System.out.println(" true & true es : " + (true & true));
    }
}
```

Salida por pantalla del programa anterior:

```bash
Demostracion de operadores logicos
Negacion: ! false es : true
          ! true es : false
Suma: false | false es : false
      false | true es : true
      true | false es : true
      true | true es : true
Producto: false & false es : false
          false & true es : false
          true & false es : false
          true & true es : true
```

## El operador condicional

Este operador ternario tomado de C/C++ permite devolver valores en función de una expresión lógica. Sintaxis:

    expresionLogica ? expresion_1 : expresion_2

Si el resultado de evaluar la expresión lógica es verdadero, devuelve el valor de la primera expresión, y en caso contrario, devuelve el valor de la segunda expresión.

| Operador | Descripción          | Ejemplo de expresión      | Resultado del ejemplo |
|----------|----------------------|---------------------------|-----------------------|
| ?:       | operador condicional | a = 4;                    |                       |
|          |                      | b = (a == 4 ? a+5 : 6-a;) | b vale 9              |
|          |                      | b = (a > 4 ? a*7 : a+8;)  | b vale 12             |

La sentencia de asignación:

    valor = (expresionLogica ? expresion_1 : expresion_2);

como se verá más adelante es equivalente a:

```java
if (expresionLogica)
    valor = expresion_1;
else
    valor = expresion_2
```

```java
/**
 * Ejemplo de uso del operador condicional.
*/
public class OperadorCondicional {
    public static void main(String[] args) {
        int i,j,k;
        i = 1;
        j = 2;
        k = i > j ? 2*i : 3*j+1;

        System.out.println("i = " + i);
        System.out.println("j = " + j);
        System.out.println("k = " + k);

        i = 2;
        j = 1;
        k = i > j ? 2*i : 3*j+1;

        System.out.println("i = " + i);
        System.out.println("j = " + j);
        System.out.println("k = " + k);
    }
}
```

Salida por pantalla del programa anterior:

```bash
i = 1
j = 2
k = 7
i = 2
j = 1
k = 4
```

## Operador concatenación de cadenas

El operador concatenación '+', es un operador binario que devuelve una cadena resultado de concatenar las dos cadenas que actúan como operandos. Si sólo uno de los operandos es de tipo cadena, el otro operando se convierte implícitamente en tipo cadena.

| Operador | Descripción            | Ejemplo de expresión | Resultado del ejemplo |
|----------|------------------------|----------------------|-----------------------|
| +        | Operador concatenación | “Hola” + “Juan”      | “HolaJuan”            |

## Separadores

Existen algunos caracteres que tienen un significado especial en el lenguaje Java.

| Separador | Descripción |
|-----------|-------------|
| ()        | Permiten modificar la __prioridad de una expresión__, contener expresiones para el control de flujo y realizar __conversiones de tipo__. Por otro lado pueden contener la __lista de parámetros o argumentos__, tanto en la definición de un método como en la llamada al mismo. |
| {}        | Permiten definir bloques de código y ámbitos y contener los valores iniciales de las variables array. |
| []        | Permiten declarar __variables de tipo array__ (vectores o matrices) y referenciar sus elementos
| ;         | Permite __separar sentencias__. |
| ,         | Permite __separar identificadores__ consecutivos en la declaración de variables y en las listas de parámetros. También se emplea para encadenar sentencias dentro de un __bucle for__. |
| .         | Permite __separar el nombre de un atributo o método__ de su instancia de referencia. También separa el identificador de un __paquete__ de los de los subpaquetes y clases.

## Expresiones

Una expresión es una combinación de operadores y operandos que se evalúa generándose un único resultado de un tipo determinado.

## Prioridad entre operadores

Si dos operadores se encuentran en la misma expresión, el orden en el que se evalúan puede determinar el valor de la expresión. En la siguiente tabla se muestra el orden o prioridad en el que se ejecutan los operadores que se encuentren en la misma sentencia. Los operadores de la misma prioridad se evalúan de izquierda a derecha dentro de la expresión.

| Prioridad | Operador    | Tipo de operador | Operación                                                      |
|-----------|-------------|------------------|----------------------------------------------------------------|
| 1         | ++          | Aritmético       | Incremento previo o posterior (unario)                         |
|           | --          | Aritmético       | Decremento previo o posterior (unario)                         |
|           | +, -        | Aritmético       | Suma unaria, Resta unaria                                      |
|           | ¡           | Booleano         | Negación (unario)                                              |
| 2         | (tipo)      | Cualquiera       |                                                                |
| 3         | *, /, %     | Aritmético       | Multiplicación, división, resto                                |
| 4         | +, -        | Aritmético       | Suma, resta                                                    |
|           | +           | Cadena           | Concatenacion de cadenas                                       |
| 5         | <, <=       | Aritmético       | Menor que, menor o igual que                                   |
|           | >, >=       | Aritmético       | Mayor que, mayor o igula que                                   |
|           | instanceof  | Objeto, tipo     | Comparación de tipos                                           |
| 6         | ==          | Primitivo        | Igual (valores idénticos)                                      |
|           | ¡=          | Primitivo        | Distinto (valores diferentes)                                  |
|           | ==          | Objeto           | Igual (referencia al mismo objeto)                             |
|           | ¡=          | Objeto           | Distinto (referencia a distintos objetos)                      |
| 7         | &           | Booleano         | Producto booleano                                              |
| 8         | ^           | Booleano         | Suma exclusiva booleana                                        |
| 9         | \|          | Booleano         | Suma booleana                                                  |
| 10        | &&          | Booleano         | AND condicional                                                |
| 11        | \|\|        | Booleano         | OR condicional                                                 |
| 12        | ? :         | Booleano         | Operador condicional (ternario)                                |
| 13        | =           | Variable         | Asignación                                                     |
| 14        | *=, /=, %=  | Variable         | Asignación con operación                                       |
|           | +=, -=      |                  |                                                                |
|           | <<=, >>=    |                  |                                                                |
|           | >>>=        |                  |                                                                |
|           | &=, ^=, \|= |                  |                                                                |
