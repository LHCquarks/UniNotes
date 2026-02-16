We can **extend** the functionality of classes through **inheritance**. A class that **extends** another is called a **subclass** and the original class is called a **superclass**. **subclasses** can access all the **public** and **protected** fields of it's **superclass** whilst also being able to create new methods and data.

Inheritance reduces repetition whilst still allowing for separation between parts of code.

## Example
Say we have a Circle class like so:
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
And we want to extend this class to be able to draw itself to a screen. Whilst we could add a method to do so a mathematician might not care for this functionality so instead we make a new class **GraphicalCircle**:
```Java
public class GraphicalCircle extends Circle {
	protected Color outline, fill;
	public GraphicalCircle() {
		super();
		this.outline = Color.black;
		this.fill = Color.white;
	}
	
	public GraphicalCircle(int x, int y, int r, Color o, Color f) {
		super(x, y, r);
		this.outline = o;
		this.fill = f;
	}
	
	public void draw(Graphics g) {
		g.setColor(outline);
		g.drawOval(x - r, y - r, 2*r, 2*r);
		g.setColor(fill);
		g.fillOval(x - r, y - r, 2*r, 2*r);
	}
}
```

Even though we did not write any code to handle the positions, radius and methods of circles we still get the functionality of circles allowing us to do this:
```Java
GraphicalCircle gc = new GraphicalCircle();
double area = gc.area();
gc.draw(g);

Circle c = gc;
// Can not call draw from "c"
```
