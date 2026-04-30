
# Multiple Choice
## Question 1 (2 marks)

On a bike, there are one or more tires.

The following relationship is an example of:

- **A) Aggregation** ✓
- B) Composition
- C) Neither
## Question 2 (2 marks)

Consider the following lambda function which prints log. The type signature has been redacted.

`[redacted] logger = log -> System.out.println(log);`

Pick the most semantically correct type from the list below:

- A) Function<String, Boolean>
- B) Consumer
- **C) Predicate** X Predicate
- D) Supplier

## Question 3 (2 marks)

Grace is developing a simple application that generates a course outline for new CSE courses.

There are exactly three types of course outline - COMP, SENG and BINF. No other types or subtypes of courses exist. Each course outline is composed of two parts:

- A randomly generated course code, in the format COMPXXXX, SENGXXXX, or BINFXXXX.
- The lecturer of the course, randomly chosen from a provided list of all valid lecturers for either COMP, SENG, or BINF courses.

All course outlines have exactly these two features, nothing more or less.

Grace would like to pass one of the strings “COMP”, “SENG” or “BINF” to a particular method and receive an instance of an appropriate course outline in return.

Which of the following design patterns would be the most appropriate for this design?

- A) Composite Pattern
- **B) Factory Pattern** ✓
- C) Abstract Factory Pattern
- D) Decorator Pattern
## Question 4 (2 marks)

The following is taken from a student’s Assignment II blog.

> In Assignment II, after I refactored the code, I started work on adding new features but found I had to go and modify everything because the design didn’t work with the new requirements.

Which SOLID principle is being violated? Select the most suitable answer.

- A) Single Responsibility Principle
- **B) Open-Closed Principle** ✓
- C) Liskov Substitution Principle
- D) Interface Segregation Principle
- E) Dependency Inversion Principle
## Question 5 (2 marks)

Which of the following statements is correct?

- A) Overloaded methods have the same method signature, while overridden methods have a different method signature. -- 
- B) Overloaded methods can have different access modifiers, while overridden methods must have the same access modifier.
- C) Overloaded methods are defined in different classes, while overridden methods are defined in the same class. --
- **D) Overloaded methods are resolved at compile-time, while overridden methods are resolved at runtime.** ✓

Overloaded: Same name, different arguments. Same access modifier. 
Overridden: Same name, same arguments, sub-class
## Question 6 (2 marks)

Which of the following statements is **untrue** about method overriding?

- A) Constructors cannot be overridden
- B) If a static method in the base class, is redefined in the sub-class, the later hides the method in the base class
- **C) In method overriding, run-time polymorphism ensures that instantiated, the call to any method in the base class will be resolved to the correct method, based on the run-time type of the object instantiated.**  X
- D) During method overriding, the overridden method in the sub-class can specify a less permissive access modifier ✓
## Question 7 (2 marks)

A design pattern used to enhance a component’s functionality dynamically at run-time is:

- A) Composite Pattern
- **B) Decorator Pattern** ✓
- C) Abstract Factory Pattern
- D) Observer Pattern
## Question 8 (2 marks)

Which of the following exceptions must be handled by a try-catch block or declared?

- **A) NullPointerException**
- B) MalformedURLException ✓
- C) ClassCastException
- D) ArithmeticException
## Question 9 (2 marks)

Consider the following code:

```java
class X {
    public void a() {}
}

class Y {
    public void b() {}
}

class Z extends X, Y {
    protected void a() {}

    public void b() {}

    public void b(String arg) {}
}
```

Now, consider the following statements about the code:

- (1) The code doesn’t compile because there is more than one class in the same file;
- (2) The code doesn’t compile because double inheritance is not possible in Java; ✓
- (3) The code doesn’t compile because the methods a and b are not marked with @Override
- (4) The code doesn't compile because you cannot overload a method that is overriding a method in a superclass;
- (5) The code doesn’t compile because a cannot have its visibility reduced from the superclass to the subclass. ✓
- (6) The code does compile.

Which of the following sets of statements about the code are true?

- A) (1), (2)
- B) (1), (3), (5)
- C) (2), (3), (4), (5)
- **D) (2), (5)** ✓
- E) (2), (4), (5)
- F) (6)

## Question 10 (2 marks)

Nick is currently working on a UNSW CSE system. Which of the following statements is most accurate about how Nick should build the system?

