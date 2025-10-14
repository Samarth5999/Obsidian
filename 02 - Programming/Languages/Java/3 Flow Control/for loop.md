---
~
---
=> for loop is the most commonly used loop in java. If we know number of iterations in advance then for loop is the best choice.
## Syntax
```java
for(initialization-section; conditional-check; increment-decrement-section)
{
	loop body
}
```
**Sequence:** *1 -> initialization-section, 2 -> conditional-check, 3 -> increment-decrement-section, 4 -> loop body, 5 -> conditional-check, 6 -> increment-decrement-section, 7 -> loop body, 8 -> conditional-check, 9 -> increment-decrement-section, 10 -> loop body, ......*

### Initialization Section
* This part will be executed only **once** in loop life cycle.
* Here, we can declare and initialize local variables of for-loop.
* Here, we can declare any number of variables but should be of the same type, by mistake if we are trying different data type variable then we will get CE.
```java 
int i = 0, j = 0; // Valid

int i = 0, String s = "durga"; // Invalid

int i = 0, int j = 0; // Valid
```
*  In the initialization section, we can take any valid Java statement including `sout`.
```java
int i = 0;

for(sout("Hello"); i < 3; i++)
{
	sout("Hi"); // o/p: Hello, Hi, Hi, Hi
}
```

### Conditional Check
* Here we can take any valid Java statement but should of the type boolean(overall expression).
* This part is optional and if we are not taking anything then compiler will always place `true`.

### Increment or Decrement Section
* In the increment decrement section any valid java statement including `sout`.

##### Note: Infinite Loops: All three parts of for-loop are independent of each other and optional.
```java
for(;;); // Infinite Loop
```

## Important Points
1. Curly braces are optional and without curly braces we can take only one statement under for-loop, which should not be declarative statement.
```java
for(int i = 0; true, i++)  // Valid
	sout("Hello");

for(int i = 0; i < 10, i++);  // Valid

for(int i = 0; i < 10, i++)  // Valid
	int x = 10;
```

2. Unreachable Statements
```java
for(int i = 0; true; i++)
{
	sout("Hello"); // CE: Unreachable Statement
}
sout("Hi");

for(int i = 0; false; i++)
{
	sout("Hello"); // CE: Unreachable Statement
}
sout("Hi");

for(int i = 0; ; i++)
{
	sout("Hello"); // CE: Unreachable Statement
}
sout("Hi");

int a = 10, b = 20;
for(int i = 0; a < b ; i++)
{
	sout("Hello"); // Hello, Hello, Hello, ......
}
sout("Hi");

int a = 10, b = 20;
for(int i = 0; a > b ; i++)
{
	sout("Hello"); // Hi
}
sout("Hi");

final int a = 10, b = 20;
for(int i = 0; a < b ; i++)
{
	sout("Hello"); // CE: Unreachable Statement
}
sout("Hi");

final int a = 10, b = 20;
for(int i = 0; a > b ; i++)
{
	sout("Hello"); // CE: Unreachable Statement
}
sout("Hi");
```