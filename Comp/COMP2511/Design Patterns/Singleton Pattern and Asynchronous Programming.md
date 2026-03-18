## Overview
The singleton pattern is a creational design pattern. It is useful when an object should only have one instance, while providing a global access point to this instance. It is often use when programs need a single object to coordinate actions or a central resource. It is very useful for Asynchronous Design.

## Implementation Details
The singleton pattern is implemented by making the constructor private, and keeping the instance as a private, static attribute of the singleton class. Then, a public static getter will call the constructor **only** if the instance hasn't been instantiated yet, storing it in the static field, and will always return the instance. This way,  the getter will always return the same instance.

All other methods will be called from the instance, and therefore do not need to be static. The remaining class structure should be similar to a normal class. 

### Implementation Example
```java
public class SingletonPattern {
	private LocalDate startDate;
	private static SingletonPattern instance = null;
	
	private SingletonPattern() {
		this.startDate = LocalDate.now();
	}
	
	public synchronized SingletonPattern getInstance() {
		if (instance == null) {
			instance = new SingletonPattern();
		}
		return instance;
	}
	
	public LocalDate getStartDate() {
		return startDate;
	}
}

// To access from client
SingletonPattern inst = SingletonPattern.getInstance();
```

## Synchronous/Asynchronous Software Design
Synchronous programming is where operations are carried out in order, where the execution of an operation depends on the completion of the previous one. This is also called **single-threading**, because synchronous programming only uses one thread. In other words, code runs line-after-line, and if one operation is slow, all following tasks must wait.

Asynchronous Programming is where operations are carried out independently, and the execution of an operation **doesn't** depend on the completion of the previous. This is **not** the same as parallelism, where **multi-threading** (different threads run different parts of the code at the same time) is used to carry out multiply tasks simultaneously, it's rather using a single thread to manage tasks, through **context switching**.

Under the hood, the OS delegates execution time to your program as it sees fit. It chooses which programs should run, and when, at the millisecond scale.

The thread manages its tasks by having them yield control when they are busy doing something else (like waiting - for example, waiting for a HTTP response), and continuing once it is ready. So, the context-switching (switching which part of the code is running very quickly) makes is seem like programs are simultaneously executing code, while realistically, it is switching threads very quickly.

### Using the Singleton pattern for Async
The singleton pattern is useful for when different parts of an asynchronous program needs to access shared data. It's bad practise for multiple threads are accessing shared data, and changing them at the same time. This is called a **race condition**, and leads to inconsistent and hard-to-follow results.

We use the Singleton Pattern to share the data, and access this from the concurrently-run parts of the program. But now we run into a the race condition: multiple parts of the program are changing the data at the same time. So, we can add a lock to the target method within the singleton class by adding the key word `synchronized` in the method definition. For example, to make the method `incrementCounter()` thread-safe, we define it as follows:
```java
public synchronized void incrementCounter() {
	// Implementation
}
```

This forces all other concurrent threads to wait until the current 'user' has exited the method, and then tries again (note: the order which the threads call upon a synchronized method does not dictate the order which they will execute the method).

It is not good practise to make a method `synchronized` if it doesn't need it, because it creates a bottleneck for the program.

**The getter for the singleton must be synchronized.**
