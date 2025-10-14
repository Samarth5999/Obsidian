## Types of Searching Algorithms
#### Linear Search
Let's consider an example: There are 7 values randomly arranged in an array. The far-left position is called location 0 or the beginning of the array. The far-right position is location 7 or the end of the array.
*Now, Is the number 50 inside the array?*
An algorithm must look at each locker to be able to see if the number 50 and if its behind one of the doors, returning the value `true` or  else `false`.

Imagine the algorithm as follows:
```pseudocode
For each door from left to right or For i from 0 to n-1
    If 50 is behind door or If 50 is behind doors[i]
        Return true
Return false
```

Best Case: $O(n)$
Worst Case: $\ohm(1)$
#### Binary Search
Now assume the values within the lockers have been arranged from smallest to largest, the pseudocode for binary search would appear as follows:
```
If no doors left
    Return false
If 50 is behind middle door
    Return true
Else if 50 < middle door
    Search left half
Else if 50 > middle door
    Search right half
```

Best Case: $O(\log n)$
Worst Case: $\ohm(1)$
### Running Time
Algorithms can be designed to be more and more efficient to a limit. Here we can see n and n/2 are linear search whereas log n is binary search.
![[cs50Week3Slide010.png]]
Computer scientists discuss efficiency in terms of _the order of_ various running times. It’s the shape of the curve that shows the efficiency of an algorithm. ![[cs50Week3Slide042 2.png]]
Common running times are:
* O(n^2) <= Slowest
* O(n log n)
* O(n)
* O(log n)
* O(1) <= Fastest
Linear search was of order O(n) because it could take _n_ steps in the worst-case to run.
Binary search was of order O(log n) because it would take fewer and fewer steps to run, even in the worst-case.

Programmers are interested in both the worst-case, or _upper bound_, and the best-case, or _lower bound_.
The <math xmlns="http://www.w3.org/1998/Math/MathML">
  <mi mathvariant="normal">&#x3A9;</mi>
</math> symbol is used to denote the best-case of an algorithm, such as <math xmlns="http://www.w3.org/1998/Math/MathML">
  <mi mathvariant="normal">&#x3A9;</mi>
</math>(log n).
The <math xmlns="http://www.w3.org/1998/Math/MathML">
  <mi mathvariant="normal">&#x398;</mi>
</math> symbol is used to denote where the upper bound and lower bound are the same: Where the best-case and the worst-case running times are the same.

**_Asymptotic notation_** is the measure of how well algorithms perform as the input gets larger and larger.

### Linear Search Code
Example-1:
```C
int numbers[] = {20, 500, 10, 5, 100, 1, 50};

int n = get_int("Number: ");
for (int i = 0; i < 7; i++)
{
    if (numbers[i] == n)
    {
         printf("Found\n");
          return 0;
    }
}
printf("Not found\n");
return 1;
```
`return 0` is used to indicate success and exit the program. `return 1` is used to exist the program with an error (failure).

Example-2:
```C
string strings[] = {"battleship", "boot", "cannon", "iron", "thimble", "top hat"};

string s = get_string("String: ");
for (int i = 0; i < 6; i++)
{
    if (strcmp(strings[i], s) == 0)
    {
	    printf("Found\n");
        return 0;
    }
}
printf("Not found\n");
return 1;
```
We cannot utilize `==`. Instead, we have to use `strcmp`, which comes from the `string.h` library. `strcmp` will return `0` if the strings are the same.


> [!NOTE] What if we try to access memory beyond what we provided?
> If a part of memory was touched by the program that it should not have access to, like `i > 7` or we just wrote `string strings[];` then the program will try to access any 7 random values from the memory.

Example-3:
```C
string names[] = {"Yuliia", "David", "John"};
string numbers[] = {"+1-617-495-1000", "+1-617-495-1000", "+1-949-468-2750"};

string name = get_string("Name: ");
for (int i = 0; i < 3; i++)
{
    if (strcmp(names[i], name) == 0)
    {
        printf("Found %s\n", numbers[i]);
        return 0;
    }
}
printf("Not found\n");
return 1;
```
While this code works, there are numerous inefficiencies. Indeed, there is a chance that names and phone numbers may not correspond to one another.


