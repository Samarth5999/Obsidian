```ad-Definition
A funtion calling itself is called a Recursion
```

Every recursive function must have a base condition to terminate; otherwise, it will result in **infinite recursion**.

```cpp
Type fun(Param)
{
	if(base condition)
	{
		1. .....
		2. fun(Param)
		3. .....
	}
}
```
Recursion is just multiple nested function calls.

### Two Types of recursion

##### 1. Head Recursion
Do the operation first then make the recursive call. Work is done during the calling phase.

```cpp 
void fun1(int n) {
    if (n > 0) {
        printf("%d ", n);   // work first
        fun1(n - 1);        // then call
    }
} // o/p: 3 2 1
```

##### 2. Tail Recursion
First make the recursive call then perform the operation. Work is done during the returning phase.

```cpp 
void fun2(int n) {
    if (n > 0) {
        fun2(n - 1);        // call first
        printf("%d ", n);   // work after
    }
} // o/p: 1 2 3
```

### Generalizing Recursion

- **Anything before the recursive call** → executes during the **calling phase** (ascending).
- **Anything after the recursive call** → executes during the **returning phase** (descending).

##### Comparison with Loops
- A **loop** has only one phase → it keeps repeating forward (like ascending only) whereas **Recursion** has **two phases** → ascending (while calling) + descending (while returning).
- That extra descending phase is the power of recursion. It allows you to do things naturally in reverse order without writing extra logic.