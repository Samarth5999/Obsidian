## 1D Array
Any location in an array can be accessed with the help of base address. The formula used by compiler to convert is $$Address(A[i]) = L_{o} + (i * w)$$
where, $L_o$ is base address
$i$ is Index
$w$ is the size of Data Type

* Base address of any array will be updated when the program starts running and once the memory is allocated. So the address of this is known during run time.
* As the base address is relative the formula for it is also relative formula.

## 2D Array

##### Row Major Mapping 
$$Addr(A[i][j])=L_{o}+(i*n +j)*w$$
##### Column Major Mapping 
$$Addr(A[i][j])=L_{o}+(j*m +i)*w$$

## nD Array

Row major formula for nD array of the type $A[d_{1}][d_{2}]\dots[d_{n}]$:- 
$$Addr(A[i_{1}][i_{2}]\dots[i_{n}])=L_{o}+[\sum^{n}_{p=1} i_{p}*\prod^{n}_{q=p+1}d_{q}]*w$$
