When recursion happens, the stack is where all the action takes place.
Every time a function is called, an Activation Record (AR) (also called stack frame) is created. AR stores Function Parameter, local variables and return address. When function finishes, its AR is deleted(stack frame popped).

Example:- 
```cpp
void fun1(int n) {
    if (n > 0) {
        printf("%d ", n);
        fun1(n - 1);
    }
}
```
 Step-by-step Execution for `fun1(3)`:
1. `main` starts → AR for `main` created (`x = 3`).
2. `main` calls `fun1(3)` → AR for `fun1` with `n = 3` created.
3. `fun1(3)` calls `fun1(2)` → new AR with `n = 2`.
4. `fun1(2)` calls `fun1(1)` → new AR with `n = 1`.
5. `fun1(1)` calls `fun1(0)` → new AR with `n = 0`.
    
Now base case hit (`n == 0`) → function returns.  
Each AR is **deleted one by one** as control returns to the caller.

#### Stack Size and Space Complexity

For input n, recursion makes n + 1 calls (including base calls). So, n + 1 activation records are created.
Each AR stores one `int n`. If `sizeof(int) = 4 bytes`, total memory used is `(n+1) * 4`.

```ad-important
Space Complexity = O(n)
```

#### Time Complexity
If each statement = 1 unit of time, printing happens once per call i.e. total = n units + 1(base case)

```ad-important
Time Complexity = O(n)
```
