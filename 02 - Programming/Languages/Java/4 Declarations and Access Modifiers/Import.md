# Normal import
```java
class Test{
	public static void main(String[] args){
		ArrayList L = new ArrayList();  // CE: cannot find symbol, symbol: class Arraylist, Location: class Test
	}
}
```
We can solve this problem by using full qualified name `java.util.ArrayList L = new java.util.ArrayList();`.The problem with usage of fully qualified name every time is it increases length of the code reduces readability.
We can solve this problem by using `import` statement. Whenever we are writing `import` statement, it is not required to use fully qualified name every time.
```java
import `java.util.ArrayList
class Test{
	public static void main(String[] args){
		ArrayList L = new ArrayList();
	}
}
```
Hence `import` statement act as typing shortcut.

---
## Case-1: Types of import Statements
##### 1. Explicit Class Import 
**Syntax: `import packagename.classname`**
Example: `import java.util.ArrayList`. It is highly recommended to use because it improves readability of the code.
Best suitable where readability is important.
##### 2. Implicit Class Import 
**Syntax: `import packagename.*`**
Example: `import java.util.*`. Not recommended to use because it reduces readability of the code.
Best suitable where typing is important.

---
## Case-2: Valid import Statements
```java
import java.util.ArrayList; // Valid
import java.util.ArrayList.*; // Invalid
import java.util.*; // Valid
import java.util; // Invalid
```

---
## Case-3:  Fully Qualified Name
Consider the following code
```java
class myObject extends java.rmi.UnicastRemoteObject
```
The code compiles fine even though we are not writing import statement because we used full qualified name.

> [!NOTE]
> Whenever we are using fully qualified name, it is not required to write import statement. Similarly, whenever we are writing import statement it is not required to use fully qualified name.

---
## Case-4: Ambiguous Names in Package
```java
import java.util.*;
import java.sql.*;

class Test{
	public static void main(String[] args){
		Date d = new Date();  // CE: reference to Date is ambiguous
	}
}
```
Even in the case of list also we may get same ambiguity problem because it is available in both `util` and `awt` packages.

---
## Case-5: Resolving Precedence
While resolving class names, compiler will always gives the precedence in the following order:-
1. Explicit class import
2. Classes present in current working directory(default package)
3. Implicit class import
```java
import java.util.Date;
import java.sql.*;

class Test{
	public static void main(String[] args){
		Date d = new Date(); 
		sout(d.getClass().getName()); // java.util.Date
	}
}
```
---
## Case-6: Subclass
Whenever we are importing a Java package, all classes and interfaces present in the package by default available but not sub package classes. If we want to use sub package class, compulsory we should write `import` statement until sub package level.
Example: `java.util.regex.*`

---
## Case-7: Default Packages
```java
java.lang
default package(current working directory)
```
All classes and interfaces present in the following packages are by default available to every java program, hence we are not required to write import statement.

---
## Case-8: Compile Time
`import` statement is totally compile time related concept, if more number of inputs then more will be the compile time but there is no effect on execution time(runtime).

---
## Case-9: `#include` vs `import`
In the case of C language `#include` , all input output header files will be loaded at the beginning only (at translation time), hence it is static include.
But in the case Java `import` statement, no `.class` file will be loaded at the beginning whenever we are using a particular class then only corresponding `.class` file will be loaded this is considered as <span style="color:rgb(255, 192, 0)">dynamic include</span> or <span style="color:rgb(255, 192, 0)"><span style="color:rgb(255, 192, 0)">load</span> on demand</span> or <span style="color:rgb(255, 192, 0)">load on fly</span>.

In 1.5v following new features were implemented to Java:
1. for-each loop
2. var-arg method
3. Autoboxing
4. Generics
5. co-variant
6. Queue 
7. Annotation
8. enum
9. [[Static Import]]
