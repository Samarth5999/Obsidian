Introduced in 1.2v, we can use strictfp(strict floating point) for classes and methods but not for variables.

Usually the result of floating point arithmetic is varied from platform to platform, if we want platform independent results for floating point arithmetic then we should go for strictfp modifier.

# strictfp method
If a method declared as strictfp, all floating point calculation in that method has to follow IEEE 754 standard so that we will get platform independent results.

abstract and strictfp method modifiers are illegal combination of modifiers.

# strictfp class
If a class declared as strictfp then every floating point calculation present in every concrete method has to follow IEEE 754 standard
so that we will get platform independent results.

We can declare abstract strictfp combinations for classes i.e. abstract strictfp combination is legal for classes but illegal for methods.

```java 
abstract strictfp class Test{} // Valid
```