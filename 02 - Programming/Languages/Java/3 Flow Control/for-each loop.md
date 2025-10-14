Introduced in 1.5v, it is specially designed to retrieve elements of arrays and collections. It is also known as enhanced for-loop.

Example-1: To print elements of 1D array 
```java
int[] x = {10,20,30};

// Normal for-loop
for(int i = 0; i < x.length; i++)
{
	sout(x[i]);
}

// Enhanced for-loop
for(int x1: x)
{
	sout(x);
}
```

Example-2: To print elements of 2D array 
```java
int[][] x = {{10,20,30},{40,50}};

// Normal for-loop
for(int i = 0; i < x.length; i++)
{
	for(int j = 0; j < x[i].length; j++)
	{
		sout(x[i][j]);
	}
}

// Enhanced for-loop
for(int[] x1: x)
{
	for(int x2: x1)
	{
		sout(x2);
	}
}
```

Example-3: To print elements of 3D array

```java
for(int[][] x1: x)
{
	for(int[] x2: x1)
	{
		for(int x3: x2)
		{
		sout(x3);
		}
	}
}
```

> [!NOTE]
> 1. for-each loop is the best choice to retrieve elements of arrays and collections but its limitation is it is applicable only for arrays and collections and it is not a general purpose rule.
> 2. By using normal for loop, we can print array elements either in original or reverse order but by using for-each loop we can print array elements only in original order.

## Iterable
```java
for (each x: target)
{
	----
}
```
The `target` element in for-each loop should be Iterable Object.

An object is said to be Iterable if and only if corresponding class implements `java.lang.Iterable(I)`. Iterable Interface introduced in 1.5v and it contains only one method `iterator`. `public Iterator iterator()`
All arrays related classes and collection implemented classes already implement Iterable Interface. Being a programmer we are not required to do anything, just we should aware the point.

### Difference b/w Iterable and Iterator

|                                  Iterator                                   |                        Iterable                        |
| :-------------------------------------------------------------------------: | :----------------------------------------------------: |
|                        It is related to collections                         |             It is related to for-each loop             |
|          We can use to retrieve elements of collections one by one          | The target element in for-each loop should be Iterable |
|                       Present in `java.util` package                        |             Present in `java.lang` package             |
| It contains 3 method:<br>1. `hasNext()`<br>2. `next()`    <br>3. `remove()` |       <br>It contains 1 method:<br>`iterator()`        |

