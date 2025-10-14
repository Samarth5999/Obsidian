There are two types of type-casting:-
##### 1. Implicit Type Casting
* Compiler is responsible to perform implicit type casting.
* Whenever we are assigning smaller data type value to bigger data type variable, implicit type casting will be performed.
* It is also knowns as <span style="color:rgb(222, 217, 74)">widening</span> or <span style="color:rgb(222, 217, 74)">upcasting</span>.
* There is no loss of information in this type casting.

Example:
```java
int x = 'a';
sout(x); // 97   (compiler converts char to int automatically by implicit type casting)

double x = 10;
sout(x); // 10.0   (compiler converts int to double automatically by implicit type casting)
```

##### 2. Explicit Type Casting
* Programmer is responsiable to perform explicit type casting
* Whenever we are assigning bigger data type value to smaller data type variable then explicit type casting is required.
* It is also knowns as <span style="color:rgb(222, 217, 74)">Narrowing</span> or <span style="color:rgb(222, 217, 74)">Down-casting</span>.
* There maybe a chance of loss of information in this type casting.

Example:
```java
int x = 130;
byte b = x; // CE: PLP found: int, req: byte

byte b = (byte)x;
sout(b); // -126 (loss of information)
```
###### How the loss of information is taking place(i.e. 130 = -126)?
=> Whenever we are assigning bigger data type value to smaller data type variable by explicit type casting, the most significant bits will be lost, we have to consider only least significant bits.
![[Pasted image 20250518175638.png]]

If we assign floating point values to the integral types by explicit type casting, the digits after the decimal point will be lost.
```java 
double d = 130.456
int x = (int)d;
sout(x); // 130

byte b = (byte)d; 
sout(b); // -126
```