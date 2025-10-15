```ad-Definition
Array is a collection of similar data types grouped under one name. Its alse called vector value.
```

We can access or differentiate all the elements in an array using index values.

##### Ways of Declaring and initialization of array 
```cpp 
int A[5]; // Garbage Values
int B[5] = {1, 2, 3, 4, 5}; // 1 2 3 4 5
int C[5] = {1, 2}; // 1 2 0 0 0
int D[]={1, 2, 3, 4, 5}; // 1 2 3 4 5 
```

##### Ways of accessing elements inside an array 
```cpp 
for (int i = 0; i < 5; i++) {  
    cout << A[i] << endl;   
}
cout << A[2] << endl;  
cout << 2[A] << endl;  
cout << *(A+2) << endl; 
```

##### We can also get the address of the array elements
```cpp 
int A[5] = {1, 2, 3, 4, 5};  
for (int i = 0; i < 5; i++) {  
    cout << &A[i] << endl;  
    // 0x7ffc92f56f70, 0x7ffc92f56f74, 0x7ffc92f56f78 ....
}
```
