# Sentencias Condicionales y Bucles

Objetivos:

* Describir el funcionamiento de las sentencias selectivas o condicionales (if-else y switch).
* Interpretar el resultado de una secuencia de sentencias condicionales combinadas.
* Codificar una tarea sencilla convenientemente especificada, utilizando la secuencia y combinación de sentencias condicionales.

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

[img_01]: ../img/ut05/01.png "Sentencia if-else"
