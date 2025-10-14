If we want to execute loop body at least once then we should go for do-while.
## Syntax
```java
do
{
	body
} while (boolean expression); // ; -> mandatory
```

## Important Points
1. Curly braces are optional and without curly braces we can take only one statement between do and while which should be declarative statement.
```java
do
	sout("hello");  // Valid
while(true);

do;
while(true);   // Valid

do
	int x = 10;  // InValid
while(true);

do{
	int x = 10;  // Valid
}
while(true);

do
while(true); // Valid
```

###### Important Example
```java
do while(true)
	sout("Hello");   // PERFECTLY Valid
while(false);
```
The while at line 2 is inside do block.


2. Unreachable Statement
```java
do
{
	sout("Hello");   // CE: Unreachable statement sout 
} while(true)
sout("Hi");

do
{
	sout("Hello");   // o/p: Hello, Hi 
} while(false)
sout("Hi");

int a = 10, b = 20;
do
{
	sout("Hello");   // o/p: Hello, Hello, Hello, ..... 
} while(a < b)
sout("Hi");

int a = 10, b = 20;
do
{
	sout("Hello");   // o/p: Hello, Hi
} while(a > b)
sout("Hi");

final int a = 10, b = 20;
do
{
	sout("Hello");   // CE: Unreachable statement sout 
} while(a < b)
sout("Hi");

final int a = 10, b = 20;
do
{
	sout("Hello");   // Hello, Hi 
} while(a > b)
sout("Hi");
```