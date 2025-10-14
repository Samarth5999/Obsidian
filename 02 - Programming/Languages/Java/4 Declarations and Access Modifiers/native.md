The methods which are implemented in non-Java(mostly C or C++) are called <span style="color:rgb(253, 223, 126)">native methods</span> or <span style="color:rgb(253, 223, 126)">foreign methods</span>.
native is a modifier applicable only for methods and we can't apply anywhere else. 

##### The main objectives of native keyword are 

1. To improve performance of the system. (Important Objective)
2. To achieve machine level or memory level communication.
3. To use already existing legacy non-Java code.

##### Pseudocode to use native keyword in Java

```java
class Native{
	static{
	System.loadLibrary("native library path"); // 1. Load Native Libraries
	}
	public native void m1(); // 2.Declare a native method
}
```

```java
class Client{
	public static void main(String[] args){
	Native n = new Native();
	n.m1(); // 3. Invoke a native method
	}
}
```

For native methods, implementation is already available in old languages like C or C++ and we are not responsible to provide implementation, hence native method declaration should ends with `;` otherwise we will get `CE: native method cannot have a body`.

We can't declare native method as strictfp because there is no guarantee that old languages follow IEE754 standard, hence native strictfp combination is illegal combinations for methods.

The main advantage of native keyword is performance will be improved but the main disadvantage of native keyword is breaks platform independent nature of Java.