
| Expression | Initial Value of x | Value of y | Final Value of x |
| :--------: | :----------------: | :--------: | :--------------: |
| `y = ++x;` |         10         |     11     |        11        |
| `y = x++;` |         10         |     10     |        11        |
| `y = --x;` |         10         |     9      |        9         |
| `y = x--;` |         10         |     10     |        9         |
>[!important] 
>`sout(y = x++);` means print x then increment by 1 i.e. o/p: x
>`sout(y = ++x);` means increment x by 1 then print x i.e. o/p: x + 1


#### Some Important Points

1. We can apply increment and decrement operators only for variables but not for constant values, if we are trying to apply for constant values then we will get compile time error.
```java
int x = 10;
int y = ++ (++x);
sout(y); // CE: Unexpected type 
```

2. Reassignment of <span style="color:rgb(222, 217, 74)">final variable</span> is not possible i.e. we cannot apply increment or decrement operators for <span style="color:rgb(222, 217, 74)">final variable.</span>
```java
int x = 10;
x++;
sout(x); //CE: Cannot assign a value to final variable
```

3. We can apply increment and decrement operator for every primitive type except Boolean.
```java
boolean b = ture;
b++;
sout(b): //CE: operator ++ cannot be applied to boolean
```

 4. Difference Between b++ and b+1?
If we apply any arithmetic operator between two variables a and b the result type is always max(int, type of a, type of b).
```java
byte a, b = 10,20;
byte c = a + b; // CE: PLP, found: int, req: byte
byte c = (byte)(a+b) // Valid (Type Casting)
```
But in the case of increment and decrement operator internal type casting will be performed automatically.
```java
byte b = 10;
b = b + 1; // CE: PLP, found: int, req: byte coz max(int, byte, int)
b = (byte)(b+1); // Valid (Type Casting)
b++; // o/p: 11, Internal Type Casting b = (Type of b)(b+1)
```
