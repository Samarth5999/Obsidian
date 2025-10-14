By convention, all hexadecimal numbers are often represented with the `0x` prefix as follows:
![[cs50Week4Slide066.png|500]]

## Pointers

The C language has two powerful operators that relate to memory:
```C
& Provides the address of something stored in memory.
* Instructs the compiler to go to a location in memory.
```
We can print an integer's address as follows:
```C
int main(void)
{
    int n = 50;
    printf("%p\n", &n);
}
```
Notice the `%p`, which allows us to view the address of a location in memory.
`&n` can be literally translated as “the address of `n`.” Executing this code will return an address of memory beginning with `0x`.
```ad-important
A _pointer_ is a variable that stores the address of something. Most succinctly, a pointer is an address in your computer’s memory and a pointer is usually stored as an 8-byte value.
```

```C
int n = 50;
int *p = &n;
```
Here, `p` is a pointer that contains the address of an integer `n`.

```C
int main(void)
{
    int n = 50;
    int *p = &n;
    printf("%p\n", p); // prints memory address o/p: x0123
    printf("%i\n", *p); // prints value at memory address o/p: 50
}
```
This code has the same effect as our previous code. We have simply leveraged our new knowledge of the `&` and `*` operators.

`type *` is a pointer that stores the address of a type
`*x` takes a pointer x and goes to the address stored at that pointer
`&x` takes x and gets its address

## String 

Recall that a string is simply an array of characters. For example, `string s = "HI!"` can be represented as follows:
![[cs50Week4Slide085.png|500]]
###### What is `s` really?
`s` is a pointer that tells the compiler where the first byte of the string exists in memory.
```C
// Prints a string's address as well the addresses of its chars

#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string s = "HI!";
    printf("%p\n", s);
    printf("%p\n", &s[0]);
    printf("%p\n", &s[1]);
    printf("%p\n", &s[2]);
    printf("%p\n", &s[3]);
}
```

Taking off the training wheels, you can modify your code again:
```C
#include <stdio.h>

int main(void)
{
    char *s = "HI!";
    printf("%s\n", s);
}
```
The cs50 library includes a struct as follows: `typedef char *string

---
## Pointer Arithmetic

Pointer arithmetic is the ability to do math on locations of memory.
```C
// Prints a string's chars via pointer arithmetic

#include <stdio.h>

int main(void)
{
    char *s = "HI!";
    printf("%c\n", *s);
    printf("%c\n", *(s + 1));
    printf("%c\n", *(s + 2));
}
```
Notice that the first character at the location of `s` is printed. Then, the character at the location `s + 1` is printed, and so on.

```C
// Prints substrings via pointer arithmetic

#include <stdio.h>

int main(void)
{
    char *s = "HI!";
    printf("%s\n", s);
    printf("%s\n", s + 1);
    printf("%s\n", s + 2);
}
```
Notice that this code prints the values stored at various memory locations starting with `s`.

---
## String Comparison

A string of characters is simply an array of characters identified by the location of its first byte.

Utilizing the == operator in an attempt to compare strings will attempt to compare the memory locations of the strings instead of the characters therein. Accordingly, we recommended the use of `strcmp`.

The == sees if the memory addresses are same, not the strings themselves.

## Copying and malloc

```C
// Capitalizes a string

#include <cs50.h>
#include <ctype.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    // Get a string
    string s = get_string("s: ");

    // Copy string's address
    string t = s;

    // Capitalize first letter in string
    t[0] = toupper(t[0]);

    // Print string twice
    printf("s: %s\n", s);
    printf("t: %s\n", t);
}
```
Notice that `string t = s` copies the address of `s` to `t`. This does not accomplish what we are desiring. The string is not copied – only the address is. Further, notice the inclusion of `ctype.h`.
This is not an authentic copy of a string. Instead, these are two pointers pointing at the same string.

`malloc` allows the programmer to allocate a block of a specific size of memory:
```C
// Capitalizes a copy of a string

#include <cs50.h>
#include <ctype.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main(void)
{
    // Get a string
    char *s = get_string("s: ");

    // Allocate memory for another string
    char *t = malloc(strlen(s) + 1);

    // Copy string into memory, including '\0'
    for (int i = 0; i <= strlen(s); i++)
    {
        t[i] = s[i];
    }

    // Capitalize copy
    t[0] = toupper(t[0]);

    // Print strings
    printf("s: %s\n", s);
    printf("t: %s\n", t);
}
```
Notice that `malloc(strlen(s) + 1)` creates a block of memory that is the length of the string `s` plus one. This allows for the inclusion of the _null_ `\0` character in our final copied string. Then, the `for` loop walks through the string `s` and assigns each value to that same location on the string `t`.

Both `get_string` and `malloc` return `NULL`, a special value in memory, in the event that something goes wrong. You can write code that can check for this `NULL` condition as follows:
```C
// Capitalizes a copy of a string without memory errors

