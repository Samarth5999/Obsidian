## Syntax
```java
if (b){
	Action if b is true
}
else {
	Action if b is false
}
```

## Important Points
1. Argument to the if statement should be boolean type if any other type we will get CE: incompatible types.

Example-1:
```java 
int x = 10;
if (x){
	sout("Hello");
}
else{
	sout("Hi");   // CE: incompatible types
}
-------------------------------------------
if (x = 20){
	sout("Hello");
}
else{
	sout("Hi");   // CE: incompatible types
}
```
Example-2:
```java
int x = 10;
if (x == 20){
	sout("Hello");
}
else{
	sout("Hi");   // Hi
}
```
Example-3:
```java 
boolean b = true;
if (b = false){
	sout("Hello");
}
else{
	sout("Hi");   // Hi
}
```
Example-4:
```java 
boolean b = false;
if (b == false){
	sout("Hello");
}
else{
	sout("Hi");   // Hello
}
```

2. Else part and curly braces are optional, without curly braces only one statement is allowed under `if` which should not be declarative statement.

```java
if (true)
	sout("Hello") // Hello

if (true); // no o/p

if (true)
	int x = 10; // CE 

if (true){
	int x = 10; // no o/p
}
```

*Note: Semicolon(;) is a valid Java statement which is also known as empty statement.*

3. There is no dangling else problem in Java, every `else` is mapped to the nearest `if` statement.

```java
if (true)
	if (true)
	sout("hello");
else{
 sout("Hi");
}
   // the else is mapped to the if at line 4
```
