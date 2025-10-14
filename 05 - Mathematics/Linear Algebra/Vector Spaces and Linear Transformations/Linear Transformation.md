
>[!important] Definition
>Let $V(F)$ and $U(F)$ are two vector spaces over the same field $F$. Then a map: 
>$$T : V(F) \longrightarrow U(F)$$
>is called a Linear Transformation if 
>$$\begin{cases}
(i) T(\alpha x) = \alpha T(x) \\
(ii) T(x + y) = T(x) + T(y) \\
\end{cases}$$
$$or$$
$${T(\alpha x + \beta y)} = \alpha T(x) + \beta T(y)$$
where 
$x, y \in V$,
$\alpha, \beta \in F$


#### Represent linear transformations as Matrices

$$T : \mathbb{R}^n \longrightarrow \mathbb{R}^m$$

We can represent this as $T(\vec{v}) = A\vec{v}$ where A is an $m\times n$ matrix
To get A we transform the standard basis of $\mathbb{R}^n$

Example:

>[!question] $T : \mathbb{R}^2 \longrightarrow \mathbb{R}^3$ and $T(\vec{v}) = \begin{bmatrix}v_{2} \\v_{1} + v_{2}\\v_{1}-v_{2}\end{bmatrix}$

$$\text{Standard Basis of } \mathbb{R}^2 = \begin{bmatrix}1 \\ 0\end{bmatrix} \begin{bmatrix}0 \\ 1\end{bmatrix}$$
Now, $$L\begin{bmatrix}1 \\ 0\end{bmatrix} = \begin{bmatrix}0 \\ 1 \\ 1\end{bmatrix}$$
and $$L\begin{bmatrix}0 \\ 1\end{bmatrix} = \begin{bmatrix}1 \\ 1 \\ -1\end{bmatrix}$$
This two give us the the columns for a matrix A i.e.
$$A = \begin{bmatrix}0 & 1\\ 1 & 1\\ 1& -1\end{bmatrix}$$
We can verify this by putting it in the equation

$$T(\vec{v}) = A\vec{v} =\begin{bmatrix} 0 & 1 \\ 1 & 1 \\ 1 & -1 \end{bmatrix} \begin{bmatrix} V_1 \\ V_2 \end{bmatrix} = \begin{bmatrix} 0V_1 + 1V_2 \\ 1V_1 + 1V_2 \\ 1V_1 - 1V_2 \end{bmatrix} = \begin{bmatrix} V_2 \\ V_1+V_2 \\ V_1-V_2 \end{bmatrix}$$

>[!important] Note 
>Every Linear Transformation maps zero vector into a zero vector i.e.
>$T: V \longrightarrow U$ then $T(0) = 0$
>Useful to disprove Linear Transformation

