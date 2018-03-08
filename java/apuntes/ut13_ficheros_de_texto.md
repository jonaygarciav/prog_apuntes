# Ficheros de Texto

Mediante un programa en Java se puede acceder al contenido de un fichero grabado en un dispositivo de almacenamiento (por ejemplo en el disco duro) tanto para leer como para escribir (grabar) datos.

La información contenida en las variables, los arrays, los objetos o cualquier otra estructura de datos es volátil, es decir, se pierde cuando se cierra el programa. Los ficheros permiten tener ciertos datos almacenados y disponibles en cualquier momento para cuando nuestro programa los necesite.

Pensemos por ejemplo en un juego. Podríamos utilizar un fichero para guardar el ranking de jugadores con las mejores puntuaciones. De esta manera, estos datos no se perderían al salir del juego. De igual forma, en un programa de gestión, puede ser útil tener un fichero de configuración con datos como el número máximo de elementos que se muestran en un listado o los distintos tipos de IVA aplicables a las facturas. Al modificar esta información, quedará almacenada en el fichero correspondiente y no se perderá cuando se cierre el programa.

Cuando un programa se cierra, se pierde la información almacenada en variables, arrays, objetos o cualquier otra estructura. Si queremos conservar ciertos datos, debemos guardarlos en ficheros.

La creación y uso de ficheros desde un programa en Java se lleva a cabo cuando hay poca información que almacenar o cuando esa información es heterogénea. En los casos en que la información es abundante y homogénea es preferible usar una base de datos relacional (por ejemplo MySQL) en lugar de ficheros.

## Lectura de un fichero de texto

Aunque Java puede manejar también ficheros binarios, vamos a centrarnos exclusivamente en la utilización de ficheros de texto. Los ficheros de texto tienen una gran ventaja, se pueden crear y manipular mediante cualquier editor como por ejemplo __GEdit__, __Notepad__, etc.

Siempre que vayamos a usar ficheros, deberemos incluir al principio del programa una o varias líneas para cargar las clases necesarias. Aunque se pueden cargar varias clases en una sola línea usando el asterisco de la siguiente manera:

```java
import java.io.*;
```

nosotros no lo haremos así, ya que nuestro código sigue las normas del estándar de Google y estas normas lo prohiben taxativamente. Se importarán las clases usando varias líneas, una línea por cada clase que se importa en el programa:

```java
import java.io.BufferedReader;
import java.io.FileReader;
```

> __Nota:__ No es necesario saber de memoria los nombres de las clases, el entorno de desarrollo _Eclipse_ detecta qué clases hacen falta cargar y añade los import de forma automática.

Todas las operaciones que se realicen sobre ficheros deberán estar incluidas en un bloque __try-catch__. Esto nos permitirá mostrar mensajes de error y terminar el programa de una forma ordenada en caso de que se produzca algún fallo: el fichero que estamos intentando abrir no existe o no tenemos permisos para acceder a él, etc.

El bloque __try-catch__ tiene el siguiente formato:

```java
try {
    Operaciones_con_fichero
} catch (tipo_de_error nombre_de_variable) {
    Mensaje_de_error
}
```

Tanto para leer como para escribir utilizamos lo que en programación se llama un __manejador de fichero__. Es algo así como una variable que hace referencia al fichero con el que queremos trabajar.

En nuestro ejemplo, el manejador de fichero se llama __bf__ y se crea de la siguiente manera:

```java
BufferedReader bf = new BufferedReader(new FileReader("tenerife.txt"));
```

El fichero con el que vamos a trabajar tiene por nombre __tenerife.txt__ y contiene información extraída de la Wikipedia sobre la isla de Tenerife. A partir de aquí, siempre que queramos realizar una operación sobre ese archivo, utilizaremos su manejador de fichero asociado, es decir, __bf__.

En el ejemplo que se muestra a continuación, el programa lee el contenido del fichero _tenerife.txt_ y lo muestra tal cual en pantalla, igual que si lo mostraráramos a través de un terminal:

```bash
cat tenerife.txt.
```

Observa que se va leyendo el fichero línea a línea mediante el método __bf.readLine()__ hasta que se acaban las líneas. Cuando no quedan más líneas por leer se devuelve el valor __null__.

