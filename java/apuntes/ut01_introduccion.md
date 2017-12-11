# UT01. INTRODUCCIÓN

## Objetivos

* Describir las características del lenguaje de programación Java.
* Describir las herramientas ligadas a la construcción y ejecución de programas escritos en Java.
* Construir las primeras aplicaciones en Java.

Esta unidad de trabajo pretende ser una rápida introducción a la programación en Java. En primer lugar muestra lo que es Java, sus características y las herramientas que están ligadas a él y, a continuación, enseña cómo compilar y ejecutar algunos programas sencillos escritos en Java. La tecnología Java es tanto una plataforma como un lenguaje de programación. En los capítulos posteriores se trata de dar una visión más detallada de la sintaxis del lenguaje de programación Java.

## Introducción

### El Lenguaje de Programación Java

El lenguaje de programación Java, fue diseñado por la compañía __Sun Microsystems Inc__, con
el propósito de crear un lenguaje que pudiera funcionar en sistemas de ordenadores heterogéneos (redes de computadoras formadas por más de un tipo de ordenador, ya sean PC compatibles, Macintosh o estaciones de trabajo que empleen diferentes sistemas operativos como Windows, OS/2 o Unix), y que fuera independiente de la plataforma en la que se vaya a ejecutar. Esto significa que un programa de Java puede ejecutarse en cualquier máquina o plataforma.

Su origen se remonta a la creación de un lenguaje de programación para el desarrollo de
aplicaciones para electrodomésticos y otros aparatos electrónicos de consumo por parte de una empresa filial de _Sun_, llamada FirstPerson en 1991. Su creador, __James Gosling__, lo bautizó como Oak. Al abandonarse este proyecto, el lenguaje se modificó, al igual que su nombre y se orientó al desarrollo de aplicaciones para la red. En septiembre de 1995 aparece el primer Kit de Desarrollo de Java (JDK). A principios de 1997 se presenta la primera revisión de Java (la versión 1.1) y a finales de 1998 surge la versión 1.2 (Java 2) que introdujo modificaciones bastante significativos. En octubre de 2004 se hace pública la versión Java 1.5 (Java 5) incluyendo innovaciones muy importantes en la plataforma.

En la siguiente tabla se muestra el histórico de _versiones de Java_:

| Versión    | Fecha de Lanzamiento     | Comentario |
| -------    | --------------------     | ---------- |
| JDK 1.0    | 23 de enero de 1996      | Primera versión.     |
| JDK 1.1    | 19 de febrero de 1997    | Se da a conocer la nueva versión de Java Card, orientado a pequeñas tarjetas inteligentes.     |
| J2SE 1.2   | 8 de diciembre de 1998   | Se modificó el nombres bajo la denominación Java 2 y el nombre "J2SE" (Java 2 Platform, Standard Edition), reemplazó a JDK para distinguir la plataforma base de J2EE (Java 2 Platform, Enterprise Edition) y J2ME (Java 2 Platform, Micro Edition). |
| J2SE 1.3   | 8 de mayo de 2000        | Se incorporan nuevas utilidades de red y comienzan a incluirse características multimedia.     |
| J2SE 1.4   | 6 de febrero de 2002     | &nbsp;     |
| J2SE 5     | 30 de septiembre de 2004 | Originalmente numerado 1.5, esta notación aún es usada internamente.
| Java SE 6  | 11 de diciembre de 2006  | En esta versión, Sun cambió el nombre "J2SE" por Java SE. |
| Java SE 7  | julio de 2011            | Se simplifican algunas características del lenguaje. También ofrece un mayour soporte a los emergentes lenguajes scripting ejecutados sobre la máquina virtual.     |
| Java SE 8  | marzo de 2014            | Nuevas utilidades del lenguaje, destacan las expresiones lambda y las nuevas APIs para manipular fechas y colecciones de objetos.     |
| Java SE 9  | 26 de septiembre de 2017 | &nbsp;     |

> __Nota__: Cada 3 ó 4 años sale una versión de Java. La versión actual _Java SE 9_ es muy reciente: la más utilizada actualmente es __Java SE 8__.

