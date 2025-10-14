---
prerequisites: "[[Matrices]]"
follow-up:
  - "[[Computing inverses]]"
---

When a matrix A has an inverse, we say it is invertible and denote its inverse by $A^{−1}$. 
* $AA^{-1} = A^{-1}A = I$
* $(AB)^{-1} = B^{-1}A^{-1}$
* $(A^\mathrm{T})^{-1} = (A^{-1})^\mathrm{T}$

##### Inverse of a 2x2 Matrix
Let Inverse of a 2x2 matrix be $\begin{pmatrix} x_1 & x_2 \\ y_1 & y_2 \end{pmatrix}$. So we can write it as:

$$\begin{pmatrix} a & b \\ c & d \end{pmatrix} \begin{pmatrix} x_1 & x_2 \\ y_1 & y_2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$$


Trying to solve this equation we will get two inhomogeneous and two homogeneous linear equations:
$$ax_1 + by_1 = 1,\quad cx_1 + dy_1 = 0,\quad cx_2 + dy_2 = 1,\quad ax_2 + by_2 = 0$$

The solution for the inverse matrix is found to be:
$$\begin{pmatrix} a & b \\ c & d \end{pmatrix}^{-1}= \frac{1}{ad - bc}\begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$$


The term $ad − bc$ is just the definition of the determinant of the two-by-two matrix: $$\det\begin{pmatrix} a & b \\ c & d \end{pmatrix} = ad - bc$$A is invertible only if det $A \neq 0.$

