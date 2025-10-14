There are three types of assignment operators:-

1. Simple Assignment
```java
int a = 10;
```

2. Chained Assignment
```java
int a, b, c, d;
a = b = c = d = 20;

int a = b = c = d = 20; // CE: cannot find symbol

int b, c, d;
int a = b = c = d = 20; // Valid
```
We can't perform assignment directly at the time of declaration.

3. Compound Assignment
Sometimes assignment operator mixed with some other operator such type of assignment operators are called compound assignment operators.
```java
int a = 10;
a += 20;
sout(a); // 30
```
The following are all possible compound assignment operator in java:-

| +=  | *=  | %=  | \|= | >>= | >>>= |
| :-: | :-: | :-: | :-: | :-: | ---- |
| -=  | /=  | &=  | ^=  | <<= |      |

In the case compound assignment operator, internal type-casting will be performed automatically.
```java 
byte b = 10;

b = b + 1; // CE: PLP
b++; // 11
b += 1; // 11 (internal type casting) 

byte b = 127;
b += 3; // -126
```


```java
int a, b, c, d;
a = b = c = d = 20;
a += b -= c *= d /= 20;
sout(a + ".." + b + ".." c + ".." + d); // -160..-180..200..10
```