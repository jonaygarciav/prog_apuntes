# UT09. Objetos y Clases

## Ejercicios

__Ejercicio 1__

Crear una clase llamada _Calculadora_ que contendrá los siguientes atributos:

* __valor1__: número entero.
* __valor2__: número entero.

Además tendrá los siguientes métodos:

* __calculaMultiplicacion()__: devuelve el resultado de multiplicar valor1 y valor2.
* __calculaDivision()__: devuelve el resultado de dividir valor1 y valor2.
* __calculaMedia()__: devuelve el resultado de calcular la media de valor1 y valor2.
* __valor1EsPar()__: devuelve un tipo booleano e indica si valor1 es par.
* __valor2EsPar()__: devuelve un tipo vooleano e indica si valor2 es par.
* __metodos set()__: métodos que permitan asignar un valor a las variables valor1 y valor2.
* __metodos get()__: métodos que permitan devolver el valor de las variables variables valor1 y valor2.

Crear un menú interactivo que permita elegir entre las siguientes opciones:

* Asignar valor a valor1.
* Asignar valor a valor2.
* Imprimir valores.
* Calcular Multiplicación.
* Calcular División.
* Calcular Media.
* Calcular si valor1 es par.
* Calcular si valor2 es par.

__Ejercicio 2__

Crea una clase llamada _Cuenta_ que tendrá los siguientes atributos: 

* __titular__: nombre del titular de la cuenta.
* __saldo__: cantidad en euros que contiene la cuenta.

Además tendrá los siguientes métodos:

* __ingresar(double cantidad)__: se ingresa una cantidad a la cuenta, si la cantidad introducida es negativa, no se hará nada.
* __retirar(double cantidad)__: se retira una cantidad a la cuenta, si restando la cantidad actual a la que nos pasan es negativa, la cantidad de la cuenta pasa a ser 0.
* __saldo()__: muestra el saldo de nuestra cuenta.

Crear un menú interactivo que permita elegir entre las siguientes opciones:

* ingresar efectivo.
* retirar efectivo.
* Mostrar saldo.

Realizar las siguientes acciones:

1. Ingresar 100€ en la cuenta.
2. Mostrar saldo.
3. Ingresar 50€ en la cuenta.
4. Retirar 125€ de la cuenta.
5. Retirar 75€ de la cuenta.
6. Mostrar saldo.

__Ejercicio 3__

Haz una clase llamada __Persona__ que siga las siguientes condiciones:

Sus atributos son: nombre, edad, sexo (H hombre, M mujer), peso y altura. No queremos que se accedan directamente a ellos. Piensa que modificador de acceso es el más adecuado, también su tipo. Si quieres añadir algún atributo puedes hacerlo.

Los métodos que se implementaran son:

* __calcularIMC()__: calculara si la persona esta en su peso ideal (peso en kg/(altura^2  en m)), si esta fórmula devuelve un valor menor que 20, la función devuelve un -1, si devuelve un número entre 20 y 25 (incluidos), significa que esta por debajo de su peso ideal la función devuelve un 0  y si devuelve un valor mayor que 25 significa que tiene sobrepeso, la función devuelve un 1. Te recomiendo que uses constantes para devolver estos valores.
* __esMayorDeEdad()__: indica si es mayor de edad, devuelve un booleano.
* __comprobarSexo(char sexo)__: comprueba que el sexo introducido es correcto. Si no es correcto, sera H. No sera visible al exterior.
* __metodos set()__: métodos que permiten asignar un valor a los atributos de la clase.
* __metodos get()__: métodos que permiten devolver el valor de los atributos de la clase.



* Métodos necesarios para modificar los atributos de la clase (métodos set).

Ahora, crea una clase ejecutable que haga lo siguiente:

* Crea 3 objetos de la clase anterior.
* Para cada objeto, deberá comprobar si esta en su peso ideal (18 de IMC), tiene sobrepeso (> 18 de IMC) o por debajo de su peso ideal (< 18 de IMC) con un mensaje.
* Indicar para cada objeto si es mayor de edad.
* Por último, mostrar la información de cada objeto.


## Ejercicios con constructores y método toString()

__Ejercicio 1__

Crear una clase llamada _Calculadora_ que contendrá los siguientes atributos:

* __valor1__: número entero.
* __valor2__: número entero.

Se implementarán los siguientes constructores:

* Un constructor vacío.
* Un constructor que inicialice los atributos valor1 y valor2.

Además tendrá los siguientes métodos:

