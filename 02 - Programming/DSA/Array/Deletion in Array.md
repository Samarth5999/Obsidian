```ad-Pseudocode
```pseudocode
Delete(array, index)
    Declare x ← 0

    If index ≥ 0 AND index < array.length Then
        x ← array.A[index]                     // Store element to be deleted

        For i ← index To array.length - 2 Do   // Shift elements left
            array.A[i] ← array.A[i + 1]
        End For

        array.length ← array.length - 1        // Decrease length
        Return x                               // Return deleted value
    End If

    Return 0                                  // Invalid index case
```
---
```cpp
int Delete(struct Array *arr,int index){
	int x=0;
	int i;
	if(index>=0 && index<arr->length){
		x=arr->A[index];
		for(i=index;i<arr->length-1;i++)
			arr->A[i]=arr->A[i+1];
		arr->length--;
		return x;
	}
	return 0;
}
```