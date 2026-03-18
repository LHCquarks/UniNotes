## Multiple Inheritance
- In Java, a class can extend exactly one superclass. This is called **single inheritance.**
- While some object-oriented language allow multiple inheritance, it can lead to problems when a superclass' behaviour is inherited in multiple ways (and memory management can become strange)
- In Java, an **interface** in the class hierarchy can be used to add multiple inheritance.

## Interfaces
An interface is like a header file.
- Interfaces are like abstract classes, but:
	- All methods in an interface are implicitly abstract.
	- Variables declared in an interface must be static and final (constants)
- **Sub-interfaces**: Interfaces can extend other interfaces
- To implement an interface, a class must declare the interface using `implements interfaceName` in the class signature
- A class can implement more than one interface
- All methods of an interface **must** be implemented in the class which implements it (duh).
- **Polymorphism**: If you have a class `Circle` which implements `ShapeI`, it is polymorphic and `Circle` can be treated as type `ShapeI`
- **Method Forwarding**: If, for example, you have an interface `X` with implementation in class `C`, and you have another class `B` which extends `A`. If `B` has the same `X` implementation as `C`, you might create an instance of class `C` in `B` and use Method Forwarding
## Interface or Abstract Class?
It is always best to start with an interface, and move to an abstract class if code becomes repetitive or a need arises.

