If we don't know number of iteration in advance then we should go for while loop.
Example: `while(rs.next){ }`, `while(e.hasmoreElements()){ }`, `while(itr.hasnext()){ }`
## Syntax
```java
while (b) 
{
	Action
}
```
The argument should be boolean type otherwise we will get CE.

## Important Points
1. Curly braces are optional and without curly braces we can take only one statement under while which should be declarative statement.
```java
while(true)
	sout("hello");  // Valid

while(true);   // Valid


while(true)
	int x = 10; // CE

```

2. Unreachable Statement
```java
while(true)
{
	sout("Hello");   // CE: Unreachable statement sout
}
sout("Hi");

while(false)
{
	sout("Hello");   // CE: Unreachable statement {  
}
sout("Hi");

int a = 10, b = 20;
while(a < b)
{
	sout("Hello");   // o/p: Hello, Hello, Hello, ..... 
}
sout("Hi");

final int a = 10, b = 20;
while(a < b)
{
	sout("Hello");   // CE: Unreachable statement sout 
}
sout("Hi");
```


##### Note: Every final variable(Compile time constant) will be replaced by the value at compile time only.
```java
fianl int a = 10, b = 20;
c = 30;

sout(a);  After Compilation => sout(10);
sout(c);  After Compilation => sout(c);
sout(a + b);  After Compilation => sout(30);
sout(a + c);  After Compilation => sout(10 + c);
sout(a < b);  After Compilation => sout(true);
sout(a < c);  After Compilation => sout(10 < c);
```