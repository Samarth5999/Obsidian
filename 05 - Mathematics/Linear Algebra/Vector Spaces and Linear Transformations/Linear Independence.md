---
prerequisites:
  - "[[Reduced Row Echelon Form]]"
  - "[[Vector Space]]"
follow-up:
  - "[[Basis and Dimension]]"
---

The vectors $\{\mathbf{u}_1, \mathbf{u}_2, \ldots, \mathbf{u}_n\}$ are **linearly independent** if, for any scalars $c_1, c_2, \ldots, c_n$, the equation  
$$
c_1\mathbf{u}_1 + c_2\mathbf{u}_2 + \cdots + c_n\mathbf{u}_n = 0
$$  
has only the **trivial solution**:  
$$
c_1 = c_2 = \cdots = c_n = 0.
$$

This means **none** of the vectors $\mathbf{u}_1, \mathbf{u}_2, \ldots, \mathbf{u}_n$ can be written as a **linear combination** of the others.

If scalars are non-zero then the elements are linearly dependent.

---

### Example 1: Linearly Dependent Vectors

Let the vectors be:
$$
\mathbf{u} = 
\begin{bmatrix}
1 \\
0 \\
0
\end{bmatrix}, \quad
\mathbf{v} = 
\begin{bmatrix}
0 \\
1 \\
0
\end{bmatrix}, \quad
\mathbf{w} = 
\begin{bmatrix}
2 \\
3 \\
0
\end{bmatrix}.
$$

These vectors are **linearly dependent**, because:  
$$
\mathbf{w} = 2\mathbf{u} + 3\mathbf{v}.
$$
We can solve this by assuming three constants$$ c_{1}u + c_{2}v + c_{3}w = 0 $$
By solving we get two equations $$c_{1}+2c_{3}=0$$$$c_{2} + 3c_{3}= 0$$

> [!tip] 
> If all zero -> Linearly Independent
> If some zero -> Linearly Dependent

---

### Example 2: Linearly Independent Vectors

Let the vectors be:
$$
\mathbf{u} = 
\begin{bmatrix}
1 \\
0 \\
0
\end{bmatrix}, \quad
\mathbf{v} = 
\begin{bmatrix}
0 \\
1 \\
0
\end{bmatrix}, \quad
\mathbf{w} = 
\begin{bmatrix}
0 \\
0 \\
1
\end{bmatrix}.
$$

These vectors are **linearly independent**, since no one of them can be written as a combination of the others. To see this, consider:
$$
a\mathbf{u} + b\mathbf{v} + c\mathbf{w} =
\begin{bmatrix}
a \\
b \\
c
\end{bmatrix}
= 
\begin{bmatrix}
0 \\
0 \\
0
\end{bmatrix}
\Rightarrow a = b = c = 0.
$$

---

### Algorithmic Check for Linear Independence

Lets assume three vectors 
$$\vec{x} = \begin{bmatrix}x_{1} \\ x_{2} \\ x_{3} \\x_{4}\end{bmatrix}, \space
\vec{y} = \begin{bmatrix}y_{1} \\ y_{2} \\y_{3} \\y_{4}\end{bmatrix}, \space
\vec{z} = \begin{bmatrix}z_{1} \\z_{2} \\z_{3} \\z_{4}\end{bmatrix}$$
Converting to Linear Combinations:
$$c_{1}x+c_{2}y+c_{3}z = 0$$
$$OR$$
$$c_{1}\begin{bmatrix}x_{1} \\ x_{2} \\ x_{3} \\x_{4}\end{bmatrix}+ \space
c_{2}\begin{bmatrix}y_{1} \\ y_{2} \\y_{3} \\y_{4}\end{bmatrix}+ \space
c_{3}\begin{bmatrix}z_{1} \\z_{2} \\z_{3} \\z_{4}\end{bmatrix} = 
\begin{bmatrix}0\\ 0\\0\\0\end{bmatrix}$$
We can rewrite this equation in Augmented Form:-
$$\begin{bmatrix}x_1 & y_1 & z_1 & 0 \\x_2 & y_2 & z_2 & 0 \\x_3 & y_3 & z_3 & 0 \\
x_{4} & y_4 & z_4 & 0 \\\end{bmatrix}$$
Now compute its **reduced row echelon form (RREF)**:-

Case-1:
$$\left[
\begin{array}{ccc|c}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 \\
\end{array}\right]
$$
$$where \space  c_{1}=c_{2}=c_{3}=0$$
It means the vectors are linearly independent.

Case-2: $$\left[
\begin{array}{ccc|c}
1 & k_{1} & k_{2} & 0 \\
0 & 1 & k_{3} & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
\end{array}
\right]$$
Here $k_{n}$ is some constant value.
$$where \space c_{1}+c_{2}k_{2}+c_{3}k_{3}=0,\space c_{2}+c_{3}k_{3}=0$$
Here the vectors are linearly dependent coz $c_{1},c_{2},c_{3}$ are non-zero values.

##### Summary:-

|                    Linearly Independent                     |                                       Linearly Dependent                                       |
| :---------------------------------------------------------: | :--------------------------------------------------------------------------------------------: |
|              All columns are **pivot columns**              |                         At least one column is **not** a pivot column                          |
|                    No **free variables**                    |                             At least one **free variable** exists                              |
| Vectors **cannot** be written as combinations of each other | The column corresponding to the free variable is a **linear combination** of the pivot columns |
|                    $c_{1}=c_{2}=c_{3}=0$                    |                                $c_{1}+c_{2}k_{2}+c_{3}k_{3}=0$                                 |

> [!important] Linear Independence Using Determinants
> If the determinant of a set of vectors is zero then the vectors are Linearly Dependent else Linearly Independent.
