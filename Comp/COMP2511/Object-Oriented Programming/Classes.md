## Designing a Class
- Think carefully (😭) about functionality (methods) a class should offer
- Always try to keep data private (local to the class/instance), and use getters and setters (which adds security - when **getting/settings** data, do all necessary checks) 
- Consider the different ways an object might be created
- Always initialize data
- Break up classes with too many responsibilities
- Factor out common attributes and behaviors, and place these in a class. Then use association/inheritance relationships between these classes.
### Terminology:
- `public`: data/method can be accessed and called from anywhere
- `private`: data/method can only be accessed from within the class
- `protected`: data/method can only be accessed from within the class or any subclass
- `final`:  Unchangeable (constant)
- `static`: Accessible by referencing the class (do not need to initialise a class instance to access object). If this is included, only one copy of the variable is stored in memory, and if not, it is called an **instance variable** (a copy is created for every instance of the class).
- `this.*` : if you have a local definition of a variable `*` with the same name as a class variable, `this.*` refers to the class definition, while `*` refers to the local definition.
## Constructors
- A constructor initialises an instance of a class. To construct an instance of a class, use the syntax `className objectName = new className(argument 1, ...)`
- Name of constructor must be identical to the name of the class
- When a constructor is called, the `super()` function is automatically called, which is the constructor of the constructor class' superclass. The object class is the superclass of a 'parent' class. This can be overridden to call the `super(argument1, ...)` constructor if necessary
- It's possible to have multiple constructors with different arguments. 
- If there are two constructors for an object, it is good practise to call `this()` to reduce repeated code, and to use `this.setX()`  (use getters and setters in constructors)
```java
public class Circle {
	private static final double pi 3.14159;
	private int x, y;
	private int r;
	// Constructor 1
	public Circle(int x, int y, int r) {
		this.x = x;
		this.y = y;
		this.r = r;
	}
	// Constructor 2
	public Circle() {
		this(1, 1, 1);
	}
	public double circumference() {
		return 2 * pi * r;
	}
	public double area() {
		return pi * r * r;
	}
}
```
## Getters/Setters
It's good practise to make all attributes (variables) private, and use getters and setters to access the data. This adds a layer of protection and also maintains encapsulation. Getters are methods which return the attribute, while setters are methods which save the value. For example:
```java
public class Circle {
	private int radius;
	
	public int getRadius() {
		return radius;
	}
	
	public void setRadius(int radius) {
		this.radius = radius;
	}
}
```
## Access Modifiers

| Access Modifier       | Visibility                                |
| --------------------- | ----------------------------------------- |
| public                | Visible to all                            |
| private               | Visible within class                      |
| protected             | Visible to the package and all subclasses |
| default / no modifier | Visible to package                        |
## Overriding Methods
- @Override overrides the default method with the same name. For example, `toString()`, `equals()`. 
- Overriding the `equals()` function is useful because 
- Overriding a method requires the same arguments to be used (otherwise it's a different method signature and you're defining a new function). Therefore, when overriding the `equals()` method, you need to take in the argument `Object objName`.
- An overridden `equals()` class may look like this:
```java
@Override
public boolean equals(Object obj) {
	if (obj == null) return false;
	if (obj == this) return true;
	if (this.getClass() != obj.getClass()) return false;
	// Both are sameclass, so downcast as className :
	className other = (className) obj;
	// Now check all attributes
	return true;
}
  ```

## Strings
- A string is a proper type in java, unlike c. 
- String literals are stored in read-only memory. If you initialise two strings `String s1, s2 = "Sydney"`, they both point to the same memory address and therefore `s1 == s2`.
- If you want two different strings which are the same, use the constructor: `String s3 = new String("Sydney")` and `String s4 = new String("Sydney")`.
- Therefore, each instance of an object is a new address. so `s3 != s4` but `s3.equals(s4)`