

> [!info] Definition-1
> Any service requirement specification(SRS) is considered as an Interface.

Example-1: JDBC API acts as requirement specification to develop database driver, database vender(like Oracle, MySQL, DBL) is responsible to implement this JDBC to develop their own driver classes.

Example-2: Servlet API acts as requirement specification to develop webserver, webserver vender(like Apache, Oracle, IBM) is responsible to implement this Servlet API to develop their own webserver.

> [!info] Definition-2
> From Client POV, an Interface defines a set of services what he's accepting and from Service Provider POV, an Interface defines the set of services what he's offering, hence any contract between Client and Service Provider is considered as an Interface.

Example-1: Through Bank ATM GUI screen, Bank People are highlighting the set of services they are offering, at the same time the same GUI screen represents the set of services what Customer is expecting, hence this GUI screen act as contract between Customer and Bank People.


> [!info] Definition-3
> Inside Interface, every method is always abstract weather we are declaring or not, hence Interface is considered as 100% pure abstract class.


> [!important] Final Definition
> Any Service Requirement Specification or any contract between Client and Service Provider or 100% pure Abstract Class is nothing but Interface.

---
# Declaration & Implementation

Whenever we are implementing an Interface for each and every method of that Interface we have to provide implementation otherwise we have to declare class as abstract then next level child class is responsible to provide implementation.

Every Interface method is always public and abstract whether we are declaring or not, hence whenever we are implementing an Interface method compulsory we should declare as public otherwise we will get compile time error.

```java
interface Interf{
	void m1();
	void m2();
}
abstract class ServiceProvider implements Interf{
	public void m1(){}
}
class SubServiceProvider extends ServiceProvider{
	public void m2(){}
}
```