* __calculaMultiplicacion()__: devuelve el resultado de multiplicar valor1 y valor2.
* __calculaDivision()__: devuelve el resultado de dividir valor1 y valor2.
* __calculaMedia()__: devuelve el resultado de calcular la media de valor1 y valor2.
* __valor1EsPar()__: devuelve un tipo booleano e indica si valor1 es par.
* __valor2EsPar()__: devuelve un tipo vooleano e indica si valor2 es par.
* __metodos set()__: métodos que permiten asignar un valor a las variables valor1 y valor2.
* __metodos get()__: métodos que permiten devolver el valor de las variables valor1 y valor2.
* __metodo toString()__: método que permite imprimir los atributos valor 1 y valor2.

A la hora de crear un objeto de tipo _Calculadora_, deberemos inicializar los valores de los atributos _valor1_ y _valor2_ a 0.

Crear un menú interactivo que permita elegir entre las siguientes opciones:

* Asignar valor a valor1.
* Asignar valor a valor2.
* Imprimir valores (utilizando el método toString()).
* Calcular Multiplicación.
* Calcular División.
* Calcular Media.
* Calcular si valor1 es par.
* Calcular si valor2 es par.

__Ejercicio 2__

Crea una clase llamada _Cuenta_ que tendrá los siguientes atributos: 

* __titular__: nombre del titular de la cuenta.
* __saldo__: cantidad en euros que contiene la cuenta.

Se implementarán los siguientes constructores:

* Un constructor vacío.
* Un constructor que inicialice los atributos titular y saldo.

Además tendrá los siguientes métodos:

* __ingresar(double cantidad)__: se ingresa una cantidad a la cuenta, si la cantidad introducida es negativa, no se hará nada.
* __retirar(double cantidad)__: se retira una cantidad a la cuenta, si restando la cantidad actual a la que nos pasan es negativa, la cantidad de la cuenta pasa a ser 0.
* __saldo()__: muestra el saldo de nuestra cuenta.
* __metodo toString()__: método que permite imprimir los atributos titular y saldo.

A la hora de crear un objeto de tipo Cuenta, deberemos inicializar los valores de los atributos _titular_ a vacío y _saldo_ a 0.

Crear un menú interactivo que permita elegir entre las siguientes opciones:

* ingresar efectivo.
* retirar efectivo.
* Mostrar saldo.

Realizar las siguientes acciones:

1. Ingresar 100€ en la cuenta.
2. Mostrar saldo.
3. Ingresar 50€ en la cuenta.
4. Retirar 125€ de la cuenta.
5. Retirar 75€ de la cuenta.
6. Mostrar saldo (utilizando el método toString()).

__Ejercicio 3__

Haz una clase llamada __Persona__ que siga las siguientes condiciones:

Sus atributos son: nombre, edad, sexo (H hombre, M mujer), peso y altura. No queremos que se accedan directamente a ellos. Piensa que modificador de acceso es el más adecuado, también su tipo. Si quieres añadir algún atributo puedes hacerlo.

Se implementarán los siguientes constructores:

* Un constructor vacío.
* Un constructor que inicialice los atributos nombre, edad, sexo, peso y altura.

Los métodos que se implementaran son:

* __calcularIMC()__: calculara si la persona esta en su peso ideal (peso en kg/(altura^2  en m)), si esta fórmula devuelve un valor menor que 20, la función devuelve un -1, si devuelve un número entre 20 y 25 (incluidos), significa que esta por debajo de su peso ideal la función devuelve un 0  y si devuelve un valor mayor que 25 significa que tiene sobrepeso, la función devuelve un 1. Te recomiendo que uses constantes para devolver estos valores.
* __esMayorDeEdad()__: indica si es mayor de edad, devuelve un booleano.
* __comprobarSexo(char sexo)__: comprueba que el sexo introducido es correcto. Si no es correcto, sera H. No sera visible al exterior.
* __metodos set()__: métodos que permiten asignar un valor a los atributos de la clase.
* __metodos get()__: métodos que permiten devolver el valor de los atributos de la clase.
* __toString()__: devuelve toda la información del objeto.

* Métodos necesarios para modificar los atributos de la clase (métodos set).

Ahora, crea una clase ejecutable que haga lo siguiente:

* Crea 3 objetos de la clase anterior.
* Para cada objeto, deberá comprobar si esta en su peso ideal (18 de IMC), tiene sobrepeso (> 18 de IMC) o por debajo de su peso ideal (< 18 de IMC) con un mensaje.
* Indicar para cada objeto si es mayor de edad.
* Por último, mostrar la información de cada objeto.
