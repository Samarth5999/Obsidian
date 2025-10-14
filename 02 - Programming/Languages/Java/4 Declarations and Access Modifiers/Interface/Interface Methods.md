Every method present inside interface is always `public` and `abstract` whether we are declaring or not.
```java
interface Interf 
{
	void m1();
}
```
`public`: To make this method available to every implementation class.
`abstract`: Implementation class is responsible to provide implementation.

Hence, inside interface the following method declarations are equal:-
```java
void m1();
public void m1();
abstract void m1();
public abstract void m1();
```

As every interface method is always `public` and `abstract`, we can't declare interface method with the following modifiers:-
`private`, `protected`, `static`, `final`, `synchronized`, `strictfp` and `native`

> [!question] 
> Which of the following method declarations are allowed inside interface?
```java
public void m1(){} // Invalid
private void m1(); // Invalid
protected void m1(); // Invalid 
static void m1(); // Invalid
public abstract native void m1(); // Invalid
abstract public void m1(); // Valid
```