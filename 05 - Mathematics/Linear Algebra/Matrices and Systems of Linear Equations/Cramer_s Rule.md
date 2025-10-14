---
prerequisites:
  - "[[System of Linear Equations]]"
---

To solve  $Ax = b$, where A is an $n \times n$ matrix, X and b are $n \times 1$ vectors, the solution is given by:
$$
\alpha_i = \frac{|A_i(b)|}{|A|} = \frac{\text{det}(A_i(b))}{\text{det}(A)}
$$
where \( $A_i(b)$ is obtained by replacing the $i_{th}$ column of A with b.

**Example**
Given the system of equations:
$$
\begin{cases}
2x + y + z = 1 \\
x + 2y + z = 1 \\
x + y + 2z = 1
\end{cases}
$$

Represented in matrix form:
$$
\begin{bmatrix}
2 & 1 & 1\\
1 & 2 & 1\\
1 & 1 & 2
\end{bmatrix}
\begin{bmatrix}
x \\
y \\
z
\end{bmatrix}
=
\begin{bmatrix}
1 \\
1 \\
1 \\
\end{bmatrix}
$$

$$
x = \frac{|A_1(b)|}{|A|} = \frac{(1-i)-(2-i)+1(i-2)}{2(i-1)-1(2-i)+(i-2)} = \frac{1}{4}
$$

$$
y = \frac{|A_2(b)|}{|A|} = \frac{1}{4}
$$

$$
z = \frac{|A_3(b)|}{|A|} = \frac{1}{4}
$$

##### Disadvantages of Cramer's Rule:

1. Only provides a unique solution (does not apply for systems with infinite or no solutions).
2. Not applicable for $m \times n$ system of equation.