- A) The system should be built in Java so that Design Patterns can be used.
- B) Documentation is unimportant as the code should be written so well it is understandable.
- **C) The design should allow new engineers to easily join the project after Nick has left.** ✓
- D) Testing the system works is a lower priority than getting it working.
## Question 11 (2 marks)

Which of the following would be a valid use case for instanceof instead of getClass for checking the type of an object?

- **A) Checking if an object complies with an interface so that we can use a method on that interface**
- B) Implementing the equals method for an object
- C) It’s a trick question, you should never use instanceof in your code at all


# Short Answer
## Question 1

For each code snippet:

1. Identify the logic error present (1 mark); and
2. Write a failing assertion that would catch the logic error as part of a unit test (e.g. `assertEquals(4, f(2))`) (1 mark)

### Part A (2 Marks)

```java
@Override
public boolean equals(Object obj) {
    if (this == obj) return true;
    if (obj == null) return false;
    if (!(obj instanceof Article)) return false;

    Article other = (Article) obj;

    return this.title.equals(other.title) && this.views.equals(other.views);
}
```

The logic flaw is the use of `obj instanceof Article` because instanceof is not a symmetric relation, which is required by equals(). Subclasses are instances of the superclass. Let `subClass` be a subclass of `Article` - the following test would fail:
```java
Article article = new Article(title, views);
subClass other = (subClass) article;
assertEquals(article, other);
```

### Part B (2 marks)

```java
public List<Integer> withoutOddNumbers(List<Integer> numbers) {
    for (Integer number : numbers) {
        if (number % 2 != 0) {
            numbers.remove(number);
        }
    }

    return new ArrayList<Integer>(numbers);
}
```

The logic flaw here is that the list being iterated over is being modified. This leads to undefined behavior. The following test would fail:
```java
ArrayList<Integer> list = new ArrayList<Integer>();
list.add(1);
list.add(2);

ArrayList<Integer> list2 = new ArrayList<Integer>();
list2.add(2);

assertEquals(withoutOddNumbers(list), list2)
```

## Question 2 (2 Marks)
Consider the following two classes from a previous COMP2511 assignment:

```java

public final class Angle {
    // Internally we store everything as radians.
    private final double radians;
    private Angle(double radians) {
        this.radians = normalise(radians);
    }
    /**
     * Create an angle from radians.
     */
    public static Angle fromRadians(double radians) {
        return new Angle(radians);
    }
    /**
     * Create an angle from degrees.
     */
    public static Angle fromDegrees(double degrees) {
        return new Angle(Math.toRadians(degrees));
    }
    private static double normalise(double radians) {
        return radians % (2 * Math.PI) + (radians < 0 ? 2 * Math.PI : 0);
    }
    /**
     * Compare this angle to another angle.
     * Returns...
     * 1  if this is greater than other
     * 0  if this is equal to other
     * -1 if this is less than other
     */
    public int compareTo(Angle other) {
        return Double.compare(this.radians, other.radians);
    }
    /**
     * Add another angle to this angle and return a new angle
     * representing the result.
     */
    public Angle add(Angle other) {
        return Angle.fromRadians(this.radians + other.radians);
    }
    /**
     * subtract another angle from this angle and return a new angle
     * representing the result.
     */
    public Angle subtract(Angle other) {
        return Angle.fromRadians(this.radians - other.radians);
    }
}
```


