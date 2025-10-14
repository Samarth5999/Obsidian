Java has 53 reserved words:

## Keywords (50)

### Used Keywords (48)

| Data Types | Flow Control | Modifiers           | Exception Handling | Class Related | Object Related | Others |
| ---------- | ------------ | ------------------- | ------------------ | ------------- | -------------- | ------ |
| `byte`     | `if`         | `public`            | `try`              | `class`       | `new`          | `void` |
| `short`    | `else`       | `private`           | `catch`            | `interface`   | `instanceof`   | `enum` |
| `int`      | `switch`     | `protected`         | `finally`          | `extends`     | `super`        |        |
| `long`     | `case`       | `static`            | `throw`            | `implements`  | `this`         |        |
| `float`    | `default`    | `final`             | `throws`           | `package`     |                |        |
| `double`   | `while`      | `abstract`          | `assert` *(1.4V)*  | `import`      |                |        |
| `boolean`  | `do`         | `synchronized`      |                    |               |                |        |
| `char`     | `for`        | `native`            |                    |               |                |        |
|            | `break`      | `strictfp` *(1.2V)* |                    |               |                |        |
|            | `continue`   | `transient`         |                    |               |                |        |
|            | `return`     | `volatile`          |                    |               |                |        |

###  Unused Keywords (2)
- `goto`: Reserved but not used (caused problems in older languages).
- `const`: Replaced by `final` in Java.
---
## Reserved Literals (3)

- `true`: Boolean value
- `false`: Boolean value
- `null`: Default value for object references

---

## Additional Notes

* All 53 reserved words contains lower-case alphabet.
- In java, we have only `new`keyword and there is no `delete`keyword because destruction of useless objects is the responsibility of garbage collector.
- `void`: In java written type is mandatory, if a method won’t return anything then we have to declare that method with `void` return type.
- `goto` : Usage of `goto` created several problems in old languages and hence some banned this keyword in java.
- `const`: Use final instead of `const`.
- `goto` and `const` are unused keywords and if we are trying to use we will get compile time error.
- `enum`: We can use `enum` to define a group of named constants](<- All reserved words in Java are lowercase.
- Java has only the `new` keyword; **no `delete`** (memory managed by Garbage Collector).
- `void`: Used when a method returns nothing.
- `enum`: Introduced in Java 1.5, defines a set of named constants.>)
