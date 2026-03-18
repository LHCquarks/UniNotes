## Overview
The strategy pattern is a Behavioural Design pattern that lets you define a family of methods which are interchangeable at runtime. It does so in a way that doesn't break the open-close principle. It's useful when we need to achieve the same task in multiple ways.

- Define a family of algorithms
- Encapsulate each algorithm in a separate strategy class
- Make algorithms interchangeable in the context object (parent object)
- Vary behaviour without changing the context class
### Implementation Example
```java
public class Context {
	private MethodStrategy method;
	
	public Context(MethodStrategy method) {
		this.method = method;
	}
	
	public void methodAlgorithm() {
		method.algorithm();
	}
}


using the car:
public static void main(String[] args) {
	EngineStrategy engine = new ElectricEngine();
	BrakeStrategy brake = new RegenerativeBrake();
	Car car = new Car(engine, brake);
	car.startEngine();
	car.applyBrake();

}
```

### Benefits of Strategy Pattern
- Promotes composition over inheritance (behaviours can be combined and reused without deep inheritance hierarchies).
- Supports runtime behaviour exchange
- Encourages separation of concerns (car delegates specific behaviours to strategy classes)
- Enables Open-Closed Principle (New strategies can be added without changing existing code)
- Encourages modular design