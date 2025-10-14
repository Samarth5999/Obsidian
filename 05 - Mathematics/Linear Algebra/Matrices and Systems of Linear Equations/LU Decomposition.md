The row reduction algorithm of Gaussian elimination can be implemented by multiplying elementary matrices. Here, we show how to construct these elementary matrices, which differ from the identity matrix by a single elementary row operation.

Consider the first row reduction step for the following matrix $A$:  
$$
A = \begin{pmatrix}
-3 & 2 & -1 \\
6 & -6 & 7 \\
3 & -4 & 4
\end{pmatrix}
\rightarrow
\begin{pmatrix}
-3 & 2 & -1 \\
0 & -2 & 5 \\
3 & -4 & 4
\end{pmatrix}
= M_1 A,
$$  
where  
$$
M_1 = \begin{pmatrix}
1 & 0 & 0 \\
2 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}.
$$  
To construct the elementary matrix $M_1$, the number $2$ is placed in column-one, row-two. This matrix multiplies the first row by $2$ and adds the result to the second row.
The next step in row elimination is  
$$
\begin{pmatrix}
-3 & 2 & -1 \\
0 & -2 & 5 \\
3 & -4 & 4
\end{pmatrix}
\rightarrow
\begin{pmatrix}
-3 & 2 & -1 \\
0 & -2 & 5 \\
0 & -2 & 3
\end{pmatrix}
= M_2 M_1 A,
$$  
where  
$$
M_2 = \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
1 & 0 & 1
\end{pmatrix}.
$$  
Here, to construct $M_2$, the number $1$ is placed in column-one, row-three, and the matrix multiplies the first row by $1$ and adds the result to the third row.

The last step in row elimination is  
$$
\begin{pmatrix}
-3 & 2 & -1 \\
0 & -2 & 5 \\
0 & -2 & 3
\end{pmatrix}
\rightarrow
\begin{pmatrix}
-3 & 2 & -1 \\
0 & -2 & 5 \\
0 & 0 & -2
\end{pmatrix}
= M_3 M_2 M_1 A,
$$  
where  
$$
M_3 = \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & -1 & 1
\end{pmatrix}.
$$  
Here, to construct $M_3$, the number $-1$ is placed in column-two, row-three, and this matrix multiplies the second row by $-1$ and adds the result to the third row.
We have thus found that  
$$
M_3 M_2 M_1 A = U,
$$  
where $U$ is an upper triangular matrix.

Upon inverting the elementary matrices, we have  
$$
A = M_1^{-1} M_2^{-1} M_3^{-1} U.
$$

Now, the matrix $M_1$ multiplies the first row by $2$ and adds it to the second row.  
To invert this operation, we simply need to multiply the first row by $-2$ and add it to the second row, so that  
$$
M_1 = \begin{pmatrix}
1 & 0 & 0 \\
2 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}, \quad
M_1^{-1} = \begin{pmatrix}
1 & 0 & 0 \\
-2 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}.
$$

Similarly, **Just invert the sign of non-diagonal elements in $M_{n}$ to get $M_{n}^{-1}$**
$$
M_2 = \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
1 & 0 & 1
\end{pmatrix}, \quad
M_2^{-1} = \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
-1 & 0 & 1
\end{pmatrix}; \quad
M_3 = \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & -1 & 1
\end{pmatrix}, \quad
M_3^{-1} = \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 1 & 1
\end{pmatrix}.
$$

*When computing the final lower triangular matrix $L=M_{1}^{-1}+M_{2}^{-1}+M_{3}^{-1}$​, these off-diagonal values accumulate in the same positions where the row eliminations occurred*.
Therefore, 
$$
L = M_1^{-1} M_2^{-1} M_3^{-1}
$$  
is given by  
$$
L =
\begin{pmatrix}
1 & 0 & 0 \\
-2 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
-1 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 1 & 1
\end{pmatrix}
=
\begin{pmatrix}
1 & 0 & 0 \\
-2 & 1 & 0 \\
-1 & 1 & 1
\end{pmatrix},
$$  
which is lower triangular.

