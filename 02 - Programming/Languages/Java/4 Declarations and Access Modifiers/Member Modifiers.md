We can also say method or variable level modifiers.

---
# public member
If a member declared as public then we can access that member <span style="color:rgb(148, 194, 255)">from anywhere</span> but corresponding class should be visible before checking member visibility we have to check class visibility.

---
# default member
If a member declared as default then we can access that member <span style="color:rgb(148, 194, 255)">only within the current package</span> i.e. from outside of the package we can't access, hence default access is also known as <span style="color:rgb(255, 192, 0)">package level access</span>.

---
# private members
If a member declared as private then we can access that member <span style="color:rgb(148, 194, 255)">only within the current class</span> i.e. from outside of the class we can't access.

abstract methods should be available to the child classes to provide implementation whereas private method are not available to the child classes, hence private abstract combination is illegal for methods.

---
# protected modifier (most misunderstood modifier in Java)
If a member declared as protected then we can access that member <span style="color:rgb(148, 194, 255)">anywhere within the current package but only in child classes of outside package</span>. `protected = <default> + kids`

We can access protected member within the current package anywhere either by using parent reference or child reference but we can access protected member in outside package only in child classes and we should use child reference only i.e. parent reference cannot be used to access protected members form outside package.
```java 
package pack1;
public class A{
	protected void m1(){
		sout("The most misunderstood topic");
	}
}
class B extends A{
	public static void main(String[] args){
	
		A a = new A();
		a.m1(); // Valid
		
		B b = new B();
		b.m1(); // Valid
		
		A a1 = new B();
		a1.m1(); // Valid
	}
}
```

```java 
package pack2;
import pack1.A;
class C extends A{
	public static void main(String[] args){
	
		A a = new A();
		a.m1(); // CE: m1() has protected access in pack1.A
		
		C c = new C();
		c.m1(); // Valid
		
		A a1 = new C();
		a1.m1(); // CE: m1() has protected access in pack1.A
	}
}
```

We can access protected members from outside package only in child classes and we should use that child class reference only.
For example from D class if we want to access we should use D class reference only.
```java 
package pack2;
import pack1.A;
class C extends A{
}
class D extends C{
	public static void main(String[] args){
	
		A a = new A();
		a.m1(); // CE: m1() has protected access in pack1.A
		
		C c = new C();
		c.m1(); // CE: m1() has protected access in pack1.A
		
		D d = new D();
		d.m1(); // Valid
		
		A a1 = new C();
		a1.m1(); // CE: m1() has protected access in pack1.A
		
		A a1 = new D();
		a1.m1(); // CE: m1() has protected access in pack1.A
		
		C c1 = new D();
		c1.m1(); // CE: m1() has protected access in pack1.A
	}
}
```

---
# Summary
The most restricted access modifier is private and the most accessible modifier is public.
Recommended modifier for data member(variable) is private whereas recommended modifier for methods is public.

|               Visibility                |                    private                     |                    default                     |                   protected                    |                     public                     |
| :-------------------------------------: | :--------------------------------------------: | :--------------------------------------------: | :--------------------------------------------: | :--------------------------------------------: |
|          Within the same class          | <span style="color:rgb(0, 176, 80)">YES</span> | <span style="color:rgb(0, 176, 80)">YES</span> | <span style="color:rgb(0, 176, 80)">YES</span> | <span style="color:rgb(0, 176, 80)">YES</span> |
|    From child class of same package     |  <span style="color:rgb(255, 0, 0)">NO</span>  | <span style="color:rgb(0, 176, 80)">YES</span> | <span style="color:rgb(0, 176, 80)">YES</span> | <span style="color:rgb(0, 176, 80)">YES</span> |
|  From Non-child class of same package   |  <span style="color:rgb(255, 0, 0)">NO</span>  | <span style="color:rgb(0, 176, 80)">YES</span> | <span style="color:rgb(0, 176, 80)">YES</span> | <span style="color:rgb(0, 176, 80)">YES</span> |
|   From child class of outside package   |  <span style="color:rgb(255, 0, 0)">NO</span>  |  <span style="color:rgb(255, 0, 0)">NO</span>  | <span style="color:rgb(0, 176, 80)">YES</span> | <span style="color:rgb(0, 176, 80)">YES</span> |
| From Non-child class of outside package |  <span style="color:rgb(255, 0, 0)">NO</span>  |  <span style="color:rgb(255, 0, 0)">NO</span>  |  <span style="color:rgb(255, 0, 0)">NO</span>  | <span style="color:rgb(0, 176, 80)">YES</span> |

