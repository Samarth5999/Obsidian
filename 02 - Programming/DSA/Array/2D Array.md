There are 3 methods of declaring 2D Arrays:- 

###### 1. Normal Declaration

Memory will be created like a single dimension array, but compiler will allow us to access that array as a 2D arrays with rows and columns. We can directly mention the array list and initialize it. It is partial in stack.
```cpp 
int A[3][4] = { {1,2,3,4} , {2,4,6,8} , {3,5,7,9} };
```

###### 2. Array of Pointers

The pointer will be created inside heap memory and through that we can access, initialize and declare all the elements inside the array. This is array of integer pointer. It is partial in Heap.
```cpp 
int *A[3];
A[0] = new int[4];
A[1] = new int[4];
A[2] = new int[4];
```
###### 3. Double Pointer

Everything is created inside the heap pointer, here the pointer will be like a variable there is no new operator so it is created inside stack in the memory.
```cpp 
int **A;
A = new int * [3]
A[0] = new int[ 4 ] ;
A[1] = new int[ 4 ] ;
A[3] = new int[ 4 ] ;
```