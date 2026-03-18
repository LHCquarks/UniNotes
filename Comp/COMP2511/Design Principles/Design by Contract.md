## Defensive Programming v.s. Design by Contract
**Defensive Programming**
Tries to address unforeseen circumstances to ensure continuing functionality of the software element. Allows the software to behave predictably despite unexpected inputs.
- Results in redundant checks, more complex software for maintenance
- More expensive in computation, because inputs are checked excessively.
**Design by Contract**
At the design time, responsibilities are clearly assigned to different software elements, clearly documented and enforced during development unit testing and/or language support (some languages natively support design by contract).
- Clear demarcation of responsibility helps prevent redundant checks
- Crashes if required conditions are not satisfied
Design by contract outlines preconditions which are required for program to have predictable behaviour. If these are not met, behaviour is undefined.
## Definition
Every software element should define a specification or contract which governs its interaction with the rest of the software components.

A contract should address the following:
- **Precondition**: what does the contract expect (argument constraints)?
- **Postcondition**: what does the contract guarantee?
- **Invariant**: what does the contract maintain (object attribute contraints)?
A contract should not include implementation details
### Advantages of DbC
- No need to error check
- Clearly assigned responsibilities helps in locating errors
- Helps for cleaner and faster development
### Disadvantages of DbC
- Java doesn't natively support DbC (Junit testing should be used in place to test pre/postconditions)
- In the absence of native language support, unit testing is used to test the contracts

## Design by Contract in Inheritance
### Preconditions
An implementation or redefinition of an inherited method **must** comply with the inherited contract for the method. This allows for the preconditions to be weakened (rules for the input are relaxed) but not strengthened by an inherited method. 
For example:
- Original contract requires numbers between 25 and 75.
- Inherited/redefined method requires numbers between 0 and 100
### Postconditions
An implementation or redefinition of an inherited method **must** comply with the inherited contract for the method. This allows for the postconditions to be strengthened (more restricted), but not weakened.
For example:
- Original contract returns a set
- Inherited/Redefined method returns a sorted set
### Class Invariants
Class invariants are inherited, meaning all invariants of the parents of a class applies to the class itself. A subclass can access implementation data of parents, but must always satisfy their invariants. They can also add their own invariants.