---
follow-up:
  - "[[Sub Spaces]]"
  - "[[Linear Independence]]"
  - "[[Span]]"
---
>[!important] Definition
>Let (F,+,\*) be a field where F are called Scalers. If V is a **non-empty set** (whose elements are called **vectors**), then V is a vector space(or Linear Space) over the field F with respect to vector addition (+) and scalar multiplication (\*) if the following postulates are satisfied:
##### Additive Axioms:
$$
\begin{cases}
\text{(i)} & u, v \in V \implies u+v \in V & \text{(closure)} \\
\text{(ii)} & u+v = v+u \quad \forall u,v \in V & \text{(commutativity)} \\
\text{(iii)} & u+(v+w) = (u+v)+w \quad \forall u,v,w \in V & \text{(associativity)} \\
\text{(iv)} & \exists!  0 \in V \text{ such that } u+0 = u \quad \forall u \in V & \text{(additive identity)} \\
\text{(v)} & \forall u \in V, \exists -u \in V \text{ such that } u + (-u) = 0 & \text{(additive inverse)}
\end{cases}
$$
*This makes $(V, +)$ a **commutative group (abelian group)***.

##### Scalar Multiplication Axioms:
$$
\begin{cases}
\text{(vi)} & k \in F \land u \in V \implies k \cdot u \in V & \text{(closure)} \\
\text{(vii)} & k \cdot (u+v) = k \cdot u + k \cdot v & \forall u,v \in V,  \forall k \in F \\
\text{(viii)} & (k+m) \cdot u = k \cdot u + m \cdot u & \forall u \in V,  \forall k,m \in F \\
\text{(ix)} & k \cdot (m \cdot u) = (k \cdot m) \cdot u & \forall u \in V,  \forall k,m \in F \\
\text{(x)} & 1 \cdot u = u & \forall u \in V  \\
& \small{\text{(where $1$ is multiplicative identity in $F$)}}
\end{cases}
$$

Then $V$ is a vector space over $F$, denoted $V(F)$.

>[!example] 
Prove that $V = \{ A = [a_{ij}]_{2 \times 2} \mid a_{ij} \in \mathbb{R} \}$ over $F=\mathbb{R}$ is a vector space over $\mathbb{R}$
##### **Axiom (i): Closure under addition**  
For any $A, B \in V$:  
$$A = \begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{bmatrix}, \quad B = \begin{bmatrix} b_{11} & b_{12} \\ b_{21} & b_{22} \end{bmatrix}, \quad a_{ij}, b_{ij} \in \mathbb{R}$$  
$$A + B = \begin{bmatrix} a_{11} + b_{11} & a_{12} + b_{12} \\ a_{21} + b_{21} & a_{22} + b_{22} \end{bmatrix}$$  
Since $a_{ij} + b_{ij} \in \mathbb{R}$, $A + B \in V$.

---
##### **Axiom (ii): Commutativity of addition**  
$$A + B = \begin{bmatrix} a_{11} + b_{11} & a_{12} + b_{12} \\ a_{21} + b_{21} & a_{22} + b_{22} \end{bmatrix} = \begin{bmatrix} b_{11} + a_{11} & b_{12} + a_{12} \\ b_{21} + a_{21} & b_{22} + a_{22} \end{bmatrix} = B + A$$

---
##### **Axiom (iii): Associativity of addition**  
$$ For \space C = \begin{bmatrix} c_{11} & c_{12} \\ c_{21} & c_{22} \end{bmatrix} \in V$$
$$A + (B + C) = \begin{bmatrix} a_{11} + (b_{11} + c_{11}) & a_{12} + (b_{12} + c_{12}) \\ a_{21} + (b_{21} + c_{21}) & a_{22} + (b_{22} + c_{22}) \end{bmatrix} = \begin{bmatrix} (a_{11} + b_{11}) + c_{11} & (a_{12} + b_{12}) + c_{12} \\ (a_{21} + b_{21}) + c_{21} & (a_{22} + b_{22}) + c_{22} \end{bmatrix} = (A + B) + C$$

---
##### **Axiom (iv): Additive identity**  

Zero matrix: $O = \begin{bmatrix} 0 & 0 \\ 0 & 0 \end{bmatrix} \in V$  For any $A \in V$

---
##### **Axiom (v): Additive inverses**  

