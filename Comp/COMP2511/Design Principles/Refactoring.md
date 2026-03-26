## Overview
Refactoring is the process of restructuring existing code without changing its external behaviour. The aim is to improve structure, readability, and maintainability, detect bugs, increase development speed, conform to design principles and eliminate code smells. 

Refactoring should be done **before** adding new features if the current structure is not suitable, when fixing bugs, and during code reviews

## Code Smells
Code smells are indicators of potential design issues, which don't necessarily guarantee issues. Refactoring addresses code smells. Some common code smells include:
- Duplicated Code
- Long Method
- Large Class
- Long Parameter List
- Divergent Change (Adding/changing feature requires changing many unrelated methods within the same class)
- Shotgun Surgery (Adding feature requires changing many classes)
- Feature Envy (Class accesses data/methods of another class more often than its own)
- Lazy Classes
- Data Classes


## Refactoring Cycle
- Identify Code Smell
- Write tests to confirm current behaviour
- Apply small refactoring step
- Re-run tests
- Repeat
## Refactoring Techniques

### Extract Method
Extracting a Method involves identifying logical chunks of code and extracting them into separate methods. This improves readability and reduces duplication of code.
### Move Method
Move method refers to moving a method to the class whose data the method uses the most.
### Replace Temp with Query
Move mathematical/logical expressions into methods instead of temporary variables 

### Replace Conditional with Polymorphism
`switch` of `if-else` chains based on types/classes are hard to maintain and violate Object-Oriented Programming Principles, because adding a new type means changing every switch statement (Open/Close Principle). These should be replaced with inheritance. Define a superclass with an abstract method, and implement this method in each subclass, each representing a case of the switch.
### Refactoring using Composition
It's better to favour composition over inheritance. Instead of extending a class (is-a relationship), use composition (has-a) and method forwarding.
## Design/Code Smells

### Refused Bequest
When a class inherits inappropriate behaviour, this is calls **refused bequest**. For example, the code below:
```java
abstract class Transport {
	private String model;
	public String getModel() {
		return model;
	}
}

class Camel extends Transport {
	@Override
	public String getModel() {
		throw new UnsupportedOperationException("Camels don't have models");
	}
	// This method is inappropriate for the camel class.
}
```

The treatment for this problem is generally to move the method down a class. In this case, it could be moved to a `Vehicle` class, which can be further extended by relevant classes.
### Long Parameter List
To avoid long parameter lists, encapsulate related parameters into a data class, and pass an instance of that class instead.

```java
void CreateUser(String name, int age, String email, String phone);
// Can be fixed by wrapping this data in a class, then passing in an instance
class UserInfo {
	private String name;
	private int age;
	private String email;
	private String phone;
	// Relevant Constructors, Getters and Setters
}

void CreateUser(UserInfo info);
```

Treatment of this problem involves:
- If the data comes directly from a method call of another object, call this method within the current method instead of including it as a parameter
- Instead of passing a group of data received from another object as parameters, pass the object itself
- If the parameters all come from different sources, pass them as a single parameter object, 
### Large Method/Class
**Method**
Treat this smell (many lines, doing multiple things) using **Extract Method**

**Class**
Treat this smell (20+ methods, many attributes) using **Extract Class** to separate concerns
### Similar Code Fragments
**Case 1**
If the same code is repeated within the same class, use **Extract Method** and invoke it from each place of repetition
**Case 2**
If the same code is repeated in two subclasses of the same level, use the **Extract Method** in both subclasses, use **Pull Up Field/Method/Constructor** to unify code in the superclass. For code which is similar but not identical, use the **Template Method Pattern** . For different algorithms, use **Strategy Pattern**
**Case 3**
If the same code is repeated in two unrelated classes, use **Extract Superclass** to unify shared logic

### Feature Envy
If a method is more interested in another class' data than its own, then you have a code smell called **feature envy**. This causes unnecessary coupling and breaks encapsulation. The treatment involves:
- **Move Method** into the class which owns the data (or the majority of the data)
- **Extract Method** then **Move Method** if only part of the code smells of feature envy.
### Divergent Change
If one class is changed in many unrelated ways for different reasons, then the code smells of **divergent change**. The class probably breaks the Single Responsibility principle. Treat this smell by identifying the reasons for change and separate them into cohesive classes, encapsulating each responsibility.
### Shotgun Surgery
Shotgun surgery appears similar to divergent change, but is a different issue altogether. When a small change requires updating many different classes, the code is brittle, and you have the code smell **shotgun surgery**. This is treated by localising the related methods/fields to a single class.

Note: the difference between Divergent Change is listed below:
- Divergent Change: One class changes for many unrelated reasons
- Shotgun Surgery: One change spreads across many classes
Refactoring addresses both of these, improving modularity and flexibility
