## Overview
Often in software design, the initial design is clean, elegant and well-structured. Over time, design degrades due to evolving requirements and rushed changes. This is hard to maintain/evolve, and is known as **software rot**. The symptoms of this are:
- **Rigidity**: Small changes make widespread impact due to interdependencies
- **Fragility**: One change breaks unrelated parts
- **Immobility**: Useful components are not transferable
- **Viscosity**: The environment/process encourages 'hacks' rather than clean design

Most software rot are caused by bad dependency management/structures, rather than evolving requirements.

### What are Software Design Principles?
Software design principles are guidelines under which to develop systems which are:
- **Maintainable**: Software should be easy to update and enhance without extensive refactoring
- **Flexible**: Systems should adapt smoothly to changing requirements
- **Reusable**: Components and Modules should be designed to be easily reusable across various parts of the application or even in different projects
- **Robust**: The software should handle errors gracefully and maintain functionality across different circumstances 

Adhering to these principles helps mitigate common issues such as design rot and ensures software remains scalable and adaptable over time. Good design anticipates change, while bad design breaks under it.

## SOLID Principles
We have the **SOLID** acronym which represents five crucial principles for object-oriented design:
- **Single Responsibility Principle**: A class should only have one reason to change, focusing on a single functionality. A class should only do one thing.
- **Open/Closed Principle**: Software entities should be open for extension but closed for modification
- **Liskov Substitution Principle**: Objects of a superclass should be replaceable with objects of subclasses without affecting the correctness of the program.
- **Interface Segregation Principle**: Clients should not be forced to depend on interfaces they do not use. Favour many specific interfaces over a single general-purpose one.
- **Dependency Inversion Principle**: Depend on abstractions, not concrete implementations. Higher-level modules should not depend on lower-level modules, but rather on abstractions. The higher level modules should not need to worry about the implementation of lower level modules.
## Software Cohesion and Coupling
- **Cohesion** is the degree to which elements of a module/class belong together.
- **Coupling** is the degree of interdependence between software modules/classes.
**High cohesion** and **low coupling** are hallmarks of good software design.

There are a few types of coupling:
- Data Coupling: Modules share data through parameters
- Control Coupling: One module controls the flow of another
- External Coupling: Modules depend on externally imposed data formats
- Common Coupling: Shared global values
- Content Coupling: One module modifies data of another

To achieve high cohesion, use SRP as far as possible, group related functionalities, and avoid "God" classes. If a class or a method grows too large, refactor it. To achieve low coupling, minimise shared data, use interfaces and abstractions, apply dependency injection, and use event-driven or observer patterns, for loosely dynamically coupled systems.


Design principles are good for identifying and removing code smells. However, if there are no code smells, they shouldn't be used. Don't make your software needlessly complex.

## Principle of Least Knowledge (Law of Demeter)
The principle of least knowledge (also called the Law of Demeter) suggests that an object/module should **only** talk to its immediate friends - not to strangers. In other words, only call methods you know.

Formally, a method `M` of an object `O` make only invoke methods that belong to:
- `O` itself
- `M`'s parameters
- Any objects instantiated with `M`
- `O`'s direct fields (its own instance variables)
The code smell telling you that the LoD is being violated is **method chaining** (not to be confused with **method forwarding**) - this is when a line looks like `A.B().C().D()`. Note that native java functions or methods like `equals()` or `toString()` do **not** count as all classes have knowledge of these functions.


The law of Demeter minimises coupling, which enhances maintainability, and improves encapsulation.

## Liskov Substitution Principle
Objects of a superclass should be replaceable with objects of a subclass without breaking the application. Therefore, if it doesn't make sense for a subclass to inherit a superclass method, then it breaks LSP.

### Example: Penguins and Birds
Code breaking LSP:
```java
public class Bird {
	void fly() {
		System.out.println("Flying...");
	}
	void eat() {
		System.out.println("Eating...");
	}
}

public class Penguin extends Bird {
	@Override
	void fly() {
		throw new UnsupportedOperationException("Penguin can't fly");
	}
}
```

This is fixed by having a subclass of `Bird` called `FlyingBird` and having relevant classes extend that.

```java
public class Bird {
	void eat() {
		System.out.println("Eating...");
	}
}

public class Penguin extends Bird {
	// implementation
}

public class FlyingBird extends Bird {
	void fly() {
		System.out.println("Flying...");
	}
}
```

LSP encourages safe polymorphism and correct hierarchy modelling, and reduces unexpected behaviour at runtime. It is like a contract: subclasses must honour the promise of their superclass.

## Covariance and Contravariance
Covariance and Contravariance describe how types behave in inheritance when method overriding:
- **Covariance**: Return type of overridden method can be **more specific** than the superclass method
- **Contravariance**: Parameters of overridden method can be **more general** than the superclass method
The rules for method overriding in java are summarised in the table:

| Aspect          | Rule in OOP Overriding                            |
| --------------- | ------------------------------------------------- |
| Method Name     | Must match                                        |
| Parameters      | Type must match. Contravariant conditions allowed |
| Return Type     | Covariant Allowed                                 |
| Exceptions      | Can be narrower                                   |
| Access Modifier | Can be more open                                  |

