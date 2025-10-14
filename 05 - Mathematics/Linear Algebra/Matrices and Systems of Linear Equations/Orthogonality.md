---
prerequisites: "[[Matrices]]"
---
>[!important] Definition
>**Orthogonal vectors** are **perpendicular**, i.e., the angle between them is $\frac{\pi}{2}$​ radians or **90°** and **Dot product** of orthogonal vectors is **zero**.
##### Example:
Given:

$$
\vec{a} = (4, 2, -1), \quad \vec{b} = (1, -3, -2)
$$

Then:

$$
\vec{a} \cdot \vec{b} = 4(1) + 2(-3) + (-1)(-2) = 4 - 6 + 2 = 0
$$

So, the vectors are orthogonal.

---

### 3. Vector Length and Normalization

Length of vector:

$$
\|\vec{v}\| = \sqrt{v_1^2 + v_2^2 + v_3^2}
$$

Also:

$$
\|\vec{v}\| = \sqrt{\vec{v} \cdot \vec{v}}
$$

To normalize a vector:

$$
\hat{v} = \frac{\vec{v}}{\|\vec{v}\|}
$$

Example:

$$
\|\vec{a}\| = \sqrt{4^2 + 2^2 + (-1)^2} = \sqrt{16 + 4 + 1} = \sqrt{21}
$$

$$
\|\vec{b}\| = \sqrt{1^2 + (-3)^2 + (-2)^2} = \sqrt{1 + 9 + 4} = \sqrt{14}
$$

Normalized vectors:

$$
\hat{a} = \frac{(4, 2, -1)}{\sqrt{21}}, \quad \hat{b} = \frac{(1, -3, -2)}{\sqrt{14}}
$$

---

### 4. Orthogonal Subspaces

Subspaces \( A \) and \( B \) are orthogonal if:

$$
\vec{a} \cdot \vec{b} = 0 \quad \forall \vec{a} \in A, \vec{b} \in B
$$

Example:

$$
\vec{a} = (a_1, 0, 0), \quad \vec{b} = (0, b_2, b_3)
$$

Then:

$$
\vec{a} \cdot \vec{b} = a_1 \cdot 0 + 0 \cdot b_2 + 0 \cdot b_3 = 0
$$

---

### 5. Orthogonal Matrices

A square matrix \( A \) is orthogonal if:

$$
A^T A = I
$$

This means the columns of \( A \) are orthonormal:

- Orthogonal:

$$
\vec{u}_i \cdot \vec{u}_j = 0 \quad \text{for } i \ne j
$$

- Unit vectors:

$$
\|\vec{u}_i\| = 1
$$

Also:

$$
A^{-1} = A^T
$$

---

### 6. Orthogonality of Functions

Inner product of functions \( f(x) \) and \( g(x) \) on interval \([a, b]\):

$$
\langle f, g \rangle = \int_a^b f(x)g(x)\,dx
$$

If:

$$
\langle f, g \rangle = 0
$$

Then \( f \) and \( g \) are orthogonal on \([a, b]\).

Example:

Let:

$$
f(x) = x, \quad g(x) = 1, \quad [a, b] = [-1, 1]
$$

Then:

$$
\langle f, g \rangle = \int_{-1}^{1} x\,dx = \left[ \frac{x^2}{2} \right]_{-1}^{1} = \frac{1^2}{2} - \frac{(-1)^2}{2} = 0
$$

If the interval is \([0, 1]\):

$$
\langle f, g \rangle = \int_0^1 x\,dx = \left[ \frac{x^2}{2} \right]_0^1 = \frac{1}{2} - 0 = \frac{1}{2}
$$

So not orthogonal on that interval.

---

### 7. Weighted Inner Product

Sometimes a weight function \( w(x) \) is added:

$$
\langle f, g \rangle = \int_a^b f(x)g(x)w(x)\,dx
$$
