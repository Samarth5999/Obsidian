#### Valid Combinations

1. A class can extend only one class at a time.

2. An Interface can extend any number of Interfaces simultaneously
```java
interface A {}
interface B {}
interface C extends A,B {}
```

3. A class can implement any number of Interfaces simultaneously

4. A class can extend another class and can implement any number of Interfaces simultaneously.
```java
class A extends B implements C,D,E {}
```


#### Invalid Combinations

1. A class can extend any number of classes at a time.
2. A class can implement only one interface at a time.
3. Interface can extend only one interface at a time.
4. An Interface can implement any number of Interfaces simultaneously.
5. A class can extend another or can implement an Interface but not both simultaneously.



> [!question] Question-1
> Consider the following expression `X extends Y`, which of the following argument is Valid?
> 1. Both X and Y should be classes
> 2. Both X and Y should be interfaces
> 3. <span style="color:rgb(146, 208, 80)">Both X and Y can be either classes or interface</span>
> 4. No Restrictions

> [!question] Question-2
> Consider the following expression `X extends Y,Z` , write all the possible arguments?
> ANS: <span style="color:rgb(146, 208, 80)">X, Y, Z should be Interfaces</span>

> [!question] Question-3
> Consider the following expression `X implements Y,Z` , write all the possible arguments?
> ANS: <span style="color:rgb(146, 208, 80)">X -> Class and Y, Z -> Interfaces</span>

> [!question] Question-4
> Consider the following expression `X extends Y implements Z` , write all the possible arguments?
> ANS: <span style="color:rgb(146, 208, 80)">X ,Y-> Classes and Z -> Interface</span>

>[!caution] 
>`X implements Y extends Z` gives CE: because we have to take extends first followed by Interface.

