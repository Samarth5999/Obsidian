If we don't know anything about implementation just we have requirement specification then we should go for <span style="color:rgb(253, 223, 126)">Interface</span>.
Example: Servlet

If we are talking about implementation but not completely(partial implementation) then we should go for <span style="color:rgb(253, 223, 126)">Abstract Class</span>.
Example: Generic Servlet, Http Servlet, etc.

If we are talking about implementation completely and ready to provide service then we should go for <span style="color:rgb(253, 223, 126)">Concrete Class</span>.
Example: My Own Servlet

---
---

# Difference b/w Interface and Abstract Class

|                                                            Interface                                                            |                                                  Abstract Class                                                   |
| :-----------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------: |
|                    When we don't know anything about implantation and just we have requirement specification                    |                When we are talking about implementation but not completely(partial implementation)                |
|      Inside interface, every method is always public and abstract, hence interface is considered 100% pure abstract class       | Every mesthod present inside abstract class need not be public and abstract and we can take concrete methods also |
| `private`, `protected`, `static`, `final`, `synchronized`, `strictfp` and `native` are illegal combination in interface methods |                           There are no restrictions on abstract class method modifiers                            |
|              Every variable present inside interface is always public static final weather we are declaring or not              |                   Every variable present inside abstract class need not be public static final                    |
|                `private`, `protected`, `transient` and `volatile` are illegal combination in interface variables                |                           There are no restriction on abstract class variable modifiers                           |
|                 For interface variables, compulsory we should perform initialization at the time of declaration                 |      For abstract class variables, we are not required to perform initialization at the time of declaration       |
|                                  Inside interface, we can't declare static and instance blocks                                  |                         Inside abstract class, we can declare static and instance blocks                          |
|                                         Inside interface we can't declare constructors                                          |                                 Inside abstract class we can declare constructor                                  |

>[!question] Any way we can't create object for abstract class but abstract class can contain contractor, What is the need? 
>Abstract class constructor will be executed whenever we are creating child class object to perform initialization of child class object.

Approach-1: Without having constructor in abstract class
```java
abstract class Person
{
	String name;
	int age;
	.
	.
	. 100 properties
}

class Student extends Person
{
	int rollno;
	Student(String name, int age,...101 properties)
	{
		this.name = name;
		this.age = age;
		.
		.
		.
		this.rollno = rollno;
	}
}
Student s = new Student(101 properties);
```
More code and Code Redundancy Problem

Approach-2: 
```java
abstract class Person
{
	String name;
	int age;
	.
	.
	. 100 properties

	// This constructor will work for every child object 
	// creation initialization 
	Person(String name, int age,...100 properties) 
	{
		this.name = name;
		this.age = age;
		.
		.
		. 100 lines of code
	}
}

class Student extends Person
{
	int rollno;
	Student(String name, int age,...101 properties)
	{
		super(100 properties)
		this.rollno = rollno;
	}
}
Student s = new Student(101 properties);
```
Less Code and Code Readability

>[!important] Note: Either directly or indirectly we can't create object for abstract class.

>[!question] We can't create objects for abstract class and interface but abstract class can contain constructor but interface doesn't contain constructor. Why?
>The main purpose of constructor is to perform initialization for the instance variables. Abstract class can contain instance variable which are required for child object, to perform initialization of those instance variable constructor is required for abstract class. 
>But every variable present inside interface is always public static final weather we are declaring or not and there is no chance of existing instance variable inside interface, hence constructor concept is not required for interface.

Whenever we are creating child class object, parent object wont be created just parent class constructor will be executed for the child object purpose only.

```java
class P
{
	P()
	{
		sout(this.hashCode()); // 100
	}
}
class C extends P
{
	C()
	{
		sout(this.hashCode()); // 100
	}
}
class Test
{
	public static void main(String[] args)
	{
		C c = new C();
		sout(this.hashCode()); // 100 (only one number)
	}
}
```

>[!question] Inside interface, every method is always abstract and we can take only abstract methods in abstract class also then why is the difference between interface and abstract class i.e. is it possible to replace interface with abstract class?
>We can replace interface with abstract class but it is not a good programming practice. This is something like recruiting IAS officer for sweeping activity. If everything is abstract then it is highly recommended to go for interface but not for abstract class. The main differences are as follows:-
>

|                                                         Abstract                                                          |                                                  Interface                                                   |
| :-----------------------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------: |
| While extending abstract class, it is not possible to extend any other class and hence we are missing Inheritance benefit | While implementing interface, we can extend some other class and hence we won't miss any inheritance benefit |
|                                          In this case object creation is costly                                           |                                  In this case object creation is not costly                                  |





