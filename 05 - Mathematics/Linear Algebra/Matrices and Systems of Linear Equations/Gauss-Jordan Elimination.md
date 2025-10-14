---
prerequisites:
  - "[[System of Linear Equations]]"
follow-up:
  - "[[Reduced Row Echelon Form]]"
---

The extended version of Gaussian elimination that simplifies the augmented matrix to reduced row echelon form (RREF) is called _Gauss-Jordan Elimination_.

**Gauss-Jordan Elimination** goes beyond Gaussian elimination by not only making all elements below the pivot zero, but also making all elements _above_ the pivot zero — ultimately transforming the matrix into the **identity matrix** on the left side.

The process is identical to steps of reducing a matrix to reduced row echelon form.

> [!important] 
> Gauss-Jordan elimination is more computationally expensive than Gaussian elimination and is usually avoided for large systems, unless you explicitly need the inverse of a matrix or the RREF form.  
As with Gaussian elimination, **partial pivoting** (swapping rows to get a non-zero or larger pivot) may be required to ensure numerical stability and to avoid division by zero.
