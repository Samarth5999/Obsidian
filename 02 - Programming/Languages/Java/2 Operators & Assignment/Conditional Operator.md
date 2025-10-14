# ?:

The only possible ternary operator in Java is conditional operator.

###### Syntax: `(condition) ? (if true) : (if false)`
```java
int x = (10 < 20)?30:40; // if the condition is true then value after ? else after :
sout(x); // 30
```
We can perform nesting of conditional operator also.
```java
int x = (10 < 20)?30:((40 > 50)?60:70);
sout(x); // 70
```