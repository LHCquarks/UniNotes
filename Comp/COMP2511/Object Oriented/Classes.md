**Classes** are objects that have both **data** and **methods**.

This **data** and **methods** can be labeled with the different permission levels:
- **Public** - everyone can see it
- **Private** - only itself can see it
- **Protected** - only itself and classes that **inherit** it can see it
Data and methods can also have the following modifiers:

An example of a class is bellow:
```Java
public class Circle {
	protected static final double PI = 3.14159;
	protected int x, y;
	protected int r;
	
	public Circle() {
		this.x = 0;
		this.y = 0;
		this.r = 1;
	}
	
	public Circle(int x, int y, int r) {
		this.x = x;
		this.y = y;
		this.r = r;
	}
	
	public double circumference() {
		return 2* PI * r;
	}
	
	public double area() {
		return PI * r * r;
	}
}
```