## Structs
We create our own data type called a `person` that have inside of it a `name` and `number`.
```C
typedef struct
{
	string name;  // field of the struct
	string number;
} person; // name of the struct
```
We can improve our prior code by modifying our phonebook program as follows:
```C
person people[3];

people[0].name = "Yuliia";
people[0].number = "+1-617-495-1000";

people[1].name = "David";
people[1].number = "+1-617-495-1000";

people[2].name = "John";
people[2].number = "+1-949-468-2750";

// Search for name
string name = get_string("Name: ");
for (int i = 0; i < 3; i++)
{
    if (strcmp(people[i].name, name) == 0)
    {
        printf("Found %s\n", people[i].number);
        return 0;
    }
}
printf("Not found\n");
return 1;
```

# Sorting
_Sorting_ is the act of taking an unsorted list of values and transforming this list into a sorted one. When a list is sorted, searching that list is far less taxing on the computer.

### Selection Sort
Selection sort iterates through the unsorted portions of a list, selecting the smallest element each time and moving it to its correct location.
```pseudocode
For i from 0 to n–1
    Find smallest number between numbers[i] and numbers[n-1]
    Swap smallest number with numbers[i]
```
First time iterating through the list took `n - 1` steps., the second time, it took `n - 2` steps ......
Total steps = $(n - 1) + (n - 2) + (n - 3) + ... + 1 = \frac{n(n-1)}{2} = O(n^2)$

Best Case: $\ohm(n^2)$
Worst Case: $O(n^2)$ 

### Bubble Sort
_Bubble sort_ is another sorting algorithm that works by repeatedly swapping elements to “bubble” larger elements to the end.
It compares pairs of adjacent values one at a time and swaps them if they are in the incorrect order. This continues until the list is sorted.
```pseudocode
Repeat n-1 times
    For i from 0 to n–2
        If numbers[i] and numbers[i+1] out of order
            Swap them
    If no swaps
        Quit
```
Total steps = $(n-1)\times(n-2) = n^2 - 2n + 1$ = $O(n^2)$
So, in the worst-case or upper-bound, bubble sort is in the order of $O(n^2)$ and in the best-case, or lower-bound, bubble sort is also in the order of $\ohm(n  )$.

## Recursion
_Recursion_ is a concept within programming where a function calls itself.
We noticed this in [[Week-3 Algorithms#Binary Search|| Binary Search]] where we were calling `search` on smaller and smaller iterations.

We can implement pyramid building using recursion:
```C
void draw(int n)
{
    // Base Case: If nothing to draw
    if (n <= 0)
    {
        return;
    }

    // Draw pyramid of height n - 1
    draw(n - 1);

    // Draw one more row of width n
    for (int i = 0; i < n; i++)
    {
        printf("#");
    }
    printf("\n");
}
```
Notice the _base case_ will ensure the code does not run forever. The line `if (n <= 0)` terminates the recursion because the problem has been solved. Every time, `draw` calls itself, it calls itself by `n-1`. At some point, `n-1` will equal `0`, resulting in the `draw` function returning, and the program will end.

## Merge Sort
We can now leverage recursion for a more efficient sort algorithm.
Merge sort recursively divides the list into two repeatedly and then merges the smaller lists back into a larger one in the correct order.
```pseudocode
If only one number
    Quit
Else
    Sort left half of number
    Sort right half of number
    Merge sorted halves
```
Example: Consider the following list of the numbers: `6341`

**Step-1:** “Is this one number?” The answer is “no,” so the algorithm continues.

**Step-2:** Split the numbers down the middle (or as close as it can get).
`63|41`

**Step-3:** Merge sort would look at these numbers on the left and ask, “is this one number?” Since the answer is no, it would then split the numbers on the left down the middle. (This is just repeating step 1 and step 2)
`6|3`

**Step-4:** Merge sort will again ask, “is this one number?” The answer is yes. Therefore, it will quit this task and return to the last task it was running at this point.
`63|41`

**Step-5:** Merge sort will sort the numbers on the left.
`36|41`

Now we are back to Step: 2 but we have sorted left side. A similar process of steps 3-5 will occur with the right-hand numbers.
`36|14`

Both halves are now sorted. Finally, the algorithm will merge both sides. It will look at the first number on the left and the first number on the right. It will put the smaller number first, then the second smallest. The algorithm will repeat this for all numbers, resulting in:
`1346`

Merge sort is complete, and the program quits.

Merge sort is a very efficient sort algorithm with a worst-case of $O(nlogn)$. 
The best-case is still $O(nlogn)$ because the algorithm still must visit each place in the list. 
Therefore, merge sort is also $\theta(nlogn)$ since the best-case and worst-case are the same.

Best (sorted50000.txt) and Worst(reversed50000.txt) case are almost same and less than sort1 and sort2.

---
## Problem Set 3

1. [[Sort]]
2. [[Plurality]]
3. [[Runoff]]
4. [[Tideman]]