An interface can contain variables, the main purpose of interface variable is to define requirement level constants.

Every interface variable is always `public static final` whether we are declaring or not.
```java
interface Intref
{
	int x = 10;
}
```
`public`: To make this variable available to every implementation class
`static`: Without existing object also, implementation class has to access this variable
`final`: If one implementation class changes values then remaining implementation classes will be affected. To restrict this, every interface variable is always final.

Hence, inside interface the following variable declarations are equal:-
```java
int x = 10;
public int x = 10;
static int x = 10;
final int x = 10;
public static int x = 10;
public final int x = 10;
static final int x = 10;
public static final int x = 10;
```

As every interface variable is always `public`, `static` and `final`, we can't declare interface variable with the following modifiers:-
`private` ,`protected` ,`transient` and `volatile`

For interface variables, compulsory we should perform initialization at the time of declaration otherwise we will get `CE: = expected`.
```java
interface Interf{
	int x; // CE: = expected
}
```

Inside implementation class, we can access interface variables but we can't modify values.
```java
interface Interf{
	int x = 10;
}

class Test1 implements Interf{
	public static void main(String[] args){
		x = 777; // CE: cannot assign value to final variable x
		sout(x);
	}
}

class Test2 implements Interf{
	public static void main(String[] args){
		int x = 777;
		sout(x); // o/p: 777 because x is a local variable here 
	}
}
```