Whenever we are writing our own classes, we have to provide some information about our class to the JVM. Like, weather this class can be accessible from anywhere or not, weather child class creation is possible or not, weather object creation is possible or not, etc. We can specific this information by using appropriate modifier.

The only applicable modifiers for top level classes are:
1. [[public and default#public classes|public]] ^687373
2. [[public and default#default classes|default]] ^16055b
3. [[final]] ^528cf8
4. [[abstract]] ^ea76e2
5. [[strictfp]] ^643161

But for inner classes the applicable modifiers are:
1. `public`
2. `<default>`
3. `final`
4. `abstract`
5. `strictfp`
6. `private`
7. `protected`
8. `static`

Example-1:
```java
private class Test{
	public static void main(String[] arg){  // modifier private not allowed here
	}
}
```

## Difference b/w Access Specifier vs Access Modifiers
`public, private, protected, default` are considered as specifier except these remaining are considered as modifiers. But this rule is applicable only for old languages C++ but not in Java.

In Java all are considered as modifiers only there is no word like specifiers.

