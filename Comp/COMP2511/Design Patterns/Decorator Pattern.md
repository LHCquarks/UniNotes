## Overview
The decorator pattern allows us to selectively add functionality to an object (not the class) at runtime, based on the requirements. This is done without changing the class so that Open-Close principle is not violated. The decorator pattern only updates existing implementation, not adding any new implementation.

Inheritance extends behaviours at compile time, and additional functionality is bound to every instance of that class for its lifetime. So, the decorator pattern prefers a composition structure over inheritance. This is done by providing a wrapper to the existing class. An important feature of the decorator method is that Objects can be decorated in different orders, through recursion.

A use case for the decorator pattern may be a cafe system, which calculates the cost based on the additions added to each item in the order (e.g. extra milk, decaf, with cream, etc.). It becomes excessively complicated to make a class for each complication, so we use the decorator pattern, with the base item (coffee), and all the extras (additions).
## Implementation Details
The structure of a Decorator Pattern is a lot like the Russian Doll Toys. Every time we add a decoration, we wrap the object in the decoration, and the instance of the decoration behaves as the new object.
- A **Component** Interface/Abstract Class defines the common interface for both wrappers and the wrapped object
- A **Concrete Component** defines the class being wrapped (base object class). It Implements/extends **Component**
- The **Base Decorator** is an abstract class which also implements/extends **Component**. It also contains the wrappee (the object of type **Component** to be wrapped). 
- The **Concrete Decorator** is the decoration being added to the base object, defining extra behaviours through the **Component** methods. Concrete decorators override methods of the **Base Decorator** and execute their behaviour recursively before or after calling their parents (wrappee) equivalent method.
Each new decoration is another layer of the **Concrete Decorator** class.
### Implementation Example
```java
// Component Example
public abstract class Beverage {
	String description = "Unknown Beverage";
	
	public String getDiscription() {
		return description;
	}
	
	public abstract double cost();
}

// Concrete Component Example
public class Decaf {
	public Decaf() {
		description = "Decaf Coffee";
	}
	
	public double cost() {
		return 1.05;
	}
}

// Base Decorator Example
public abstract class CondimentDecorator extends Beverage {
	private Beverage beverage;
	public abstract String getDescription();
}

// Concrete Decorator Pattern
public class Cream extends CondimentDecorator {
	public Cream(Beverage beverage) {
		this.beverage = beverage;
	}
	
	public String getDescription() {
		return beverage.getDescription + ", Milk";
	}
	
	public double cost() {
		return 0.10 + beverage.cost();
	}
}
```