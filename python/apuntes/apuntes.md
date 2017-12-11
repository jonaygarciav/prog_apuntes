# Apuntes de Python

## Introducción

__Python__ es un lenguaje de programación potente y fácil de aprender. Cuenta con estructuras de datos eficientes y de alto nivel y un enfoque simple pero efectivo a la programación orientada a objetos. La elegante sintaxis de Python y su tipado dinámico, junto con su naturaleza interpretada, hacen de éste un lenguaje ideal para scripting y desarrollo rápido de aplicaciones en diversas áreas y sobre la mayoría de las plataformas.

El intérprete de Python y la extensa biblioteca estándar están a libre disposición en forma binaria y de código fuente para las principales plataformas desde el sitio web de Python, [https://www.python.org/](https://www.python.org/), y puede distribuirse libremente. El mismo sitio contiene también distribuciones y enlaces de muchos módulos libres de Python de terceros, programas y herramientas, y documentación adicional.

El _intérprete de Python_ puede extenderse fácilmente con nuevas funcionalidades y tipos de datos implementados en C o C++ (u otros lenguajes accesibles desde C). Python también puede usarse como un lenguaje de extensiones para aplicaciones personalizables.

## Características de python

Python es fácil de usar, pero es un lenguaje de programación de verdad, ofreciendo mucha más estructura y soporte para programas grandes de lo que pueden ofrecer los scripts de Unix o archivos por lotes. Por otro lado, Python ofrece mucho más chequeo de error que C, y siendo un lenguaje de muy alto nivel, tiene tipos de datos de alto nivel incorporados como arreglos de tamaño flexible y diccionarios. Debido a sus tipos de datos más generales Python puede aplicarse a un dominio de problemas mayor que Awk o incluso Perl, y aún así muchas cosas siguen siendo al menos igual de fácil en Python que en esos lenguajes.

Python permite __separar nuestro programa en módulos__ que pueden reusarse en otros programas en Python. Viene con una gran colección de módulos estándar que podemos usar como base de nuestros programas programas, o como ejemplos para empezar a aprender a programar en Python. Algunos de estos módulos nos provienen de métodos: entrada/salida a archivos, llamadas al sistema, sockets, e incluso interfaces a sistemas de interfaz gráfica de usuario como Tk.

Python es un __lenguaje interpretado__, lo cual puede ahorrarte mucho tiempo durante el desarrollo ya que no es necesario compilar ni enlazar. El intérprete puede usarse interactivamente, lo que facilita experimentar con características del lenguaje, escribir programas descartables, o probar funciones cuando se hace desarrollo de programas de abajo hacia arriba. Es también una calculadora de escritorio práctica.

Python permite escribir programas __compactos y legibles__. Los programas en Python son típicamente más cortos que sus programas equivalentes en C, C++ o Java por varios motivos:

* Los tipos de datos de alto nivel permiten expresar operaciones complejas en una sola instrucción.
* La agrupación de instrucciones se hace por identación en vez de llaves de apertura y cierre.
* No es necesario declarar variables ni argumentos.

> __Nota__: El lenguaje recibe su nombre del programa de televisión de la BBC “Monty Python’s Flying Circus” y no tiene nada que ver con reptiles. Hacer referencias a sketches de Monty Python en la documentación no sólo esta permitido, ¡sino que también está bien visto!

## Intérprete de python

Por lo general, el intérprete de Python se instala en las máquinas con __S.O. Linux__ en la ubicación  __/usr/local/bin/python3.6__ y en máquinas con __S.O. Windows__  en la ubicación _C:\Users\arte\AppData\Local\Programs\Python\Python36-32\python.exe_

> __Nota__: El directorio donde se encuentra el intérprete debe encontrarse en el _PATH_, de lo contrario, habrá que especificar toda la ruta para arrancar el intérprete.


### Modo interactivo

Se dice que estamos usando el __intérprete en modo interactivo__, cuando los comandos son leídos desde una terminal. En este modo espera el siguiente comando con el prompt primario, usualmente tres signos mayor-que (>>>); para las líneas de continuación espera con el prompt secundario, por defecto tres puntos (...). Antes de mostrar el prompt primario, el intérprete muestra un mensaje de bienvenida reportando su número de versión y una nota de copyright:

```bash
$ python3.6
Python 3.6 (default, Sep 16 2015, 09:25:04)
[GCC 4.8.2] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
>
```

Ejemplo de ejecución de código Python a través del intérprete en modo interactivo:

```python
>>> hoy_es_domingo = True
>>> if hoy_es_domingo:
...     print("¡No olvides ir a misa!")
...
¡No olvides ir a misa!
```

Se puede salir del intérprete ingresando el carácter de fin de archivo (_Control-D en Unix_, _Control-Z en Windows_). Si esto no funciona, se puede salir del intérprete ejecutando el comando __: quit()__.

## Codificación del código fuente

Los archivos fuente de Python deben ser codificados en __UTF-8__. En esa codificación, los caracteres de la mayoría de los lenguajes del mundo pueden ser usados simultáneamente en literales, identificadores y comentarios, a pesar de que la biblioteca estándar usa solamente caracteres ASCII para los identificadores, una convención que debería seguir cualquier código que sea portable. Para mostrar estos caracteres correctamente, tu editor debe reconocer que el archivo está en UTF-8 y usar una tipografía que soporte todos los careacteres del archivo.

Para asegurarnos de que esto sea así debemos añadir la siguiente línea al principio de todos nuestros ficheros python:

```python
# -*- coding: utf-8 -*-

def main():
    print("¡Hola Mundo!")

if __name__ == '__main__':
    main()
```

## Programa principal

Se recomienda que el fichero principal en un programa Python tenga la siguiente estructura:

```python
# -*- coding: utf-8 -*-

def main():
    print("¡Hola Mundo!")

if __name__ == '__main__':
    main()
```

Los programas python se guardan con extensión __.py__. Si guardamos el código anterior en un fichero llamado __holamundo.py__ y lo ejecutamos obtenemos la siguiente salida:

```bash
$ python holamundo.py
¡Hola Mundo!
```

### Significado de if __name__ == “__main__”:


Esto está ligado al modo de funcionamiento del intérprete Python, cuando el intérprete lee un archivo de código, ejecuta todo el código que se encuentra en él. Todo módulo (archivo de código) en python tiene un atributo especial llamado \__name\__ que define el espacio de nombres en el que se está ejecutando. Es usado para identificar de forma única un módulo en el sistema de importaciones.

Por su parte \__main\__ es el nombre del ámbito en el que se ejecuta el código de nivel superior (tu programa principal).

El intérprete pasa el valor del atributo a '\__main\__' si el módulo se está ejecutando como programa principal (cuando lo ejecutas llamando al intérptrete en la terminal con python my_modulo.py, haciendo doble click en él, ejecutandolo en el intérprete interactivo, etc ).

Si el módulo no es llamado como programa principal, sino que es importado desde otro módulo, el atributo __name__ pasa a contener el nombre del archivo en si.

Es decir, si tienes un archivo llamado _mi_modulo.py_, si lo ejecutamos como programa principal el atributo \__name\__ será '\__main\__', si lo usamos importándolo desde otro modulo (import mi_modulo) el atributo \__name\__ será igual a 'mi_modulo'.

> __Nota__: Básicamente, lo que haces usando if \__name\__ == “\__main\__”: es ver si el módulo ha sido importado o no. Si no se ha importado (se ha ejecutado como programa principal) ejecuta el código dentro del condicional.

Una de las razones para hacerlo es que, a veces, se escribe un módulo (un archivo .py) que se puede ejecutar directamente, pero que alternativamente, también se puede importar y reutilizar sus funciones, clases, métodos, etc en otro módulo. Con esto conseguimos que la ejecución sea diferente al ejecutar el módulo directamente que al importarlo desde otro programa.

Para ver un ejemplo, crearemos un módulo al que llamaremos _mi_modulo.py_:

```python
def hacer_algo():
    print("algo")

if __name__ == "__main__":
    print('Ejecutando como programa principal')
    hacer_algo()
```

En la misma carpeta creamos otro módulo al que llamaremos _principal.py_:

```python
import mi_modulo

mi_modulo.hacer_algo()
```

Si ejecutas el script _mi_modulo.py_ directamente el valor de __name__ será '__main__' y se ejecutará lo que hay dentro del if \__name\__ == “\__main\__”: :

```bash
Ejecutando como programa principal
algo
```

Si ejecutamos el archivo _principal.py_ que usa _mi_modulo.py_ importándolo no se cumple la condición if \__name\__ == “\__main\__” por lo que no se ejecuta nada, solo la propia llamada a la función que hacemos desde el programa principal:

```bash
algo
```

Ahora vamos a cambiar el script _mi_modulo.py_ por:

```python
def hacer_algo():
    print("algo")
print('Ejecutando como programa principal')
hacer_algo()
```

Si lo ejecutamos como programa principal el resultado es el mismo que antes, pero si ejecutamos ahora _principal.py_ nos sale esto:

```bash
Ejecutando como programa principal
algo
algo
```

Lo que pasa es que al importar ejecutamos todo el código y se imprime:

```bash
Ejecutando como programa principal
algo
```

Luego al llamar a la función nos imprime:

```bash
algo
```

[Documentación oficial](https://docs.python.org/3/library/__main__.html) sobre este tema