Also, the non-diagonal elements of the elementary inverse matrices are simply combined to form $L$.  
Our LU decomposition of $A$ is therefore:  
$$
\begin{pmatrix}
-3 & 2 & -1 \\
6 & -6 & 7 \\
3 & -4 & 4
\end{pmatrix}
=
\begin{pmatrix}
1 & 0 & 0 \\
-2 & 1 & 0 \\
-1 & 1 & 1
\end{pmatrix}
\begin{pmatrix}
-3 & 2 & -1 \\
0 & -2 & 5 \\
0 & 0 & -2
\end{pmatrix}
$$

i.e. $$ A = LU$$

## How to find LU decomposition of a Matrix?
##### Step-1: **Perform Gaussian elimination** on A to reduce it to an upper triangular matrix U.
##### Step-2: At each elimination step, create an elementary matrix $M_{i}$ that performs the row operation i.e. replace the value that becomes $0$ in A with the multiple.

##### Step-3: Therefore, $U = M_3 M_2 M_1 A$

##### Step-4: Now, invert the sign of non-diagonal elements in $M_{n}$ to get $M_{n}^{-1}$

##### Step-5: Therefore, $L = M_1^{-1} M_2^{-1} M_3^{-1}$ . Now compute L where these off-diagonal values accumulate in the same positions where the row eliminations occurred.

##### Step-5: Now , $$A = M_1^{-1} M_2^{-1} M_3^{-1} U$$
and $$ A = LU$$

# Application of LU
The LU decomposition is useful when one needs to solve $Ax = b$ for many right-hand sides. With the LU decomposition in hand, one writes:  
$$
(LU)x = L(Ux) = b,
$$  
and lets $y = Ux$. Then we solve $Ly = b$ for $y$ by **forward substitution**, starting from the first equation and working forward to complete the solution, and then solve $Ux = y$ for $x$ by **backward substitution**.

It is possible to show that for large matrices, solving $(LU)x = b$ is substantially faster than solving $Ax = b$ directly.

---

### Example

We now illustrate the solution of $LUx = b$, with:

$$
L =
\begin{pmatrix}
1 & 0 & 0 \\
-2 & 1 & 0 \\
-1 & 1 & 1
\end{pmatrix}, \quad
U =
\begin{pmatrix}
-3 & 2 & -1 \\
0 & -2 & 5 \\
0 & 0 & -2
\end{pmatrix}, \quad
b =
\begin{pmatrix}
-1 \\
-7 \\
-6
\end{pmatrix}.
$$

With $y = Ux$, we first solve $Ly = b$, that is:
$$
\begin{pmatrix}
1 & 0 & 0 \\
-2 & 1 & 0 \\
-1 & 1 & 1
\end{pmatrix}
\begin{pmatrix}
y_1 \\
y_2 \\
y_3
\end{pmatrix}
=
\begin{pmatrix}
-1 \\
-7 \\
-6
\end{pmatrix}.
$$

Using **forward substitution**:
- $y_1 = -1$
- $y_2 = -7 + 2y_1 = -7 + 2(-1) = -9$
- $y_3 = -6 + y_1 - y_2 = -6 + (-1) - (-9) = 2$

---

Now we solve $Ux = y$, that is:
$$
\begin{pmatrix}
-3 & 2 & -1 \\
0 & -2 & 5 \\
0 & 0 & -2
\end{pmatrix}
\begin{pmatrix}
x_1 \\
x_2 \\
x_3
\end{pmatrix}
=
\begin{pmatrix}
-1 \\
-9 \\
2
\end{pmatrix}.
$$

Using **back substitution**:
- $x_3 = \dfrac{2}{-2} = -1$
- $x_2 = \dfrac{-9 - 5x_3}{-2} = \dfrac{-9 - 5(-1)}{-2} = \dfrac{-4}{-2} = 2$
- $x_1 = \dfrac{-1 - 2x_2 + x_3}{-3} = \dfrac{-1 - 2(2) + (-1)}{-3} = \dfrac{-6}{-3} = 2$

### Final Answer
$$
\begin{pmatrix}x_1 \\ x_2 \\ x_3\end{pmatrix} = \begin{pmatrix}2 \\ 2 \\ -1\end{pmatrix}
$$
