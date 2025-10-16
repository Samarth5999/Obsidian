It is a type of Search method.

```ad-Pseudocode
```pseudocode
LinearSearch(array, n, key)
	FOR i ← 0 TO n - 1 DO
	        IF array[i] = key THEN
	            RETURN i
	        ENDIF
	RETURN -1
```

```cpp
int LinearSearch(struct Array arr, int key){
	int n;
	for (int i = 0; i < arr.length; i++){
		if (arr.A[i] == key)
			return i;
	}
	return -1;
}
```

### Improving Linear Search 
When you searching for a key element there is a possibility that you are searching the same element again and again.
To improve the speed of comparison we can use two methods:-

1. We can move a key element repeatedly search one step forward this method is called transposition

```cpp
if(key==arr->A[i]){
	swap(&arr->A[i],&arr->A[i-1]);
	return i;
}
```

2. We can directly swap the key element to the first element this process is called Move to Head

```cpp
if(key==arr->A[i]){
	swap(&arr->A[i],&arr->A[0]);
	return i;
}
```
