## Overview
A domain model is used to visually represent important domain concepts and relationships between them. They help communicate important domain specific concepts and are used during the requirements gathering and designing phase. One way of representing a domain model, which is used in this course, is a **UML Diagram**.
### Requirements Analysis v.s. Domain Modelling
Requirements analysis determines external (frontend) behaviour, while Domain Modelling determines internal (backend) behaviour. However, they are mutually dependent. Domain Modelling supports clarification of requirements, whereas requirements help build up the model.

Now, it's worth mentioning there's many types of UML diagrams. This course mainly uses Class Diagrams and Sequence Diagrams. The diagram below shows the many types of UML diagrams:
![[UML Diagram Types.png]]


## How do UML Diagrams Work?
A UML diagram is a sort of 'flowchart' with boxes representing classes and interfaces, containing methods and attributes, with different arrow types indicating relationships (inheritance, extension, association, composition, etc.). 
### Modelling Classes in UML Diagrams
A class in a UML diagram might be represented like this:

| className                                                    |
| ------------------------------------------------------------ |
| \-height: float<br>\-width: float                            |
| +getHeight(): float<br>+getWidth():float<br>+getArea():float |
**Notation**
- Access Modifiers can be indicated through the first symbol: `+` represents public, `-` represents private, and `#` represents protected.
- Constant (`final`) values are represented using bold, `static` values are represented using underlines, and `abstract` classes and methods are represented using italics.
**Classes v.s. Attributes**
How to decide if a concept is best represented by a class or an attribute?
	- If the concept can be represented using a number or a string, it should be an attribute.
	- If the concept is **not** representable using a number/string, make a class for that concept.

### Modelling Relationships in UML Diagrams 
Relationships are modelled using arrows with different arrowheads. The image below shows the types of relationships between classes:
![[UML Diagrams Relationships.png]]

- **Association**: One class uses another class, but it is not yet clear which direction the dependency occurs. 
- **Inheritance**: One class extends another class (arrow points to superclass)
- **Realisation**: 'Implements' relationship
- **Dependency**: A class in some way depends on another (not used often)
- **Aggregation**: A class contains another class, but can exist without the contained class (diamond is on container class)
- **Composition**: A class contains another class, but cannot exist without the contained class (diamond is on the container class)