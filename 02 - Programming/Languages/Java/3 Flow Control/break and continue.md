
# break
We can *only* use `break` statement in the following places:-

1. Inside `switch` to stop fall through.
Example: [[switch()#Fall-through inside switch]]

2. Inside `loops`, to break loop execution based on some condition. Example: 
```java
for(int i = 0; i < 10; i++)
{
	if (i == 5)
	break;
	sout(i);  // o/p: 0, 1, 2, 3, 4
}
```

3. Inside `Labeled Blocks` to break block execution based on some condition. Example: 
```java
int x = 10;
l1:
{
	sout("begin");
	if (x == 10)
	break;
	sout("End");
}
sout("Hello");      // o/p: begin, hello
```

These are the only places where we can use `break` statement otherwise we will get `CE: Break outside switch or loop`.

---
# continue
We can use `continue` statement inside loops to skip current iteration and continue for the next iteration.
```java
for(int i = 0; i < 10; i++)
{
	if (i % 2 == 0)
		continue;
	sout(i);  // o/p: 1, 3, 5, 7, 9
}
```

We can use `continue` statement only inside loops if we are using anywhere else we will get `CE: continue outside of loop`.

## do-while vs continue
Example:
```java
int x = 0;
do
{
	x++;
	sout(x);
	if (++x < 5)
		continue;
	x++;
	sout(x);
} while (x++ < 10);   // o/p: 1, 4, 6, 8, 10
```

---
# Labeled break and continue
We can use labeled `break` and `continue` to break or continue a particular loop in nested loops.
```java 
l1:{
	for (....)
	{
		.....
		l2:{
			for (......)
			{
				....
				break l1;  // => breaks out of l1
			}
			}
		break l1;
		}
	}
}
```

Example:
```java
l1:
{
	for (int i = 0; i < 3; i++)
	{
		for (int j = 0; j < 3; j++)
		{
			if (i == j)
				X;
			sout("i + ".." + j);
		}
	}
}
```
Output when X =>
1. `break`: 1..0, 2..0, 2..1
2. `breakl1`: no o/p
3. `continue`: 0..1, 0..2, 1..0, 1..2, 2..0, 2..1
4. `continuel1`: 1..0, 2..0, 2..1