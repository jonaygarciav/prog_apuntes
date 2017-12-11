# ANEXO I. INSTALACIÓN Y CONFIGURACIÓN DE JAVA Y DEL ENTORNO DE DESARROLLO ECLIPSE

## Instalar y Configurar Java Development Kit (JDK)

Descargar las Java Development Kit de la URL [http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html):

En la página de descargas, pulsar en el checkbox _Accept License Agreement_ sobre la última versión de _Java SE Development Kit_:

> __Nota__: Durante la realización de este manual, la última versión de las JDK era la _8u151_.

![java_img_01][java_img_01]

Existen varias versiones a descargar en función del Sistema Operativo en el que lo vayamos a instalar: para Sistemas Operativos _Windows_, elegir _jdk-8u151-windows-x64.exe_:

![java_img_02][java_img_02]

Una vez descargado, abrimos un _Explorador de Windows_ y localizamos el fichero descargado. Una vez localizado, para instalarlo pulsamos doble click sobre el fichero:

![java_img_03][java_img_03]

Se abre un asistente que nos guiará durante el proceso de instalación. Pulsamos el botón _Next_:

![java_img_04][java_img_04]

En esta ventana se seleccionan los elementos de JDK a instalar. Están marcadas todas las opciones, incluido las _Development Tools_ que es la opción que nos interesa:

* __Development Tools__: incluye herrientas de desarrollo como el compilador de java _javac_ entre otros.
* __Source Code__: Códifo fuente de java.
* __Public JRE__: Java Runtime Environment. Incluye sólo herramientas para ejecutar un programa java.

También se configura la localización donde se instalarán las JDK. La ubicación por defecto es __C:\Program Files\Java\jdk1.8.0_151__, la dejamos como está. Pulsamos el botón _Next_:

![java_img_05][java_img_05]

En esta ventana se pide la ubicación donde se instalarán las JRE en nuestro equipo. Si os fijáis, en la ventana anterior, estaba marcada la opción _Public JRE_, esto hace que, aparte de las _JDK_, instale también las _JRE_. La ubicación por defecto es __C:\Program Files\Java\jre1.8.0_151__, la dejamos como está. Pulsamos el botón _Next_:

![java_img_06][java_img_06]

Al finalizar el asistente de instalación nos aparecerá la siguiente ventana, eso nos indica que la instalación se ha realizado con éxito. Pulsamos el botón _Close_.

![java_img_07][java_img_07]

Para comprobar que la instalación se ha realizado correctamente, abrimos un _Explorador de archivos_ y debería existir la carpeta __C:\Archivos de programa\Java\jdk1.8.0_151__. La carpeta __bin__ del directorio de instalación contiene, entre otros, los siguientes ejecutables:

* __java.exe__: Permite ejecutar aplicaciones Java.
* __javac.exe__: Permite compilar código fuente Java (No se instala con las JRE).

![java_img_08][java_img_08]

### Configurar la variable del sistema PATH

__PATH__ es la variable del sistema que utiliza el sistema operativo para buscar los ejecutables necesarios desde la línea de comandos o la ventana Terminal. Debemos añadir a la variable __PATH__ la ruta donde se encuentran los ejecutables __java.exe__ y __javac.exe__.

Para ello abrimos el _Panel de Control_ de Windows y nos situamos en _Sistemas y seguridad - Sistema_. En el panel de la izquierda, pulsamos en la opción _Configuración avanzada del sistema_:

![java_img_09][java_img_09]

En el apartado _Variables del sistema_ seleccionamos la variable _Path_ y pulsamos en _Editar_:

![java_img_10][java_img_10]

Al final de la lista añadimos una nueva entrada y añadimos la ubicación de los ejecutables _java.exe_ y _javac.exe_, en este caso __C:\Archivos de programa\Java\jdk1.8.0_151\bin__ y pulsamos el botón _Aceptar_:

![java_img_11][java_img_11]

> __Nota__: El sistema va a cambiar la ruta __C:\Archivos de programa\Java\jdk1.8.0_151\bin__ por __C:\Program Files\Java\jdk1.8.0_151\bin__. Las dos ubicaciones apuntan a lo mismo.

Para comprobar si todo ha ido bien, abrimos la herramienta _Símbolo de sistema_ y ejecutamos el comando __java --version__, debería devolver el siguiente resultado:

![java_img_12][java_img_12]

