We can apply equality operators for every primitive type including boolean type also.
We can apply equality operators for object type also.
For object references, r1 and r2 : `r1 == r2` returns true if and only if both references pointing to the same object(reference comparison or address comparison).
```java
Tread t1 = new Thread();
Tread t2 = new Thread();
Tread t3 = t1;
sout(t1 == t2); // false
sout(t1 == t3); // true
```

If we apply equality operators for object types then we compulsory there should be some relation between argument types(either child to parent or parent to child or same type) otherwise we will get CE: incomparable types.
```java 
Thread t = new Thread();
Object o = new Object();
String s = new String("durga");
sout(t == o); // false
sout(s == o); // false
sout(t == s); // CE: incomparable types java.land.String and java.lang.Thread
```
###### Difference between == operator and .equals() method
In general we can use == operator for reference comparison(address comparison) and .equals() method for content comparison
```java
String s1 = new String("durga");
String s2 = new String("durga");
sout(s1 == s2); // false
sout(s1.equals(s2)); // true
```

For any object reference r, `r == null` is always false but `null == null` is always true.
```java
String s = new String("durga");
sout(s == null); // false

String s = null;
sout(s == null); // true

sout(null == null); // ture
```