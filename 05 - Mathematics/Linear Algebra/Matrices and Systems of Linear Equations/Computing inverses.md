By bringing an invertible matrix to reduced row echelon form, that is, to the identity matrix, we can compute the matrix inverse. Given a matrix $A$, consider the equation  $A A^{-1} = I,$

For the unknown inverse $A^{-1}$. Let the columns of $A^{-1}$ be given by the vectors $a_1^{-1}, a_2^{-1}$, and so on. And let the columns of the identity matrix $I$ be given by $e_1, e_2$, and so on. The matrix $A$ multiplying the $i-th$ column of $A^{-1}$ is the equation  
$$
A a_i^{-1} = e_i,
$$  
where $e_i$ is the $i-th$ column of the identity matrix.

This equation for the unknown columns of $A^{-1}$ suggests that we can perform row reduction on an augmented matrix which attaches the $n \times n$ identity matrix to the $n \times n$ matrix $A$.  
To find $A^{-1}$, elimination is continued until one obtains $\mathrm{rref}(A) = I$.  
$$
\begin{pmatrix}
-3 & 2 & -1 & 1 & 0 & 0 \\
6 & -6 & 7 & 0 & 1 & 0 \\
3 & -4 & 4 & 0 & 0 & 1
\end{pmatrix}
\to
\begin{pmatrix}
-3 & 2 & -1 & 1 & 0 & 0 \\
0 & -2 & 5 & 2 & 1 & 0 \\
0 & -2 & 3 & 1 & 0 & 1
\end{pmatrix}
\to
\begin{pmatrix}
-3 & 2 & -1 & 1 & 0 & 0 \\
0 & -2 & 5 & 2 & 1 & 0 \\
0 & 0 & -2 & -1 & -1 & 1
\end{pmatrix}
\to
\begin{pmatrix}
-3 & 0 & 4 & 3 & 1 & 0 \\
0 & -2 & 5 & 2 & 1 & 0 \\
0 & 0 & -2 & -1 & -1 & 1
\end{pmatrix}
\to
\begin{pmatrix}
-3 & 0 & 0 & 1 & -1 & 2 \\
0 & -2 & 0 & -\frac{1}{2} & -\frac{3}{2} & \frac{5}{2} \\
0 & 0 & -2 & -1 & -1 & 1
\end{pmatrix}
\to
\begin{pmatrix}
1 & 0 & 0 & -\frac{1}{3} & \frac{1}{3} & -\frac{2}{3} \\
0 & 1 & 0 & \frac{1}{4} & \frac{3}{4} & -\frac{5}{4} \\
0 & 0 & 1 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2}
\end{pmatrix}.
$$

And one can check that  
$$
\begin{pmatrix}
-3 & 2 & -1 \\
6 & -6 & 7 \\
3 & -4 & 4
\end{pmatrix}
\begin{pmatrix}
-\frac{1}{3} & \frac{1}{3} & -\frac{2}{3} \\
\frac{1}{4} & \frac{3}{4} & -\frac{5}{4} \\
\frac{1}{2} & \frac{1}{2} & -\frac{1}{2}
\end{pmatrix}
=
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}.
$$
