---
follow-up:
  - "[[Types of Matrices]]"
  - "[[Transpose of a Matrix]]"
  - "[[Inverse Matrix]]"
  - "[[Orthogonality]]"
  - "[[Rank of a Matrix]]"
---

An m-by-n matrix is a rectangular array of numbers (or other mathematical objects) with m rows and n columns.
$$ \text{A or }a_{ij} = \begin{pmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn}\end{pmatrix}$$
Here, the matrix element of A in the $ith$ row and the $jth$ column is denoted as $a_{ij}$.
Of special importance are column matrices and row matrices. These matrices are also called vectors. The column vector is in general n-by-one and the row vector is one-by-n.

## Addition of Matrices
Matrices can be added only if they have the same dimension. Addition proceeds element by element. $$\begin{pmatrix} a & b \\ c & d \end{pmatrix} + \begin{pmatrix} e & f \\ g & h \end{pmatrix}  =  \begin{pmatrix} a{+}e & b{+}f \\ c{+}g & d{+}h \end{pmatrix}  $$
## Multiplication of Matrices
#### With Scaler
The rule is to just multiply every element of the matrix. $$ k{\begin{pmatrix}a & b \\ c & d\end{pmatrix}} = {\begin{pmatrix} ka & kb \\ kc & kd
\end{pmatrix}}$$
#### With another Matrix
Can be multiplied only if the number of columns of the left matrix equals the number of rows of the right matrix i.e.  $m\times n$ can only be multiplied with $n\times p$. The resulting matrix will be $m \times p$.
$$\begin{pmatrix} a & b \\ c & d \end{pmatrix} \begin{pmatrix} e & f \\ g & h \end{pmatrix}  =  \begin{pmatrix} ae + bg & af{+}bh \\ ce{+}dg & cf{+}dh \end{pmatrix}  $$
Let A be an m-by-n matrix with matrix elements $a_{ij}$ and let B be an n-by-p matrix with matrix elements $b_{ij}$. Then C = AB is an m-by-p matrix, and its $ij$ matrix element can be written as $$c_{ij} = \sum^{n}_{k=1} a_{ik} \space b_{kj}$$