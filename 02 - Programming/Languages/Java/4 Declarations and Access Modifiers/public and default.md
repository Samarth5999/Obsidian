# public classes
```java
package pack1;
public class A{
	public void m1(){
	sout("Hello");
	}
}
```

```java
package pack2;
class B{
	public static void main(String[] args){
	A a = new A();
	a.m1();                 // o/p: Hello 
	}
}
```
If class A is not public then while compiling B class we will get `CE: pack1.A is not public in pack1; cannot be accessed from outside package`.

---
# default classes

If a class declared as default then we can access that class only within the current package i.e. from outside package we can't access. Hence default access is also known as package level access.