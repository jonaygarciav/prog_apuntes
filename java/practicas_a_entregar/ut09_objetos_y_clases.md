# UT08. OBJETOS y CLASES

## Práctica a Entregar

Crea una clase llamada __Libro__ que guarde la información de cada uno de los libros de una biblioteca. La clase debe guardar el título del _libro_, _autor_, _número de ejemplares del libro_ y _número de ejemplares prestados_. La clase contendrá los siguientes métodos:

* Constructor por defecto.
* Constructor con parámetros.
* Métodos __setters__ y __getters__.
* Método __prestamo()__ que incremente el atributo correspondiente cada vez que se realice un préstamo del libro. No se podrán prestar libros de los que no queden ejemplares disponibles para prestar. Devuelve true si se ha podido realizar la operación y false en caso contrario.
* Método __devolucion()__ que decremente el atributo correspondiente cuando se produzca la devolución de un libro. No se podrán devolver libros que no se hayan prestado. Devuelve true si se ha podido realizar la operación y false en caso contrario.
* Método __toString()__ para mostrar los datos de los libros. Este método se heredada de Object y lo debemos modificar (override) para adaptarlo a la clase Libro.
Escribe un programa para probar el funcionamiento de la clase Libro.

Crear un programa principal que cree los siguientes libros:

Libro 1:

* __Autor__: Miguel de Cervantes.
* __Nombre__: El Quijote de La Mancha.
* __Ejemplares__: 2.

Libro 2:

* __Autor__: Arturo Pérez Reverte.
* __Nombre__: El Capitán Alatriste.
* __Ejemplares__: 1.

> __Nota__: Se pueden crear otros libros si se quiere.

Emular un sistema de préstamo y devolución para los libros antes mencionados. No tiene por qué crearse un menú interactivo.

