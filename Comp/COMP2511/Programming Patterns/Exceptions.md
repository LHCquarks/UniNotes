An exception is an event which occurs during the execution of a program, that disrupts the normal flow of the program's instructions. When an error occurs, an `Exception` object is created and given to the runtime system. This is called **throwing** an exception. The call stack then searches the call stack for a method which contains a block of code that can handle the exception. If a handler is found, the exception handler is said to **catch** the exception. *Note:* Some exception handlers may choose to stop the execution of the program

Exceptions can be a way to check preconditions in Design by Contract

## Exceptions in Java
There are three kinds of exceptions in java:
- Checked exceptions(`IOException`, `SQLException`, etc.)
- Error (`VirtualMachineError`, `OutOfMemoryError`, etc.)
- Runtime Exception (`ArrayIndexOutOfBoundsException`,`ArithmeticException`, etc)

### Checked v.s. Unchecked Exceptions
An exception's type determines whether it is checked or unchecked: 
- All exceptions which inherit from Error or Runtime Exception are **unchecked** exceptions
- All exceptions which are subclasses of Exception but not subclasses of Runtime Exception are **checked** exceptions

In java, in order to compile and run a program, all checked exceptions **must** be handled in your code. Unchecked exceptions do not need to be checked, but can be checked. They will often crash the program if left unchecked.

### Catching an Exception
There are three stages to catch an exception. First, surround the code which may throw an exception with a `try` block. Then, immediately after, use a `catch` block to define what the program does if the exception is caught. Lastly, the `finally` block executes the code regardless of whether an exception was caught or not. It should be used to clean up the program so that it gracefully crashes.


## Example Code
```java
public void writeList() {
	PrintWriter out = null;
	try {
		out = new PrintWriter(new FileWriter("myData.txt"));
	
		for (int i = 0; i < SIZE; i++) {
			out.println("Value is" + list.get(i));
		}
	} catch (IOException e) {
		System.out.println("IOException in writeList");
	} catch (IndexOutOfBoundsException e) {
		System.out.println("IndexOutOfBoundsException in writeList");
	} finally {
		out.close;
	}	
}

public static void main(String args[]) {
	ln.writeList();
}
```

## Creating your own Exception
You can create classes representing exceptions by extending the exception class. These need to be manually thrown. These exceptions are handled in the same way as other exceptions.
```java
class MyException extends Exception { // Checked exception
	public MyException(String message) {
		super(message);
	}
}
```


## Exceptions in Inheritance
If a superclass method is overridden by a subclass, the subclass method's throws clause must contain a subset of the superclass method's throw clause. it must not throw **more** exceptions.

## Assertions
An assertion allows you to test your assumptions about a program. They are useful for checking Preconditions, Postconditions, and Class Invariants. They should not be used for checking arguments in public methods, or for any other work your program requires. If the assertion fails, the program crashes.
**Note**: Assertions must be enables in the command line using `-ea`