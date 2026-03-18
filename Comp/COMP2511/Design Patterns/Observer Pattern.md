## Overview
The observer pattern is useful for cases where the change in the state of one object may require changing the state of many other objects. It defines a subscription-like mechanism to notify multiple objects about any events that happen to the object they're observing.

This introduces a Paradigm Called **Event-Driven Programming**. This is used for systems like input handling (click detection), GUI, network requests, app notifications, and weather apps.

The observer pattern prescribes two main entities:
- The **subject** (or publisher), who maintains a list of dependents, and notifies them of any relevant state changes
- The **observer** (or subscriber), who are tracking a subject object and have a 

The aim is to define a one-to-many dependency between objects without tightly coupling them.
## Implementation Details
The observer pattern is implemented using **Subject** and **Observer** interfaces, such that when a subject changes state, all of the observers are automatically notified. The subject is responsible for keeping a list of observers, and to notify them upon a state change, while the responsibility of observers is to register and unregister themselves to a subject and to update their state when notified.

The list of observers for each subject can be changed at runtime. This pattern allows subjects and observers to be loosely coupled.

Note: although the relationship is described as **one-to-many**, it is possible (and doesn't break design principles) for an observer to be registered to multiple subjects, which makes the relationship **many-to-many**.

### Updating Observers
There are two methods of updating observers: **Pushing** or **Pulling**.
- **Pushing Data** involves only passing the changed data to its observers through `update()` arguments. This can result in there being lots of different versions of the `update()` method due to different method signatures.
- **Pulling Data** involves the subject sending a reference to itself to the observers as an argument of the `update()` function. In this case, the observers pull the data from the subject, and so it needs to provide relevant access methods.
### Implementation Example
```java
public interface Subject {
	public void addObserver(Observer observer);
	public void removeObserver(Observer observer);
	public void notifyObservers();
}

public interface Observer {
	public void update(Subject subject);
}

// Concrete Implementation
public class SubjectA extends Subject {
	ArrayList<Observer> observers;
	
	@Override
	public void addObserver(Observer observer) {
		observers.add(observer);
	}
	
	@Override
	public void removeObserver(Observer observer) {
		observers.remove(Observer);
	}
	
	public void notifyObservers() {
		for (Observer observer : observers) {
			observer.update(this);
		}
	}
}

public class ObserverA extends Observer {
	public void update(Subject subject) {
		System.out.println("Updated by subject!");
	}
}

```