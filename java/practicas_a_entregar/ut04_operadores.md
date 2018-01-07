# UT04. OPERADORES

## Práctica a Entregar

Tenemos dos jugadores y dos dados. El primer jugador realiza su tirada y lanza los dados. Posteriormente, el segundo jugador realiza su tirada y lanza de nuevo los dados. Mostrar la tirada más alta de las dos.

Cada dado puede tomar valores enteros comprendidos entre 1 y 6. El valor de cada uno de los dados ha de calcularse de manera aleatoria utilizando el método __Math.random()__.

Ejemplo de salida del programa:

```bash
El jugador 1 hace su lanzamiento:
Dado 1: 5
Dado 2: 6
El jugador 2 hace su lanzamiento:
Dado 1: 3
Dado 2: 4
La tirada más alta es 11.
```

```bash
El jugador 1 hace su lanzamiento:
Dado 1: 2
Dado 2: 1
El jugador 2 hace su lanzamiento:
Dado 1: 4
Dado 2: 6
La tirada más alta es 10.
```

__Opcional__: A parte de indicar cuál es la tirada más alta, indicar qué jugador ha realizado la tirada más alta, si el jugador 1 o el jugador 2, por ejemplo: 

```bash
Jugador 1 hace su lanzamiento:
Dado 1: 5
Dado 2: 6
Jugador 2 hace su lanzamiento:
Dado 1: 3
Dado 2: 4
La tirada más alta es 11.
El ganador es el jugador 1.
```

```bash
El jugador 1 hace su lanzamiento:
Dado 1: 2
Dado 2: 1
El jugador 2 hace su lanzamiento:
Dado 1: 4
Dado 2: 6
La tirada más alta es 10.
El ganador es el jugador 2.
```

Añadir el fichero _.gitignore_ en la raíz del proyecto y configurar Git en el proyecto:

```bash
# Mac OS
.DS_Store

# Eclipse project file
.settings/
.classpath
.project
bin/
```

> __Nota__: Recordar que sólo queremos subir la carpeta src/ y el fichero .gitignore a Github.

Crear un nuevo repositorio en Github y subir el programa.

Crear un fichero __README.md__ en la raíz del proyecto con una breve explicación del funcionamiento del programa.

Lo que hay que copiar en la tarea es el enlace del proyecto creado en GitHub. En caso de tener problemas a la hora de crear el proyecto en GitHub, copiar el contenido del fichero .java de la práctica en la tarea.

__Opcional__: A parte de indicar cuál es la tirada más alta, indicar qué jugador ha realizado la tirada más alta, si el jugador 1 o el jugador 2.