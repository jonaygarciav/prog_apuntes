# Librerías Externas

Las librerías externas nos permiten añadir funcionalidades a nuestra aplicación medienta librerías que han desarrollado terceros. Muchas de estas funcionalidades tienen que ver con: generación de informes, desarrollo de test, creación de logs, mapeo objeto-relacional, ...

Estas librerías pueden ser añadidas a nuestro proyecto de manera manual (la manera más fácil), o bien, configurando nuestro proyecto para que use __Maven__.

## Maven

Son cientos o quizás miles de librerías que podemos utilizar para múltiples propósitos. Programar no significa inventar la rueda sino aprovechar los recursos que ya existen de la mejor forma para lograr los objetivos propuestos.

Una de las herramientas más útiles a la hora de utilizar librerías de terceros es Maven. Maven se utiliza en la gestión y construcción de software. Posee la capacidad de realizar ciertas tareas claramente definidas, como la compilación del código y su empaquetado. Es decir, hace posible la creación de software con dependencias incluidas dentro de la estructura del JAR. Es necesario definir todas las dependencias del proyecto (librerías externas utilizadas) en un fichero propio de todo proyecto Maven, el POM (Project Object Model). Este es un archivo en formato XML que contiene todo lo necesario para que a la hora de generar el fichero ejecutable de nuestra aplicación este contenga todo lo que necesita para su ejecución en su interior.

Sin embargo, la característica más importante de Maven es su capacidad de trabajar en red. Cuando definimos las dependencias de Maven, este sistema se encargará de ubicar las librerías que deseamos utilizar en Maven Central, el cual es un repositorio que contiene cientos de librerías constantemente actualizadas por sus creadores. Maven permite incluso buscar versiones más recientes o más antiguas de un código dado y agregarlas a nuestro proyecto.

Todo se hará de forma automática sin que el usuario tenga que hacer nada más que definir las dependencias.

Ejemplo de fichero _pom.xml_:

```xml
    <project xmlns="http://maven.apache.org/POM/4.0.0"   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
      xsi:schemaLocation="http://maven.apache.org/POM/4.0.0   
    http://maven.apache.org/xsd/maven-4.0.0.xsd">  
      
      <modelVersion>4.0.0</modelVersion>  
      
      <groupId>com.prog.applications</groupId>  
      <artifactId>application1</artifactId>  
      <version>1.0</version>  
      <packaging>jar</packaging>  
      
      <name>Maven Quick Start Archetype</name>  
      <url>http://maven.apache.org</url>  
      
      <dependencies>  
        <dependency>  
          <groupId>junit</groupId>  
          <artifactId>junit</artifactId>  
          <version>4.8.2</version>  
        </dependency>  
      </dependencies>  
      
    </project>  
```

En el fichero anterior, en el fichero _pom.xml_ se aprecia que la aplicación tiene la dependencia de la librería externa _JUnit_.

> __Nota__: JUnit es un conjunto de bibliotecas creadas por Erich Gamma y Kent Beck que son utilizadas en programación para hacer pruebas unitarias de aplicaciones Java. Es un conjunto de clases (framework) que permite realizar la ejecución de clases Java de manera controlada, para poder evaluar si el funcionamiento de cada uno de los métodos de la clase se comporta como se espera.

En cada fichero _pom.xml_ se deben definir al menos los siguientes elementos:

* __groupId__: Es el conjunto de proyectos al que pertenece nuestro proyecto. Por ejemplo, yo puedo tener todos mis programas de ejemplo en un grupo que llamaré "com.prog.applications". Este nombre que pongamos aquí va a servir de paquete inicial para todas las clases del proyecto. Todos los proyectos maven deben pertenecer a un grupo, aunque sea único para él, que se denominará groupId.
* __artifactId__: Es el nombre que queramos dar al proyecto. Maven creará un directorio con este nombre y el jar que genere para el proyecto tendrá también este nombre. Todos los proyectos maven tienen un nombre para identificarlos, que se denomirá artifactId.
* __version__: Es la versión de la librería, a medida que vaya introduciendo cambios en ella se irá modificando el número de versión.
* __packaging__: Es cómo está empaquetada la librería, la mayoría de librerías están empaquetadas con fichero de extensión .jar.

