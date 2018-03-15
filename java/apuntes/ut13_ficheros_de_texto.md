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
            System.out.println("No se encuentra el fichero tenerife.txt");
        } catch (IOException e) { // qué hacer si hay un error en la lectura del fichero
            System.out.println("No se puede leer el fichero tenerife.txt");
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

El siguiente programa de ejemplo comprueba si un determinado archivo existe o no mediante  el método __exists()__ y, en caso de que exista, lo elimina mediante el método __delete()__. Si intentáramos borrar un archivo que no existe obtendríamos un error.

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

## Procesamiento de archivos de texto

La posibilidad de realizar desde Java operaciones con ficheros abre muchas posibilidades a la hora de procesar archivos: cambiar una palabra por otra, eliminar ciertos caracteres, mover de sitio una línea o una palabra, borrar espacios o tabulaciones al final de las líneas o cualquier otra cosa que se nos pueda ocurrir.

Cuando se procesa un archivo de texto, los pasos a seguir son los siguientes:

1. Leer una línea del fichero origen mientras quedan líneas por leer.
2. Modificar la línea (normalmente utilizando los métodos que ofrece la clase String).
3. Grabar la línea modificada en el fichero destino.
4. Volver al paso 1.

A continuación tienes algunos métodos de la clase String que pueden resultar muy útiles para procesar archivos de texto:

• __charAt(int n)__: Devuelve el carácter que está en la posición n-ésima de la cadena (Recuerda que la primera posición es la número 0).
• __indexOf(String palabra)__: Devuelve un número que indica la posición en la que comienza una palabra determinada.
• __length()__: Devuelve la longitud de la cadena.
• __replace(char c1, char c2)__: Devuelve una cadena en la que se han cambiado todas las ocurrencias del carácter c1 por el carácter c2.
• __substring(int inicio,int fin)__: Devuelve una subcadena.
• __toLowerCase()__: Convierte todas las letras en minúsculas.
• __toUpperCase()__: Convierte todas las letras en mayúsculas.

Puedes consultar todos los métodos de la clase String en la documentación oficial en la siguiente URL [https://docs.oracle.com/javase/8/docs/api/java/lang/String.html](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html)

A continuación tienes un ejemplo en el que se usan los métodos descritos anteriormente.

```java
/**
 * Ejemplos de uso de String
 *
 * @author Jonay Garcia
 */
public class EjemplosString {

    public static void main(String[] args) {
        System.out.println("\nEjemplo 1");
        System.out.println("En la posición 2 de \"berengena\" está la letra " + "berengena".charAt(2));
        
        System.out.println("\nEjemplo 2");
        String frase = "Hola caracola.";
        char[] trozo = new char[10];
        trozo[0] = 'z'; trozo[1] = 'z'; trozo[2] = 'z';
        frase.getChars(2, 7, trozo, 1);
        System.out.print("El array de caracteres vale ");
        System.out.println(trozo);

        System.out.println("\nEjemplo 3");
        System.out.println("La secuencia \"co\" aparece en la frase en la posición " + frase.indexOf("co"));

        System.out.println("\nEjemplo 4");
        System.out.println("La palabra \"murciélago\" tiene " + "murciélago".length() + " letras");
        
        System.out.println("\nEjemplo 5");
        String frase2 = frase.replace('o', 'u');
        System.out.println(frase2);

        System.out.println("\nEjemplo 6");
        frase2 = frase.substring(3, 10);
        System.out.println(frase2);
        
        System.out.println("\nEjemplo 7");
        System.out.println(frase.toLowerCase());
        
        System.out.println("\nEjemplo 8");
        System.out.println(frase.toUpperCase());
    }
}
```

## Archivos CSV

Los archivos __CSV__ (del inglés comma-separated values) son un tipo de documento en formato abierto sencillo para representar datos en forma de tabla, en las que las columnas se separan por comas (o punto y coma en donde la coma es el separador decimal) y las filas por saltos de línea.

El formato __CSV__ es muy sencillo y no indica un juego de caracteres concreto, ni cómo van situados los bytes, ni el formato para el salto de línea. Estos puntos deben indicarse muchas veces al abrir el archivo, por ejemplo, con una hoja de cálculo.

El formato __CSV__ no está estandarizado. La idea básica de separar los campos con una coma es muy clara, pero se vuelve complicada cuando el valor del campo también contienen comillas dobles o saltos de línea. Las implementaciones de CSV pueden no manejar esos datos, o usar comillas de otra clase para envolver el campo. Pero esto no resuelve el problema: algunos campos también necesitan embeber estas comillas, así que las implementaciones de CSV pueden incluir caracteres o secuencias de escape.

Además, el término "CSV" también denota otros formatos de valores separados por delimitadores que usan delimitadores diferentes a la coma (como los valores separados por tabuladores). Un delimitador que no está presente en los valores de los campos (como un tabulador) mantiene el formato simple. Estos archivos separados por delimitadores alternativos reciben en algunas ocasiones la extensión aunque este uso sea incorrecto. Esto puede causar problemas en el intercambio de datos, por ello muchas aplicaciones que usan archivos CSV tienen opciones para cambiar el carácter delimitador.

Ejemplo de representación de datos:

| Año  | Marca | Modelo                                 | Descripción            | Precio  |
|------|-------|----------------------------------------|------------------------|---------|
| 1997 | Ford  | E350                                   | ac, abs, moon          | 3000.00 |
| 1999 | Chevy | Venture "Extended Edition"             |	                    | 4900.00 |
| 1999 | Chevy | Venture "Extended Edition, Very Large" |                        | 5000.00 |
| 1996 | Jeep  | Grand Cherokee                         | air, moon roof, loaded | 4799.00 |


La tabla superior puede ser representada en el siguiente archivo __CSV__:

```bash
Año,Marca,Modelo,Descripción,Precio
1997,Ford,E350,"ac, abs, moon",3000.00
1999,Chevy,"Venture ""Extended Edition""","",4900.00
1999,Chevy,"Venture ""Extended Edition, Very Large""",,5000.00
1996,Jeep,Grand Cherokee,"air, moon roof, loaded",4799.00
```

### Lectura de un fichero CSV

Dado el siguiente fichero:

```
"1.0.0.0","1.0.0.255","16777216","16777471","AU","Australia"
"1.0.1.0","1.0.3.255","16777472","16778239","CN","China"
"1.0.4.0","1.0.7.255","16778240","16779263","AU","Australia"
"1.0.8.0","1.0.15.255","16779264","16781311","CN","China"
"1.0.16.0","1.0.31.255","16781312","16785407","JP","Japan"
"1.0.32.0","1.0.63.255","16785408","16793599","CN","China"
"1.0.64.0","1.0.127.255","16793600","16809983","JP","Japan"
"1.0.128.0","1.0.255.255","16809984","16842751","TH","Thailand"
```

```java
import java.io.BufferedReader;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;

public class CSVReader {

    public static void main(String[] args) {

        String csvFile = "country.csv";
        BufferedReader br = null;
        String line = "";
        String cvsSplitBy = ",";

        try {

            br = new BufferedReader(new FileReader(csvFile));
            while ((line = br.readLine()) != null) {

                // use comma as separator
                String[] country = line.split(cvsSplitBy);

                System.out.println("Country [code= " + country[4] + " , name=" + country[5] + "]");

            }

        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }

}
```

La salida del programa anterior:

```bash
Country [code= "AU" , name="Australia"]
Country [code= "CN" , name="China"]
Country [code= "AU" , name="Australia"]
Country [code= "CN" , name="China"]
Country [code= "JP" , name="Japan"]
Country [code= "CN" , name="China"]
Country [code= "JP" , name="Japan"]
Country [code= "TH" , name="Thailand"]
```