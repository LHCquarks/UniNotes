Generics enable types to be parameters when defining classes, interfaces and methods. This allows implementation of generic algorithms which work on collections of different types, which can be customised and is type safe. The logic for the algorithm is only implemented once, but can be performed for any class.

Benefits of Generics:
- Removes casting and offers stronger type checks at compile time
- Allows implementation of generic algorithms, which can work on collections of different types, can be customised, and are type safe
- Adds stability to your code 

## Generic Types/Classes
A generic type is a generic class or interface which is parameterized over types. A **generic class** is defined with the following format: `class name<T1, T2, T3, ...> {\\implementation}`. While any generic parameter name works, the common convention is as follows:
- `E` - element
- `K` - Key
- `N` - Number
- `T` - Type
- `V` - Value
### Example Implementation
```java
// Class definition
public class Box<T> {
	// T stands for "Type"
	private T t;
	
	public void set(T t) {
		this.t = t;
	}
	
	public T get() {
		return t;
	}
}

// Instantiating a generic type
Box<Integer> boxName = new Box<Integer>();
// Java can also infer types
Box<Integer> boxName = new Box<>();
```

## Generic Methods
Generic methods are methods which introduce their own **type parameters**. They work similarly to generic types, allowing them to operate on variable types without needing to be rewritten. Generic methods can often be needed to implement generic classes.

```java
public class Util {
	public static <K, V> boolean compare(Pair<K, V> p1, Pair<K, V> p1) {
		return p1.getKey().equals(p2.getKey()) && 
			   p1.getValue.equals(p2.getValue());
	}
}
```

The complete syntax for invoking this method is:
```java
Pair<Integer, String> p1 = new Pair<>(1, "Apple");
Pair<Integer, String> p2 = new Pair<>(2, "Pear");
boolean same = Util.<Integer, String>compare(p1, p2);
```

The type has been explicitly provided, as shown above. Generally, this can be left out and the compiler will **infer** the type that is needed:
```java
Pair<Integer, String> p1 = new Pair<>(1, "Apple");
Pair<Integer, String> p2 = new Pair<>(2, "Pear");
boolean same = Util.compare(p1, p2);
```

Generally, the second method is better practise.


## Bounded Type Parameters
There may be times where you want to restrict the types that can be used as type arguments within a parameterised type. For example, a method that operates on a number might only want to accept instances of `Number` or its subclasses. To declare a bounded type parameter, list the type parameter's name, followed by the `extends` keyword, followed by its upper bound, which in this case is `Number`.

```java
public class NaturalNumber<T extends Integer> {
	// Implementation
}
```

The `extends` keyword here works for subclasses or implementations. This is called an **upper bound**. 

Another bound, called the **lower bound** is done by restricting the parameters to classes which are superclasses of another given class - for example:
```java
public static <T super Box> boolean isDrawn() {
	// Implementation
}
```

### Multiple Bounds
A type parameter can have multiple bounds (`<T extends B1 & B2 & B3>`). A type variable satisfying this condition must be a subtype of **all** of the types listed in the bound (note that at most one of the bounds should be a class, because java doesn't allow multiple inheritance. This bound **must** be specified first).
### Implementing Generics
How do we implement generic classes and methods if we can't guarantee the input has a specific attribute? The easiest way to do so is using bounds. See the example below.\

```java
public static <T extends Comparable<T>> int countGreaterThan(T[] anArray, T elem){
	int count = 0;
	for (T e : anArray) {
		if (e.compareTo(elem) > 0) {
			count++;
		}
	}
	return count;
}

```

In the example above, forcing the upper bound of `Comparable` guarantees all types being compared will implement comparable, and therefore will contain the method `compareTo()`.

### Inheritance in Generics
Consider the inheritance structure, where `Integer` is a subclass of `Number`. A common misunderstanding of generics is that this implies `Box<Integer>` is a subclass of `Box<Number`, which in reality is not true.

However, you **can** subtype a generic class by extending/implementing it. For example:
- `ArrayList<E>` implements `List<E>`, which extends `Collection<E>`.
More generically, you can have the following structure:
- `genericSubclass<T, P>` extends `GenericClass<T>`
As long as the type argument is consistent, the subtyping relationship is preserved between the types.

### Wildcards
Wildcards in Generics are representations of an unknown or unspecified type. It is represented by a `?` in place of the generic parameter name. These can be used as the type of parameter, field, or local variable, and sometimes as a return type.

- The **upper bounded** wildcard `<? extends Foo>`, where `Foo` is any type, is any type which is `Foo` or any subtype of `Foo`.
- The **unbounded** wildcard `<?>` is an unknown/unspecified type. (e.g. `List<?>`).
- The **lower bounded** wildcard `<? super Foo>`, where `Foo` is any type, is any type which is `Foo` or a superclass of `Foo`.

The difference between `?` and `T` (or any other generic parameter name) is that all `T`s used across a generic definition refer to the same type, while all `?` do not. For example,
- `public static <T extends Comparable<T>> int countGreaterThan(T[] anArray, T elem)` forces `elem` to have the same type as contained by `anArray`
- `public static <? extends Comparable<?>> int countGreaterThan(?[] anArray, <?> elem)` **does not** force `elem` to have the same type as contained by `anArray`, leading to errors.

## Collections in Java
A collections framework is a unified architecture for representing and manipulating collections. A collection is simply an object that groups multiple elements into a single unit. All collections frameworks contain the following:
- **Interface**: allows collections to be manipulated independently of the details of their representation.
- **Implementation**: Concrete Implementations of the collection interfaces.
- **Algorithms**: The methods that perform useful computations, such as searching and sorting. These algorithms should be polymorphic (work on many different implementations of the collection interface)

Java has a native `Collection` interface with some general base operations:
- `int size()`
- `boolean isEmpty()`
- `boolean contains(Object element)`
- `boolean add(E element)`
- `boolean remove(Object element)`
- `Iterator<E> iterator()`
- and more
This allows collections to be manipulated independently of the details of their implementation.