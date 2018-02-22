# UT11. Interfaces

## Práctica a Entregar

Tenemos un Instituto de Enseñanza Secundaria donde conviven Alumnos y Profesores.

Implementar una clase Persona, que debe contener los siguientes atributos:

* nombre: Nombre de la persona.
* anyoNacimiento: Año de nacimiento de la persona.

A parte se deben implementar la clase Profesor que hereda de la clase Persona y contiene los siguientes atributos:

* salario: Salario que cobra el profesor.

También se debe implementar la clase Alumno que hereda de la clase Persona y contiene los siguientes atributos:

* curso: Curso actual que está cursando (puede definirse como un string).

Implementar los constructores , métodos getters y setters, y los métodos toString() para cada una de las clases.

Crear una clase principal que cree objetos tanto de la clase Profesor como de la clase Alumno.

A los alumnos del centro se les aplica un descuento en secretaría del 10% a la hora de comprar artículos, mientras que a los profesores se les aplica un descuento del 2%. Crear un método llamado calculaDescuento() que se le pase una cantidad como parámetro, y devuelva el porcentaje correcto en caso de si es un profesor o un alumno. Utilizar Herencia en Programación Orientado a Objetos para implementar esta funcionalidad.

__Opcional__: Implementar el método calculaDescuento() utilizando polimorfismo y definiéndolo de manera abstracta en la clase Persona, para obligar a todas las clases que heredan de la clase Persona a definirlo.