---
prerequisites:
  - "[[System of Linear Equations]]"
follow-up:
  - "[[Row Echelon Form]]"
  - "[[LU Decomposition]]"
---

The standard numerical algorithm used to solve a system of linear equations is called _Gaussian elimination_.

---
###### Example: - 

Consider the linear system of equations given by $$-3x_1 + 2x_2 - x_3 = -1$$ 
$$6x_1 - 6x_2 + 7x_3 = -7$$  
$$3x_1 - 4x_2 + 4x_3 = -6$$
which can be written in matrix form as $$\begin{pmatrix} -3 & 2 & -1 \\ 6 & -6 & 7 \\ 3 & -4 & 4 \end{pmatrix} \begin{pmatrix} x_1 \\ x_2 \\ x_3 \end{pmatrix} = \begin{pmatrix} -1 \\ -7 \\ -6 \end{pmatrix}$$

or symbolically as Ax = b.

We can easily solve this by Gaussian Elimination Method, We first form what is called an augmented matrix by combining the matrix A with the column vector b: $$\begin{pmatrix}  -3 & 2 & -1 & -1 \\ 6 & -6 & 7 & -7 \\ 3 & -4 & 4 & -6 \end{pmatrix}$$
Now we have to reduce the number of rows i.e. make it an upper triangular or lower triangular matrix. 

When performing Gaussian elimination, the matrix element that is used during the elimination procedure is called the **pivot**. Usually, it’s the diagonal element. Here, -3 is the first pivot so we have to make the elements below it (i.e. 6 and 3) zero by using multiple of -3, then move on to next pivot i.e. -6.

By using these operations we will get $\begin{pmatrix} -3 & 2 & -1 & -1 \\ 0 & -2 & 5 & -9 \\ 0 & 0 & -2 & 2 \end{pmatrix}$
Transformed equations can be determined from the augmented matrix as $$x_3 = -1, \quad x_2 = -\frac{1}{2}(-9 - 5x_3) = 2, \quad x_1 = -\frac{1}{3}(-1 + x_3 - 2x_2) = 2.$$

We have thus found the solution $$\begin{pmatrix} x_1 \\ x_2 \\ x_3 \end{pmatrix} = \begin{pmatrix} 2 \\ 2 \\ -1 \end{pmatrix}$$

NOTE:
Gaussian elimination in the way done here will fail if the pivot is zero. **If the pivot is zero, a row interchange must first be performed**. Even if no pivots are identically zero, small values can still result in an unstable numerical computation.
The resulting numerical technique is called **Gaussian elimination with partial pivoting**.