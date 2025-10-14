In java every variable and every expression has some type. Each and every data type is clearly defined. Every assignment should be checked by complier for type compatibility. Because of above reason we can conclude java language is strongly typed programming language.

Java is not considered as pure oops language because several oops feature are not satisfies by java like operator overloading, multiple inheritance, etc. Moreover we are depending on primitive data types which are non-objects.

---

# Numeric Data Types 

## 1. Integral Types 

### `byte`

- Size: 1 byte
- Range: -128 to 127
- Default: 0
- Used in stream processing (files, network)

### `short`

- Size: 2 bytes
- Range: $-2^{15}$ to $2^{15}-1$
- Default: 0
- Rarely used; designed for 16-bit processors

### `int`

- Size: 4 bytes
- Range: $-2^{31}$ to $2^{31}-1$
- Default: 0
- Most commonly used

### `long`

- Size: 8 bytes
- Range: $-2^{63}$ to $2^{63}-1$
- Default: 0
- Used when `int` is not sufficient (e.g., file sizes)

#### Example

```java
int x = 2147383648;     // Compile error: integer number too large
int x = 2147383648L;    // Compile error: incompatible types - found long, required int
