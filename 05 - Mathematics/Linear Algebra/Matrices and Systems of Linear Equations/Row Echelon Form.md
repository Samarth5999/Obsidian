---
prerequisites:
  - "[[Elementary Row Transformations on Matrices]]"
follow-up:
  - "[[Gaussian Elimination]]"
---

A matrix is said to be in <span style="color:rgb(253, 223, 126)">row echelon form</span> when:
1. Any zero rows occur at the bottom of the matrix.
2. Each leading non-zero entry in a row is to the right of the leading non-zero entry in the preceding row i.e. every row starts with more zeros than the row above.
3. All entries **below a pivot** are zeros.
Pivot is the <span style="color:rgb(103, 235, 250)">first non-zero number in a row of a matrix</span>.

---
##### Equivalent Matrices
A matrix A is equivalent to B if $\exists$ invertible matrices P $ Q such that $A = PBQ$

---
##### Row Equivalent Matrices
If $\exists$ a sequence of elementary row transformations that convert A to B.
