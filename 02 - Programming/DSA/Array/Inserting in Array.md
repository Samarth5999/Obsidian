## Adding or Append

```ad-Pseudocode
```pseudocode
Append(array, x)
    If array.length < array.size Then
        array.A[array.length] ← x         // Place x at the end
        array.length ← array.length + 1   // Increase length
    End If
```

---

```cpp 
void Add(struct Array *arr, ){
	if(arr->length < arr->size)
		arr->A[arr->length++] = x;
}
```

## Inserting at an Index

```ad-Pseudocode
```pseudocode
Insert(array, index, x)
    If index ≥ 0 AND index ≤ array.length Then
        For i ← array.length DownTo index + 1 Do
            array.A[i] ← array.A[i - 1]   // Shift elements right
        End For
        array.A[index] ← x               // Place new element
        array.length ← array.length + 1  // Increase length
    End If
```
---
```cpp 
void Insert(struct Array *arr, int index, int value){
	if(index >= 0 && index <= arr->length){
		for (int i = arr->length; i > index; i--){
			arr->A[i] = arr->A[i-1];
		}
		arr->A[index] = x;
		arr->length++;
	}
}
```