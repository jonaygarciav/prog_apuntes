# ANEXO II. CREAR UNA APLICACIÓN EN JAVA UTILIZANDO ECLIPSE

Ejecutamos el _Eclipse_ y seleccionamos el workspace creado anteriormente _java_workspace_ y pulsamos el botón _Launch_:

![img_01][img_01]

Para crear un nuevo proyecto, vamos al menú _File-New-Java Project_:

![img_02][img_02]

En el campo _Project name_ definimos el nombre del proyecto, en este caso __HolaMundo__. Posteriormente seleccionamos las JDK que instalamos anteriormente y pulsamos el botón _Next >_:

![img_03][img_03]

En esta ventana del asistente se pueden añadir a nuestro proyecto librerías externas, pero como no es el caso pulsamos el botón _Finish_:

![img_04][img_04]

En el panel izquierdo, en la pestaña _Package Explorer_ podemos ver el nuevo proyecto creado. Por defecto crea una carpeta llamada _src_ donde va a ir el código de nuestra aplicación.

Para crear la clase principal, pulsamos botón derecho sobre la carpeta _src_ y luego seleccionamos la opción del menú contextual _New-Class_:

![img_05][img_05]

En esta ventana del asistente, en el campo _Package_ debemos definir el paquete donde se creará la clase, para este caso hemos _com.cip.prog_. En el campo _Name_ definimos el nombre de la clase principal, en este caso _HolaMundo_. Marcamos la opción _public static void main(String[] args)_ para que dentro de la clase cree el método _main()_. Pulsamos en el botón _Finish_:

![img_06][img_06]

En el panel izquierdo, en la pestaña _Package Explorer_, vemos cómo se ha creado la clase _HolaMundo_ dentro del paquete _com.cip.prog_ en la carpeta _src_ del proyecto.

En la ventana principal podemos ver el código fuente que ha generado Eclipse. Vemos cómo ha generado el método _main()_ vacío sin ninguna sentencia:

![img_07][img_07]

Dentro del método _mail()_ añadimos la siguiente sentencia:

```java
System.out.println("¡Hola Mundo!");
```

Esta línea imprimirá por consola el texto _¡HolaMundo!_.

Guardamos el fichero y pulsamos en el botón _Run_ para ejecutar la aplicación:

![img_08][img_08]

Si todo va bien podremos ver en el panel inferior, en la pestaña _Console_ el mensaje _¡Hola Mundo!_.

[img_01]: ../img/anexo_ii/01.png "Crear una aplicación en Java con Eclipse"
[img_02]: ../img/anexo_ii/02.png "Crear una aplicación en Java con Eclipse"
[img_03]: ../img/anexo_ii/03.png "Crear una aplicación en Java con Eclipse"
[img_04]: ../img/anexo_ii/04.png "Crear una aplicación en Java con Eclipse"
[img_05]: ../img/anexo_ii/05.png "Crear una aplicación en Java con Eclipse"
[img_06]: ../img/anexo_ii/06.png "Crear una aplicación en Java con Eclipse"
[img_07]: ../img/anexo_ii/07.png "Crear una aplicación en Java con Eclipse"
[img_08]: ../img/anexo_ii/08.png "Crear una aplicación en Java con Eclipse"