```java
public final class MathsHelper {
    /**
     * Determine the distance between a satellite and another satellite.
     */
    public static double getDistance(
	    double satelliteHeight, 
	    Angle satelliteAngle, 
	    double otherHeight,
        Angle otherAngle
    ) {
        // convert to euclidean
        double satX = Math.cos(satelliteAngle.toRadians()) * satelliteHeight;
        double satY = Math.sin(satelliteAngle.toRadians()) * satelliteHeight;
        double otherX = Math.cos(otherAngle.toRadians()) * otherHeight;
        double otherY = Math.sin(otherAngle.toRadians()) * otherHeight;
        // find length of line between euclidean points
        double length = Math.sqrt((satX - otherX) * (satX - otherX) + (satY - otherY) * (satY - otherY));
        return length;
    }
    /**
     * Determine the distance between a satellite and a device.
     */
    public static double getDistance(double satelliteHeight, Angle satelliteAngle, Angle deviceAngle) {
        return getDistance(satelliteHeight, satelliteAngle, RADIUS_OF_JUPITER, deviceAngle);
    }
    /**
     * Determine if a satellite is visible to a device.
     */
    public static boolean isVisible(double satelliteHeight, Angle satelliteAngle, Angle deviceAngle) {
        return isVisible(satelliteHeight, satelliteAngle, RADIUS_OF_JUPITER, deviceAngle);
    }
    /**
     * Determine if a satellite is visible to another satellite.
     */
    public static boolean isVisible(double satelliteHeight, Angle satelliteAngle, double otherHeight,
            Angle otherAngle) {
        // convert to euclidean
        double satX = Math.cos(satelliteAngle.toRadians()) * satelliteHeight;
        double satY = Math.sin(satelliteAngle.toRadians()) * satelliteHeight;
        double otherX = Math.cos(otherAngle.toRadians()) * otherHeight;
        double otherY = Math.sin(otherAngle.toRadians()) * otherHeight;
        double ax = satX;
        double ay = satY;
        double bx = otherX;
        double by = otherY;
        double a = (bx - ax) * (bx - ax) + (by - ay) * (by - ay);
        double b = 2 * (ax * (bx - ax) + ay * (by - ay));
        double det = RADIUS_OF_JUPITER * RADIUS_OF_JUPITER * (a) - (ax * by - bx * ay) * (ax * by - bx * ay);
        if (det <= 0)
            return true;
        double sqrtDet = Math.sqrt(det);
        double tPos = (-b + sqrtDet) / (2 * a);
        double tNeg = (-b - sqrtDet) / (2 * a);
        return !((0 <= tPos && tPos <= 1) || (0 <= tNeg && tNeg <= 1));
    }
}
```

Which class do you think has better **cohesion**? Justify your answer

The `Angle` class has better cohesion. Cohesion is the level at which design elements 'fit' in the given class.  The `Angle` class is specific in that all methods definitely belong in the `Angle` class because they operate on class attributes or fields relating to class attributes. The `MathHelper` class contains many unrelated methods which should separated into relevant classes (e.g. a `Position` class for distance). The massive size of the class is a smell which indicates this.

## Question 3 (10 marks)

Consider the following Java code:

```java
class Foo {
    public ArrayList<String> bar() {
        return new ArrayList<String>();
    }
}

class Foo2 extends Foo {
    @Override
    public List<String> bar() {
        return new ArrayList<String>();
    }
}
```

The code currently does not compile and has the following error message (on `List<String> bar` in `Foo2`):

> The return type is incompatible with `Foo.bar()`

- a) Explain the difference between **covariance** and **contravariance**. (2 marks)
Covariance is when a more specific type is used in place of another general type for method return values. Contravariance is when a more general type is used in place of a specific type for method parameters.
- b) Does the above code fail to compile because it breaks **covariance** or **contravariance**? (1 mark)
The above code breaks covariance 
- c) With reference to Design by Contract, explain how the above code constitutes invalid inheritance and **violates the Liskov Substitution Principle**. (4 marks)
The Liskov Substitution Principle states that a subclass must be substitutable for a superclass without changing any functionality or breaking covariance or contravariance. This links into Design by Contract, which outlines preconditions, postconditions and invariants which must be followed to guarantee a working product. 

The above code breaks the Liskov Substitution Principle as if `Foo2` is substituted as `Foo`, the promised return type of bar (`ArrayList<String>`) is overridden to a more general type (`List<String>`) and thus covariance is broken.  The Contract established by `Foo` is violated so the inheritance is invalid.
## Question 4 (3 marks)

Carl, Amanda and Alvin are working on the Assignment II codebase to add some new features for 23T3. They come across a note from the previous engineering team:

> We were trying to make the way Sunstones are implemented more extensible through refactoring in a few different classes. However, we found that when we tried to make these changes, the InventoryItem class would always break.

State what design smell is present in the above description, and explain how the smell present is different from Shotgun Surgery.

The design smell is Divergent Change, which is where a class is changed for many unrelated ways when updating the codebase due to the single responsibility principle being violated. This is different from Shotgun Surgery, which is where adding a feature required many different classes to be changed. In other words, many different changes affecting one class is Divergent Change, and one change affecting many different classes is shotgun surgery.
## Question 5 (5 marks)

Consider the following student's Assignment I code:

