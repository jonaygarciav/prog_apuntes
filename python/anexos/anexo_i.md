# ANEXO I. INSTALAR Y CONFIGURAR PYTHON Y PYDEV

## Instalar y Configurar Python 3

Descargar Python de la URL [https://www.python.org/downloads/](https://www.python.org/downloads/)

En la página de descargas, pulsar en el botón _Download Python 3.6.3_:

> __Nota__: Durante la realización de este manual, la última versión de Python era la _3.6.3_.

![python_img_01][python_img_01]

Una vez descargado, abrimos un _Explorador de Windows_ y localizamos el fichero descargado llamado _python-3.6.3.exe_. Una vez localizado, para instalarlo pulsamos doble click sobre el fichero para abrir el asistente de instalación:

![python_img_02][python_img_02]

Marcamos la opción _Add Python 3.6 to PATH_. Esto nos actualizará la variable PATH del sistema insertando la ubicación de los ejecutables de Python. Una vez marcada la opción, pulsamos en _Install Now_. Por defecto, la instalación se realizará en la ubicación __C:\User\arte\AppData\Local\Programs\Python\Python36-32__:

![python_img_03][python_img_03]

Una vez finalizado el asistente, pulsamos en el bóton _Close_ para cerrarlo:

![python_img_04][python_img_04]

Para comprobar si todo ha ido bien, abrimos la aplicación _Símbolo de sistema_ y ejecutamos el comando __python --version__, debería devolver el siguiente resultado:

![python_img_05][python_img_05]

¡Listo! Ya hemos instalado el intérprete de Python.

## Instalar el Plugin de Terceros PyDev para Eclipse

La versión de _Eclipse IDE for Java Developers_ instalada no viene con soporte para programar en Python, para ello, debemos instalar un plugin adicional que nos permita implementar esta funcionalidad. Existe un plugin de terceros llamado __Pydev__ que nos permite desarrollar aplicaciones en Python con Eclipse.

Página oficial del Plugin Pydev: [http://www.pydev.org/](http://www.pydev.org/),

Ir al menú _Help - Install New Software_:

![eclipse_pydev_img_01][eclipse_pydev_img_01]

Pulsamos en el botón _Add_ para añadir un nuevo repositorio:

![eclipse_pydev_img_02][eclipse_pydev_img_02]

Añadimos el repositorio desde donde poder descargar e instalar _PyDev_:

* __Name__: PyDev.
* __Location__: http://pydev.org/updates

Una vez configurado el repositorio pulsamos el botón _OK_:

![eclipse_pydev_img_03][eclipse_pydev_img_03]

En el recuado marcamos el software que queremos instalr, en este caso _PyDev_ y pulsamos el botón _Next:

![eclipse_pydev_img_04][eclipse_pydev_img_04]

En esta ventana se muestra información de los plugins que se van a instalar. Pulsamos el botón _Next_:

![eclipse_pydev_img_05][eclipse_pydev_img_05]

Aceptamos la licencia marcando la opción _I accept the terms of the license agreement_. Luego pulsamos el botón _Finish_.

![eclipse_pydev_img_06][eclipse_pydev_img_06]

Durante el proceso de instalación (podemos ver el proceso de instalación en la barra de estado) nos avisa de que el plugin que estamos instalando no está firmado y que no se puede comprobar su autenticidad. Pulsamos el botón _Install anyway_:

![eclipse_pydev_img_07][eclipse_pydev_img_07]

Una vez instlado nos pide reiniciar el Eclipse. Pulsamos _Restart Now_:

![eclipse_pydev_img_08][eclipse_pydev_img_08]

Listo! ya tenemos instalado el plugin PyDev para Eclipse.

## Configurar Intérprete de Python en Eclipse

Abrir el menú _Window-Preferences_:

![eclipse_python_img_01][eclipse_python_img_01]

En el menú de opciones de la izquierda nos situamos en _PyDev-Interpreters-Python Interpreter_, posteriormente pulsamos el botón _New..._ para agregar el intérprete de Python instalado previamente:

![eclipse_python_img_02][eclipse_python_img_02]

Pulsamos el botón _Browse_ y en el Explorar de archivos buscamos la instalación de Python que instalamos previamente en este caso __C:\User\usuario\AppData\Local\Programs\Python\Python36-32\python.exe__, donde _usuario_ corresponde al __usuario del sistema con el que hemos iniciado sesión en nuestro equipo__. En el campo _Interpreter Name_ modificamos el nombre a uno más corto, en este caso _Python 3.6.3_ y pulsamos el botón _OK_:

* __Interpreter Name__: Python 3.6.3
* __Interpreter Executable__: __C:\User\usuario\AppData\Local\Programs\Python\Python36-32\python.exe__

![eclipse_python_img_03][eclipse_python_img_03]

Automáticamente detecta las librerías del intérprete:

![eclipse_python_img_04][eclipse_python_img_04]

Ahora en la lista de intérpretes vemos el intérprete _Python 3.6.3_ que apunta a la ubicación __C:\User\usuario\AppData\Local\Programs\Python\Python36-32\python.exe__. Pulsamos el botón _Apply and Close_

![eclipse_python_img_05][eclipse_python_img_05]

¡Listo! Ya hemos configurado el intérprete de Python en Eclipse.

[python_img_01]: ../img/anexo_i/python/01.png "Descarga de Python"
[python_img_02]: ../img/anexo_i/python/02.png "Descarga de Python"
[python_img_03]: ../img/anexo_i/python/03.png "Instalación de Java"
[python_img_04]: ../img/anexo_i/python/04.png "Instalación de Java"
[python_img_05]: ../img/anexo_i/python/05.png "Probando Python en Símbolo de Sistema"

[eclipse_pydev_img_01]: ../img/anexo_i/eclipse_pydev/01.png "Configuración de PyDev"
[eclipse_pydev_img_02]: ../img/anexo_i/eclipse_pydev/02.png "Configuración de PyDev"
[eclipse_pydev_img_03]: ../img/anexo_i/eclipse_pydev/03.png "Configuración de PyDev"
[eclipse_pydev_img_04]: ../img/anexo_i/eclipse_pydev/04.png "Configuración de PyDev"
[eclipse_pydev_img_05]: ../img/anexo_i/eclipse_pydev/05.png "Configuración de PyDev"
[eclipse_pydev_img_06]: ../img/anexo_i/eclipse_pydev/06.png "Configuración de PyDev"
[eclipse_pydev_img_07]: ../img/anexo_i/eclipse_pydev/07.png "Configuración de PyDev"
[eclipse_pydev_img_08]: ../img/anexo_i/eclipse_pydev/08.png "Configuración de PyDev"

[eclipse_python_img_01]: ../img/anexo_i/eclipse_python/01.png "Configuración de Python"
[eclipse_python_img_02]: ../img/anexo_i/eclipse_python/02.png "Configuración de Python"
[eclipse_python_img_03]: ../img/anexo_i/eclipse_python/03.png "Configuración de Python"
[eclipse_python_img_04]: ../img/anexo_i/eclipse_python/04.png "Configuración de Python"
[eclipse_python_img_05]: ../img/anexo_i/eclipse_python/05.png "Configuración de Python"
