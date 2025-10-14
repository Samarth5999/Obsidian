---
prerequisites:
  - "[[Span]]"
  - "[[Linear Independence]]"
---
>[!important] Definition
>A set $S = x_{1},x_{2},\dots x_{n}$ of vectors is said to form a basis of V is each element $v \in V$ can be written as linear combination of the vector of S, where S should be linearly independent.
>$$OR$$
>A set $S = x_{1},x_{2},\dots x_{n}$ of vector forms a basis of V if it satisfies following 2 properties
>(i) S is Linearly Independent
>(ii) L(S) = V i.e. span(S) = V

**Basis is the smallest Linear Independent set that spans V**

---
##### Checking for Basis

Step-1: Check for Linear Independence
Step-2: Check if span(S) = V i.e. Verify that the number of vectors equals the dimension of V, and the set spans the space (i.e., any vector in V can be formed from them).

---
##### Finding Basis

Step-1: Start with a spanning set or the entire space V.
Step-2: Reduce it to a minimal linearly independent set.

---
###### Standard Basis

Standard Basis for a vector space is a set of vectors that are fundamental in describing the space.

For Example:- 
$$\begin{pmatrix}1 \\0 \\0\end{pmatrix},\begin{pmatrix}
 0\\1 \\0\end{pmatrix}$$
 is the standard basis of $\mathbb{R}^2$

---
>[!question] Extend $S = \{(2, 3, 7), (1, 5, 3)\}$ to form a basis of $\mathbb{R}^3$?

Start with including standard basis in S 
$$ S_{new} = 
\begin{bmatrix}
2 & 3 & 7 \\
1 & 5 & 3 \\
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$
Now,
1. Keep the first two rows unchanged.
2. Make two rows as zero rows and rest 3 should be linearly independent.

$$\text{Basis of S in }\mathbb{R}^3 = \{(2,3,7), (1,5,3),(0,-5,-3)\}$$

---

### Dimension

> [!important] Definition
> The number of vectors or elements in a basis set is the **dimension** of the vector space.

In this example, the dimension is:
$$
\dim = 2
$$
because we only need **two** independent vectors to span all 3-by-1 vectors with zero in the third row.

##### Important Points
1. Every Linearly Independent Set Can Be Extended to a Basis
2. If $dim(V)=n$, then any set of $n+1$ vectors in V must be linearly dependent.
3. Any two distinct bases of a vector space V will have the same number of elements.
4. Any set containing '0' vector is always linearly dependent.
5. If $U_1 \cup U_2$ are two subspaces of $U$ then
	1. $dim (U_1 + U_2) = \dim (U_1) + \dim (U_2) - \dim (U_1 \cap U_2)$.
	2. $U_1 + U_2$ is always a subspace $U$.
	3. $U_1 \cap U_2$ is always a subspace $U$.
	4. $U_1 \cup U_2$ may or may not be a subspace $U$.
6. If V is a vector space with dimension n, then any set of n linear independent vectors of V will form a basis of V.