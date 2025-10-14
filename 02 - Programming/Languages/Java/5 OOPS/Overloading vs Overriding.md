
| S.no |        Property        |                          [[Overloading]]                          |                         [[Overriding]]                          |
| :--: | :--------------------: | :---------------------------------------------------------------: | :-------------------------------------------------------------: |
|  1   |     Methods Names      |                               Same                                |                              Same                               |
|  2   |    Arguments Types     |                     Different(at least order)                     |                              Same                               |
|  3   |    Method Signature    |                             Different                             |                              Same                               |
|  4   |      Return Types      |                          No Restrictions                          |  Same until 1.4v but from 1.5v co-variant return type allowed   |
|  5   | private, static, final |                         Can be Overloaded                         |                      Cannot be Overridden                       |
|  6   |    Access Modifiers    |                          No Restrictions                          | Scope of access modifier cannot be reduced but can be increased |
|  7   |      throws class      |                          No Restrictions                          |               [[Overriding#^2d1126\|Refer this]]                |
|  8   |   Method Resolution    |       Always taken care by compiler based on Reference Type       |        Always taken care by JVM based on Run time object        |
|  9   |     also Known as      | Compile Time Polymorphism<br>Static Polymorphism<br>Early Binding |  Run Time Polymorphism<br>Dynamic Polymorphism<br>Late Binding  |
>[!important] 
>In Overloading we have to check only method names (must be same) and argument types (must be different). We are not required to check remaining like return types, access modifiers, etc.
>But in Overriding everything we have to check like method names, argument types, return types, access modifiers, throws class, etc.

```ad-question
title: Consider the following method in parent class `public void m1(int i) throws Exception`. In the child class which of the following methods we can take:-
1. `public void m1(int i)`
2. `public static int m1(long l)`
3. `public static int m1(int i)`
4. `public void m1(int i) throws Exception`
5. `public static abstract void m1(double d)`
``````ad-answer
collapse: closed
1. Valid, Overriding
2. Valid, Overloading
3. InValid, Overriding
4. InValid, Overriding
5. CE: illegal combination of modifiers
```

