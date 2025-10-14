---
prerequisites:
  - "[[Divisibility]]"
  - "[[GCD]]"
---

If a and b are positive integers, then there exist integers x and y such that $$ax + by = c$$
>[!important] Results
>1. $ax + by = c$ has a solution if and only if $gcd(a,b)|c$


>[!example] 
>1. $4x+6y=10$ => $gcd(4,6) = 2$ which divides 20 <- Solution Exists
>2. $5x+10y=12$ => $gcd(5,10) = 5$ which doesn't divide 12 <- Solution does not Exists

>[!example]
>1. $172x + 20y = 12$
>First have to find $gcd(172,20)$
>$172 = 20\times 8 + 12$ <- eq-1
>$20 = 12\times 1 + 8$
>$12 = 8\times 1 + 4$ <- GCD
>$8 = 4\times 2 + 0$
>$gcd(172,20) = 4$
>Now we can rewrite eq-1 as
>$12 = 172(1) + 20(-8)$
>Hence, $x=1$ and $y=-8$
>---
>2. $35x + 5y = 10$
>$gcd(35,5) = 5$
>We can't write it as $35 = 5 \times 7 + 0$, because we won't get solution
>Instead, $35 = 5 \times 6 + 5$
>Now, $5 = 35(1) + 5(-6)$
>Hence, $x=1$ and $y=-6$



