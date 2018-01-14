# UT05. SENTENCIAS CONDICIONALES Y BUCLES

__Ejercicio 1__

Pedir un número por pantalla e indicar si es un número par o impar.

__Ejercicio 2__

Pedir dos números por pantalla e indicar cuál es mayor o si son iguales.

__Ejercicio 3__

Pedir dos números por pantalla y calcular la división. Controlar que, si el divisor es cero, imprimir un mensaje que diga: '_no puede dividirse un número entre cero_'.

> En matemáticas el resultado de dividir un número entre 0 es indefinido.

__Ejercicio 4__

Pedir una nota numérica de 0 a 10 y mostrarla de la siguiente forma: Insuficiente, Suficiente, Bien, Notabie y Sobresaliente:

* __Insuficiente__: de 0 a 5, sin contar el 5.
* __Suficiente__: de 5 a 6, sin contar el 6.
* __Bien__: de 6 a 7, sin contar el 7.
* __Notable__: de 7 a 9, sin contar el 9.
* __Sobresaliente__: de 9 a 10.

__Ejercicio 5__

Pedir una nota numérica entera entre 0 y 10, y mostrar dicha nota de la forma: cero, uno, dos, tres, cuatro, cinco, seis, siete, ocho, nueve y diez.

__Ejercicio 6__

Leer un número y mostrar su raíz cuadrada, repetir el proceso hasta que se introduzca un número negativo.

> Usar el método _sqrt()_ de la clase Math.

__Ejercicio 7__

Hacer un programa en Java que le dé al usuario la opción de calcular la raíz cuadrada de un número o calcular el cuadrado de un número. Para ello hay que hacer un pequeño menú que nos permita darle al usuario la opción de elegir qué operación quiere realizar:

1. Mostrar al usuario un listado con todas las operaciones que puede realizar.
2. Si el usuario elige la opción 1, el programa deberá pedir un número y calcular la raíz cuadrada.
3. Si el usuario elige la opción 2, el programa deberá pedir un número y calcular su cuadrado.
4. Si el usuario introduce un 0, saldremos del programa.
5. Si el usuario introduce un valor que no esté entre el 0 y el 2, debemos mostrar al usuario un mensaje de que el número indicado no es el correcto.
6. Repetir el proceso hasta que el usuario introduzca un 0.

Ejemplo de salida del programa:

```java
Menú
1.- Calcular la raíz cuadrada de un número.
2.- Calcular el cuadrado de un número.
0.- Salir.
Elija una opción: 1
Introduzca un numero: 9
La raíz cuadrada es: 3.0

Menú
1.- Calcular la raíz cuadrada de un número.
2.- Calcular el cuadrado de un número.
0.- Salir.
Elija una opción: 2
Introduzca un numero: 6
El cuadrado es: 36.0

Menú
1.- Calcular la raíz cuadrada de un número.
2.- Calcular el cuadrado de un número.
0.- Salir.
Elija una opción: 3
Opción incorrecta. Por favor, introduzca un valor entre 0 y 2.

Menú
1.- Calcular la raíz cuadrada de un número.
2.- Calcular el cuadrado de un número.
0.- Salir.
Elija una opción: 0
Gracias por utilizar este programa.
```

__Ejercicio 8__

Leer un número e indicar si es positivo o negativo. El proceso se repetirá  hasta que se introduzca un 0.

__Ejercicio 9__

Pedir un número por pantalla y calcular su tabla de multiplicar.

__Ejercicio 10__

Pedir un número por pantalla y calcular su factorial.

> El factorial de un entero positivo '_n_' se define como el producto de todos los números enteros positivos desde 1 (es decir, los números naturales) hasta '_n_'. Por ejemplo, para calcular el factorial de 5: 5! = 5\*4\*3\*2\*1 = 120.

__Ejercicio 11__

Crear un array de 10 enteros con los siguientes valores: 1, 524, 423, 825, 1524, 324, 899, 975, 775, 657. Indicar cuál es el valor más alto.

