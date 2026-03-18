## Overview
In procedural programming language (like 'C'), programming tends to be **action-oriented**, whereas in Java, programming is **object-oriented**

In **procedural** programming:
- Groups of actions that perform some tasks are formed into functions
- Functions are grouped to form programs
In **OOP**,
- Programmers concentrate of creating their own user-defined types called classes
- Each class contains **data** as well as a set of **methods** which manipulate the data
- An instance of a class is called an object
- OOP **encapsulates** data and methods into objects (the data and methods of an object are intimately tied together)
- Objects have the property of information hiding (public and private data/methods). This is useful to reduce coupling
- A class is similar to an ADT

A program is like a state machine.
## Inheritance in OOP
Inheritance relationships form tree-like hierarchical structures. A **subclass** of a class inherits all of its data and methods, and can contain more. 
- Note: subclass is a little misleading - a subclass will have **more** behavior/data. A subclass will have everything in the parent class and more, which is dissimilar to a subset in mathematics.
- In some O-O languages, it is possible for a subclass to inherit data/methods from multiple superclasses. Multiple-Inheritance is not possible in java (this will be touched on again later).
- **"Is-a" Inheritance relationship** - a `subclass` is a `superclass`. However, do not use inheritance unless all or most attributes/methods make sense. For example, a circle is a(n) oval, but it doesn't make sense for a circle to be a subclass of an oval (oval has width and height, while a circle only has radius)
## Association in OOP
You might have a class containing an object of another class within it to store its state/attributes. This way, classes can be created using composition of other classes. This is different to Inheritance, which *extends* classes.
- **"Has-a" Association relationship** - the `parentClass` *has a* `childClass`.
- Example: A rectangle **is not** a line, but it contains four lines. If we have a class `line`, then we might construct a `rectangle` class which contains four `line` instances 
- Association is used more frequently than inheritance
## Pillars
- Encapsulation
- Inheritance
- Association
- Polymorphism