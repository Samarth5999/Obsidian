A Java program can contain any number of classes but at most one class can be declared as public, if there is a public class then name of the program and name of the public class must be matched otherwise we will get `CE: class x is public, should be declared in a file named x.java`.

Example: 
```java
class A{
	public static void main(String[] args){
		sout("A class main");
	}
}
class B{
	public static void main(String[] args){
		sout("B class main");
	}
}
class C{
	public static void main(String[] args){
		sout("C class main");
	}
}
class D
{
}
```
```mermaid
flowchart TD

  FC[Javac durga.java] --> SS[A.class]
  FC[Javac durga.java] --> IS[B.class]
  FC[Javac durga.java] --> TS[C.class]
  FC[Javac durga.java] --> HS[D.class]
  ```
```java
Java A => o/p: A class main
Java B => o/p: B class main
Java C => o/p: C class main
Java D => RE: NoSuchMethodError: main
Java durga => RE: NoClassDefFoundError: durga
```

##### Conclusion
1. Whenever we are compiling a Java program, for every class present in that program a separate `.class` will be generated.
2. We can compile a Java program(Java source file) but we can run a Java `.class` file.
3. Whenever we are executing a Java class, the corresponding class main method() will be executed. If the class doesn't contain main method() then we will get `RE: NoSuchMethodError: main`.
4. If the corresponding `.class` file not available then we will get `NoClassDefFoundError`.
5. It is not recommended to declare multiple classes in a single source file, it it highly recommended to declare only one class per source file and name of the program we have to keep same as class name. The main advantage of this approach is readability and maintainability of the code will be improved.


Java File Structure has two main components:
1. [[Import]]
2. [[Package]]