En 2009 Oracle adquiere Sun Microsystems por un valor de 5710 millones de dólares.

### Características del Lenguaje Java

El lenguaje Java muestra las siguientes características generales:

* __Sencillo__: Elimina la complejidad de los lenguajes como C y da paso al contexto de los
lenguajes modernos orientados a objetos. Aunque la sintaxis de Java es muy similar a C y
C++, que son lenguajes a los que una gran mayoría de programadores están acostumbrados a
emplear.

* __Orientado a Objetos__: La filosofía de programación orientada a objetos es diferente a la
programación convencional (imperativa o procedural). Su nivel de abstracción facilita la
creación y mantenimiento de programas. Existen muchas referencias que dan una
introducción a esta forma de programar.

* __Independiente a la arquitectura y portable__: Al compilar un programa en Java, el código
resultante es un tipo de código binario conocido como Java bytecodes. Este código es interpretado por
diferentes computadoras de igual manera, por lo que únicamente hay que
implementar un intérprete para cada plataforma. De esa manera Java logra ser un lenguaje
que no depende de una arquitectura de ordenador específica. Como el código compilado de
Java es interpretado, un programa compilado de Java puede ser utilizado por cualquier
computadora que tenga implementado el intérprete de Java.

* __Robusto__: Java simplifica la gestión de la memoria dinámica. Por ejemplo, ya no es necesario
la liberación explícita, el intérprete de Java lo lleva acabo automáticamente cuando detecta
que una variable dinámica ya no es usada por el programa. Por otra parte, impide que un
puntero Java apunte a una dirección de memoria no válida, los punteros (referencias) Java
son seguros y deterministas: o bien apuntan a un elemento correctamente alojado en memoria
o bien tienen el valor nulo. Finalmente el acceso a la memoria es supervisado por el intérprete
de tal manera que no es posible acceder a zonas de memoria no autorizadas sin provocar un
error. Por ejemplo, no es posible escribir fuera de los límites de un vector.

* __Seguro__: El sistema de Java tiene ciertas políticas que evitan que se puedan codificar virus con
este lenguaje. Existen muchas restricciones, especialmente para los denominados applets, que
limitan lo que se puede y no puede hacer con los recursos críticos de una computadora.

* __Multitarea (Multithreaded)__: Un lenguaje que soporta múltiples threads, hilos o tareas, es un
lenguaje que puede ejecutar diferentes líneas de código al mismo tiempo. El soporte y la
programación de hilos en Java está integrado en la propia sintaxis del lenguaje.

* __Dinámico__: En Java no es necesario cargar completamente el programa en memoria sino que
las clases compiladas pueden ser cargadas bajo demanda en tiempo de ejecución (dynamic
binding). Esto proceso permite la carga de código bajo demanda, lo que es especialmente
importante en los applets.

### Mecanismo de Creación de un Programa Java

En este aspecto la principal originalidad de Java estriba en que es a la vez __compilado__ e
__interpretado__. Con el compilador de Java, el programa fuente (fichero con extensión _.java_) es traducido a un lenguaje intermedio o pseudo-código (no es código máquina) llamado __Java bytecodes__ generándose un programa compilado almacenado en un archivo con extensión __.class__ . Este archivo puede ser posteriormente interpretado y ejecutado por el intérprete de Java (lo que se conoce como la Máquina Virtual Java o Java Virtual Machine). Por eso Java es multi-plataforma, ya que existe un intérprete para cada máquina diferente. Por tanto, la compilación se produce una vez y la interpretación cada vez que el programa se ejecuta.

![img_01][img_01]

Actualmente las máquinas virtuales modernas realizan una compilación JIT (Just In Time) en
donde el bytecode no es interpretado sino que se compila directamente a código máquina en tiempo de ejecución de acuerdo con la arquitectura (procesador y sistema operativo) en la que se ejecuta la máquina virtual. Esto permite conseguir velocidades de ejecución similares al C. En la práctica las máquinas virtuales suelen utilizar técnicas mixtas de interpretación/compilación JIT normalmente según la frecuencia de paso por un bytecode concreto.

