---
~
---

---
# new vs newInstance()
1.  new operator is used to create an object if we know class at the beginning. Ex: `Test t = new Test();`

	newInstance() is a method present in class Class, we can use newInstance() method to create object if we don't know class name at the beginning and it is available dynamically at runtime. Ex:
```java
class Test{
public static void main(String[] args){
		Object o = Class.forName(args[0]).newInstance();
		sout("Object created for: " + o.getClass().getName()); // java test Customer <= o/p: Object created for: Customer
	}
}
```

2. In the case of new operator based on our requirement, we can invoke any constructor. Ex: `Test t = new Test();`

	But newInstance() method internally calls no-argument constructor, hence to use newInstance() method compulsory corresponding class should no-argument constructor otherwise we will get RE: Instantiation Exception. *Because of this every Servlet should contain no-argument constructor*

3. While using new operator, at runtime if the corresponding .class file is not available then we will get *RE: NoClassDefFoundError*.

	While using newInstance() method, at runtime if the corresponding .class file is not available then we will get *RE: ClassNotFoundException*.
```java
Test t = new Test(); // RE: NoClassDefFoundError: Test

Object o = Class forName(args[0]).newInstance(); // Java Test Test123 <= o/p: RE: ClassNotFoundException: Test123
```

|                                         new                                         |                                                         newInstance()                                                          |
| :---------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------------------: |
|                              It is a operator in Java                               |                                           It is a method present in java.land.Class                                            |
|     We can use this to create an object if we know class name at the beginning      |   We can use this to create object if we don't know class name at the beginning and it is available dynamically at runtime     |
|      To use new operator class not required to contain no-argument constructor      | To use newInstance() compulsory class should contain no-argument constructor otherwise we will get RE: Instantiation Exception |
| At runtime if class file is not available then we will get RE: NoClassDefFoundError |                     At runtime if class file is not available then we will get RE: ClassNotFoundException*                     |

---
# ClassNotFoundException vs NoClassDefFoundError

|                                                                     ClassNotFoundException                                                                     |                                                                           NoClassDefFoundError                                                                           |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| For hard coded class names, at runtime if the corresponding .class is not available then we will get *RE: NoClassDefFoundError*, which is unchecked exception. | For dynamically provided class names, at runtime if the corresponding .class is not available then we will get *RE: ClassNotFoundException*, which is checked exception. |
|                                                    `Test t = new Test(); // RE: NoClassDefFoundError: Test`                                                    |                           `Object o = Class forName(args[0]).newInstance(); // Java Test Test123 <= o/p: RE: ClassNotFoundException: Test123`                            |

---
# [[Instanceof Operator| instanceof]] vs isInstance()

instanceof is a operator in java, we can use instance of to check whether the given object is of particular type or not

|                                                           instanceof                                                            |                                                                                                         isInstance()                                                                                                          |
| :-----------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|                                                    It is a operator in java                                                     |                                                                                           It is a method present in java.lang.Class                                                                                           |
|   We can use instance of to check whether the given object is of particular type or not and we know the type at the beginning   |                         We can use instance of to check whether the given object is of particular type or not and we don' t know the type at the beginning and it is available dynamically at runtime                         |
| <pre><code>Thread t = new Thread();<br>sout(t instanceof Runnable); // true<br>sout(t instanceof String); // false</code></pre> | <pre><code>class Test{<br>	public static void main(String[] args) throws Exception{<br>		Thread t = new Thread();<br>		sout(Class.forNAme(args[0].isInstance(t))); // Java Test Runnable <= o/p: true<br>	}<br>}</code></pre> |

---
