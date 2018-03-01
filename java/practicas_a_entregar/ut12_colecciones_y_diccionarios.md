# UT12. Colecciones y Diccionarios

## Práctica a Entregar

Crear una aplicación que sea capaz de insertar los siguientes datos en un ArrayList:

| Nombre | Apellidos       | DNI       | Edad | Calle            | Número | CP    | Provincia              |
|--------|-----------------|-----------|------|------------------|--------|-------|------------------------|
| Adrián | García Santos   | 11111111A | 23   | C/ Los Olivos    |  3     | 38493 | Santa Cruz de Tenerife |
| Ana    | Méndez Núñez    | 22222222B | 22   | C/ Los Pinos     | 25     | 38403 | Santa Cruz de Tenerife |
| María  | Sánchez Camacho | 33333333C | 45   | C/ Los Franceces | 23     | 38505 | Las Palmas             |
| Julio  | Brito González  | 44444444D | 30   | C/ Los Pinos     | 25     | 38403 | Las Palmas             |

Para ello habrá que crear las siguientes clases:

* __Direccion__: contiene los campos de la tabla relacionados con la dirección de la persona. Debe contener los atributos:

    * calle (String): Calle donde vive la persona.
    * cp (int): Código Postal de la calle.
    * Provincia: Provincia donde se encuentra la calle.

* __Persona__: contiene los campos de la tabla relacionados con los datos personales de la persona. Debe contener los siguientes atributos:

    * nombre (String): nombre de la persona.
    * apellidos (String): apellidos de la persona.
    * dni (String): Documento nacional de identidad de la persona.
    * edad (int): Edad de la persona.
    * direccion (Direccion): atributo a partir la clase Dirección.

* __Lista__: contiene la lista de Personas y los métodos para operar con ella. Debe contener los siguientes atributos:

    * lista (ArrayList<String>): ArrayList con el listado de Personas.

Crear los métodos getter(), setter() y los constructores que sean necesarios para las clases _Direccion_,  _Persona_ y Lista.

Crear un menú interactivo que permita realizar las siguientes operaciones:

* cargar(): cargar los datos de la tabla anterior en la lista. 
* listar(): lista todos las personas de la lista.
* insertar(): insertar una persona de final de la lista.
* eliminar(): eliminar una persona de la lista.
* contar(): muestra el número de personas de la lista.

Cada opción del menú debe llamar a un método de la clase _Lista_ que implemente dicha funcionalidad.

__Opcional__: Añadir las siguientes opciones al menú:

* buscar(): busca una Persona por el DNI, si la encuentra, muestra los datos de la persona, en caso contrario monstrar un mensaje que diga que esa persona no se encuentra en la lista.

* ordenar(): ordenar los elementos de la lista por array.