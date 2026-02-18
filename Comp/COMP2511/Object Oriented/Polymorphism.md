**Polymorphism** is the concept of grouping multiple classes that have a common ancestor in one and interacting with them as if they were that ancestor.

If we have a class `Mammal` that has a function `walk()` and we have two more classes that extend `Mammal`; `Dog` and `Cat` then we can group these two classes into a `Mammal` array and run `walk()` on both as done bellow:
```Java
package zoo;

public abstract class Mammal {
	public void walk();
}

public class Dog extends Mammal {
	public void walk() {
		System.out.println("I am walking");
	}
	
	public void bark() {
		System.out.println("Bark!");
	}
}

public class Cat extends Mammal {
	public void walk() {
		System.out.println("I am walking 2");
	}
	
	public void meow() {
		System.out.println("meow!");
	}
}

public class Zoo {
	public static void main(String[] args) {
		Dog d = new Dog();
		Cat c = new Cat();
		
		Mammal[] mammals = {d, c};
		
		d.bark(); // prints Bark!
		c.meow(); // prints meow!
		mammals[0].walk(); // prints I am walking
		mammals[1].walk(); // prints I am walking 2
	}
}
```