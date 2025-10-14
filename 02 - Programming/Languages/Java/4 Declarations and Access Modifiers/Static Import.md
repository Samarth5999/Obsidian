Introduced in 1.5v, According to SUN, usage of static import reduces length of the code and improves readability but according world wide programming experts like me usage of static import creates confusion and reduces readability. Hence if there is no specific requirement then it is not recommended to use static import.

Usually we can access static members by class name but we are writing static import we can access static members directly without class name.
```java
import static java.lang.Math.sqrt;
import static java.lang.Math.*;

class Test{
	public static void main(String[] args){
		sout(sqrt(4));
		sout(max(10,20));
		sout(random());
	}
}
```
##### Explain about `System.out.println()`?
```java
class Test{
	static string s = "java";
	.
	.
}
	Test.s.length()
```
Here, `Test` is class name,`s` is a static variable present in `test` class of `string` type,`length()` is a method present in string class.
Similarly,
```java
class System{
	static PrintStream out;
	.
	.
}
	System.out.println()
```
`System` is class name
`out` is a static variable present in `System` class of `PrintStream` type
`println()` is a method present in `PrintStream` class.

`out` is a static variable present in `System` class, hence we can access by using class `System` but whenever we are writing static import its not required to use class name and we can access `out` directly.
```java
import static java.lang.System.out;
class Test{
	out.println("Hello"); // o/p: Hello
}
```



```java
import static java.lang.Integer.*;
import static java.lang.Byte.*;
class Test{
	public static void main(String[] args){
		sout(MAX_VALUE); // CE: reference to MAX_VALUE is ambiguous
	}
}
```

While resolving static members, compiler will always consider precedence in the following order:
1. Current class static members
2. Explicit static import
3. Implicit static import
```java
import static java.lang.Integer.MAX_VALUE;
import static java.lang.Byte.*;
class Test{
	public static void main(String[] args){
		static int MAX_VALUE = 999;
		sout(MAX_VALUE); // o/p: 999, if we comment line 5 then o/p: 2147483647
	}
}
```

##### 1. Explicit Static Import 
**Syntax: `import static packagename.classname.staticmember`**

Example: `import static java.lang.Math.sqrt`. It is highly recommended to use because it improves readability of the code.
Best suitable where readability is important.

##### 2. Implicit Class Import 
**Syntax: `import static packagename.classname.*`**

Example: `import java.util.*`. Not recommended to use because it reduces readability of the code.
Best suitable where typing is important.

##### Why we don't use static import?

1. Two packages contains a class and interface with the same name is very rare and hence ambiguity problem is very rare in normal import.
   But two classes or interfaces contain a variable and method with the same name is very common and hence ambiguity problem is also very common problem in static import.
2. Usage of static import reduces readability and creates confusion and hence if there is no specific requirement then is not recommended to use static import.

## Difference b/w Normal import and static import


|                                                      Normal import                                                       |                                                         static import                                                          |
| :----------------------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------------------: |
|                    We can use normal import to import classes and interfaces of a particular package                     |                      We can use static import to import static members of a particular class or interface                      |
| Whenever we are writing normal import, it is not required to use full qualified name and we can use short names directly | Whenever we are writing static import, it is not required to use class name to access static member and we can access directly |


