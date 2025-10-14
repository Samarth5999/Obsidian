Adapter Class is a simple Java class that implements an interface with only empty implementation.
```java
interface X
{
	m1();
	m2();
	m3();
	.
	.
	.
	m1000();
}
```

If we want to implement only m3 in a Test class:-
```java
class Test implements X
{
	m3()
	{
		.
		.
		.
	}
	m1(){}
	m2(){}
	m4(){}
	.
	.
	.
	m1000(){}	
}
```
The problem in this approach is, it increases length of the code and reduces readability.

We can solve this problem by using adapter classes.
```java
abstract class AdapterX implements X
{
	m1(){}
	m2(){}
	m3(){}
	.
	.
	.
	m1000(){}
}
```
If we implement an interface for each and every method of that interface, compulsory we should provide implementation weather it is required or not required.

Instead of implementing interface, if we extend adapter class we have to provide implementation only for required methods and we are not responsible to provide implementation for each and every method of the interface so that length of the code will be reduced.
```java
class Test extends AdapterX
{
	m3()
	{
		
	}
}
```

```java
class Demo extends AdapterX
{
	m7()
	{
		
	}
}
```

```java
class Sample extends AdapterX
{
	m1000()
	{
		
	}
}
```

##### Example

We can develop a Servlet in the following three ways:-
1. By implementing Servlet Interface
2. By extending Generic Servlet
3. By extending HTTP Servlet

If we implement Servlet interface, for each and every method of that interface we should provide implementation. It increases length of the code and reduces readability.
Instead of implementing Servlet interface directly, if we extend Generic Servlet we have to provide implementation only for Service Method and for all remaining methods we are not required to provide implementation. Hence, more or less Generic Servlet act as Adapter Class for Servlet interface.

>[!important] Note
>Marker interface and adapter classes simplifies complexity of programming and these best utilities to the programmer and programmer life will become simple.