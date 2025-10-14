# Method Naming Conflicts
### Case-1
If two interfaces contains a method with same signature and same written type then in the implementation class we have to provide implementation for only one method.
```java
interface Left{
	public void m1();
}
interface Right{
	public void m1();
}

class Test implements Left, Right{
	public void m1(){
	}
}
```

### Case-2
If two interfaces contains a method with the same name but different argument types then in the implementation class, we have to provide implementation for both methods and these methods acts as <span style="color:rgb(146, 208, 80)">overloaded methods</span>.
```java
interface Left{
	public void m1();
}
interface Right{
	public void m1(int i);
}

class Test implements Left, Right{
	public void m1(){
	}
	public void m1(int i){
	}
}
```

### Case-3
If two interfaces contains a method with same signature but different written types then it is impossible to implement both interfaces simultaneously(if written types are not covariant).
```java
interface Left{
	public void m1();
}
interface Right{
	public int m1();
}
```
We can't write any Java class which implements both interfaces simultaneously.


> [!question] Is a Java class can implement any number of interfaces simultaneously?
> Yes, except a particular case i.e. if two interfaces contains a method with same signature but different written types then it is impossible to implement both interfaces simultaneously.

---
---
# Variable Naming Conflicts

Two interfaces can contain a variable with the same name and there maybe a chance of variable naming conflicts but we can solve this problem by using interface names.
```java
interface Left{
	x = 777;
}
interface Right{
	x = 888;
}

class Test implements Left, Right{
	public static void main(String[] args){
		sout(x); // CE: reference to x is ambiguous
		sout(Left.x); // o/p: 777
		sout(Right.x); // o/p: 888
	}
}
```