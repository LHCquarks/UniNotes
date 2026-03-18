**Code Recap:**
- Can you override a static method? No.

**Design by Contract**
Design by contract is a software development approach which provides an interface for others to use with clear *preconditions*, *postconditions* and *invariants* which, where adhered to, guarantees correct and expected behaviour.

**Defensive Programming**
- Code actively checks/guards against invalid inputs

## LSP: Liskov Substitution Principle
LSP is a design principle used to check if you have a valid inheritance or not. LSP states **subclasses** must be substitutable for their **superclasses**. To be suitable, the subclass must behave like the superclass.

Subclasses must NOT:
- Have more restrictive preconditions (Strengthen preconditions)
- Violate promised postconditions (Weaken postconditions)


Code Smell:
- Refused Bequest - If a subclass uses only some of the methods/attributes

## Domain Modelling using UML
- Domain Modelling is a way to represent java classes visually.
-



| Account                         |
| ------------------------------- |
| -name: String<br>-balance:float |
| +getBalance(): float            |
- `-` represents private, `#` represents protected, and `+` represents public
- Caps represent static/constant values
- Italics represent abstract classes/methods
- Arrows point to the super*

## JUnit Testing
```java
public class ClassNameTest {
	@Test
	public void testName {
		Integer expected = 1;
		assertEquals(expected, 1);
	}
}
```

**Exceptions**
There are two types of exceptions: 
- Checked (Try/Catchable)
- Unchecked
Use `assertThrows`