For $A \in V$, define $-A = \begin{bmatrix} -a_{11} & -a_{12} \\ -a_{21} & -a_{22} \end{bmatrix} \in V$:  $A + (-A) = \begin{bmatrix} a_{11} - a_{11} & a_{12} - a_{12} \\ a_{21} - a_{21} & a_{22} - a_{22} \end{bmatrix} = O$

---

##### **Axiom (vi): Closure under scalar multiplication**  

For $\alpha \in \mathbb{R}$, $A \in V$:  $\alpha A = \alpha \begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{bmatrix} = \begin{bmatrix} \alpha a_{11} & \alpha a_{12} \\ \alpha a_{21} & \alpha a_{22} \end{bmatrix} \in V$

---

##### **Axiom (vii): Distributivity of scalar multiplication over vector addition**

For $\alpha \in \mathbb{R}$, $A, B \in V$:  $\alpha (A + B) = \alpha \begin{bmatrix} a_{11} + b_{11} & a_{12} + b_{12} \\ a_{21} + b_{21} & a_{22} + b_{22} \end{bmatrix} = \begin{bmatrix} \alpha(a_{11} + b_{11}) & \alpha(a_{12} + b_{12}) \\ \alpha(a_{21} + b_{21}) & \alpha(a_{22} + b_{22}) \end{bmatrix} = \alpha A + \alpha B$

---

##### **Axiom (viii): Distributivity of scalar multiplication over field addition**  

For $\alpha, \beta \in \mathbb{R}$, $A \in V$:  $(\alpha + \beta) A = \begin{bmatrix} (\alpha + \beta)a_{11} & (\alpha + \beta)a_{12} \\ (\alpha + \beta)a_{21} & (\alpha + \beta)a_{22} \end{bmatrix} = \begin{bmatrix} \alpha a_{11} + \beta a_{11} & \alpha a_{12} + \beta a_{12} \\ \alpha a_{21} + \beta a_{21} & \alpha a_{22} + \beta a_{22} \end{bmatrix} = \alpha A + \beta A$

---

##### **Axiom (ix): Compatibility of scalar multiplication**  

For $\alpha, \beta \in \mathbb{R}$, $A \in V$:  $\alpha (\beta A) = \alpha \left( \beta \begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{bmatrix} \right) = \alpha \begin{bmatrix} \beta a_{11} & \beta a_{12} \\ \beta a_{21} & \beta a_{22} \end{bmatrix} = \begin{bmatrix} \alpha(\beta a_{11}) & \alpha(\beta a_{12}) \\ \alpha(\beta a_{21}) & \alpha(\beta a_{22}) \end{bmatrix} = (\alpha \beta) A$

---

##### **Axiom (x): Scalar identity**  
$$1 \cdot A = 1 \cdot \begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{bmatrix} = \begin{bmatrix} 1 \cdot a_{11} & 1 \cdot a_{12} \\ 1 \cdot a_{21} & 1 \cdot a_{22} \end{bmatrix} = A$$

---

**Conclusion**: All vector space axioms are satisfied. Thus, $V$ is a vector space over $\mathbb{R}$.

---

> [!important] Definition-2
> For the set of vectors and scalars to form a vector space, the set of vectors must be **closed under vector addition and scalar multiplication**. That is, when you multiply any two vectors in the set by real numbers and add them, the resulting vector must still be in the set i.e. $$Vector\space Space = set \space of \space vectors + set \space of \space scalers$$
> 


**In most cases we have to only check postulates (i) and (vi) i.e. closure property.**

---

### Example: $\mathbb{R}^3$


The proof is straightforward. Let  
$$
\mathbf{u} =
\begin{pmatrix}
u_1 \\
u_2 \\
u_3
\end{pmatrix}, \quad
\mathbf{v} =
\begin{pmatrix}
v_1 \\
v_2 \\
v_3
\end{pmatrix},
$$  
then 
$$
c\vec{u} = c\begin{pmatrix}
u_{1} \\
u_{2} \\
u_{3}
\end{pmatrix} =
\begin{pmatrix}
cu_{1} \\
cu_{2} \\
cu_{3}
\end{pmatrix}
$$
which is also a vector so it satisfies postulates (i).

Now their linear combination is:  
$$
a\mathbf{u} + b\mathbf{v} =
\begin{pmatrix}
au_1 + bv_1 \\
au_2 + bv_2 \\
au_3 + bv_3
\end{pmatrix},
$$which is also a vector and it satisfies postulates (vi).

Hence, *This vector space is called $\mathbb{R}^3$.*

