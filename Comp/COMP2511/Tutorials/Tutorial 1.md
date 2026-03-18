## Outline and Tips
- Week 2 Onwards is Manually Marked
- Submission is pushing onto main branch on gitlab
- Lab09 is an attendance/participation lab
- Lab `n` can be marked in week `n + 2` at the latest 
- Assignments can be very content heavy, start early
- The content from the tut-labs make up 50% of the final exam
- It is helpful to learn to read documentation (You are learning java on your own for the most part)
- Gradle Testing/Linting doesn't work properly unless you have opened the correct directory (usually the repository root)
- Extension pack for java is required
- Programs are run using the run button above the main function


## Object-Oriented Programming
- OOP is a programming pradigm
- C is a procedural language
- OOP organises code into objects, which combine data and behaviour
- So far, you would have only encountered procedural programming (C) where code is organised into procedures/functions.
- Javascript/Typescript are also Object-Oriented
- Java is in the middle in terms of high/low level programming language
- All code in java exists inside a class
```java
public class HelloWorld {
	// Main Function
	public static void main(String[] args) {
		System.out.println("hello world");
	}
}
```
- One class per file is enforced in COMP2511 because it's cleaner and organised


A class is a blueprint/module that contains data fields and methods, which are used to create objects. An instance is the copy of the class which is stored in memory (a variable)
- A static function means it is not required to make an instance of a class, but we can call the function directly from the class 
- Generally, it's good practice to make a class' attributes private. Getters and setters should be how other classes interact with these variables (with permission from the class)
## Abstraction
- Public and private methods/data fields are how java deals with abstraction and hides the complexity of classes.
- This controls the visibility of certain functions