## Maven Central

__Maven Central__ es un repositorio en el que están alojados las principales librerías hechas por terceros. Desde Maven Central podemos descargarnos las librerías que nos hagan falta, bien de manera manual, o bien haciendo uso de la herramienta __Maven__.

URL de __Maven Central__ [https://mvnrepository.com/repos/central](https://mvnrepository.com/repos/central)

### Librería IText

La librería __iText__ es una librería OpenSource para crear y manipular documentos PDF. La URL en Maven Central es [https://mvnrepository.com/artifact/com.itextpdf/itextpdf](https://mvnrepository.com/artifact/com.itextpdf/itextpdf)

A continuación se muestra un ejemplo de uso de la librería para generar un informe:

```java
import java.io.File;
import java.io.FileOutputStream;
import java.io.OutputStream;
import java.util.ArrayList;

import com.itextpdf.text.Document;
import com.itextpdf.text.pdf.PdfWriter;
import com.itextpdf.text.Paragraph;

public class EjemploPersonasPDF {
	public static void main(String args[]) {
		try {
			
			// Listado de Personas
			ArrayList<String> lista = new ArrayList<String>();
			lista.add("Juan Garcia");
			lista.add("Andres Hernández");
			lista.add("Reyes Estévez");
			lista.add("Pedro Moreno");
			
			// Se crea la instancia del Documento.
			Document document = new Document();

			// Se crea el OutputStream para el fichero donde queremos escribir el pdf.
			OutputStream outputStream = new FileOutputStream(new File("Usuarios.pdf"));

			// Se crea el PDFWriter que realiza la asociación entre el Documento y el OutputStream.
			PdfWriter.getInstance(document, outputStream);

			// Se abre el documento.
			document.open();
			
			// Se añade la cabecera
			document.add(new Paragraph("LISTADO:"));
			document.add(Chunk.NEWLINE);
			
			// Se añade el contenido del ArrayList.
			for (String persona: lista) {
				document.add(new Paragraph(persona));
			}

			// Se cierra el DocumentoClose document and outputStream.
			document.close();
			outputStream.close();

			System.out.println("Documento PDF creado correctamente.");
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}
```

* __document.add(new Paragraph("LISTADO:"));__: añade al documento pdf el texto listado como si fuera un párrafo. Lo bueno de utilizar el párrafo es que nos añade un retorno de carro al final de la línea.
* __document.add(Chunk.NEWLINE);__: añade al documento pdf una línea en blanco.
* __document.add(new Paragraph(persona));__: añade al documento la información de una persona.

Para utilizar este ejemplo correctamente es necesario importar la librería externa _itext_:

```xml
<!-- https://mvnrepository.com/artifact/com.itextpdf/itextpdf -->
<dependency>
    <groupId>com.itextpdf</groupId>
    <artifactId>itextpdf</artifactId>
    <version>5.5.13</version>
</dependency>
```

Más ejemplos del uso de la librería itextpdf:
* [https://tutorialspointexamples.com/itext-tutorial-java-beginners-eclipse/](https://tutorialspointexamples.com/itext-tutorial-java-beginners-eclipse/)
* [http://chuwiki.chuidiang.org/index.php?title=Ejemplo_sencillo_de_creaci%C3%B3n_de_un_pdf_con_iText](http://chuwiki.chuidiang.org/index.php?title=Ejemplo_sencillo_de_creaci%C3%B3n_de_un_pdf_con_iText)


### Librería openCSV

La librería iTextPDF es una librería OpenSource para crear y manipular documentos CSV. La URL en Maven Central es [https://mvnrepository.com/artifact/com.opencsv/opencsv](https://mvnrepository.com/artifact/com.opencsv/opencsv)

Esta librería tiene métodos más avanzados para leer ficheros CSV ya que son capaces de distinguir el delimitador cuando se encuentra incluido dentro de unos de los campos.

A continuación se muestra un ejemplo de uso de la librería para leer un documento CSV:

```java
Rajeev Kumar Singh,rajeevs@example.com,+91-9999999999,India
Sachin Tendulkar,sachin@example.com,+91-9999999998,India
Barak Obama,barak.obama@example.com,+1-1111111111,United States
Donald Trump,donald.trump@example.com,+1-2222222222,United States
```

```java
import com.opencsv.CSVReader;

import java.io.IOException;
import java.io.Reader;
import java.nio.file.Files;
import java.nio.file.Paths;

public class EjemploCSV01 {

    private static final String SAMPLE_CSV_FILE_PATH = "users.csv";

    public static void main(String[] args) throws IOException {
        try (
            Reader reader = Files.newBufferedReader(Paths.get(SAMPLE_CSV_FILE_PATH));
            CSVReader csvReader = new CSVReader(reader);
        ) {
            // Reading Records One by One in a String array
            String[] nextRecord;
            while ((nextRecord = csvReader.readNext()) != null) {
                System.out.println("Name : " + nextRecord[0]);
                System.out.println("Email : " + nextRecord[1]);
                System.out.println("Phone : " + nextRecord[2]);
                System.out.println("Country : " + nextRecord[3]);
                System.out.println("==========================");
            }
        }
    }
}
```

En el ejemplo anterior leemos las entradas del fichero CSV una a una mediante el método __readNext()__. CSVReader proporciona un método llamado __readAll()__ para leer todas las entardasy guardarlas en una estructura _List<String[]>_:

```java
import com.opencsv.CSVReader;

import java.io.IOException;
import java.io.Reader;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.List;

public class EjemploCSV02 {

    private static final String SAMPLE_CSV_FILE_PATH = "users.csv";

    public static void main(String[] args) throws IOException {
        try (
            Reader reader = Files.newBufferedReader(Paths.get(SAMPLE_CSV_FILE_PATH));
            CSVReader csvReader = new CSVReader(reader);
        ) {
            // Reading Records One by One in a String array
        	List<String[]> records = csvReader.readAll();
        	for (String[] record : records) {
        	    System.out.println("Name : " + record[0]);
        	    System.out.println("Email : " + record[1]);
        	    System.out.println("Phone : " + record[2]);
        	    System.out.println("Country : " + record[3]);
        	    System.out.println("---------------------------");
        	}
        }
    }
}
```

#### Omitir la línea de la cabecera

Si estamos intentando leer un fichero CSV que contiene una cabecera, si queremos omitirla, podemos usar la clase __CSVReaderBuilder__ para construir un __CSVReader__ especificándole el número de líneas a omitir.

```java
import com.opencsv.CSVReaderBuilder;

CSVReader csvReader = new CSVReaderBuilder(reader).withSkipLines(1).build();
```

Para utilizar este ejemplo correctamente es necesario importar la librería externa openCSV:

```xml
<!-- https://mvnrepository.com/artifact/com.opencsv/opencsv -->
<dependency>
    <groupId>com.opencsv</groupId>
    <artifactId>opencsv</artifactId>
    <version>3.8</version>
</dependency>
```

A parte la librería __openCSV__ tiene dependencias, _Maven_ es capaz de gestionar las dependencias de una librería, pero si añadimos a mano las librería _openCSV_, deberemos añadir a mano también la librerías __commons-beanutils__ y __commons-lang3__:

```xml
<!-- https://mvnrepository.com/artifact/commons-beanutils/commons-beanutils -->
<dependency>
    <groupId>commons-beanutils</groupId>
    <artifactId>commons-beanutils</artifactId>
    <version>1.9.2</version>
</dependency>
```

```xml
<!-- https://mvnrepository.com/artifact/org.apache.commons/commons-lang3 -->
<dependency>
    <groupId>org.apache.commons</groupId>
    <artifactId>commons-lang3</artifactId>
    <version>3.4</version>
</dependency>
```
