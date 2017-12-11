# ANEXO II. CREAR UNA APLICACIÓN EN PYTHON UTILIZANDO ECLIPSE

Ejecutamos el _Eclipse_ y seleccionamos el workspace creado anteriormente _python_workspace_ y pulsamos el botón _Launch_:

![img_01][img_01]

Para crear un nuevo proyecto, vamos al menú _File-New-PyDev Project_:

![img_02][img_02]

En el campo _Project name_ definimos el nombre del proyecto, en este caso __HolaMundo__. En el campo _Interpreter_ vemos que está seleccionado el intérprete de _Python 3.6_ que configuramos anteriormente. Posteriormente pulsamos el botón _'Next >'_:

![img_03][img_03]

En esta ventana del asistente podemos hacer referencia a otros proyectos que necesitemos en nuestra aplicación, pero como no es el caso pulsamos el botón _Finish_:

![img_04][img_04]

En el panel izquierdo, en la pestaña _PyDev Package Explorer_ podemos ver el nuevo proyecto creado.

Para crear la clase principal, pulsamos botón derecho sobre el nombre del proyecto _HolaMundo_ y luego seleccionamos la opción del menú contextual _New-PyDev Module_:

![img_05][img_05]

En esta ventana del asistente, el campo _Package_ lo dejamos vacío. En el campo _Name_ definimos el nombre de la clase principal, en este caso _main_. Pulsamos en el botón _Finish_:

![img_06][img_06]

En el panel izquierdo, en la pestaña _Package Explorer_, vemos cómo se ha creado el fichero _main.py_ en la carpeta _raiz_ del proyecto.

En la ventana principal añadimos el siguiente código:

```python
# -*- coding: utf-8 -*-
'''
Created on 30 nov. 2017

@author: jonay
'''

def main():
    print("¡Hola Mundo!")

if __name__ == '__main__':
    main()
```

Para ejecutar el programa pulsamos el botón _Run_:

> __Nota__: La primera línea le indicamos el tipo de codificación que usaremos en el fichero y es importante si queremos imprimir por consola caracteres que no están en el alfabeto inglés como ¡á..ú, Á..Ú, ñ, ...

![img_07][img_07]

Si todo va bien podremos ver en el panel inferior, en la pestaña _Console_ el mensaje _¡Hola Mundo!_:

![img_08][img_08]

[img_01]: ../img/anexo_ii/01.png "Crear una aplicación en Java con Eclipse"
[img_02]: ../img/anexo_ii/02.png "Crear una aplicación en Java con Eclipse"
[img_03]: ../img/anexo_ii/03.png "Crear una aplicación en Java con Eclipse"
[img_04]: ../img/anexo_ii/04.png "Crear una aplicación en Java con Eclipse"
[img_05]: ../img/anexo_ii/05.png "Crear una aplicación en Java con Eclipse"
[img_06]: ../img/anexo_ii/06.png "Crear una aplicación en Java con Eclipse"
[img_07]: ../img/anexo_ii/07.png "Crear una aplicación en Java con Eclipse"
[img_08]: ../img/anexo_ii/08.png "Crear una aplicación en Java con Eclipse"