```java
/**
 * Ejemplo de uso de la clase File
 * Lectura de un fichero de texto
 *
 * @author Jonay Garcia
 */
import java.io.BufferedReader;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;

class EjemploFichero01 {

    public static void main(String[] args) {
        try {
            BufferedReader bf = new BufferedReader(new FileReader("tenerife.txt"));
            String linea = "";
            while (linea != null) {
                System.out.println(linea);
                linea = bf.readLine();
            }
            bf.close();
        } catch (FileNotFoundException e) { // qué hacer si no se encuentra el fichero
            System.out.println("No se encuentra el fichero malaga.txt");
        } catch (IOException e) { // qué hacer si hay un error en la lectura del fichero
            System.out.println("No se puede leer el fichero malaga.txt");
        }
    }
}
```

Es importante __cerrar el fichero__ cuando se han realizado todas las operaciones necesarias sobre él. En este ejemplo, esta acción se ha llevado a cabo con el método __bf.close()__.

A continuación se muestra un programa un poco más complejo. Se trata de una aplicación que pide por teclado un nombre de fichero. Previamente en ese fichero (por ejemplo numeros.txt) habremos introducido una serie de números, a razón de uno por línea. Se podrían leer también los números si estuvieran separados por comas o espacios aunque sería un poco más complicado (no mucho más). Los números pueden contener decimales ya que se van a leer como Double. Cada número que se lee del fichero se va sumando de tal forma que la suma total estará contenida en la variable suma; a la par se va llevando la cuenta de los elementos que se van leyendo en la variable i. Finalmente, dividiendo la suma total entre el número de elementos obtenemos la media aritmética de los números contenidos en el fichero.

```java
/**
 * Ejemplo de uso de la clase File
 * Calcula la media de los números que se encuentran en un fichero de texto
 *
 * @author Jonay Garcia
 */
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

class EjemploFichero02 {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Introduzca el nombre del archivo donde se encuentran los números: ");
        String nombreFichero = sc.nextLine();
        try {
            BufferedReader bf = new BufferedReader(new FileReader(nombreFichero));
            String linea = "0";
            int i = 0;
            double suma = 0;
            
            while (linea != null) {
                i++;
                suma += Double.parseDouble(linea);
                linea = bf.readLine();
            }
            i--;
            bf.close();
            System.out.println("La media es " + suma / (double)i);
        } catch (IOException e) {
            System.out.println(e.getMessage());
        }
        sc.close();
    }
}
```

## Escritura sobre un fichero de texto

La escritura en un fichero de texto es, si cabe, más fácil que la lectura. Solo hay que cambiar System.out.print("texto") por __bw.write("texto")__. Se pueden incluir saltos de línea,  tabuladores y espacios igual que al mostrar un mensaje por pantalla.

Es importante ejecutar el método __bw.close()__ después de realizar la escritura; de esta manera nos aseguramos que se graba toda la información en el disco.

Al realizar escrituras en ficheros con Java hay que tener ciertas precauciones. Cuando toca dar este tema en clase es frecuente que a más de un alumno le empiece a ir lento el ordenador, luego se le queda inutilizado y, por último, ni siquiera le arranca ¿qué ha pasado? Pues que ha estado escribiendo datos en ficheros y por alguna razón, su programa se ha metido en un bucle infinito lo que da como resultado cuelgues y ficheros de varios gigabytes de basura. Por eso es muy importante asegurarse bien de que la información que se va a enviar a un fichero es la correcta ¿cómo? muy fácil, enviándola primero a la pantalla.

> __Nota__: Para probar antes de escribir en fichero podemos imprimir todo primero por consolatodo lo que quieras escribir en el fichero. Cuando compruebes que lo que se ve por pantalla es realmente lo que quieres grabar en el fichero, entonces y solo entonces, cambia System.out.print("texto") por manejador.write("texto").

A continuación se muestra un programa de ejemplo que crea un fichero de texto y luego esribe en él tres palabras, una por cada línea.

