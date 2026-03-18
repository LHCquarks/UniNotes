## Factory Pattern
The factory pattern is a creational design pattern that uses 'factory methods' to deal with the problem of creating objects without having to specify the exact class of the object that will be created (further than being subclasses of a common interface). One class behaves as a 'factory' which creates the objects of a family in a superclass but allows subclasses to alter the type of objects that will be created.

For example, I might have a program written which displays different shapes onto the screen. I want the logic to display the shape to be the same, so I don't specify which subclass of `Shape` to create, rather let the `ShapeFactory` handle the logic of specifying a class.

### Implementation Details
A possible implementation method for the factory pattern involves a `Creator` class, which contains the method `CreateProduct`. This method will take in an argument(s) which is used to determine which class to create.

The classes must all be subclasses of a parent interface, `Product`. This contains all the methods common to each class, and each concrete class which is created by the `Creator` class will extend `Product`.

## Abstract Factory Pattern
Say you've made a factory pattern, and you're producing different types of furniture. You've increased the magnitude of your factory, and now you're selling multiple styles of each furniture type. The **abstract factory** pattern allows you to produce families of related objects without specifying their concrete classes.

An abstract factory is just an abstraction up from the factory class. It allows you to create multiple factories which are subclasses of the common `AbstractFactory`, each producing a different variant/group of objects. 

Although concrete factories instantiate concrete products, signatures of their creation methods must return corresponding _abstract_ products.

If your product doesn't deal with product families, you don't need the abstract factory pattern.
### Implementation Details
A possible implementation of the Abstract Factory Pattern would be to have the `AbstractFactory` class with method `createProduct()`.  Then, each time a variant of the `Product` family is added to the program, a `Factory` class extending `AbstractFactory` is added, with specific implementations for  the `createProduct()` method. 

