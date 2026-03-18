## Overview
Lambda Expressions allow us to easily define anonymous methods, treat code as data and pass functionality as a method argument. They offer **functions** as objects - a feature of functional programming.

Lambda expressions can be used to implement an interface with only one abstract class, to create an instance of it. It can also replace an anonymous class with only one method. The data types are inferred from the function being implemented.
## Lambda Expression Syntax
A lambda expression is a function without a declaration, consisting of the following:
- A comma-separated list of parameters enclosed in parentheses. Data type is inferred, and if only one parameter, there is no need for parentheses
- The arrow (`->`) token
- A body, which consists of a single expression or statement block

A lambda expression can also reference an existing method rather than defining a new one. This can be done using the `::` operator:
- Static Method: `ClassName::MethodName`
- Instance Method: `InstanceName::MethodName`
-  Class Constructor: `Classname::new`

### Functional Interfaces in Java
Java contains some functional interfaces in the `java.util.function` package, which provide predefined types for lambda expression variables. Each interface has a single abstract method, called the functional method. The lambda expression's parameters and return values are for this method.

There are several different function 'shapes', including the following:
- **Function<T, R>**: Unary Function from T to R
- **Consumer\<T>**: Unary Function from T to void
- **Predicate\<T>**: Unary Function from T to boolean
- **Supplier\<R>**: Nilary function to R

**Example Usage**
```java
//
Function<String, Integer> func = x -> x.length();
Integer ans = func.apply("Sydney"); // ans = 6
//
Consumer<String> print = x -> System.out.println(x);
print.accept("Sydney"); // prints "Sydney" to terminal
//
Predicate<Integer> pass = x -> x >= 50;
Boolean status = pass.test(75); // status = True
```

### Comparators
Lambda expressions can be used to implement comparators for collection sorting, by implementing the compare method. Using an anonymous class, the implementation looks like:
```java
Comparator<Customer> myCmpAnonymous = new Comparator<Customer> () {
	@Override
	public int compare(Customer o1, Customer o2) {
		return o1.getRewardsPoints() - o2.getRewardsPoints;
	}
};
customerList.sort(myCmpAnonymous);
```

Using a lambda expression, this becomes one line:

```java
customerList.sort((Customer o1, Customer o2) -> o1.getRewardsPoints() - o2-getRewardsPoints);
```

When the code is used once or twice, lambda expressions become cleaner than comparators

## Pipelines and Streams
A pipeline is a series of **aggregate** (referring to collecting objects into groups) operations at the most simply level. A pipeline contains the following:
- A **source** (a collection of objects to operate on)
- **Intermediate Operations**, which will perform computations on the elements in the stream. For example, the `.filter()` operation will return a stream which match the predicate (lambda expression) argument.
- A **stream**, which is a sequence of elements to be conveyed through a series of operations. All implementations of the `java.util.Collection` interface has a `.stream()` method which converts the collection into a stream. 
- A **terminal operation**, such as `.forEach()`, produces a non-stream result, such as a primitive value, a collection, or, in some cases, nothing. Note that **reduction operations** are a type of terminal operation which combines the contents of the stream (e.g. `.average()` ) into a single value.

It is best to think of the `.` operator used in streams to specify operations as different to the `.` operator used to retrieve methods and attributes from an instance of a class.
### Example
```java
List<Person> maleWorkers = roster.stream().filter(e -> e.getGender() == Person.Sex.MALE).collect(Collectors.toList());
```

In the above example:
- `.stream()` creates a stream created using elements from the roster list
- `.filter(e -> e.getGender() == Person.Sex.MALE)` is an intermediate operation which excludes all elements in roster which are not male
- `.collect(Collectors.toList())` is a terminal operation which produces a List from the resultant stream

