final is a modifier applicable for classes, methods and variables.

# final method
Whatever methods parent has by default available to child through inheritance, if the child not satisfied with parent method implementation then child is allowed to redefine that method based on its requirement. This is process is called Overriding.

If the parent class method is declared as final then we can't overwrite that method in the child class because its implementation is final.
```java
class P{
	public void property(){
	sout("cash, gold, cars");
	}
	
	public final void marry(){
	sout("subhalaxmi");
	}
}
class C extends P{
	public final void marry(){
	sout("Trisha"); // CE: marry() in C cannot override marry() in P; overridden method is final
	}
}
```

---
# final class
If a class declared as final, we can't extend functionality of that class i.e. we can't create child class for that class i.e. **inheritance is not possible for final classes** else we will get `CE: cannot inherit from final P`
```java
class P
{
}
class C extends P
{
}
```

> [!NOTE] Note
> Every method present inside final class is always final by default but every variable present inside final class need not be final.

 The main advantage of final keyword is we can achieve security and we can provide unique implementation but the main disadvantage of final keyword is we are missing key benefits of OOPS : Inheritance(because of final classes) and Polymorphism(because of final methods), hence if there is no specific requirement then is it not recommended to use final keyword.

---
# [[final variables]]