---
prerequisites:
  - "[[Elementary Row Transformations on Matrices]]"
follow-up:
  - "[[Gauss-Jordan Elimination]]"
---


A matrix is A said to be in <span style="color:rgb(253, 223, 126)">reduced row echelon form</span> when:
1. A is in row echelon form
2. The first non-zero entry(i.e. diagonal elements) in every row is a 1.
3. Each column containing a leading entry 1 has zero everywhere else in that column.


> [!important]
> Row echelon form is not unique but reduced row echelon form is always unique.
> If A is square invertible matrix, then $\mathrm{rref}(A)$ is the identity matrix.

##### Steps to obtain reduced row echelon form:

1. Find the first non-zero column from left say it is the $i_{th}$ column interchange rows, if necessary, to make the first entry of the column as non-zero.
2. Use elementary row operations to make all entries below this first entry equal to zero.
3. Move to the next row and column, and repeat the same process for the remaining submatrix until the matrix is in row echelon form.
4. Use the leading term (pivot element) in each of the leading columns to make all other entries of that column equal to zero (using elementary row operations), starting from the rightmost column.
5. Scale all leading (non-zero) entries to 1 by dividing or multiplying with suitable constants.

###### Example
$$
A = \begin{pmatrix}
1 & 2 & 3 & 4 \\
4 & 5 & 6 & 7 \\
6 & 7 & 8 & 9
\end{pmatrix}.
$$

Row elimination can proceed as  
$$
\begin{pmatrix}
1 & 2 & 3 & 4 \\
4 & 5 & 6 & 7 \\
6 & 7 & 8 & 9
\end{pmatrix}
\to
\begin{pmatrix}
1 & 2 & 3 & 4 \\
0 & -3 & -6 & -9 \\
0 & -5 & -10 & -15
\end{pmatrix}
\to
\begin{pmatrix}
1 & 2 & 3 & 4 \\
0 & 1 & 2 & 3 \\
0 & 1 & 2 & 3
\end{pmatrix}
\to
\begin{pmatrix}
1 & 0 & -1 & -2 \\
0 & 1 & 2 & 3 \\
0 & 0 & 0 & 0
\end{pmatrix};
$$

and we therefore have  
$$
\mathrm{rref}(A) =
\begin{pmatrix}
1 & 0 & -1 & -2 \\
0 & 1 & 2 & 3 \\
0 & 0 & 0 & 0
\end{pmatrix}.
$$

Matrix $A$ has two pivot columns, that is, two columns that contain a pivot position with a one in the reduced row echelon form.

---

##### Free Variables

In a system of linear equations, **free variables** are variables that are **not leading variables** (i.e. they **don’t correspond to a pivot column** in the matrix after row reduction or **column which doesn't have any pivot value**). These variables can take **any value**, and other variables are expressed **in terms of them**.

They appear when the system has **infinitely many solutions**.

###### When Do Free Variables Occur?

- When the system is **underdetermined** (fewer independent equations than variables).
    
- When the matrix has **non-pivot columns** (columns without a leading 1 in RREF).
    
- When the **rank** of the matrix is **less than the number of variables**.