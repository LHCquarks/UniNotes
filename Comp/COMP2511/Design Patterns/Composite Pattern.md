## Composite Pattern
The composite pattern in object-oriented programming is a structural pattern that lets you compose objects into tree structures, then work with these structures as if they were individual objects. A composite is an object designed as a composition of other similar objects. A group of objects can be treated as a single object, and vice versa. This pattern works like a tree structure. 

The composite pattern consists of:
- Leaf nodes - single part objects containing a value
- Composite Nodes - multi part objects composed of other Nodes (Composites or Leaves)

There are two options for composite patterns: **Uniform** or **Type Safe**. The composite design pattern behaves as a trade-off between transparency/uniformity and type-safety.
**Uniformity:**
- All composite and leaf objects are treated the same, and have the same methods and attributes - these composite methods must be implemented as "do nothing" for the leaf nodes
- Useful for dynamic structures, where leaf and composite children change often.
**Type Safety**
- Only define child-related operations in the composite class
- Type system forces type safety.
- Useful for static structures where the client doesn't need to perform "child" operations on "unknown" objects
- During Programming, the `Leaf` and the `Composite` class must be treated differently
- If a `Leaf` needs to changed into a `Composite`, the composite class should have a constructor which takes a `Leaf` as an argument
### Implementation Details
A possible implementation of the composite pattern would work with `Composite` and `Leaf` classes through a common `Node` interface. This node interface would include the relevant functions, which would be implemented recursively by `Composite` nodes and normally by `Leaf` nodes.

Each `Composite` node contains 1 or more 'child' `Node` attributes (depending on the specific application), and implements the `Node` functions recursively by referencing the return values of their children's implementation of that same function.

Each `Leaf` node contains a value, and their specific implementation of the `Node` functions, the simplest of which will simply return their value.
### Implementation Example
```java
public interface Node {
	public int evaluate();
	public String prettyPrint();
}

public class Sum implements Node {
	private Node child1;
	private Node child2;
	
	@Override
	public int evaluate() {
		return child1.evaluate() + child2.evaluate();
	}
	
	@Override
	public String prettyPrint() {
		return "(" + child1.prettyPrint() + " + " + child2.prettyPrint() + ")";
	}
}

public class Num implements Node {
	private int value;
	
	@Override
	public int evaluate() {
		return value;	
	}
	
	@Override
	public String prettyPrint() {
				return +value;
	}
}
```



