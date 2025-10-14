It is an inculpation mechanism to group related classes and interfaces into a single unit, which is nothing but package.

Example-1: All classes and interfaces which are required for database operations are grouped into a single package which is nothing but `java.sql` package.
Example-2: All classes and interfaces which are useful for file io operations are grouped into a separate package which is nothing but `java.io` package.

## Advantages of Package
1. To resolve naming conflicts i.e. unique identification of our components.
2. It improves modularity and maintainability of the application.
3. It provides security of our components.

There is one universally accepted naming convention for packages i.e. to use internet domain name in reverse.
![[Pasted image 20250522120254.png]]
```java
package com.durgasoft.scjp;

public class Test{
	public static void main(String[] args){
		sout("package demo");
	}
}
```
1st Command: `Javac Test.java`
Generated `.class` file will be placed in current working directory.

2nd Command: `Javac -d . Test.java`; `-d`: destination to place generated class file, `.`: CWD
Generated `.class` file will be placed in corresponding package structure.
CWD -> com -> durgasoft -> scjp -> `Test.class`

1. If the corresponding package structure not already available then this command itself will create corresponding package structure.
2. As destination instead of `.` we can take any valid directory name. Example: `Javac -d F: Test.java`
3. If the specified directory not already available then we will get `CE: directory not found: F:`
4. At the time of execution we have use fully qualified name. Example: `java com.durgasoft.scjp.Test`

### Conclusions

1. In any Java source file there can be at most 1 package statement otherwise we will get `CE: class, interface or enum expected`.
2. In any Java program the first non-comment statement should be package statement (if it available) otherwise we will get `CE: class, interface or enum expected`.

---

## Java Source File Structure Summary
This order is important
```java
package statement; // <- Atmost one
import statements; // <- Any number
class/interface/enum declarations // <- Any number
```


> [!NOTE] Note
>An empty source file is a valid Java program.
