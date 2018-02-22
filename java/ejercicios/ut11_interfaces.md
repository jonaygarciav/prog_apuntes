# UT11. Polimorfismo

## Ejercicios

__Ejercicio 1__

Ejercicio de Polimorfismo de clases y herencias.

La clase principal de este programa es la clase abstracta Animal que es la clase Padre de Caballo, Oveja y Vaca, los cuales implementarán no solamente los métodos abstractos de la clase Animal sino también el método sonido() de la clase Animal:

```java
public abstract class Animal {
	
    private String nombre;
	
    public Animal(String nombre) {
        this.nombre = nombre;
    }
	
    public String habla() {
        return nombre + " dice " + sonido();
    }
    
    public abstract String sonido();
    
}
```

La clase abstracta Animal posee el método sonido() el cual es completamente abstracto. También define el atributo nombre, el cual almacenará el nombre del animal.

A continuación definimos las clases Vaca, Caballo y Oveja:

```java
public class Vaca extends Animal {
	
	public Vaca(String nombre) {
		super(nombre);
	}
		
	@Override public String sonido() {
		return "¡Muuuu!";
	}
	
}
```

```java
public class Caballo extends Animal {
	
    public Caballo(String nombre) {
        super(nombre);
    }
	
    @Override public String sonido() {
        return "¡Iiiiih!";
    }
    
}
```

```java
public class Oveja extends Animal {
	
    public Oveja(String nombre) {
        super(nombre);
    }
	
    @Override public String sonido() {
        return "¡Beeee!";
    }
    
}
```

Como vemos las Clases Vaca, Caballo y Oveja heredan de la clase abstracta Animal, entonces, estas clases en concreto están obligadas a implementar el método sonido().

En las clases también podemos ver que se utiliza la propiedad nombre que es enviada al constructor de Animal mediante la llamada super(nombre).

Hasta aquí ya tenemos las clases definidas, ahora veremos cómo relacionarlas mediante una clase principal:

```java
public class AnimalMain {

    public static void main(String[] args) {
		
        Animal c = new Caballo("Rocinante");
        System.out.println(c.habla());
		
        Animal v = new Vaca("Montesa");
        System.out.println(v.habla());
		
        Animal o = new Oveja("Dolly");
        System.out.println(o.habla());			

    }

}
```

Esta clase permite la creación de Objetos Polimorficos donde vemos que podemos usar las superClases (Animal) para crear objetos de sus subClases (Caballo, Vaca y Oveja), de esa forma podemos decir que c, v y o son un Animal.

Al ejecutarlo obtenemos el siguiente resultado:

```bash
Rocinante dice ¡Iiiiih!
Montesa dice ¡Muuuu!
Dolly dice ¡Beeee!
```



