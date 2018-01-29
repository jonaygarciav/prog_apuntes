# Objetos y Clases

## Objetivos

* Presentar el concepto de objeto, clase, atributo, método e instancia.
* Interpretar el código fuente de una aplicación Java donde aparecen implementados los conceptos anteriores.
* Construir una aplicación Java sencilla, convenientemente especificada, que emplee los conceptos anteriores.

## Introducción

Aunque parezca una obviedad, la base de la Programación Orientada a Objetos es el objeto.
En la vida real todos los objetos tienen una serie de características y un comportamiento. Por
ejemplo, una puerta tiene color, forma, dimensiones, material... (goza de una serie de características) y puede abrirse, cerrarse... (posee un comportamiento). En Programación Orientada a Objetos, un objeto es una combinación de unos datos específicos y de las rutinas que pueden operar con esos datos. De forma que los dos tipos de componentes de un objeto son:

* __Campos o atributos__: componentes de un objeto que almacenan datos. También se les denomina variables miembro. Estos datos pueden ser de tipo primitivo (boolean, int, double, char...) o, a su vez, de otro tipo de objeto (lo que se denomina agregación o composición de objetos). La idea es que un atributo representa una propiedad determinada de un objeto.
* __Rutinas o métodos__: es una componente de un objeto que lleva a cabo una determinada acción
o tarea con los atributos.

## Clases

Una clase representa al conjunto de objetos que comparten una estructura y un comportamiento comunes. Una clase es una combinación específica de atributos y métodos y puede considerarse un tipo de dato de cualquier tipo __no__ primitivo. Así, una clase es una especie de plantilla o prototipo de objetos: define los atributos que componen ese tipo de objetos y los métodos que
pueden emplearse para trabajar con esos objetos. Aunque, por otro lado, una clase también puede
estar compuesta por métodos estáticos que no necesitan de objetos (como las clases construidas en
los capítulos anteriores que contienen un método estático main). La declaración de una clase sigue la siguiente sintaxis:

```java
[modificadores] class IdentificadorClase {
    // Declaraciones de atributos
    ...
    // Declaraciones de métodos
    ...
}
```

> __Nota__: Los identificadores de las clases deberían ser simples, descriptivos y sustantivos y, en el caso de nombres compuestos, con la primera letra de cada uno en mayúsculas.


## Instancias

Una __instancia__ es un elemento tangible (ocupa memoria durante la ejecución del programa) generado a partir de una definición de clase. Todos los objetos empleados en un programa han de
pertenecer a una clase determinada.

Aunque el término a veces se emplea de una forma imprecisa, un objeto es una instancia de
una clase predefinida en Java o declarada por el usuario y referenciada por una variable que
almacena su dirección de memoria. Cuando se dice que Java no tiene punteros simplemente se indica que Java no tiene punteros que el programador pueda ver, ya que todas las referencias a objeto son de hecho punteros en la representación interna.

En general, el acceso a los atributos se realiza a través del operador punto, que separa al
identificador de la referencia del identificador del atributo (idReferencia.idAtributo). Las
llamadas a los métodos para realizar las distintas acciones se llevan a cabo separando los
identificadores de la referencia y del método correspondiente con el operador punto
(idReferencia.idMetodo(parametros)).

### Ejemplo sencillo de clase e instancia

El siguiente código muestra la declaración de la clase __Precio__. La clase __Precio__ consta de un único atributo (euro) y dos métodos: uno que asigna un valor al atributo llamado __setEuros__ sin devolver ningún valor y otro que devuelve el valor del atributo llamado __getEuros__:

```java
/**
 * Ejemplo de declaracion de la clase Precio
 * double getEuros() --> devuelve el valor almacenado en euros
 * void setEuros(double euros) --> almacena valor en euros
 * Jonay Garcia
 */
public class Precio {
    // Atributo o variable miembro
    private double euros;
    
    // Metodos
    public double getEuros() {
        return euros;
    }
    
    public void setEuros(double euros) {
        this.euros = euros;
    }
}
```

jhj