```java
/**
 * Ejemplo de uso de la clase File
 * Escritura en un fichero de texto
 *
 * @author Jonay Garcia
 */
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

class EjemploFichero03 {

    public static void main(String[] args) {
        try {
            BufferedWriter bw = new BufferedWriter(new FileWriter("fruta.txt"));
            bw.write("naranja\n");
            bw.write("limón\n");
            bw.write("manzana\n");
            bw.close();
        } catch (IOException e) {
            System.out.println("No se ha podido escribir en el fichero");
        }  
    }
}
```

## Lectura y escritura combinadas

Las operaciones de lectura y escritura sobre ficheros se pueden combinar de tal forma que haya un flujo de lectura y otro de escritura, uno de lectura y dos de escritura, tres de lectura, etc.

En el ejemplo que presentamos a continuación hay dos flujos de lectura y uno de escritura. Observa que se declaran en total tres manejadores de fichero (dos para lectura y uno para escritura). El programa va leyendo, de forma alterna, una línea de cada fichero - una línea de fichero1.txt y otra línea de fichero2.txt - mientras queden líneas por leer en alguno de los ficheros; y al mismo tiempo va guardando esas líneas en otro fichero con nombre mezcla.txt.

```java
/**
 * Ejemplo de uso de la clase File
 * Mezcla de dos ficheros
 *
 * @author Jonay Garcia
 */
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

class EjemploFichero04 {

    public static void main(String[] args) {
        try {
            BufferedReader bf1 = new BufferedReader(new FileReader("fichero1.txt"));
            BufferedReader bf2 = new BufferedReader(new FileReader("fichero2.txt"));
            BufferedWriter bw = new BufferedWriter(new FileWriter("mezcla.txt"));

            String linea1 = "";
            String linea2 = "";
            while ( (linea1 != null) || (linea2 != null) ) {
                linea1 = bf1.readLine();
                linea2 = bf2.readLine();
                if (linea1 != null)
                    bw.write(linea1 + "\n");
                if (linea2 != null)
                    bw.write(linea2 + "\n");
            }
            bf1.close();
            bf2.close();
            bw.close();
        } catch (IOException ioe) {
            System.out.println("Se ha producido un error de lectura/escritura");
            System.err.println(ioe.getMessage());
        }
    }
}
```

## Otras operaciones sobre ficheros

Además de leer desde o escribir en un fichero, hay otras operaciones relacionadas con los archivos que se pueden realizar desde un programa escrito en Java.

Veremos tan solo un par de ejemplos. Si quieres profundizar más, échale un vistazo a
la documentación oficial de la clase _File_ en la URL [https://docs.oracle.com/javase/8/docs/api/java/io/File.html](https://docs.oracle.com/javase/8/docs/api/java/io/File.html).

El siguiente ejemplo muestra por pantalla un listado con todos los archivos que contiene un directorio.

```java
/**
 * Ejemplo de uso de la clase File
 * Listado de los archivos del directorio actual
 *
 * @author Jonay Garcia
 */
import java.io.File;

class EjemploFichero05 {
    public static void main(String[] args) {
        File fichero = new File("."); // se indica la ruta entre comillas
        // el punto (.) es el directorio actual
        String[] listaArchivos = fichero.list();
        for(int i = 0; i < listaArchivos.length; i++){
            System.out.println(listaArchivos[i]);
        }
    }
}
```

El siguiente programa de ejemplo comprueba si un determinado archivo existe o no mediante  el método __exists()__ y, en caso de que exista, lo elimina mediante el médoto __delete()__. Si intentáramos borrar un archivo que no existe obtendríamos un error.

```java
/**
 * Ejemplo de uso de la clase File
 * Comprobación de existencia y borrado de un fichero
 *
 * @author Jonay Garcia
 */
import java.io.File;

class EjemploFichero06 {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Introduzca el nombre del archivo que desea borrar: ");
        String nombreFichero = sc.nextLine();
        File fichero = new File(nombreFichero);
        if (fichero.exists()) {
            fichero.delete();
            System.out.println("El fichero se ha borrado correctamente.");
        } 
        else {
            System.out.println("El fichero " + nombreFichero + " no existe.");
        }
        
        sc.close();
    }
}
```
