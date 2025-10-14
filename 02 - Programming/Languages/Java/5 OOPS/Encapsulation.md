The process of binding data and corresponding method into a single unit is nothing but <span style="color:rgb(253, 223, 126)">Encapsulation</span>.

```java
class Student
{
	data members
		+
	methods(behaviour)
}
```

If any component follows data hiding and abstraction, such type of component is said to be Encapsulated component.
$$\text{Encapsulation = Data Hiding + Abstraction} $$

```java
public class Account
{
	private double balance;

	public double getBalance()
	{
		// validation
		return balance;
	}
	
	public double setbalance(double balance)
	{
		// validation
		this.balance = balance;
	}
}
```

##### Advantages of Encapsulation

1. We can achieve security.
2. Enhancement will become easy.
3. It improves maintainability of the application.

>[!important] Note 
>The main disadvantage of encapsulation is it increases the length of the code and slows down execution.


### Tightly Encapsulated Class

A class is said to be Tightly Encapsulated, if and only if each and every variable declared as `private`. Weather class contains corresponding getter or setter methods or not and weather these methods are declared as `public` or not these things we are required to check.
```java
public class Account
{
	private double balance;

	public double getBalance()
	{
		// validation
		return balance;
	}
}
```

>[!question] Which of the following classes are Tightly Encapsulated Class?

1.
```java
class A // Tightly Encapsulated Class
{
	private int x = 10;
}
class B extends A // Not Tightly Encapsulated Class
{
	int y = 20;
}
class C extends A // Tightly Encapsulated Class
{
	private int z = 30;
}
```

2.
```java
class A // Not Tightly Encapsulated Class
{
	int x = 10;
}
class B extends A // Not Tightly Encapsulated Class
{
	private int y = 20;
}
class C extends A // Not Tightly Encapsulated Class
{
	private int z = 30;
}
```
If the parent class is not Tightly Encapsulated then no child class is Tightly Encapsulated.