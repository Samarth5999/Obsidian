---
~
---

##### Bitwise &, | and ^ 
<p style="text-align: center;" > & -> AND => Returns true iff both arguments are true.</p>
<p style="text-align: center;" > | -> OR => Returns true iff at least one argument is true.</p>
<p style="text-align: center;" > ^ -> X-OR => Returns true iff both arguments are different.</p>

We can apply these operators for integral types as well as boolean types.
```java
sout(4 & 5); // 100 = 4
sout(4 | 5); // 101 = 5
sout(4 ^ 5); // 001 = 1
```
---
##### Bitwise Complement Operator (~)
We can apply ~ operator only for integral types but not for Boolean type if we are trying to apply for Boolean type then we will get CE.
```java
sout(~4); // -5
```
Explanation: The most significant bit(MSB) act as sign bit, 0 means positive number and 1 means negative number. Positive number will be represented directly in the memory whereas negative number will be represented indirectly in the memory in 2's complement form.

![[sout(~4) = 5.png|1000]]

---
##### Boolean Compliment Operator (!)
We can apply this operator only for boolean types but not for integral types.
```java
sout(!4); // CE: operator cannot be applied to int
sout(!false); // true
```
