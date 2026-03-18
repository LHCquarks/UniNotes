## Method Overriding
Method overriding is when a subclass has its own implementation of a method inherited from a superclass. It is indicated with the `@Override` field above a method. The below

```java
class Foo {
	public boolean isSuperClass() {
		return true;
	}
}

class Bar extends Foo {
	@Override
	public boolean isSuperClass() {
		return false;
	}
}
```

There is some flexibility with method overriding. The method signature of the overridden method does not have to be the same as the superclass method's signature. The return type can be **more specific** than (i.e. a subclass of) the superclass method's return type, and the access modifier of the overridden method can be **less restrictive** than the superclass method's access modifier.


This will be explored again when covering **contravariance** and **covariance** in Software Design Principles.

## Method Overloading
Method Overloading is when a class has multiple methods of the same name, but with different signatures. For example:
```java
class Foo {
	public boolean Bar() {
		return true;
	}
	
	public boolean Bar(int offset) {
		return offset > 50;
	}	
}
```

Overloaded methods can have different return types and different access modifiers. So far, I have not come across a reason why they can't be thought of as simple different methods. Overridden methods **can** be overloaded.

For example:

```java
class Foo {
	public boolean Bar() {
		return true;
	}
	
	public int Bar(int offset) {
		return offset - 50;
	}
}
```