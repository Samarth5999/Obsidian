static is a modifier applicable for methods and variables but not for classes, we can't declare top level class with static modifier but we can declare inner class as static(such type of inner classes are called <span style="color:rgb(255, 192, 0)">static nested classes</span>)

We can't access instance members directly from static area but we can access from instance area directly.
We can access static members from both instance and static area directly.

###### Consider the following declaration:-
```java
I. int x = 10; 
II. static int x = 10;
III. public void m1(){ sout(x); }
IV. public static void m1(){ sout(x); }
```
Within the same class, which of the above declaration we can take simultaneously?

1. I and III: Valid
2. I and IV: `CE: non static variable x cannot be referenced from a static context`
3. II and III: Valid
4. II and IV: Valid
5. I and II: `CE: varibale x is already defined in Test`
6. III and IV: `CE: m1() is already defined in Test`

Case-1: Overloading concept applicable for static methods including main() method but JVM can always call `String[] args` main() method only.
```java
public static void main(String[] args){
	sout("String[]");
}
public static void main(int[] args){
	sout("int[]");
}
```

Case-2: Inheritance concept applicable for static methods including main() method, hence while executing child class if child doesn't contain main method then parent class main() method will be executed.
```java
class P{
	public static void main(String[] args){
		sout("Parent Main"); // Java P = o/p: Parent Main
	}
}
class C{
	public static void main(String[] args){
	} // Java C = o/p: Parent Main
}
```

Case-3: It seems overriding concept applicable for static methods but it is not overriding and it is method hiding.
```java
class P{
	public static void main(String[] args){
		sout("Parent Main"); // Java P = o/p: Parent Main
	}
}
class C{
	public static void main(String[] args){
	sout("Child Main"); // Java C = o/p: Child Main
	}
}
```

Note: For static methods, overloading and Inheritance concepts are available but overriding concepts are not applicable but instead of overriding method hiding concept is applicable.

Inside method implementation if we are using at least one instance variable then that method talks about a particular object, hence we should declare method as instance method.
Inside method implementation if we are not using any instance variable then this method nowhere related to a particular object, hence we have to declare such type of method as static method irrespective of weather we are using static variables or not. 

For static method, implementation should be available whereas for abstract methods implementation is not available, hence abstract static combination is illegal for methods