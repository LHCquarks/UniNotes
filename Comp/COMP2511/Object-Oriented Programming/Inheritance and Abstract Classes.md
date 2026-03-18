## Inheritance

## Abstract Classes
Abstract classes are classes where the methods do not need to be implemented. You cannot create an instance of an abstract class, and they are made to be subclassed, where the subclass implements the abstract method.

Shape class:
```java
public abstract class Shape {
	public abstract double area();
	
	public
}
```
Rectangle Class
```java
public class Rectangle extends Shape {
	int width;
	int height;
	
	public Rectangle(int width, int height) {
		this.width = width;
		this.height = height;
	}
	// Implementation of the abstract method
	public double area() {
		return width * height;
	}
}
```