Un programa Java puede funcionar como una aplicación independiente (por ejemplo, el
entorno de desarrollo NetBeans) o como un applet (contracción de la expresión little application), que es un pequeño programa que no se ejecuta de forma independiente. Los applets de Java se pueden introducir o incrustar en una página de Web (empleando el lenguaje HTML), y con esto se puede tener un programa que puede ser ejecutado por cualquier persona que tenga un navegador compatible con Java. Aunque queda fuera del alcance de este manual, es necesario indicar que también pueden construirse un tercer tipo de aplicaciones: los denominados servlets (contracción de la expresión server application), que se ejecutarían en servidores web conectados a intranets o a internet.

### Ventajas en el Uso de Java

Pueden destacarse las siguientes ventajas en el empleo de Java como lenguaje de
programación:

* __Compatibilidad__: No es necesario modificar (reescribir) el código si se desea ejecutar el programa en otra máquina. Un único código funciona para todos los navegadores
compatibles con Java o donde se tenga una Máquina Virtual de Java (ordenadores PC
compatibles, Macintosh o estaciones de trabajo que empleen diferentes sistemas operativos
como Windows, Mac OS X, Linux o Unix).

* __Funcionalidad__: Si interesa desarrollar un servicio Web con funciones dinámicas más allá de las posibilidades del lenguaje HTML, puede emplearse Java para incluir en las páginas toda clase de elementos multimedia y permitir un alto nivel de interactividad.

* __Ahorro de recursos__: Un navegador compatible con Java deberá ejecutar cualquier programa hecho en Java, esto ahorra a los usuarios tener que estar insertando programas adicionales o plug-ins que necesitan emplear memoria adicional y espacio en disco.

* __Metodología OO__: Java es un lenguaje de programación orientado a objetos, y tiene todos los beneficios que ofrece esta metodología de programación: facilita la creación, el
mantenimiento y la reutilización de código.

* __Menos y mejor código__: Comparaciones de métricas de programas indican que un programa
en escrito en Java es cuatro veces de menor tamaño que uno escrito en C++ y además
favorece los buenos hábitos en la programación como, por ejemplo, la gestión de la memoria
dinámica.

* __Gratuidad__: El kit de desarrollo Java es gratuito y puede descargarse de diversos servidores WWW.

### Inconvenientes del Lenguaje Java

El uso de Java también tiene algunos inconvenientes o limitaciones:

* __Mayor consumo memoria__: un programa Java consume más memoria por dos razones, es
necesario cargar la máquina virtual y, en general, Java necesita más memoria para alojar los
elementos de un programa que un programa similar hecho en un lenguaje nativo.

* __Mayor tiempo de carga__: la carga de la máquina virtual lleva tiempo y como la carga de las clases son bajo demanda la ejecución al principio de un programa Java es relativamente lenta.

* __Integración no perfecta con el sistema operativo__: como Java y sus librerías están
diseñados para ser multiplataforma la integración con el sistema operativo en forma de
extensiones al mismo no es sencilla y suele necesitar extensiones nativas que rompen la
portabilidad. Por otro lado exigen la presencia y carga de la máquina virtual por lo que no se suele utilizar como lenguaje para el desarrollo de elementos básicos de sistemas.

* __Es un lenguaje de programación__: El hecho de que Java sea un lenguaje de programación es otra gran limitación. Aunque sea orientado a objetos y “más sencillo” de aprender que C o
C++, sigue siendo un lenguaje y por lo tanto aprenderlo no es tarea fácil. Especialmente para los programadores noveles.

### La plataforma Java

Normalmente, una __plataforma__ es un sistema mixto que incluye el hardware y/o el entorno
software en el que se ejecuta un programa. __La plataforma Java__ se diferencia de la mayoría de las demás en que está formada únicamente por software que se ejecuta en cualquier otra plataforma independiente de hardware. La _plataforma Java_ tiene dos componentes:

* El intérprete, Máquina Virtual Java ó Java Virtual Machine (Java VM) que ya se ha
comentado anteriormente.
* La Interfaz de Programación de Aplicaciones Java ó Java Application Programming
Interface (Java API).

