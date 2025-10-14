Local variables are freshly created in each activation record on the stack whereas 
Static variables are created only once, stored in the static/global section. So all recursive calls share the same single copy of a static variable.

#### Example: Using Local Variable
```cpp 
int fun(int n) {
    if (n > 0) {
        return fun(n - 1) + n;
    }
    return 0;
}

main(){
	int a = 5;
	printf("%d", fun(a));	// o/p: 15
}
```
fun(5) 
= fun(4) + 5
= (fun(3) + 4) + 5
= ((fun(2) + 3) + 4) + 5
= (((fun(1) + 2) + 3) + 4) + 5
= ((((fun(0) + 1) + 2) + 3) + 4) + 5
= ((((0 + 1) + 2) + 3) + 4) + 5
= 15

With local variable n → each call had its own value → gave sum = 15

#### Example: Using Static Variable
```cpp
int fun(int n) {
    static int x = 0;   // only one copy for all calls
    if (n > 0) {
        x++;
        return fun(n - 1) + x;
    }
    return 0;
}
```
fun(5)
= fun(4) + x → (x = 1 … but by the time we return, x keeps increasing)
= (fun(3) + 2) + 5
= ((fun(2) + 3) + 5) + 5
= (((fun(1) + 4) + 5) + 5) + 5
= ((((fun(0) + 5) + 5) + 5) + 5) + 5
= ((((0 + 5) + 5) + 5) + 5) + 5
= 25

With static variable x → all calls used the same x = 5 → result = 25. If we declared x as a global variable instead of static, the behavior would be identical.