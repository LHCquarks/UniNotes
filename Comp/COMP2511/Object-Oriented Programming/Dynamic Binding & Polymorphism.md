## Polymorphism
Polymorphism is a powerful feature of java which allows a `subclass` to behave/be treated as a `class` type. For example, if we have an abstract class`shape` with subclasses `circle`, `square`, `rectangle`, you could keep track of all the shapes with a `shape[]` array, and assign each entry as a different (subclass) shape. This can also be done with classes which implement the same interface. 

## Dynamic Binding / Method Overriding
Dynamic Binding refers to the process where the implementation of a method is determined at runtime. If there are two classes `A` and `B`, where `B` extends `A`, which both contain the same method `printClass()` with identical method signatures, dynamic binding allows `B` to override `A`'s implementation, so that if an object of type `B` (or an object which is created **from** an object of type `B`) calls the method `printClass()`, `B`'s implementation will be used.

There is an exception for this. Static methods are never overridden, because static methods are associated with the class, not the instance.