El __API de Java__ es una amplia colección de componentes de software que facilitan muchas
necesidades de programación como puede ser código necesario para construir una interfaz de
usuario (GUI). El API de Java se agrupa en __librerías__ o __paquetes__ (packages) de componentes relacionados entre sí: componentes básicos de programación, creación de applets, redes, internacionalización, seguridad, componentes de software, conectividad y redes, etcétera. Hay, además, extensiones estándar fuera del núcleo del API de Java que facilitan recursos para servidores, gráficos 3D, animación…

![img_02][img_02]

## Herramientas de Desarrollo para JAVA

### Java SE

Para poder trabajar con Java en nuestro equipo necesitamos uno de los siguientes paquetes:

* JRE (Java Runtime Environment).
* Servidor JRE (Server Java Runtime Environment).
* JDK (Java Development Kit).

Estos paquetes tienen distintas finalidades, en función de las tareas que vayamos a realizar.

#### ¿Qué paquete Java necesito?

* __Desarrolladores de software__: _JDK (Java SE Development Kit)_ Para desarrolladores de Java. Incluye un JRE completo más herramientas para desarrollar, compilar, depurar y monitorizar aplicaciones Java.
* __Administradores que ejecutan aplicaciones en un servidor__: _Servidor JRE (Server Java Runtime Environment)_ Para desplegar aplicaciones Java en servidores. Incluye herramientas para el monitoreo de JVM y herramientas comúnmente requeridas para aplicaciones de servidor, pero no incluye integración de navegador (el complemento de Java), actualización automática ni un instalador. Lea más aquí (en ingles) arrow
* __Usuario final que ejecuta Java en un escritorio__: _JRE (Java Runtime Environment)_: Cubre la mayoría de las necesidades de los usuarios finales. Contiene todo lo necesario para ejecutar aplicaciones Java en su sistema.

