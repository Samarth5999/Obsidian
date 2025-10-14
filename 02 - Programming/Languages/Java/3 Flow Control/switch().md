## Syntax
```java
switch(x)
{
	case 1: Action-1;
			break;
			
	case 2: Action-2;
			break;
		.
		.
		.
	case n: Action-n;
			break;
			
	default: default-action
}
```

## Important Points

1. The allowed argument types for the switch statement are `byte`, `short`, `char` and `int` until 1.4v but from 1.5v onwards corresponding wrapper class and `enum` type also allowed. From 1.7v onwards `string` type also allowed.
2. Curly braces are mandatory except switch everywhere curly braces are optional.
3. Inside switch every statement should under some case or default i.e. independent statements are not allowed inside a switch otherwise we will get CE.
4. Every case label should be compile time constant(i.e. constant expression).
```java
int x = 10;
int y = 20;
switch(x){
	case 10: sout("hi");
			break;
			
	case y: sout("hello"); // CE: constant expression required
			break;
}
```
* If we declare y as final then we won't get CE

5. Both switch argument and case label can be expression but case label should be constant expression.
```java
int x = 10;
switch(x+1){
	case 10: sout(10);
			break;	
	case 10+20+30: sout(60); 
			break;
}
```

6. Every case label should be in the range of switch argument type otherwise we will get CE.
```java
byte b = 10;
switch(b){
	case 10: sout(10);
			break;	
	case 1000: sout(1000); // CE: PLP
}
```
If it was `switch(b+1)` then its valid.

7. Duplicate case label are not allowed otherwise we will get CE.
```java
int x = 10;
switch(x){
	case 97: sout(97);
			break;	
	case 'a': sout('a'); // CE: Duplicate case label
}
```

### Case label
1. It should be constant expression.
2. The value should be in the range of switch argument type.
3. Duplicate case label are not allowed.

## Fall-through inside switch
Within the switch if any case is matched, from that case onwards all statements will be executed until break or end of the switch this is called <span style="color:rgb(222, 217, 74)">fall-through inside switch</span>.
The main advantage of this is we can define common action for multiple cases(code reusability).
```java
switch(x)
{
	case 1:
	case 2: 
	case 3:
			sout("Q-4"); 
			break;
	case 4:
	case 5: 
	case 6:
			sout("Q-1");
			break;
}
```
Example-1:
```java
switch(x)
{
	case 0: sout(0); // x = 0 o/p: 0,1
	case 1: sout(1); // x = 1 o/p: 1
			break;
	case 2: sout(2); // x = 2 o/p: 2, def
	default: sout("def"); // x = 3 o/p: def
}
```

## Default Case
1. Within the switch we can take default case at most ones.
2. Default case will be executed if and only if there is no case matched.
3. Within the switch we can write default case anywhere but it is recommended to write as last case.
```java
```java
switch(x)
{
	default: sout("def"); // x = 3 o/p: def, 0
	case 0: sout(0); // x = 0 o/p: 0
			break; 
	case 1: sout(1); // x = 1 o/p: 1, 2
	case 2: sout(2); // x = 2 o/p: 2
}
```
