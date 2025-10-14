## First program

We will be using three commands to write, compile, and run our first program:

```bash
code hello.c #makes a C file

make hello #compiles the file in C

./hello #Runs the program
```

We can build your first program in C by typing `code hello.c` into the [[Terminal Commands]] window.
```C
#include <stdio.h> 

int main(void)
{
    printf("hello, world\n");
}
```

`\` character is called an _escape character_ that tells the compiler that `\n` is a special instruction to create a line break. Other escape characters:
```bash
\n  #create a new line
\r  #return to the start of a line
\"  #print a double quote
\`  #print a single quote
\\  #print a backslash
```
---
## Header files

The statement at the start of the code `#include <stdio.h>` is a very special command that tells the compile that you want to use the capabilities of a _library_ called `stdio.h`, a _header file_. This allows you, among many other things, to utilize the `printf` function.
CS50 has its own library called `cs50.h`:
```C
get_char
get_double
get_float
get_int
get_long
get_string
```
---
## Getting Input 
<div style="text-align: center;">
  <span style="font-weight:bold; color:rgb(40, 74, 120)">Type</span> 
  <span style="color:rgb(146, 84, 89)">Name</span> = 
  <span style="color:rgb(103, 127, 86)">Function</span>
</div>

Function can be `get_int` or `get_string` from <cs.50.h>.
```C
#include <cs50.h> //for get_string
#include <stdio.h> //for printf

int main(void)
{
    string answer = get_string("What's your name? ");
    printf("hello, %s\n", answer);
}
```
`%s` is a placeholder called a _format code_ that tells the `printf` function to prepare to receive a `string`. `answer` is a special holding place we call a _variable_. `answer` is of type `string` being passed to `%s`.

#### Types
```C
%c //char
%f //float
%i //int
%li //long
%s //string
```
---
## Variables
We can write a variable in C as:
<div style="text-align: center;">
  <span style="font-weight:bold; color:rgb(40, 74, 120)">Type of variable</span> 
  <span style="color:rgb(146, 84, 89)">Name of the variable</span> = 
  <span style="color:rgb(103, 127, 86)">Value of the variable</span>
</div>

```C
int counter = 0;
counter = counter + 1;
counter =+ 1;               //All similar
counter++;
```

```C
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // Prompt user for integers
    int x = get_int("What's x? ");
    int y = get_int("What's y? ");

    // Compare integers
    if (x < y)
    {
        printf("x is less than y\n");
    }
}
```
---
## Conditional Statements
### Loops

#### if-else
```C
if (boolean expression)
{
	Action when boolean expression is true;
}
else{
	Action when boolean expression is false;
}
```

#### While Loop

```C
while (boolean expression)
{
	Action when boolean expression is true;
	increment or decrement i;	
}
```

```C
#include <stdio.h>

int main(void)
{
    int i = 0;
    while (i < 3)
    {
        printf("meow\n");
        i++;
    }
}
```
Counter `i` is started at `0`. Each time the loop runs, it will increment the counter by `1`. Once the counter is equal to `3`, it will stop the loop.

#### For Loop
```C
for (intialization; boolean expression; increment)
{
	Action
}
```

The first argument `int i = 0` starts our counter at zero. The second argument `i < 3` is the condition that is being checked. Finally, the argument `i++` tells the loop to increment by one each time the loop runs.
```C
#include <stdio.h>

int main(void)
{
    for (int i = 0; i < 3; i++)
    {
        printf("meow\n");
    }
}
```

```C
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    while (true)
    {
        printf("meow\n");
    }
}
```
> Notice that `true` will always be the case. Therefore, the code will always run. You will lose control of your terminal window by running this code. You can break from an infinite by hitting `control-C` on your keyboard.

