- Method Signature/ Input Parameters tell java which constructor to use
- Aim for self-documenting code (easy to figure out what it does)
- JavaDoc is one way of documenting in Java, targeting class definitions and method/function definitions. In this course, unneeded unless asked.
- Subclasses must call superconstructor


- equals() is a method defined in the object class and compares attributes to determine if two objects are equivalent
- A subclass is equivalent to a superset
- Abstract class is a class which cannot be instantiate, and is meant to be subclassed
For example:
```java
abstract class Shape() {
	// Implementation in subclass
	abstract double area();
}

//////
class Circle extends Shape {
	double area() {
		//implementation here
	}
}

```

- Interfaces are function declarations and are `implemented`.
