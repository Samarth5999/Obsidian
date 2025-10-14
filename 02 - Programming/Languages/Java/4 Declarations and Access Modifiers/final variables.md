# final instance variables

If the value of a variable is varied from object to object such type of variables are called instance variable. For every object, a separate copy of instance variables will be created.
For instance variable, we are not required to perform initialization explicitly JVM will always provide default values.

If the instance variable declared as final then compulsory we have to perform initialization explicitly weather we are using or not and JVM won't provide default values.
```java
class Test{
	final int x;  // CE: variable x might have not been intitialized
}
```

**Rule:** For final instance variables, compulsory we should perform initialization before *constructor completion* i.e. the following are various places for initialization:- 
1. At the time of declaration
2. Inside Instance block
3. Inside Constructor

These are the only possible places to perform initialization for final instance variables, if we are trying to perform initialization anywhere else then we will get `CE: cannot assign a value to final variable`.

---

# final static variables

If the value of a variable is not varied from object to object such type of variable are not recommended to declared as instances variables, we have to declare those variables at class level by using static modifier.
In the case of static variables a single copy will be created at class level and shared by every object of that class.
For static variable, we are not required to perform initialization explicitly JVM will always provide default values.

If the static variable declared as final then compulsory we have to perform initialization explicitly weather we are using or not and JVM won't provide default values.
```java
class Test{
	final static int x;  // CE: variable x might have not been intitialized
}
```

**Rule:** For final static variables, compulsory we should perform initialization before *class loading completion* i.e. the following are various places for initialization:-
1. At the time of declaration
2. Inside static block

These are the only possible places to perform initialization for final static variables, if we are trying to perform initialization anywhere else then we will get `CE: cannot assign a value to final variable`.

---

# final local variables

Sometimes to meet temporary requirements of the programmer, we can declare variables inside a method or block or constructor such type of variables are called <span style="color:rgb(255, 192, 0)">Local Variables</span> or <span style="color:rgb(255, 192, 0)">Temporary Variables</span> or <span style="color:rgb(255, 192, 0)">Stack Variables</span> or <span style="color:rgb(255, 192, 0)">Automatic Variables</span>.
For local variables, JVM won’t provide any default variables compulsory we should perform initialization explicitly before using that variable i.e. if we are not using then it is not required to perform initialization.

Even though local variable is final before using only we have to perform initialization i.e. if we are not using then it is not required to perform initialization even though it is final.
```java
class Test{
	public static void main(String[] args){
	final int x;
	sout("Hello"); // o/p: Hello
	}
}
```

The only applicable modifier for local variable is final, by mistake if we are trying to apply any other modifier then we will get 
`CE: illegal start of expression`.

If we are not declaring any modifier then by default it is `<default>` but this rule is applicable only for instance and static variables but not for local variables.

### Formal parameters 
Formal parameters of a method simply act as local variable of that method, hence formal parameter can be declared as final. If formal parameter declared as final then within the method we cannot perform reassignment.
```java
class Test{
	public static void main(String[] args){
		m1(10,20);
	}
	public static void m1(final int x, int y){
	x = 100; // CE: cannot assign a value to final variable
	y = 200;
	sout(x + y);
	}
}
```