__Nota__: Ver la documentación Oficial de Oracle sobre [cómo cambiar la variable del sistema PATH](https://www.java.com/es/download/help/path.xml).

¡Listo! Ya hemos instalado las herramientas de desarrollo de Java _JDK_.

## Instalar Entorno de Desarrollo Eclipse

Descargar Eclipse de la URL [https://www.eclipse.org/downloads/](https://www.eclipse.org/downloads/)

![eclipse_img_01][eclipse_img_01]

Pulsamos en el bótón de _Download_:

![eclipse_img_02][eclipse_img_02]

Una vez descargado, abrimos un _Explorador de Windows_ y localizamos el fichero descargado llamado __eclipse-inst-win64.exe__. Una vez localizado, para instalarlo pulsamos doble click sobre el fichero para abrir el asistente de instalación:

![eclipse_img_03][eclipse_img_03]

Pulsamos sobre la opción _Eclipse IDE for Java Developers_ que trae las herramientas necesarias para desarrollar aplicaciones Java.

> __Nota__: Si quisiéramos desarrollar Aplicaciones Web, necesitaríamos descargar la versión _Eclipse IDE for Java EE Developers_:

![eclipse_img_04][eclipse_img_04]

Elegimos la ubicación donde vamos a instalar Eclipse. En este caso no vamos a dejar la ubicación que viene por defecto, sino que lo instalaremos en la ubicación __C:\Users\usuario\eclipse\java-oxygen__, donde _usuario_ corresponde al __usuario del sistema con el que hemos iniciado sesión en nuestro equipo__. Posteriormente pulsamos en el botón __INSTALL__:

![eclipse_img_05][eclipse_img_05]

Una vez finalizado el proceso de instalación debería verse la siguiente pantalla. Pulsamos el botón _X_ situado en la esquina superior derecha.

![eclipse_img_06][eclipse_img_06]

Abrimos un _Explorador de archivos_ y localizamos la carpeta de instalación __C:\Usuarios\usuario\eclipse\java-oxygen__:

![eclipse_img_07][eclipse_img_07]

### Configurar Java en Eclipse

Abrimos la aplicación Eclipse descargada en el apartado anterior (Deberíamos tener en el escritorio un enlace a la aplicación).

![eclipse_java_img_01][eclipse_java_img_01]

Modificamos la ubicación para el _Workspace_ que viene por defecto, en este caso __C:\Users\usuario\eclipse\workspace-java__.

> __Nota__: Todas las configuraciones que hagamos y los proyectos que creemos se guardarán en esta carpeta.

![eclipse_java_img_02][eclipse_java_img_02]

Esta es la pantalla principal del IDE eclipse.

![eclipse_java_img_03][eclipse_java_img_03]

Configurar el JDK instalado en el paso anterior, para ello abrimos el menú _Window - Preferences_ y pulsamos _Enter_:

![eclipse_java_img_04][eclipse_java_img_04]

Pulsamos el botón _Add..._ para añadir una nueva instalación de las _JDK_:

![eclipse_java_img_05][eclipse_java_img_05]

En _Installed JRE Types_ seleccionamos _Standard VM_ y pulsamos el botón _Next_:

![eclipse_java_img_06][eclipse_java_img_06]

Pulsamos en el botón _Directory_ y en la ventana del _Explorador de archivos_ que se abre buscamos la ruta donde se encuentra instalada las JDK, en este caso __C:\Archivos de programa\Java\jdk1.8.0_151__

![eclipse_java_img_07][eclipse_java_img_07]

Vemos que se han completado los campos _JRE home_ con __C:\Archivos de programa\Java\jdk1.8.0_151__ y _JRE name_ con __jdk1.8.0_151__. Pulsamos el botón _Finish_:

![eclipse_java_img_08][eclipse_java_img_08]

Marcamos la opción __jdk1.8.0_155__, para que sea la versión JDK por defecto:

![eclipse_java_img_09][eclipse_java_img_09]

Una vez marcada la opción __jdk1.8.0_155__ debe aparecer en negrita y pulsamos el botón _Apply and Close_:

![eclipse_java_img_10][eclipse_java_img_10]

¡Listo! Ya hemos instalado el IDE Eclipse.

### Configurar Java en Eclipse

Abrimos la aplicación Eclipse descargada en el apartado anterior (Deberíamos tener en el escritorio un enlace a la aplicación).

![eclipse_java_img_01][eclipse_java_img_01]

Modificamos la ubicación para el _Workspace_ que viene por defecto, en este caso __C:\Users\usuario\eclipse\workspace-java__.

> __Nota__: Todas las configuraciones que hagamos y los proyectos que creemos se guardarán en esta carpeta.

![eclipse_java_img_02][eclipse_java_img_02]

Esta es la pantalla principal del IDE eclipse.

![eclipse_java_img_03][eclipse_java_img_03]

Configurar el JDK instalado en el paso anterior, para ello abrimos el menú _Window - Preferences_ y pulsamos _Enter_:

![eclipse_java_img_04][eclipse_java_img_04]

Pulsamos el botón _Add..._ para añadir una nueva instalación de las _JDK_:

![eclipse_java_img_05][eclipse_java_img_05]

En _Installed JRE Types_ seleccionamos _Standard VM_ y pulsamos el botón _Next_:

![eclipse_java_img_06][eclipse_java_img_06]

Pulsamos en el botón _Directory_ y en la ventana del _Explorador de archivos_ que se abre buscamos la ruta donde se encuentra instalada las JDK, en este caso __C:\Archivos de programa\Java\jdk1.8.0_151__

![eclipse_java_img_07][eclipse_java_img_07]

Vemos que se han completado los campos _JRE home_ con __C:\Archivos de programa\Java\jdk1.8.0_151__ y _JRE name_ con __jdk1.8.0_151__. Pulsamos el botón _Finish_:

![eclipse_java_img_08][eclipse_java_img_08]

Marcamos la opción __jdk1.8.0_155__, para que sea la versión JDK por defecto:

![eclipse_java_img_09][eclipse_java_img_09]

Una vez marcada la opción __jdk1.8.0_155__ debe aparecer en negrita y pulsamos el botón _Apply and Close_:

![eclipse_java_img_10][eclipse_java_img_10]

¡Listo! Ya hemos instalado el IDE Eclipse.

[java_img_01]: ../img/anexo_i/java/01.png "Descarga de Java"
[java_img_02]: ../img/anexo_i/java/02.png "Descarga de Java"
[java_img_03]: ../img/anexo_i/java/03.png "Instalación de Java"
[java_img_04]: ../img/anexo_i/java/04.png "Instalación de Java"
[java_img_05]: ../img/anexo_i/java/05.png "Instalación de Java"
[java_img_06]: ../img/anexo_i/java/06.png "Instalación de Java"
[java_img_07]: ../img/anexo_i/java/07.png "Instalación de Java"
[java_img_08]: ../img/anexo_i/java/08.png "Instalación de Java"
[java_img_09]: ../img/anexo_i/java/09.png "Configuración del PATH"
[java_img_10]: ../img/anexo_i/java/10.png "Configuración del PATH"
[java_img_11]: ../img/anexo_i/java/11.png "Configuración del PATH"
[java_img_12]: ../img/anexo_i/java/12.png "Probando Java en Símbolo de Sistema"

[eclipse_img_01]: ../img/anexo_i/eclipse/01.png "Descarga de Eclipse"
[eclipse_img_02]: ../img/anexo_i/eclipse/02.png "Descarga de Eclipse"
[eclipse_img_03]: ../img/anexo_i/eclipse/03.png "Instalación de Eclipse"
[eclipse_img_04]: ../img/anexo_i/eclipse/04.png "Instalación de Eclipse"
[eclipse_img_05]: ../img/anexo_i/eclipse/05.png "Instalación de Eclipse"
[eclipse_img_06]: ../img/anexo_i/eclipse/06.png "Instalación de Eclipse"
[eclipse_img_07]: ../img/anexo_i/eclipse/07.png "Instalación de Eclipse"

[eclipse_java_img_01]: ../img/anexo_i/eclipse_java/01.png "Configuración de Java"
[eclipse_java_img_02]: ../img/anexo_i/eclipse_java/02.png "Configuración de Java"
[eclipse_java_img_03]: ../img/anexo_i/eclipse_java/03.png "Configuración de Java"
[eclipse_java_img_04]: ../img/anexo_i/eclipse_java/04.png "Configuración de Java"
[eclipse_java_img_05]: ../img/anexo_i/eclipse_java/05.png "Configuración de Java"
[eclipse_java_img_06]: ../img/anexo_i/eclipse_java/06.png "Configuración de Java"
[eclipse_java_img_07]: ../img/anexo_i/eclipse_java/07.png "Configuración de Java"
[eclipse_java_img_08]: ../img/anexo_i/eclipse_java/08.png "Configuración de Java"
[eclipse_java_img_09]: ../img/anexo_i/eclipse_java/09.png "Configuración de Java"
[eclipse_java_img_10]: ../img/anexo_i/eclipse_java/10.png "Configuración de Java"
