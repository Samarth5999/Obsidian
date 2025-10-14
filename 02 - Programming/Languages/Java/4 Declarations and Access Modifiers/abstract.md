abstract is a modifier applicable for classes and methods but not for variables.

# abstract method
Even though we don't know about implementation still we can declare a method with abstract modifier i.e. for abstract methods only declaration is available but not implementation, hence abstract method declaration should ends with `;`.
Example: `public abstract void m1();`
Child class is responsible to provide to implementation for parent class abstract methods.

```java
abstract class Vehicle{ // Why this is abstract class?
	public abstract int getNoofWheels();
}

class Bus extends Vehicles{
	public int getNoofofWheels(){
	return 7; // 6 wheels + 1 stepney
	}
}
```

> [!NOTE] Why we are declaring abstract method in parent class(we can declare and implement them directly in child class)?
> By declaring abstract in the parent class we can provide guidelines to the child classes such that which method compulsory child has to implement.


abstract method never talks about implementation, if any modifier talks about implementation then it forms illegal combination will abstract modifier. The following are illegal modifiers for methods with combination to abstract:
`final`, `native`, `synchronized`, `static`, `private`, `strictfp`
```java
abstract final void m1(); // CE: illegal combination of modifiers: abstract and final
```

---
# abstract class
For any Java class, if we are not allowed to create an object(because of partial implementation) such type of class we have to declare with abstract modifier i.e. for abstract classes instantiation is not possible.
```java
abstract class Test{
	public static void main(String[] args){
	Test t = new Test(); // CE: Test is abstract: cannot be instantiated
	}
}
```

# abstract class vs abstract method
1. If a class contains at least one abstract method then compulsory we should declare class as abstract otherwise we will get CE. It is because, If a class contains at least one abstract method then implementation is not complete and hence it is not recommended to create object, to restrict object instantiation(creation) compulsory we should declare class as abstract.
2. Even though class doesn't contain any abstract method still we can declare class as abstract, if we don't want instantiation i.e. abstract class can contain 0 number of abstract methods also.

Example-1: `HttpServlet` is abstract but it doesn't contain any abstract methods.
Example-2: Every Adapter Class is recommended to declare as abstract but it doesn't contain any abstract method.

```java
class P{
	public void m1(); // CE: missing method body or declare abstract
}
```

```java
class P{
	public abstract void m1(){} // CE: abstract methods cannot hava a body
}
```

```java 
class P{
	public abstract void m1(); // P is not abstract and does not override abstract method m1 in P
}
```

If we extending abstract class then for each and every abstract method of parent class we should provide implementation otherwise we have to declare child class as abstract in this case next level child class is responsible to provide implementation.
```java
abstract class P{
	public abstract void m1();
	public abstract void m2();
}
class C extends P{
	public void m1(){} // CE: C is not abstract and doesn't override abstract method m2 in P
}
```

# final vs abstract
1. abstract methods compulsory we should override in child classes to provide implementation whereas we can't override final methods, hence final abstract combination is illegal combination for methods.
2. For final classes we can't create child class whereas for abstract classes we should create child class to provide implementation, hence final abstract combination is illegal combination for classes.
3. abstract class can contain final method whereas final class can't contain abstract method.



It is highly recommended to use abstract modifier because it promotes several OOPS features like Inheritance and Polymorphism.