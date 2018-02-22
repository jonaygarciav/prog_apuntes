# UT11. Polimorfismo

## Ejercicios

__Ejercicio 1__

Definir la interfaz MiInterfaz, que contenga la definición de los métodos: metodo1() y metodo2().

```java
interface MiInterfaz
{
   public void method1();
   public void method2();
}
```

Definir la clase Demo a partir de la interfaz MiInterfaz: 

```java
class Demo implements MyInterface
{

    public void method1()
    {
        System.out.println("Implementación del método1");
    }

    public void method2()
    {
        System.out.println("Implementación del método 2");
    }
}
```

Crear la clase principal DemoMain que haga uso de la clase Demo:

```java
public class DemoMain {

    public static void main(String arg[])
    {
        MiInterfaz mi = new Demo();
        mi.metodo1();
        mi.metodo2();
    }
    
}
```

__Ejercicio 2__

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

__Ejercicio 3__

Ejercicio de Herencia Múltiple usando Interfaces.


En este ejercicio definiremos cuatro interfaces: IAdd, ISub, IMul e IDiv. Cada implementación contiene la definición de un método:

* IAdd: define el método add().
* ISub: define el método sub().
* IMul: define el método mul().
* IDiv: define el método div().

```java
interface IAdd
{
	public int add(int a,int b);
}

interface ISub
{
	public int sub(int a,int b);
}

interface IMul
{
	public int mul(int a,int b);
}

interface IDiv
{
	public int div(int a,int b);
}
```

Posteriormente definiremos 4 clases que serán las implementaciones de las interfaces:

* Al implementar la clase Add a partir de la interfaz IAdd, debe definir obligatoriamente el método add(), en este caso este método realiza la suma de dos números pasados como parámetros.
* Al implementar la clase Sub a partir de la interfaz ISub, debe definir obligatoriamente el método sub(), en este caso este método realiza la resta de dos números pasados como parámetros.
* Al implementar la clase Mul a partir de la interfaz IMul, debe definir obligatoriamente el método mul(), en este caso este método realiza la multiplicación de dos números pasados como parámetros.
* Al implementar la clase Div a partir de la interfaz IDiv, debe definir obligatoriamente el método div(), en este caso este método realiza la división de dos números pasados como parámetros:

```java
class Add implements IAdd {

    public int add(int a,int b) {
	int result  =  a+b;
	return result;
    }
    
}

class Sub implements ISub {

    public int sub(int a,int b) {
	int result  =  a-b;
	return result;
    }

}

class Mul implements IMul {

    public int mul(int a,int b)
    {
	int result  =  a*b;
	return result;
    }
    
}

class Div implements IDiv {

    public int div(int a,int b)
    {
	int result  =  a/b;
	return result;
    }
    
}
```

A continuación generamos la clase Calculadora, que se define a partir de las interfaces IAdd, ISub, IMul, e IDiv. Esta clase tiene los siguiente métodos:

* add(): crea un objeto A de la clase Add y llama al método A.add() para calcular la suma.
* sub(): crea un objeto S de la clase Sub y llama al método S.sub() para calcular la resta.
* mul(): crea un objeto M de la clase Mul y llama al método M.mul() para calcular la multiplicación.
* div(): crea un objeto D de la clase Div y llama al método D.div() para calcular la división.

```java
public class Calculadora implements IAdd,ISub,IMul,IDiv {

	public int add(int a,int b)
	{
		Add A  =  new Add();
		return A.add(a, b);
	}
	
	public int sub(int a,int b)
	{
		Sub S  =  new Sub();
		return S.sub(a, b);
	}

	public int mul(int a,int b)
	{
		Mul M  =  new Mul();
		return M.mul(a, b);
	}

	public int div(int a,int b)
	{
		Div D  =  new Div();
		return D.div(a, b);
	}
}
```

La clase Calculadora también se crea a partir de las interfaces IAdd, ISub, IMul, e IDiv.

A continuación la clase Principal que llama a las clases anteriores:

```java
public class CalculadoraMain {

    public static void main(String[] args) {
		
	Calculadora c  =  new Calculadora();
	System.out.println(c.add(10, 20));
	System.out.println(c.sub(10, 20));
	System.out.println(c.mul(10, 20));
	System.out.println(c.div(10, 20));
	
    }

}
```






