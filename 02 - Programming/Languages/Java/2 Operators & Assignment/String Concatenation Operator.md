The only overloaded operator in Java is `+` operator, sometimes it act as arithmetic addition operator and sometimes it act as string concatenation operator.

If at least one argument is string type then `+` operator acts as concatenation operator and if both arguments are number type then `+` operator acts as arithmetic addition operator.
```java
String a = "durga"
int b = 10, c = 20, d = 30;
sout(a + b + c + d); // durga102030
sout(b + c + d + a); // 60durga
sout(b + c + a + d); // 30durga30
sout(b + a + c + d); // 10durga2030
```

```java
String a = "durga"
int b = 10, c = 20, d = 30;
a = b + c + d; // CE: Incompatible Types
a = a + b + c; // Valid
b = a + c + d; // CE: Incompatible Types
b = b + c + d; // Valid
```