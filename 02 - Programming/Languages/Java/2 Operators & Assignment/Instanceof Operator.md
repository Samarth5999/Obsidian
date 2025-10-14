We can use Instanceof operator to check whether the given object is of particular type or not.
```java
Object o = l.get(o);
if (o instanceof Student) {
	Student s = (Student)o; // perform Student specific funtionality
}
if (o instanceof Customer) {
	Customer s = (Customer)o; // perform Customer specific funtionality
}
```

###### Syntax
<p style="text-align: center;">
r instanceof X
</p>
Here, r is the object reference and X is the class/interface name.

Example-1
```java
Thread t = new Thread();
sout(t instanceof Thread); // true
sout(t instanceof Object); // true
sout(t instanceof Runnable); // true
```
It is because thread is a child class of object and Thread implements runnable.

Example-2
To use instanceof operator compulsory there should be some relation between argument types(either child to parent or parent to child or same type) otherwise we will get CE saying inconvertible types.
```java
Thread t = new Thread();
sout(t intanceof String); // CE: incovertiable types 
```

Note: For any class or interface `x`, `null instanceof x` is always false.