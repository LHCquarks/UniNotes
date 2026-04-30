## Overview
Inheritance is one of the most important properties of object-oriented programming. This is achieved through sub-classing. A **subclass** is a class which contains all the methods and attributes of another class, as well as its own methods and attributes. For example:
- We might have a class `Shape` with subclass `Circle`
### Methods of Sub-classing
There are three approaches for sub-classing:
- Rewriting all the code in the superclass, in the subclass (very bad practise)
- Creating a superclass instance as an attribute of the subclass, and using its constructor in the subclass constructor. This is called method forwarding (new methods return `superObj.oldMethod()`). This is useful when only some superclass methods are relevant to the subclass
- Extending a class: use the `extends` argument in the class definition (best practise)

### Class casting
It is possible to set a superclass variable equal to an instance of the subclass. In this case, you only have access to the attributes present in the superclass. Then you can downcast this to the subclass again, meaning all subclass attributes are saved. You can only downcast to `subClass` if the instance of the object was created at `subClass` or below. For example:

```java
public class GraphicCircle extends Circle {
	
	String outlineColour;
	String fillColour;
	
	public GraphicCircle(
		int x,
		int y,
		int r,
		String outlineColour,
		String fillColour
	) {
		this(x, y, r);
		this.outlineColour = outlineColour;
		this.fillColour = fillColour;
	}
	
	public void draw() {
		// Implementation not required for example
	}
	
	
	public static void main(String[] args) {
		GraphicCircle gc = new GraphicCircle(1, 1, 1, "Red", "Green");
		Circle c = gc;
		// Circle c now has access to only x, y and r, but keeps track of all variables.
		System.out.println(c == gc); // True
		System.out.println(c.equals(gc)); // False
		GraphicCircle gc2 = (GraphicCircle) c;
		// Now gc2 is identical to gc
	}
}
```

## Packages
If you want multiple files which are all related, it is best to put them all in the same package (write `package packageName`) at the top of each related script. To import a class into another script or package, use `import packageName.classname`

## The  `instanceof` Comparison
The `instanceof` comparison (often used in if statements) returns `true` if the current object is of type `class`, or a subclass of `class`. 
- Usage: `if (obj instanceof Circle) // Circle specific implementation`.