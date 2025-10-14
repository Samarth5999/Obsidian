---
prerequisites:
  - "[[Division Algorithm]]"
  - "[[Number Theory]]"
---
Also known as <span style="color:rgb(253, 223, 126)">Repetition of Division Algorithm</span>, it is mainly used to calculate to $\gcd$ of large numbers.
As we know, GCD doesn’t change if we replace the larger number by its remainder when divided by the smaller one i.e. $\gcd(a,b) = \gcd(b,r)$ where r = a mod b

### Steps

1. Given $a\geq b>0$ 
2. Apply the Division Algorithm: $a = bq +r$
3. Check Remainder:-
	1. If r = 0, $\gcd(a,b) = b$ <- Stop
	2. If $r \neq 0$, continue
4. Apply the Division Algorithm again: $a_{1} = b_{1}q_{1} + r_{1}$
	1. Replace $a_{1}\to b$
	2. Replace $b_{1}\to r$
5. Repeat Step-2
6. The **last non-zero remainder** is $gcd⁡(a,b)$

>[!example]  $\gcd(172,20)$
>$172 = 20\times 8 + 12$
>$20 = 12\times 1 + 8$
>$12 = 8\times 1 + 4$ <- GCD
>$8 = 4\times 2 + 0$

