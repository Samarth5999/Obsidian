# Operator Precedence
### 1. Unary Operators: `[], x++, x--, ++x, --x, ~, !, new, <type>`
### 2. Arithmetic Operators: `*, /, %, +, -`
### 3. Shift Operators: `>>, >>>, <<`
### 4. Comparison Operators: `<, <=, >, >=, instanceof`
### 5. Equality Operators: `==, !=`
### 6. Bitwise Operators: `&, ^, |`
### 7. Short Circuit Operators: `&&, ||`
## 8. Conditional Operator: `?:`
### 9. Assignment Operators: `=, +=, -=, *=,....`
---

# Evaluation Order of Operand
In Java, we have only operator precedence but not operand precedence before applying any operator, all operands will be evaluated from left to right.
```java
class Test{
public static void main(String[] args){
		sout(m1(1) + m1(2) * m1(3) / m1(4) + m1(5) * m1(6));
	}
	public static int m1(int i){                                   // o/p: 1, 2, 3, 4, 5, 6, 32
		sout(i);
		return i;
	}
}
```
