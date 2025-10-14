> [!important] Definition
> An expression of the form $ax ≡ b \pmod m$ where $a \not\equiv 0 \pmod m$ i.e. m does not divide a, is called a linear congruence modulo m

$$d = gcd(a,m)$$
Solution only exists if and only if $d|b$ i.e. $gcd$ of a and m divides b

The solution of the linear congruence can be obtained by solving the following congruence:
$$\frac{a}{d}x = \frac{b}{d} \pmod{\frac{m}{d}}$$
The given congruence has d solutions which are mutually in congruent modulo m.

>[!important] Note 
>Let $x_{0}$ be the unique smallest positive solution, then
>$$x_0,\ x_0 + \frac{m}{d},\ x_0 + 2\left(\frac{m}{d}\right),\ \ldots,\ x_0 + (d - 1)\left(\frac{m}{d}\right)$$
>will be the d solutions of the given congruence.


> [!example] Find the solution of the congruence: $6x \equiv 3 \pmod{9}$
> 
> $\gcd(6, 9) = 3$ and $3$ divides $3$.  
> Thus, $3$ solutions are possible.
> 
> We reduce the congruence by dividing the equation with $gcd(6,9)$:  
> $2x \equiv 1 \pmod{3}$
> 
> Choosing $x = 0, 1, 2$ and testing the congruence, we get $x_0 = 2$.  
> We have $m = 9$ and $d = 3$.
> 
> Thus, the other two solutions are:  
> $x_1 = x_0 + \frac{m}{d} = 2 + 3 = 5$  
> $x_2 = x_0 + 2\left(\frac{m}{d}\right) = 2 + 6 = 8$
> 
> Hence, $2$, $5$, and $8$ are the solutions.