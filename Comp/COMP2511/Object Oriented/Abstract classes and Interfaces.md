**Abstract classes** and **interfaces** are objects that define what attributes a subclass should have. 

**Abstract classes** can define methods and variables but can also create abstract methods that any subclass needs to implement.

We define **abstract classes** with the `abstract` keyword like so:
```Java
abstract class Shape {
	public double area();
	public double perimiter();
	public int colour() {
		return 1;
	}
}
```
And implement them like so:
```Java
class Circle extends Shape {
	private double r;
	private final double PI = 3.1415;
	
	public Circle(double radius) {
		r = radius;
	}
	
	public double area() {
		return r *r * PI;
	}
	
	public double perimiter() {
		return 2 * r * PI;
	}
}
```

**Interfaces** can only have abstract methods but multiple interfaces can be implemented in a subclass.
```Java
public interface Shape {
	public double area();
	public double perimiter();
}

public interface Coloured {
	public int colour();
}
```
and implemented like so:
```Java
class Circle implements Shape, Coloured {
	private double r;
	private final double PI = 3.1415;
	
	public Circle(double radius) {
		r = radius;
	}
	
	public double area() {
		return r *r * PI;
	}
	
	public double perimiter() {
		return 2 * r * PI;
	}
	
	public int colour() {
		return 1;
	}
}
```