#include <cs50.h>
#include <ctype.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main(void)
{
    // Get a string
    char *s = get_string("s: ");
    if (s == NULL)
    {
        return 1;
    }

    // Allocate memory for another string
    char *t = malloc(strlen(s) + 1);
    if (t == NULL)
    {
        return 1;
    }

    // Copy string into memory
    strcpy(t, s);

    // Capitalize copy
    if (strlen(t) > 0)
    {
        t[0] = toupper(t[0]);
    }

    // Print strings
    printf("s: %s\n", s);
    printf("t: %s\n", t);

    // Free memory
    free(t);
    return 0;
}
```
Notice that if the string obtained is of length `0` or malloc fails, `NULL` is returned. Further, notice that `free` lets the computer know you are done with this block of memory you created via `malloc`.
`free` allows you to tell the compiler to _free up_ that block of memory you previously allocated.

##### Valgrind
_Valgrind_ is a tool that can check to see if there are memory-related issues with your programs wherein you utilized `malloc`. Specifically, it checks to see if you `free` all the memory you allocated.
If you type `make memory` followed by `valgrind ./memory`, you will get a report from valgrind that will report where memory has been lost as a result of your program.

##### Garbage Values
When you ask the compiler for a block of memory, there is no guarantee that this memory will be empty. It’s very possible that the memory you allocated was previously utilized by the computer. Accordingly, you may see _junk_ or _garbage values_. This is a result of you getting a block of memory but not initializing it.

## Swapping

```C
// Fails to swap two integers

#include <stdio.h>

void swap(int a, int b);

int main(void)
{
    int x = 1;
    int y = 2;

    printf("x is %i, y is %i\n", x, y);
    swap(x, y);
    printf("x is %i, y is %i\n", x, y);
}

void swap(int a, int b)
{
    int tmp = a;
    a = b;
    b = tmp;
}
```
Even after being sent to the `swap` function, do not swap. Why? 
When you pass values to a function, you are only providing copies. The scope of `x` and `y` is limited to the main function as the code is presently written. That is, the values of `x` and `y` created in the curly `{}` braces of the `main` function only have the scope of the `main` function. In our code above, `x` and `y` are being passed by value.
![[cs50Week4Slide163.png|1000]]
Notice that _global_ variables, which we have not used in this course, live in one place in memory. Various functions are stored in the `stack` in another area of memory.

`main` and `swap` have two separate _frames_ or areas of memory. Therefore, we cannot simply pass the values from one function to another to change them.
```C
// Swaps two integers using pointers

#include <stdio.h>

void swap(int *a, int *b);

int main(void)
{
    int x = 1;
    int y = 2;

    printf("x is %i, y is %i\n", x, y);
    swap(&x, &y);
    printf("x is %i, y is %i\n", x, y);
}

void swap(int *a, int *b)
{
    int tmp = *a;
    *a = *b;
    *b = tmp;
}
```
Notice that variables are not passed by _value_ but by _reference_. That is, the addresses of `a` and `b` are provided to the function. Therefore, the `swap` function can know where to make changes to the actual `a` and `b` from the main function.

#### Overflow

- A _heap overflow_ is when you overflow the heap, touching areas of memory you are not supposed to.
- A _stack overflow_ is when too many functions are called, overflowing the amount of memory available.
- Both of these are considered _buffer overflows_.

## scanf

We can reimplement `get_int` rather easily using `scanf` as follows:
```C
// Gets an int from user using scanf

#include <stdio.h>

int main(void)
{
    int n;
    printf("n: ");
    scanf("%i", &n);
    printf("n: %i\n", n);
}
```
Notice that the value of `n` is stored at the location of `n` in the line `scanf("%i", &n)`.

However, attempting to reimplement `get_string` is not easy. The program will not function correctly every time it is run. Nowhere in this program do we allocate the amount of memory required for our string. Indeed, we don’t know how long of a string may be inputted by the user! Further, we don’t know what garbage values may exist at the memory location.

## File I/O

* `fopen` open a file for future reading/writing
* `fclose` closes a file
Always `fclose` all the files you `fopend’ed`

`FILE *name = fopen("fileName.abc", "mode")`
There are different types of mode such as:
`r`: Reads the file
`w`: Writes in the file
`a`: Append extra into the file

After we opened a file, we can manipulate the data using:-
* `fread` reads data from a file into a buffer
* `fwrite` write data from a buffer to a file
>A buffer is a chunk of memory that can temporarily store some data from the file.
##### Syntax
`fread(Location to store blocks, Size of blocks to read (in bytes), How many blocks to read , Location to read from)`
`fwrite(Location to read from, Size of blocks to read (in bytes), How many blocks to read , Location to store)`

Example: `fwrite(&buffer, 1, 4, input);` or `fwrite(&buffer, 1, 4, output);`

```ad-Doubt
title: Why are we using buffer in the first place?
Buffer like `uint8_t buffer;` is used because file I/O in C is done in chunks, and we need a place to temporarily store data between the file and our program's memory and we can decide how much to read.
```

You can read from and manipulate files.
```C
// Saves names and numbers to a CSV file

#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    // Open CSV file
    FILE *file = fopen("phonebook.csv", "a");

    // Get name and number
    char *name = get_string("Name: ");
    char *number = get_string("Number: ");

    // Print to file
    fprintf(file, "%s,%s\n", name, number);

    // Close file
    fclose(file);
}
```
Notice that this code uses pointers to access the file. After running the above program and inputting a name and phone number, you will notice that this data persists in your CSV file.

We can implement our own copy program by typing `code cp.c` and writing code as follows:
```C
// Copies a file
    
#include <stdio.h>
#include <stdint.h>
    
typedef uint8_t BYTE;
    
int main(int argc, char *argv[])
{
    FILE *src = fopen(argv[1], "rb");
    FILE *dst = fopen(argv[2], "wb");
    
    BYTE b;
    
    while (fread(&b, sizeof(b), 1, src) != 0)
    {
        fwrite(&b, sizeof(b), 1, dst);
    }
    
    fclose(dst);
    fclose(src);
}
```
Notice that this file creates our own data type called a BYTE , which is the size of a uint8_t. Then, the file reads a `BYTE` and writes it to a file.

BMPs are also assortments of data that we can examine and manipulate. This week, you will be doing just that in your problem sets!

## Problem Set 4

1. [[Volume]]
2. 