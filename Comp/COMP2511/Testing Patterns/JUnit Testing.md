## Software Testing
Different Types of Testing for different requirements/levels:
- O-O Design Document describes class/method responsibilities $\rightarrow$ **Unit Testing**
- System Design Document: $\rightarrow$ **Integration Testing**
- Requirements Analysis Document $\rightarrow$ **System Testing**
- Client Expectation $\rightarrow$ Acceptance Testing
Unit testing is also useful for refactoring. This course focuses on unit testing.
## JUnit
JUnit is a popular open source unit testing framework for java. Most IDE's facilitate JUnit test integrations.

Basic JUnit Terminology:
- **Test Case**: A java class, containing test code
- **Test Method**: A method in a Test Case which executes the test code, annotated with `@Test`
- **Asserts**: Assert statements used to check expected results against the actual result
- **Test Suites**: Collection of several test cases

Below is an example of a JUnit Test Case
```java
public class exampleTestCase {
	@Test
	public void exampleTestMethod() {
		Course course = new Course("COMP2511");
		assertEquals("COMP15211", course.getName());
	}
	
	@Test
	public void exampleTestMethod2() {
		CourseOffering courseOffering = new CourseOffering("COMP2511", "25t3");
		assertEquals("COMP2511", courseOffering.getName());
		assertEquals("25t3", courseOffering.getTerm());
		assertDoesNotThrow(() -> {
			courseOffering.addStudent("John Adams", "z1234567");
			courseOffering.addStudent("John Addams", "z5671234");		
		})
	}
}
```

### `@` Tags
- The `@Test` tag should be written before each test method you want to be automatically run
- The `@BeforeEach` tag above a method will make the test suite run the method before every test.
- The `@DisplayName("name");` tag will define the name of the test displayed to the user
- The `@RepeatedTest(num)` tag (replaces `@Test`) will define the test and run it `num` times
- The `@ParameterisedTest` tag (replaces `@Test`) will define the test with parameters. This is explored later
### Assertions
- `assertEquals(val1, val2, optionalFailureMessage)`
- `assertTrue(expression1, optionalFailureMessage)`
- `assertFalse(expression1, optionalFailureMessage)`
- `assertNotNull(object, optionalFailureMessage)`
- `assertNull(object, optionalFailureMessage)`
- `assertThrows(optionalExceptionName, () -> { //Code which throws exception })
- `assertDoesNotThrow(optionalExceptionName, () -> { // Code which throws exception})`
- `assertAll("testName", () -> {\\code 1}, () -> {//code 2})`
- `assertTimeout(ofMinutes(num)), () -> obj.doSomething())`
- 
### Parameterised Tests
Parameterised Tests are tests which take in arguments. They are specifies with `@ParameterisedTest` and the arguments are specified in the next line, with a few options:
- `@ValueSource(array = {"arg1", "arg2"})`, allows you to pass in an array of values to test. The limitations of this is that there are limited types allowed to be used, and only one argument can be passed into each test
- `@NullSource` provides a single null value
- `@EmptySource` provides a single empty argument (i.e. empty string or collection)
- `@EnumSource(Class.enum)` provides all values from an enumeration. To pass in specific values, use `@EnumSource(Class.enum, names = {"ENUMVALUE1", "ENUMVALUE2"})`
- `@MethodSource(value = "methodName")` allows complex objects to be used. It allows a method to be used as an argument source.  The return collection of the method `methodName` is then passed into the function, with each entry being used for each test.
There's more, but it wasn't covered in lectures.

### Dynamic Tests
Dynamic Tests were not covered in lectures, but they use Lambda Functions.