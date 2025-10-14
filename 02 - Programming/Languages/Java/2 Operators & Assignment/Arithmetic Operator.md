# + 
If we apply any arithmetic operator between two variables a and b, the result type is always max(type of a, type of b).

|  Expression   | Result | \|  |  Expression   | Result |
| :-----------: | :----: | :-: | :-----------: | :----: |
|  byte + byte  |  int   | \|  | long + double | double |
|  byte +short  |  int   | \|  | float + long  | float  |
| short + short |  int   | \|  |  char + char  |  int   |
|  byte + long  |  long  | \|  | char + double | double |


```java
sout('a' + 'b'); // 97 + 98 = 195
sout('a' + 0.87); // 97.87
```

## Division by 0

In Integral Arithmetic(byte, short, int, long), there is no way to represent to infinity, hence, if infinity is the result we will get Arithmetic Exception in integral arithmetic.
```java
sout(10/0); // RE: AE: / by 0
```

In Floating Point Arithmetic(float and double), there is a way to represent infinity and undefined results. For this Float and Double classes contains the following three constants: 
1. POSITIVE_INFINITY;
2. NEGATIVE_INFINITY;
3. NaN Constant; (Not a Number)
Hence even though the result is infinity or undefined, we won't get any AE in floating point arithmetic. 
```java
sout(10/0.0); // Infinity
sout(-10/0.0); // -Infinity
sout(0.0/0); // NaN
```

#### `Float.NaN`

For any x value including NaN, the following expression returns false:
```java
sout(x < Float.NaN);
sout(x <= Float.NaN);
sout(x > Float.NaN);
sout(x >= Float.NaN);              // all false
sout(x == Float.NaN);
sout(Float.NaN == Float.NaN);
```
For any x value including NaN, the following expression returns true:
```java
sout(x != Float.NaN); // true
sout(Float.NaN != Float.NaN); // true
```

## Arithmetic Exception

1. It is Runtime Exception but not Compile-time Exception.
2. It is possible only in integral arithmetic but not in floating point arithmetic.
3. The only operator which cause AE are / and %.