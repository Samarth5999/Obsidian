# &&, ||

These are exactly same as [[Bitwise Operator]] except the following differences:-

|                     &, \|                      | \|  |                        &&, \|\|                        |
| :--------------------------------------------: | :-: | :----------------------------------------------------: |
|   Both arguments should be evaluated always    | \|  |         Second argument evaluation is optional         |
|          Relative performance is low           | \|  |              Relative performance is high              |
| Applicable for both boolean and integral types | \|  | Applicable only for boolean but not for integral types |

Note: 
*  x && y => y will be evaluated iff x is true.
*  x || y => y will be evaluated iff x is false.

Example-1:

```java
int x = 10, y = 15;
if ( ++x < 10 __ ++y > 15){
	x++;
}
else{
	y++;
}
sout(x + ".." + y);
```
Instead of __ put the following:-

|     |  &  | &&  | \|  | \|\| |
| :-: | :-: | :-: | :-: | :--: |
|  x  | 11  | 11  | 12  |  12  |
|  y  | 17  | 16  | 16  |  16  |

Example-2:
```java
int x = 10;
if ( ++x < 10 && x/0 > 10){
	sout("hello");
}
else{
	sout("hi"); // hi
}
```
If we replace && with & then we will get RE: AE / by zero.