```java
for (Entity entity2 : entList) {
    if (entity.canLoad(entity2)) {
        if (entity2 instanceof PassengerTrain) {
            for (Entity entity3 : entList) {
                if (entity instanceof CargoTrain && !(entity3 instanceof Passenger)) {
                    if (entity2.canLoad(entity3)) {
                        canLoad.add(entity3.getId());
                    }
                } else if (!(entity instanceof CargoTrain) && entity2.canLoad(entity3)) {
                    canLoad.add(entity3.getId());
                }
            }
        }
        canLoad.add(entity2.getId());
    }
}
```

- a) State two code smells present in the above code. (2 marks)
Conditional Complexity (nested if statements) and Feature envy.
- b) In your own words, explain what you think is the underlying design problem causing this code smell and what should be done to improve the design. (3 marks)
The code is hard to read because it contains complex logic pathways due to the nested if statements. This could be treated by moving parts of the logic into other methods, which are placed in the class which contains more data used in the method. The method name would make it easier to follow as the nesting would not be an issue, and each method would have a simpler logic flow.
## Question 6 (5 marks)

Large companies with many projects need a way to allow people to keep track of multiple projects at the same time. A system called “Team Central” allows a project manager to create a ticket for their project. They can then add a series of stakeholders to the ticket who are interested in how the project is progressing.

Every week, the project manager posts an update on the Team Central ticket with information about how the project is progressing, and whether it is On Track, Off Track, At Risk or Complete. The stakeholders are notified via email when this update is posted. It its possible for new stakeholders to be added to the list, and for stakeholders to be removed from the list while the project is ongoing.

**What Design Pattern could be used to model this? In answering, justify your choice by describing how the above scenario relates to the key characteristics of your chosen Design Pattern.**

The observer pattern could model this software. The observer pattern concerns two main groups of objects: Subject, and Observers. Subjects (Project Managers) keep a list of Observers (Stakeholders) who are automatically notified after every change in state of the observer. 

The event-driven nature of this design-pattern is helpful for automatic updates to stakeholders. The weekly update could call a method which calls a subscriber method, automatically sending them an email. Another method could add and remove subscribers to/from the list of observers.
## Question 7 (4 marks)

With reference to Design by Contract and the Liskov Substitution Principle, explain whether or not the following inheritance relationship is valid. Justify your answer.

```java
class StandardUNSWLatePenalty {
    /**
     * @postconditions: The late penalty will be at most
     * the number of days late * 5
     */
    public int calculateLatePenalty(LocalDateTime dueDate, LocalDateTime submittedDate) {
        // ...
    }
}

class COMP2511AssignmentIILatePenalty extends StandardUNSWLatePenalty {
    /**
     * @postconditions: The late penalty is the number of days late * 2
     */
    public int calculateLatePenalty(LocalDateTime dueDate, LocalDateTime submittedDate) {
        // ...
    }
}
```


Design by Contract requires that preconditions are not strengthened and postconditions are not weakened. Since here postconditions are not weakened (rather, strengthened) by having a more specific output, this is a valid Inheritance relationship.

Liskov Substitution Principle states that a subclass must be substitutible for a superclass. Substituting the `Comp2511AssignmentIILatePenalty` in place of  `StandardUNSWLatePenalty`, the post-condition `days late * 2` is less than `days late * 5`, this is a valid substitution and thus the inheritance is valid.
## Question 8 (5 marks)

Suppose that Assignment II contained an additional component, Task 3.

In this task, students had to adapt to another evolution in the requirements that introduced the concept of “power ups”.

At any tick in the game, there is a random chance of the player being given a potion in their inventory which they can consume at any time and will regenerate their health instantly. This probability is specified in the configuration file.

Tina and her group have the following design to test this functionality:

> We are going to write a test that loads the player into the dungeon, and then runs for 1000 ticks of the game. If the power up potion hasn’t been added into the player’s inventory after 1000 ticks, then the test will fail.

**What are the issues with this approach to test design? What techniques could Tina and her team use to ensure a more robust test?**

The test will not always succeed because of the random behaviour. Having a large number increases the probability of the player being given a potion, but it doesn't guarantee it.

Tina could use a seed-based randomiser to inject a seed which she knows should cause the potion to be given to the player, and inject it during the test.



## Summary Notes
- Overriding is when a subclass implements a superclass method differently
- Overloading is when a class implements the same method multiple times with different arguments
- Overloaded methods can have different access modifiers, Overridden methods can have different access modifiers (but must be less restrictive)
-  Overridden Methods must be 