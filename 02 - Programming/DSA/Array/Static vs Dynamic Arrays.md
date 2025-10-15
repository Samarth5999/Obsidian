
Static array means the size of the array is static i.e fixed whereas Dynamic array means the size of the array is dynamic i.e flexible.

When an array is created it is created inside Stack memory and the size of the array is decided during compile time only.
When declaring an array it must be a static value only and not
variable type in c language however in c++ dynamic allocation is
possible during compile time.

```cpp
// Stack memory 
int A[5];

// Heap memory
int *p; 

p = new int[5]; // C++
delete[] p;

p = (int *) malloc(sizeof(int)); // C
free(p);
```

```ad-question
title: How to Increase size of an array?

```cpp
int *p = new int[5];
int *q = new int[10];

for (int i = 0; i < 5; i++)
	q[i] = p[i];

delete[] p;
p = q;
q = NULL;
```
