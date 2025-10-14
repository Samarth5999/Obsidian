## Compiler (clang or C)
C code can also be compiled using `clang -o hello hello.c`.

#### Compiling involves four major steps:-
##### 1. Preprocessing
It is where the header files in the code, designated by a `#` are effectively copied and pasted into the file, i.e. code contained within `stdio.h` is copied into the program.
```C
#include <cs50.h> ==> string get_string(string prompt);
#include <stdio.h> ==> int printf(string format, ...);
```

##### 2. Compiling
It is where the program is converted into assembly code.

##### 3. Assembling
It involves the compiler converting the assembly code into machine code(0s and 1s).

##### 4. Linking
Code from the included libraries is also converted into machine code and combined with the code.

---
## Debugging
Debugging is the process of locating and removing bugs from the code.

#### Rubber Duck Debugging
It is where I can talk to an inanimate object (or myself) to help think through my code and why it is not working as intended. Consider speaking out loud to, quite literally, a rubber duck about the code problem.

#### Debugger
A software tool created by programmers to help track down bugs in code.

##### How to use:
1. Click left of a line number in VS Code. A red dot appears → acts like a stop sign for the compiler.
2. Use the command `debug50 ./buggy0`
3. Code execution pauses at that line. The line where the program pauses is *highlighted in gold*.

Now we can understand the flow of code by using:
1. **Step Over**: Execute current line and move to the next.
2. **Step Into**: Dive into function calls for more detail.
3. Top-left panel to track changes in variable values.

---
## Arrays
_Arrays_ are a sequence of values of same type that are stored back to back in memory.
They are the fundamental of data structure. 
C is very lenient. It will not prevent you from going “out of bounds” of your array; but be careful!

#### Declaration: 
`type name[size];`


When declaring and initializing an array simultaneously, there is a special syntax that may be used to fill up the array with its starting values.
There is no need to put the size in this method.
```C
// instantiation syntax
bool truthtable[3] = { false, true, true };
bool truthtable[] = { false, true, true };
```

Example: `int scores[3]` is a way of telling the compiler to provide a three back-to-back places in memory of size `int`(i.e. 4 bytes) to store three `scores`. 

```C
// Averages three numbers using an array, a constant, and a helper function

#include <cs50.h>
#include <stdio.h>

// Constant
const int N = 3;

// Prototype
float average(int length, int array[]);

int main(void)
{
    // Get scores from user
    int scores[N];
    for (int i = 0; i < N; i++)
    {
        scores[i] = get_int("Score: ");
    }

    // Print average using helper function
    printf("Average: %f\n", average(N, scores));
}

// Helper function to calculate average
float average(int length, int array[])
{
    int sum = 0;
    for (int i = 0; i < length; i++)
    {
        sum += array[i];  // Add each score to sum
    }
    return sum / (float) length;  // Cast to float for decimal division
}
```
---
## String
A `string` is simply an array of variables of type `char`: an array of characters.
```C
char c1 = 'H';
	char c2 = 'I';
char c3 = '!';

printf("%c%c%c\n", c1, c2, c3);  // o/p: HI!
```

[[ASCII]] codes are printed by replacing `%c` with `%i`.
```C
char c1 = 'H';
char c2 = 'I';
char c3 = '!';

printf("%i%i%i\n", c1, c2, c3);  // o/p: 727333
```

`string` is an array of characters that begins with the first character and ends with a special character called a `NUL character`(`\0`).
![[Pasted image 20250521123308.png]]
This prints the string’s ASCII codes, including NUL.
```C
int main(void)
{
    string s = "HI!";
    printf("%i %i %i %i\n", s[0], s[1], s[2], s[3]); // 72, 73, 33, 0
}
```

Both strings are stored within a single array of type `string`.
```C
string words[2];

words[0] = "HI!";
words[1] = "BYE!";

printf("%s\n", words[0]); // HI!
printf("%s\n", words[1]); // BYE!
```


#### String Length
To calculate the length of an array, we can implement a new function called `string_length` that counts characters until NUL is located.
```C
int string_length(string s)
{
    // Count number of characters up until '\0' (aka NUL)
    int n = 0;
    while (s[n] != '\0')
    {
        n++;
    }
    return n;
}
```

We can also use `string.h` library which contains a function called `strlen`, which calculates the length of the string passed to it.

#### String Casing
To create a program that converted all lowercase characters to uppercase ones.
```C
string s = get_string("Before: ");
printf("After:  ");
for (int i = 0, n = strlen(s); i < n; i++)
{
    if (s[i] >= 'a' && s[i] <= 'z')
   {
      printf("%c", s[i] - 32);
   }
    else
    {
        printf("%c", s[i]);
   }
}
printf("\n");
```
This code _iterates_ through each value in the string. The program looks at each character and if the character is lowercase, it subtracts the value 32 from it to convert it to uppercase.

We can also use `toupper` from `ctype.h` library, which automatically knows to uppercase only lowercase characters.

---
## Command Line Arguments
Arguments that are passed to the program at the command line. Statements after `clang` are considered command line arguments.

```C
int main(int argc, string argv[])
{
    if (argc == 2)
    {
        printf("hello, %s\n", argv[1]);
    }
    else
    {
        printf("hello, world\n");
    }
}
```
`./greet Samarth` would result in the program saying `hello, Samarth`

`argc` is the number of command line arguments
`argv` is an array of the characters passed as arguments at the command line.

#### Exit Status
When a program ends, a special exit code is provided to the computer. When a program exits without error, a status code of `0` is provided to the computer and when an error occurs that results in the program ending, a status of `1` is provided by the computer.

Type `echo $?` in the terminal to see the exit status of the last run command.

---
## Cryptography
_Encryption_ is the act of hiding plain text from prying eyes. _Decrypting_, then, is the act of taking an encrypted piece of text and returning it to a human-readable form.

*Cryptography* is the art of ciphering and deciphering a message. ![[Pasted image 20250521130308.png]]
The key is a special argument passed to the cipher along with the plaintext.

---
## Problem Set 2
1. [[Scrabble]]
2. [[Readability]]
3. [[Caesar]]
4. [[Substitution]]