#### Do while 
```C
#include <cs50.h>
#include <stdio.h>

int get_positive_int(void);
void meow(int n);

int main(void)
{
    int n = get_positive_int();
    meow(n);
}

// Get number of meows
int get_positive_int(void)
{
    int n;
    do
    {
        n = get_int("Number: ");
    }
    while (n < 1);
    return n;
}

// Meow some number of times
void meow(int n)
{
    for (int i = 0; i < n; i++)
    {
        printf("meow\n");
    }
}
```
Notice that a new function called `get_positive_int` asks the user for an integer while `n < 1`. After obtaining a positive integer, this function will `return n` back to the `main` function.

#### Nested Loops
```C
#include <stdio.h>

int main(void)
{
    for (int i = 0; i < 3; i++)
    {
        for (int j = 0; j < 3; j++)
        {
            printf("#");
        }
        printf("\n");
    }
}
```

### switch
Nothing Fancy



## Functions
#### Structure
```C
Return Type | Function Name | (Parameters)
{
	Code Inside
}
Return Statement // Not required if return type is void
```

```C
void meow(void) // 1st void is the return and 2nd void is the input
{
    printf("meow\n");
}
```
The initial `void` means that the function does not return any values. The `(void)` means that no values are being provided to the function.
```C
#include <stdio.h>

void meow(int n); //Prototype

int main(void)
{
    meow(3);
}

// Meow some number of times
void meow(int n) //Function
{
    for (int i = 0; i < n; i++)
    {
        printf("meow\n");
    }
}
```
Notice that the prototype has changed to `void meow(int n)` to show that `meow` accepts an `int` as its input.
`meow` function is defined at the bottom of the code, and the _prototype_ of the function is provided at the top of the code as `void meow(int n)`.`meow` accepts an `int` as its input.

---
## Operators
Arithmetic Operators: Nothing Fancy

Boolean Expressions: Nothing Fancy
**In C, every nonzero value is equivalent to true, and
zero is false.**
#### Truncation
An integer divided by an integer will always result in an integer in C. The code will often result in any digits after the decimal being thrown away. This can be solved by employing a `float`.
BUT, _Floating point imprecision_ illustrates that there are limits to how precise computers can calculate numbers i.e. printing gibberish after after certain decimal point.
To solve this use `%.5f` around that to get the desired result.

---
## Data Types
Unlike modern languages like **Python, JavaScript, or PHP**, in **C**:

- You must **explicitly specify** the data type of a variable when you **declare** it.
- This affects how **much memory** is allocated and what **operations** can be performed.

### int(integer)
*  Stores 4 bytes i.e. whole number from:  $$ -2^{31}\;to\; 2^{31}-1$$
#### Unsigned int
*  A **qualifier** added to an `int` that means it **cannot be negative**.
*  Also stores 4 byte but from: $$ 0\;to\; 2^{32}-1$$

### char(character)
* Stores **single characters** and takes up 1 byte.
$$ -128\; to\; 127$$

### float(floating point number)
- Stores *real numbers* with decimal points.    
- Takes up **4 bytes**.
- Has *limited precision* (≈ 7 decimal places).

### double
- Like `float`, but **double the precision**: **8 bytes** (64 bits)
- Stores real numbers with much **higher accuracy** (≈ 15–17 decimal places)

### void
* Means nothing or no value.
* It is a type *not a data type*. Used for functions, not variables.
* Example:
  `void printSomething() → function returns nothing`
  `int main(void) → function takes no arguments`

>[[!Note]]
> `int number; // declaration`
> `int number = 10; // initialization`

---
## Magic Number
Directly writing constants into our code is sometimes referred to as using **magic numbers**.

C provides a preprocessor directive (also called a macro) for creating symbolic constants.
<p align="center"><span style="color:rgb(255, 192, 0)">#define NAME REPLACEMENT</span></p>
At the time your program is compiled, `#define` goes through your code and replaces `NAME` with `REPLACEMENT`.
`#define` is analogous to find/replace.

---
## Problem Set 1

1. [[Mario]]
2. [[Cash]]
3. [[Credit]]