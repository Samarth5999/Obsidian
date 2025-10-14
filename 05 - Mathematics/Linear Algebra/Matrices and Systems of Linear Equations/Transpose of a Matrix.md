---
prerequisites: "[[Matrices]]"
---
The transpose of a matrix is a new matrix formed by interchanging its rows and columns.

The transpose of a matrix A, denoted by $A^T$ and spoken as A-transpose, switches the rows and columns of A.$$(a_{ij})^T=a_{ji}$$
* $(A^T)^T=A$
* $(A+B)^T=A^T +B^T$
* $(AB)^T=B^TA^T$


### Symmetric Matrix
If A is a square matrix, and $A^T$ = A, then we say that A is symmetric.$$ \begin{pmatrix}a&b&c\\ b&d&e\\c&e&f\end{pmatrix}$$Number of independent elements are 6.

### Skew Symmetric Matrix
If A is a square matrix, and $A^T$ = −A, then we say that A is skew symmetric.$$ \begin{pmatrix}0&b&c\\ -b&0&e\\ -c&-e&0\end{pmatrix}$$Number of independent elements are 3 and diagonal elements are zero.



## Inner and Outer Products

The inner product (or dot product or scalar product) between two vectors is obtained from the matrix product of a row vector times a column vector. A row vector can be obtained from a column vector by the transpose operator.
$$\mathbf{u}^\mathrm{T} \mathbf{v} = \begin{pmatrix} u_1 & u_2 & u_3 \end{pmatrix} \begin{pmatrix} v_1 \\ v_2 \\ v_3 \end{pmatrix} = u_1v_1 + u_2v_2 + u_3v_3$$
If the inner product between two nonzero vectors is zero, we say that the vectors are orthogonal.

The norm of a vector is defined by $$\|\mathbf{u}\| = \left( \mathbf{u}^\mathrm{T} \mathbf{u} \right)^{1/2} = \left( u_1^2 + u_2^2 + u_3^2 \right)^{1/2}$$
**If the norm of a vector is equal to one, we say that the vector is normalized.**
**If a set of vectors are mutually orthogonal and normalized, we say that these vectors are orthonormal.**


An outer product is also defined, and is used in some applications. The outer product between u and v is given by $$\begin{pmatrix} u_1 \\ u_2 \\ u_3 \end{pmatrix} \begin{pmatrix} v_1 & v_2 & v_3 \end{pmatrix} = \begin{pmatrix} u_1v_1 & u_1v_2 & u_1v_3 \\ u_2v_1 & u_2v_2 & u_2v_3 \\ u_3v_1 & u_3v_2 & u_3v_3 \end{pmatrix}$$
