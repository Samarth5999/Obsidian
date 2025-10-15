1. Array Space
2. Size
3. Length

```cpp 
struct Array{
	int *A;
	int size;
	int length;
};

int main(){
	struct Array arr;
	
	// Size of an Array
	cin>>arr.size;
	
	// Array in Heap
	arr.A = new int[arr.size];
	
	// Length of an array
	arr.length = 0;
}
```