Página oficial de Java SE:  [http://www.oracle.com/technetwork/es/java/javase/downloads/index.html](http://www.oracle.com/technetwork/es/java/javase/downloads/index.html)

### Entornos de Desarrollo Integrado

Utilizando las herramientas incluidas en el propio _JDK_ podemos compilar programas, empaquetarlos, depurarlos y ejecutarlos. Además, necesitaríamos un editor de texto para escribir el código fuente.

Un __IDE (Integrated Development Environment)__ nos permite realizar todas estas tareas en un único entorno de desarrollo.

> __Nota__: Un __IDE__ consiste de un editor de código fuente, herramientas de construcción automáticas y un depurador. La mayoría de los IDE tienen auto-completado inteligente de código. Algunos IDE contienen un compilador, un intérprete, o ambos, tales como NetBeans y Eclipse; otros no, tales como SharpDevelop y Lazarus.

Existen multitud de IDEs para Java, entre los más importantes se encuentran __Eclipse__, __Intellij Idea__ y __Netbeans__.

![img_03][img_03]

#### NetBeans

Inicialmente desarrollado por _Sun_ y ahora en manos de _Oracle_, __NetBeans__ es uno de los IDE para desarrollo Java más completos. _NetBeans_ tiene una estructura modular fácilmente ampliable mediante complementos, existiendo configuraciones predefinidas para desarrollo Java SE, Java EE y también dirigidas a otros lenguajes de programación, como PHP o C++.

_NetBeans_ es un proyecto de código abierto, está desarrollado en Java y, en consecuencia, puede instalarse en cualquier sistema para el que exista un JRE de Java SE, incluidos Windows, GNU/Linux y OS X/MacOS. Al tratarse de una herramienta de _Oracle_, suele ser la primera en incorporar soporte para las novedades que van apareciendo en la plataforma Java. Por ejemplo, desde la versión 8.1 de NetBeans cuenta con soporte para Java SE 9, es decir, desde antes de que esta versión de la plataforma saliera al mercado.

Página oficial de Eclipse: [https://netbeans.org/](https://netbeans.org/)

![img_04][img_04]

#### Eclipse

Al igual que _NetBeans_, __Eclipse__ también es un proyecto de código abierto y el IDE está disponible para múltiples sistemas operativos. _Eclipse_ es un IDE no sólo para Java, sino para muchos otros lenguajes y herramientas de desarrollo. Es considerado por muchos el IDE por excelencia, al incorporar un gran abanico de complementos que facilitan prácticamente todas las tareas relativas al desarrollo de software.

Página oficial de Eclipse: [https://www.eclipse.org](https://www.eclipse.org)

![img_05][img_05]

#### Intellij Idea

__IntelliJ IDEA__ es un IDE para Java desarrollado por la empresa _JetBrains_, estando disponible para Windows, OS X/MacOS y GNU/Linux. Como ocurre con _NetBeans_ y _Eclipse_, también puede incorporar soporte para otros lenguajes de programación. A diferencia de ellos, sin embargo, no se trata de un proyecto totalmente basado en software libre, sino de un producto comercial. Existe, no obstante, una edición reducida denominada Community que puede obtenerse gratuitamente.

Este IDE es valorado especialmente por su agilidad y estabilidad, así como por contar con una interfaz de usuario considerada más actual y funcional que la de _NetBeans_ o _Eclipse_. El mayor inconveniente estriba en que para ciertos tipos de proyecto se necesita la edición Ultimate que tiene un coste relativamente elevado.

Página oficial de Intellij Idea: [https://www.jetbrains.com/idea](https://www.jetbrains.com/idea)

![img_06][img_06]

### Lenguajes de Programación más Populares

¿Cuáles son los lenguajes de programación más populares? Para contestar a esta pregunta podemos hacer uso de los índices __TIOBE__ y __PYPL__ (PopularitY of Programming Language), y .

#### TIOBE Programming Community Index

El índice __TIOBE__ es una medida de popularidad de los lenguajes de programación, creado y matenido por _TIOBE Company_. El índice es calculado por el número de resultados de búsqueda en navegadores web conteniendo el nombre del lenguaje. El índice cubre búsquedas en Google, Google Blogs, MSN, Yahoo!, Baidu, Wikipedia and YouTube. No sólo utiliza el número de resultados de búsqueda en navegadores web, sino tiene en cuenta más elementos para calcular este índice, como cursos, ...El índice es actualizado una vez al mes.

![img_07][img_07]

Página oficial: [https://www.tiobe.com/tiobe-index/](https://www.tiobe.com/tiobe-index/)

#### PYPL Index

El __PYPL Index__ es una página que mide la popularidad de todos los _Lenguajes de Programación_ en función de tendencias. Usa Goolge Trends como fuente de datos.

![img_08][img_08]

Página Web: [https://pypl.github.io/PYPL.html](https://pypl.github.io/PYPL.html)

#### GitHut

__GitHut__ cuenta y agrupa por Lenguaje de Programación el número de proyectos subidos a la plataforma de desarrollo _GitHub_.

Página Web: [http://githut.info/](http://githut.info/)

![img_09][img_09]

### IDEs más Populares

#### PYPL IDE Index

El __PYPL IDE Index__ es una página que mide la popularidad de todos los IDEs en función de tendencias. Usa Goolge Trends como fuente de datos.

![img_10][img_10]

Página Web: https://pypl.github.io/IDE.html

### Lenguajes de Programación más Demandados

[Indeed.com](https://www.indeed.com/) es un portal de búsqueda de ofertas de empleo. Los 10 lenguajes de programación más demandados en 2017 en ofertas de empleo fueron los siguientes:

![img_11][img_11]

[img_01]: ../img/ut01/01.png "Proceso de creación de un programa java"
[img_02]: ../img/ut01/02.png "Plataforma Java"
[img_03]: ../img/ut01/03.png "IDEs"
[img_04]: ../img/ut01/04.png "Netbeans"
[img_05]: ../img/ut01/05.png "Eclipse"
[img_06]: ../img/ut01/06.png "Intellij Idea"
[img_07]: ../img/ut01/07.png "Tiobe Index"
[img_08]: ../img/ut01/08.png "PYPL Index"
[img_09]: ../img/ut01/09.png "GitHut"
[img_10]: ../img/ut01/10.png "PYPL IDE Index"
[img_11]: ../img/ut01/11.png "Indeed"
