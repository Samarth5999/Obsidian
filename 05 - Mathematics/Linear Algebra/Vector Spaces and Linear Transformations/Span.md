---
prerequisites:
  - "[[Vector Space]]"
follow-up:
  - "[[Basis and Dimension]]"
---

> [!important] Definition
> Given a set of vectors, one can generate a **vector space** by forming all **linear combinations** of that set. The **span** of the set $\{\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n\}$ is the vector space consisting of all linear combinations of those vectors.

The span of any number of elements of vector space V is also the subspace of V in fact this is the smallest subspace of V that contains that set of elements. 

For Example:-
$$\vec{x} = \begin{bmatrix}x_{1} \\ x_{2} \\ x_{3} \end{bmatrix}, \space
\vec{y} = \begin{bmatrix}y_{1} \\ y_{2} \\y_{3} \end{bmatrix}, \space
\vec{z} = \begin{bmatrix}z_{1} \\z_{2} \\z_{3} \end{bmatrix}$$
$$span(\vec{x},\vec{y},\vec{z}) = a \begin{bmatrix}x_{1} \\ x_{2} \\ x_{3} \end{bmatrix}+ b\begin{bmatrix}y_{1} \\ y_{2} \\y_{3} \end{bmatrix}+ c \begin{bmatrix}z_{1} \\z_{2} \\z_{3} \end{bmatrix} = \begin{bmatrix}ax_{1} + by_{1} +cz_{1}\\ ax_{2} + by_{2} +cz_{2} \\ ax_{3} + by_{3} +cz_{3}\end{bmatrix}$$


---

### Example

Consider the set:
$$
\left\{
\begin{pmatrix}
1 \\
0 \\
0
\end{pmatrix},
\begin{pmatrix}
0 \\
1 \\
0
\end{pmatrix},
\begin{pmatrix}
2 \\
3 \\
0
\end{pmatrix}
\right\}
$$

This set spans the vector space of all $3 \times 1$ matrices with a **zero in the third row**, i.e., vectors of the form:
$$
\begin{pmatrix}
a \\
b \\
0
\end{pmatrix}
$$

This is a **subspace** of $\mathbb{R}^3$.

---
